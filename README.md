# NutrientsDB (nutrientsdb)

<!-- API-EVANGELIST-PROVENANCE:BEGIN -->
> ### About this repository
>
> **This is not our API.** This repository is an independent, third-party profile of a company's
> **publicly available** API surface, maintained by [API Evangelist](https://apievangelist.com).
> API Evangelist does not operate, host, resell, or support this company's APIs, and is not
> affiliated with or endorsed by the company unless stated on the profile.
>
> **Where the information came from.** Everything here is assembled from material a member of the
> public can reach with a browser and no credentials — the company's own website, developer portal
> and documentation, the specifications it publishes for public use (OpenAPI, AsyncAPI, JSON Schema,
> `apis.json`, `llms.txt` and similar), its public repositories, and its public status, pricing and
> changelog pages. **Nothing here is obtained by breaching a system, defeating an access control, or
> using credentials of any kind.**
>
> **The rating is an independent assessment.** The Kin Score and Agent Readiness rating are
> independently calculated scores of a company's *public* API artifacts, produced by API Evangelist
> against a published rubric. They are not certifications, endorsements, security assessments, or
> audits, and they score published artifacts — not the quality, safety, or security of the software.
>
> **Corrections, re-scores, and removal are free.** No partnership, contract, or purchase is
> required, and you do not need to justify the request.
>
> - **Something wrong?** Open an issue on this repository, or email
>   [info@apievangelist.com](mailto:info@apievangelist.com).
> - **Published something new?** Ask for a re-score and we will re-run the rating.
> - **Want the listing taken down?** Say so and we will honor it. The profile is reduced to your
>   company name, a factual description, and a link to your own site, and the company is recorded as
>   **unrated** — never scored zero for having asked.
>
> **Response times.** Acknowledgement within **one business day**; removal or restriction within
> **two business days**; corrections and re-scores within **five business days**.
>
> **Not from the company, and here with a question?** You are welcome here — we would rather be the
> front line and point you the right way than have a good report go nowhere. What this repository
> can answer is narrow, though, so it is worth knowing who you are actually looking for:
>
> - **A question about how the API works, an account, billing, or a bug in the service** — that is
>   the company's own support, not us. We profile this API; we do not operate it and cannot see
>   your account.
> - **A bug in an open-source project we only catalog** — file it on that project's own repository.
>   This has happened with a real and correct bug report that reached us instead of the people who
>   could fix it, which helped nobody.
> - **Anything about this listing itself** — the description, the tags, the rating, a missing or
>   wrong artifact — is ours. Open an issue here.
> - **Not sure, or something general about API Evangelist or APIs.io** — open an issue on the
>   [APIs.io Inbox](https://github.com/api-search/inbox) and we will route it.
>
> **This repository contains no software, and we will never ask you to download anything.** There is
> no build, release, installer, or binary here — only text and machine-readable API descriptions, so
> there is nothing here that can be "corrupt" or need "repairing". Any issue, comment, or email
> claiming otherwise and offering a download link is not from us and is hostile. Do not follow the
> link; it is a lure. Report it to GitHub and, if you like, tell us at
> [info@apievangelist.com](mailto:info@apievangelist.com) so we can take it down.
>
> **On a security or compliance team?** Email
> [info@apievangelist.com](mailto:info@apievangelist.com) with *security* in the subject line and
> you will get a person, not a form. We will tell you exactly which public URLs this profile was
> built from so your team can see the same surface we did, and we will take the listing down on
> request while you work through it.
>
> Full detail: **[Where this data comes from](https://apievangelist.com/about/where-our-data-comes-from)**
<!-- API-EVANGELIST-PROVENANCE:END -->

A curated global food-composition dataset of roughly 2.9 million food entries across 86 normalized nutrient fields, deduplicated across 180+ countries and sold under a one-time license as a downloadable file for local use rather than as a hosted, metered API. Every nutrient value is expressed per 100 g of food, with the unit encoded as a suffix on the field name, and a null value means the source did not report that nutrient rather than that the value is zero. NutrientsDB fronts the licensed dataset with a free, keyless, read-only Sample API that exposes a public 1,000-food slice carrying the identical 86-field schema, so developers, researchers, and AI builders can inspect the shape and density of the data before licensing it. The same sample is mirrored as plain JSON on GitHub and Hugging Face.

**APIs.json:** [https://nutrientsdb.apievangelist.com/apis.yml](https://nutrientsdb.apievangelist.com/apis.yml)

## Tags

- nutrition
- food
- nutrients
- food-composition
- data
- search
- sample-data
- dataset
- ai-builders
- reference-data
- open-data
- keyless-api

## Timestamps

- **Created:** 2026-08-02
- **Modified:** 2026-08-09

## APIs

### NutrientsDB Foods API

The Foods API from NutrientsDB — 1 operation(s) for foods.

- **Human URL:** [https://www.nutrientsdb.com/api/docs](https://www.nutrientsdb.com/api/docs)
- **Base URL:** `https://www.nutrientsdb.com/api`

#### Tags

- Foods

#### Properties

- [OpenAPI](openapi/nutrientsdb-foods-api-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/nutrientsdb-foods-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/nutrientsdb-foods-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)
- [Postman Collection](https://documenter.getpostman.com/view/57076285/2sBY4TqJ5d) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Documentation](https://www.nutrientsdb.com/api/docs)
- [Examples](examples/_index.yml)
- [Error Catalog](errors/nutrientsdb-problem-types.yml)
- [Data Model](data-model/nutrientsdb-data-model.yml)
- [JSON Schema](json-schema/nutrientsdb-food.json) — [JSON Schema](https://json-schema.org/specification)
- [Arazzo](arazzo/nutrientsdb-search-then-lookup.yml) — [Arazzo Specification](https://spec.openapis.org/arazzo/latest.html)

## Common Properties

- [M C P Server](mcp/nutrientsdb-mcp.yml)
- [Overlay](overlays/nutrientsdb-sample-api-overlay.yaml)
- [Agentic Access](agentic-access/nutrientsdb-agentic-access.yml)
- [Domain Security](security/nutrientsdb-domain-security.yml)
- [Authentication](authentication/nutrientsdb-authentication.yml)
- [Conventions](conventions/nutrientsdb-conventions.yml)
- [Lifecycle](lifecycle/nutrientsdb-lifecycle.yml)
- [Conformance](conformance/nutrientsdb-conformance.yml)
- [Vocabulary](vocabulary/nutrientsdb-nutrient-schema.yml)
- [L L Ms Txt](llms/nutrientsdb-llms.txt)
- [Agent Skill](skills/_index.yml)
- [Documentation](https://www.nutrientsdb.com/docs)
- [API Reference](https://www.nutrientsdb.com/api/docs)
- [Postman](https://documenter.getpostman.com/view/57076285/2sBY4TqJ5d) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [GitHub Organization](https://github.com/colinearstudio)
- [Blog](https://www.nutrientsdb.com/blog)
- [Support](https://www.nutrientsdb.com/contact)
- [Pricing](https://www.nutrientsdb.com/pricing)
- [Terms of Service](https://www.nutrientsdb.com/terms)
- [Privacy Policy](https://www.nutrientsdb.com/privacy)

## Maintainers

**FN:** Colinear Studio
**URL:** https://github.com/colinearstudio
