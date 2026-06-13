# Wave Financial

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
