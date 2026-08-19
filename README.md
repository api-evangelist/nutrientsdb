# NutrientsDB (nutrientsdb)

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
