# Wave Financial

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

Free accounting software for small businesses with a GraphQL API for managing invoices, estimates, customers, products, accounts, and financial reporting.

## Overview

Wave Financial provides a GraphQL API that gives developers programmatic access to core accounting functions. The API uses a single endpoint and supports OAuth 2.0 for authentication, enabling integrations for invoicing, expense tracking, and financial reporting.

**API Endpoint:** `https://gql.waveapps.com/graphql/public`

**Developer Portal:** https://developer.waveapps.com/hc/en-us

## Authentication

Wave uses OAuth 2.0 Authorization Code Flow:

- Register an application at the Wave Developer Portal to obtain Client ID and Client Secret
- Authorization endpoint: `https://api.waveapps.com/oauth2/authorize/`
- Token endpoint: `https://api.waveapps.com/oauth2/token/`
- Access tokens expire after approximately 2 hours; refresh tokens enable long-term access
- Scopes: `accounting:read`, `accounting:write`, `transactions:write`, `offline_access`

**Note:** As of May 26, 2025, third-party applications require connected businesses to have an active Wave Pro subscription.

## API Capabilities

- **Businesses** - Retrieve settings and business details
- **Customers** - Full CRUD operations
- **Invoices** - Create, read, and update invoice management
- **Products/Services** - Product catalog management
- **Accounts** - Chart of accounts access
- **Transactions** - Accounting transaction data
- **Vendors** - Supplier management
- **Taxes** - Tax rates and configurations

## Webhooks

Supported events: `invoice.created`, `invoice.updated`, `invoice.paid`, `customer.created`, `customer.updated`, `transaction.created`, `product.created`, `product.updated`

## Rate Limits

- 60 requests per minute per access token
- 5,000 requests per day per application
- HTTP 429 returned when limits exceeded

## Pricing

Wave Financial API access is free with no per-call fees. Core accounting features are free; paid options for payments, payroll, and advisory services are available.

| Plan | Price | Notes |
|------|-------|-------|
| Starter | Free | Core accounting; payment processing 2.9% + $0.60/txn |
| Pro | $19/month | Required for third-party OAuth integrations; bank import; multi-user |
| Wave Advisors | $199+/month | Dedicated bookkeeper; monthly statements |

## Resources

- [Developer Portal](https://developer.waveapps.com/hc/en-us)
- [API Reference](https://developer.waveapps.com/hc/en-us/articles/360019968212-API-Reference)
- [OAuth Guide](https://developer.waveapps.com/hc/en-us/articles/360019493652-OAuth-Guide)
- [GraphQL Guide](https://developer.waveapps.com/hc/en-us/articles/360018570992-Building-on-GraphQL)
- [API Playground](https://developer.waveapps.com/hc/en-us/articles/360018937431-API-Playground)
- [Pricing](https://www.waveapps.com/pricing)
- [Status Page](https://status.waveapps.com/)
- [Blog](https://www.waveapps.com/blog)

## APIs.json

This repository contains an [APIs.json](apis.yml) profile (specification version 0.19) cataloging the Wave Financial API for the API Evangelist network.

**Maintainer:** Kin Lane (kin@apievangelist.com)
