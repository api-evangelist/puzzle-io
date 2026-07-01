# Puzzle (puzzle-io)

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
