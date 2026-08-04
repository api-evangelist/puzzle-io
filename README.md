# Puzzle (puzzle-io)

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
> **On a security or compliance team?** Email
> [info@apievangelist.com](mailto:info@apievangelist.com) with *security* in the subject line and
> you will get a person, not a form. We will tell you exactly which public URLs this profile was
> built from so your team can see the same surface we did, and we will take the listing down on
> request while you work through it.
>
> Full detail: **[Where this data comes from](https://apievangelist.com/about/where-our-data-comes-from)**
<!-- API-EVANGELIST-PROVENANCE:END -->

Puzzle is real-time, AI-native accounting software for startups and accounting firms. It builds a continuously reconciled general ledger on top of a company's connected Stripe, bank, card, and payroll data and surfaces financial statements plus startup metrics like burn, runway, and margin. The Puzzle API exposes that same real-time financial data hub and general ledger over a RESTful, OAuth 2.0-secured JSON interface.

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/puzzle-io/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/puzzle-io/refs/heads/main/apis.yml)

## API Availability

Puzzle has a **real, documented, first-party REST API** — but it is **partner-gated and not generally available**. Puzzle describes the API as in an "active development phase," granted case-by-case to:

- **Platform partners** building embedded / core accounting integrations
- **Large-scale accounting and advisory firms** managing high-volume portfolios

Individual companies are on a **waitlist**. Access requires joining the [Partner Program](https://puzzle.io/partners), submitting a use case, and passing a technical review.

- **Docs:** [https://puzzle-api.readme.io/docs/welcome](https://puzzle-api.readme.io/docs/welcome)
- **Reference:** [https://puzzle-api.readme.io/reference](https://puzzle-api.readme.io/reference)
- **Confirmed server:** `https://staging.southparkdata.com` (Puzzle's underlying platform is named "South Park Data")
- **Confirmed endpoint:** `GET /rest/v0/company/{id}/transactions`
- **Auth:** OAuth 2.0 (scoped) and/or API key (Authorization header)
- **Format:** RESTful JSON

Every resource is nested under `/rest/v0/company/{id}`. Only the transactions endpoint path was verified against the (gated) public reference; other endpoint paths in [openapi/puzzle-io-openapi.yml](openapi/puzzle-io-openapi.yml) follow the documented resource sections and the confirmed pattern and are flagged `x-puzzle-unverified: true`. See [review.yml](review.yml) for the full honesty assessment.

No public first-party Puzzle GitHub organization was found, so `GitHubOrganization` is intentionally omitted from `apis.yml`.

## Tags

- Accounting
- Fintech
- General Ledger
- Financial Reporting
- Bookkeeping
- Startups
- Embedded Accounting
- Metrics

## Timestamps

- **Created:** 2026-07-01
- **Modified:** 2026-07-01

## APIs

### Puzzle Companies API

Read a partner's connected companies and their accounting configuration. Company IDs returned here scope every other Puzzle API call, which is nested under `/rest/v0/company/{id}`.

- **Human URL:** [https://puzzle-api.readme.io/reference](https://puzzle-api.readme.io/reference)
- **Base URL:** `https://staging.southparkdata.com`

#### Tags

- Companies
- Accounts
- Multi-Entity

#### Properties

- [Documentation](https://puzzle-api.readme.io/docs/welcome)
- [API Reference](https://puzzle-api.readme.io/reference)
- [OpenAPI](openapi/puzzle-io-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)

### Puzzle Transactions API

Retrieve the normalized, categorized transaction feed Puzzle ingests from connected bank, card, Stripe, and payroll sources for a company, via `GET /rest/v0/company/{id}/transactions`.

- **Human URL:** [https://puzzle-api.readme.io/reference](https://puzzle-api.readme.io/reference)
- **Base URL:** `https://staging.southparkdata.com`

#### Tags

- Transactions
- Bank
- Cards

#### Properties

- [Documentation](https://puzzle-api.readme.io/docs/welcome)
- [API Reference](https://puzzle-api.readme.io/reference)
- [OpenAPI](openapi/puzzle-io-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)

### Puzzle Ledger Accounts API

Access the chart of accounts and ledger account balances that make up a company's real-time general ledger, supporting both cash and accrual bases.

- **Human URL:** [https://puzzle-api.readme.io/reference](https://puzzle-api.readme.io/reference)
- **Base URL:** `https://staging.southparkdata.com`

#### Tags

- General Ledger
- Chart of Accounts
- Accounting

#### Properties

- [Documentation](https://puzzle-api.readme.io/docs/welcome)
- [API Reference](https://puzzle-api.readme.io/reference)
- [OpenAPI](openapi/puzzle-io-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)

### Puzzle Journal Entries API

Read and sync double-entry journal entries against a company's general ledger, enabling programmatic close and reconciliation workflows.

- **Human URL:** [https://puzzle-api.readme.io/reference](https://puzzle-api.readme.io/reference)
- **Base URL:** `https://staging.southparkdata.com`

#### Tags

- Journal Entries
- General Ledger
- Sync

#### Properties

- [Documentation](https://puzzle-api.readme.io/docs/welcome)
- [API Reference](https://puzzle-api.readme.io/reference)
- [OpenAPI](openapi/puzzle-io-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)

### Puzzle Financial Reports API

Generate real-time financial statements — income statement (P&L), balance sheet, and cash activity — for a company over a requested reporting period.

- **Human URL:** [https://puzzle-api.readme.io/reference](https://puzzle-api.readme.io/reference)
- **Base URL:** `https://staging.southparkdata.com`

#### Tags

- Reports
- Financial Statements
- Income Statement
- Balance Sheet

#### Properties

- [Documentation](https://puzzle-api.readme.io/docs/welcome)
- [API Reference](https://puzzle-api.readme.io/reference)
- [OpenAPI](openapi/puzzle-io-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)

### Puzzle Metrics API

Pull the startup finance metrics Puzzle derives from the ledger — cash balance, monthly burn, runway, gross margin, and revenue — for dashboards and financial planning tools.

- **Human URL:** [https://puzzle-api.readme.io/reference](https://puzzle-api.readme.io/reference)
- **Base URL:** `https://staging.southparkdata.com`

#### Tags

- Metrics
- Burn
- Runway
- Margin

#### Properties

- [Documentation](https://puzzle-api.readme.io/docs/welcome)
- [API Reference](https://puzzle-api.readme.io/reference)
- [OpenAPI](openapi/puzzle-io-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)

### Puzzle Categories API

Read the categories, classes, departments, and projects Puzzle's AI categorization uses to code transactions, so partners can mirror and reconcile classification.

- **Human URL:** [https://puzzle-api.readme.io/reference](https://puzzle-api.readme.io/reference)
- **Base URL:** `https://staging.southparkdata.com`

#### Tags

- Categories
- Classifications
- Bookkeeping

#### Properties

- [Documentation](https://puzzle-api.readme.io/docs/welcome)
- [API Reference](https://puzzle-api.readme.io/reference)
- [OpenAPI](openapi/puzzle-io-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)

### Puzzle Integrations API

Inspect the upstream data connections (Stripe, banks, cards, Mercury, Ramp, Brex, Gusto and other payroll) that feed a company's Puzzle ledger, and their sync status.

- **Human URL:** [https://puzzle-api.readme.io/reference](https://puzzle-api.readme.io/reference)
- **Base URL:** `https://staging.southparkdata.com`

#### Tags

- Integrations
- Connections
- Stripe
- Payroll

#### Properties

- [Documentation](https://puzzle-api.readme.io/docs/welcome)
- [API Reference](https://puzzle-api.readme.io/reference)
- [OpenAPI](openapi/puzzle-io-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)

## Common Properties

- [LinkedIn](https://www.linkedin.com/company/puzzlefin)
- [Website](https://puzzle.io)
- [Documentation](https://puzzle-api.readme.io/docs/welcome)
- [Sign Up](https://puzzle.io/partners)
- [Pricing](https://puzzle.io/pricing)
- [Plans](plans/puzzle-io-plans-pricing.yml)
- [Rate Limits](rate-limits/puzzle-io-rate-limits.yml)
- [Fin Ops](finops/puzzle-io-finops.yml)

## Maintainers

**FN:** Kin Lane
**Email:** kin@apievangelist.com
