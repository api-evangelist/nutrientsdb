---
name: Evaluate whether the NutrientsDB dataset fits a project
description: >-
  Use the free 1,000-food Sample API and the published mirrors to test NutrientsDB's schema, unit
  normalization, and coverage-density against a real requirement before recommending the licensed
  full dataset — the evaluation path the provider actually designed the sample for.
api: openapi/nutrientsdb-sample-api-openapi.yml
operations:
  - findFoods
generated: '2026-08-09'
method: generated
---

# Evaluate whether the NutrientsDB dataset fits a project

Use this when someone is deciding whether to license NutrientsDB — for a nutrition app, a research
pipeline, or as grounding data for a model. The sample exists precisely so this evaluation can
happen before money changes hands. Do the evaluation; do not answer from the marketing copy.

## What is actually being evaluated

The product is a **downloadable dataset under a one-time license** (~2.9M foods, 86 nutrient fields,
180+ countries, no subscription, no per-call fees). The Sample API is **not** the product — it is a
1,000-food window onto the identical schema. So the questions worth testing are about *shape and
quality*, not about API throughput.

## Step 1 — confirm the schema carries the fields the project needs

Pull any record and inspect the `nutrients` object:

    GET https://www.nutrientsdb.com/api/foods?id=2923506

All 86 keys are present on **every** record. Check the project's required nutrients against
`vocabulary/nutrientsdb-nutrient-schema.yml`, which groups them: energy and macronutrients,
carbohydrates and sugars, fats and fatty acids (including individual fatty acids such as EPA and
DHA), minerals, vitamins, carotenoids, all 20 amino acids, plus caffeine and theobromine.

If a required nutrient is not in that list, it is not in the dataset. Stop there.

## Step 2 — measure null density, not just field presence

This is the step people skip, and it decides the answer. A field being *present* is not the same as
being *populated*: `null` means the source did not report that nutrient for that food.

Search a spread of foods representative of the project's domain and count, per required field, how
many records actually carry a number:

    GET https://www.nutrientsdb.com/api/foods?q=chicken&limit=20
    GET https://www.nutrientsdb.com/api/foods?q=bread&limit=20

Macronutrients and common minerals are densely populated. Trace elements and specialty compounds
(iodine, chromium, molybdenum, phytate, biotin, hydroxyproline) are frequently `null` in the sample.
Report the observed density honestly — it is the single most useful number in this evaluation.

Caveat the sample size out loud: 1,000 of ~2.9M records is 0.03%, so density in the sample is
indicative, not a guarantee for the full set.

## Step 3 — check name resolution against the project's inputs

Matching is a **case-insensitive substring on the food name** and food-composition naming is verbose
("Turkey, drumstick, from whole bird, meat only, raw"). Take a handful of real user-facing strings
the project would need to resolve and search them:

    GET https://www.nutrientsdb.com/api/foods?q=greek%20yogurt&limit=20

If the project needs to map free-text or barcode input to records, note that the dataset ships no
category, brand, or barcode field on the sample record — that mapping layer is the integrator's to
build. Say so in the recommendation.

## Step 4 — verify the units and basis assumption

Every value is **per 100 g**, and the unit is encoded as a field-name suffix (`_g`, `_mg`, `_ug`,
`_kcal`). If the project needs per-serving or per-volume values, a conversion layer plus portion
data is required and is not supplied here.

## Step 5 — inspect the bulk shape offline

Rather than paging the API (there is no cursor — `limit` caps at 20 and there is no way past it),
pull the whole sample from a mirror and analyze it locally:

- <https://github.com/colinearstudio/nutrientsdb-sample> — `sample.json`, 1,000 records
- <https://huggingface.co/datasets/colinearstudio/nutrientsdb> — same sample, loadable with
  `datasets`, `pandas`, or `polars`

Plain JSON, no database server needed. This is the right surface for null-density counting at scale.

## Step 6 — write the recommendation

Cover, explicitly:

- Which required nutrients exist, and their observed null density in the sample.
- Whether name resolution is workable for the project's inputs, and what mapping work remains.
- The unit/basis conversion work implied.
- The delivery model: a one-time-license file for **local** querying. There is no hosted API for the
  full data, so the project owns hosting, indexing, and refresh. Refresh cadence for the licensed
  dataset is not published — if update frequency matters, that is a question for
  <https://www.nutrientsdb.com/contact> before licensing.

Pricing and license terms: <https://www.nutrientsdb.com/pricing> and
<https://www.nutrientsdb.com/terms>.

## Reference

- Sample API docs: <https://www.nutrientsdb.com/api/docs>
- Conventions: `conventions/nutrientsdb-conventions.yml`
- Data model: `data-model/nutrientsdb-data-model.yml`
- Nutrient vocabulary: `vocabulary/nutrientsdb-nutrient-schema.yml`
