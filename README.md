# NutrientsDB

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

**Areas:** Nutrition · Food · Nutrients · food-composition · Data · Search · Sample Data · Datasets · ai-builders · Reference Data · Open Data · keyless-api

## NutrientsDB on APIs.io

Everything profiled for NutrientsDB is published on APIs.io rather than in this repository. Start at the provider page — **[apis.io/providers/nutrientsdb/](https://apis.io/providers/nutrientsdb/)** — or go straight to one of the APIs or properties below.

### APIs (1)

- [NutrientsDB Foods API](https://apis.io/apis/nutrientsdb/nutrientsdb-foods-api/) — The Foods API from NutrientsDB — 1 operation(s) for foods.

### Published properties

Each property below is a page on APIs.io carrying the machine-readable artifact and what it says.

#### Arazzo workflows (1)

Multi-step workflows that chain operations into a business task.

- [Resolve a food name to a NutrientsDB record and read its nutrient profile](https://apis.io/arazzos/nutrientsdb/nutrientsdb-search-then-lookup/)

#### MCP servers (1)

Model Context Protocol servers that expose the API to agents.

- [nutrientsdb](https://apis.io/servers/nutrientsdb/nutrientsdb/)

#### Agentic access (1)

Which operations an agent can call, which act, and which need a human in the loop.

- [Nutrientsdb Agentic Access](https://apis.io/agentic-access/nutrientsdb/nutrientsdb-agentic-access/)

#### JSON Schema (1)

The data models the API reads and writes.

- [NutrientsDB Food](https://apis.io/schemas/nutrientsdb/nutrientsdb-food/)

#### Examples (5)

Example requests and responses.

- [Nutrientsdb Error Missing Params](https://apis.io/examples/nutrientsdb/nutrientsdb-error-missing-params/)
- [Nutrientsdb Error Not Found](https://apis.io/examples/nutrientsdb/nutrientsdb-error-not-found/)
- [Nutrientsdb Error Short Q](https://apis.io/examples/nutrientsdb/nutrientsdb-error-short-q/)
- [Nutrientsdb Lookup](https://apis.io/examples/nutrientsdb/nutrientsdb-lookup/)
- [Nutrientsdb Search](https://apis.io/examples/nutrientsdb/nutrientsdb-search/)

#### Collections (1)

Postman and Open Collection request collections.

- [NutrientsDB Sample Foods API](https://apis.io/collections/nutrientsdb/open-nutrientsdb-foods-api/)

#### Overlays (1)

OpenAPI overlays, including conversational phrasing for each operation.

- [Nutrientsdb Sample Api Overlay](https://apis.io/overlays/nutrientsdb/nutrientsdb-sample-api-overlay/)

#### Security (2)

Authentication, trust centre, and vulnerability disclosure.

- [Nutrientsdb Authentication](https://apis.io/security/nutrientsdb/nutrientsdb-authentication/)
- [Nutrientsdb Domain Security](https://apis.io/security/nutrientsdb/nutrientsdb-domain-security/)

## Where to find this API

Links to the company's own pages. This repository publishes no copy of their specifications — the canonical document is theirs and lives at the URLs below.

- [Website](https://www.nutrientsdb.com/)
- [Documentation](https://www.nutrientsdb.com/docs)
- [API reference](https://www.nutrientsdb.com/api/docs)
- [Pricing](https://www.nutrientsdb.com/pricing)
- [Support](https://www.nutrientsdb.com/contact)
- [Blog](https://www.nutrientsdb.com/blog)
- [Terms of service](https://www.nutrientsdb.com/terms)
- [Privacy policy](https://www.nutrientsdb.com/privacy)
- [GitHub](https://github.com/colinearstudio)

## API Evangelist rating

**Kin Score 30.8** — thin · rubric 0.24.0 · scored 2026-10-17

| Facet | Score |
|---|---|
| Discoverability | 66.1 |
| Contract quality | 56.0 |
| Contract governance | 19.7 |
| Operational transparency | 2.6 |
| Developer ergonomics | 35.1 |
| Access clarity | 0.0 |

**Agent readiness 29.2** — agent-ready

| Agent-readiness dimension | Result |
|---|---|
| Spec Presence | yes |
| Agentic Access | derived (partial credit) |
| Reversibility Documented | na |
| MCP Server | — |
| Auth Clarity | bearer (partial credit) |
| Idempotency | na |
| Error Semantics | verified |
| OpenAPI Examples | documented (partial credit) |
| Rate Limit Signal | — |
| Event Surface Described | — |
| Agent Skills | derived (partial credit) |
| Well Known Catalog | — |
| Consent Identity | — |
| Agent Card | — |
| Dry Run Mode | na |
| Delegated Identity | — |
| Protected Resource Metadata | — |
| Dynamic Client Registration | — |
| Agentic Commerce | — |

**Regulatory alignment 16.7** — Government & Public Sector

The rubric is published at [github.com/api-evangelist/kin-score](https://github.com/api-evangelist/kin-score). The per-check breakdown behind these numbers — which checks were earned, partial or missed — along with score history and how this provider compares to its peers, is available at [apis.io/providers/nutrientsdb/](https://apis.io/providers/nutrientsdb/).

## How this profile is made

API Evangelist profiles a company's public API surface the way a developer would find it: the website, developer portal and documentation, the specifications it publishes, its public repositories, and its pricing, status and changelog pages. From that it derives the properties above — contracts split per API, workflows, schemas, collections, governance rules, plans and rate limits — and scores them against the published [Kin Score rubric](https://github.com/api-evangelist/kin-score).

The artifacts are published on [APIs.io](https://apis.io), not in this repository. This repository is the public record for NutrientsDB: the place to say something is wrong, missing or out of date, and to ask for a re-score or a removal.

## Open an issue

- **Something about this listing** — a wrong description, a missing API, a stale artifact or a question about the rating: [open an issue on this repository](https://github.com/api-evangelist/nutrientsdb/issues/new).
- **A new API, or one that is not in the catalog yet** — [submit it on APIs.io](https://apis.io/add/).
- **Anything else** — [the APIs.io inbox](https://github.com/api-search/inbox/issues/new) or [info@apievangelist.com](mailto:info@apievangelist.com).
