---
name: Look up a food's nutrition facts in NutrientsDB
description: >-
  Resolve a plain-language food name to a NutrientsDB record and read its 86-field nutrient profile
  from the free, keyless Sample API — including how to disambiguate multiple matches, how to read
  nulls correctly, and when a miss means "not in the free sample" rather than "no such food".
api: openapi/nutrientsdb-sample-api-openapi.yml
operations:
  - findFoods
generated: '2026-08-09'
method: generated
---

# Look up a food's nutrition facts in NutrientsDB

Use this when a user asks what is in a food — calories, protein, a specific vitamin or mineral.

## Before you start

- **No authentication.** Do not ask the user for an API key; there isn't one. Call it directly.
- **Base URL:** `https://www.nutrientsdb.com/api`
- **One operation:** `findFoods` — `GET /api/foods`
- **Scope limit that matters:** this endpoint serves only a **1,000-food public sample**. The full
  ~2.9M-food NutrientsDB is a licensed download, not an API. Plenty of real foods are simply not
  here. Never tell a user a food "doesn't exist" — say it is not in the free sample.

## Step 1 — search by name

Call `findFoods` with `q` set to a short, distinctive fragment of the food name.

    GET https://www.nutrientsdb.com/api/foods?q=banana&limit=10

Rules the API enforces:

- `q` must be **2 to 100 characters**. Shorter returns `400` with `q must contain at least 2 characters`.
- `limit` defaults to `10` and is **capped at 20** — values above 20 are silently reduced, not rejected.
- Matching is **case-insensitive substring on the food name**, so `q=banana` also matches
  "Babyfood, cereal, rice, with bananas". Search broad, then filter yourself.

Read `total_matches` against `count`. If `total_matches` exceeds `count`, there are more matches you
did not receive — and there is **no cursor, offset, or page parameter**, so you cannot fetch them.
Narrow `q` instead.

## Step 2 — pick the right record, and say which one you picked

Food-composition names are precise and the differences are nutritionally large: "raw" vs "cooked",
"meat only" vs "with skin", "prepared with whole milk". Choose the record whose name best matches
what the user actually described, and **state the full record name in your answer**. If two records
are plausibly what they meant and differ materially, ask rather than guess.

Keep the record's `public_id` — it is stable.

## Step 3 — read the nutrients correctly

Each food carries a `nutrients` object with **all 86 keys present on every record**. Two rules you
must not get wrong:

- **Every value is per 100 g of the food.** If the user asked about a portion, convert explicitly
  and show your arithmetic basis ("per 100 g" → their serving).
- **`null` means the source did not report that nutrient. It does NOT mean zero.** If the field the
  user asked for is `null`, say it is unreported for that record. Reporting `null` as `0 mg` is the
  single worst failure mode in this API, and it is easy to make.

The unit is encoded as a suffix on the field name: `_g` grams, `_mg` milligrams, `_ug` micrograms,
`_kcal` kilocalories. So `energy_kcal`, `protein_g`, `vitamin_c_mg`, `folate_ug`. The full field
reference with groupings is in `vocabulary/nutrientsdb-nutrient-schema.yml`.

## Step 4 — re-fetch by ID when you need it again

Once you have a `public_id`, fetch that exact record without re-searching:

    GET https://www.nutrientsdb.com/api/foods?id=2923506

`q` and `id` are **mutually exclusive** — send one, never both, never neither.

## Error handling

Errors are plain `application/json` (not RFC 9457 problem+json), shaped
`{"sample": {...}, "error": "<message>"}`. Note that the `sample` block is present on **successes
and errors alike**, so its presence proves nothing — branch on the HTTP status:

| Status | Meaning | What to do |
|---|---|---|
| `400` | Neither `q` nor `id` sent, or `q` under 2 characters | Fix the request; do not retry unchanged |
| `404` | `public_id` not in the 1,000-food sample | Tell the user it is outside the free sample; do not retry |

The operation is a safe `GET`, so retrying on a network or 5xx failure is safe by HTTP semantics.
There is no `Idempotency-Key` header and none is needed. No rate limit is published; do not poll in
a loop.

## What to tell the user when the sample comes up empty

Say plainly: the free sample covers 1,000 foods and this one is not among them. If they need full
coverage, the complete ~2.9M-food dataset (86 nutrient fields, 180+ countries) is a one-time-license
download from <https://www.nutrientsdb.com/pricing> intended for local querying — there is no paid
tier of this API to upgrade to.

## Reference

- Docs: <https://www.nutrientsdb.com/api/docs>
- OpenAPI: <https://www.nutrientsdb.com/api/openapi>
- Conventions: `conventions/nutrientsdb-conventions.yml`
- Errors: `errors/nutrientsdb-problem-types.yml`
- Nutrient vocabulary: `vocabulary/nutrientsdb-nutrient-schema.yml`
