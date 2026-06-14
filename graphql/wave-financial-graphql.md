# Wave Financial GraphQL API

## Description

Wave Financial provides a public GraphQL API for programmatic access to its small-business accounting and invoicing platform. The API covers core business data including businesses, customers, invoices, estimates, products, accounts, transactions, vendors, sales taxes, and payments. Authentication uses OAuth 2.0.

## Endpoint

```
https://gql.waveapps.com/graphql/public
```

## Documentation

- API Reference: https://developer.waveapps.com/hc/en-us/articles/360019968212-API-Reference
- Building on GraphQL: https://developer.waveapps.com/hc/en-us/articles/360018570992-Building-on-GraphQL
- API Playground: https://developer.waveapps.com/hc/en-us/articles/360018937431-API-Playground
- OAuth Guide: https://developer.waveapps.com/hc/en-us/articles/360019493652-OAuth-Guide

## Schema Notes

The schema was obtained via live introspection of the public endpoint on 2026-06-14. Wave's GraphQL API is publicly documented and supports introspection. The schema includes 216 user-defined types across objects, enums, input types, interfaces, and scalars.

Key object types:
- **Business** — the top-level entity; all data is scoped to a business
- **User** — authenticated Wave user linked to one or more businesses
- **Customer** — customer records with shipping details and contact info
- **Vendor** — vendor records for expenses
- **Invoice** — invoices with line items, discounts, taxes, and payments
- **InvoiceItem** — individual line items on invoices
- **InvoicePayment** — payment records against invoices
- **Estimate** — estimates/quotes that can be converted to invoices
- **Product** — products and services used as invoice/estimate line items
- **Account** — chart of accounts entries (assets, liabilities, income, expenses)
- **Transaction** — financial transactions with line items
- **SalesTax** — tax rates applied to invoice and estimate items
- **Currency** / **Money** — monetary amounts with currency support
- **Address** / **Country** / **Province** — geographic data

Key enum types:
- **InvoiceStatus** — DRAFT, SAVED, OVERDUE, PAID, PARTIAL, SENT, VIEWED, UNPAID
- **EstimateStatus** — DRAFT, SAVED, SENT, VIEWED, ACCEPTED, EXPIRED
- **CurrencyCode** — ISO 4217 currency codes
- **CountryCode** — ISO country codes
- **AccountTypeValue** / **AccountSubtypeValue** — chart of accounts classification
- **TransactionDirection** — DEPOSIT / WITHDRAWAL

## GraphQL Support

Wave's API is GraphQL-native. There is no REST equivalent. All queries and mutations go through a single endpoint using HTTP POST with a JSON body containing `query` and optional `variables` fields.
