---
name: Browse NAB banking products
description: Retrieve and filter NAB's openly published banking product catalogue (home loans, deposits, credit cards, business products) and drill into a single product's fees, rates, eligibility and terms via the public CDR Product Reference Data API. No authentication required.
api: openapi/national-australia-bank-cds-banking-products-openapi.yml
operations: [listBankingProducts, getBankingProductDetail]
---

# Browse NAB banking products

NAB's Product Reference Data (PRD) API is public and unauthenticated. It conforms to
the DSB Consumer Data Standards (CDS) Banking API and is served at
`https://openbank.api.nab.com.au/cds-au/v1`.

## Rules

- **No credentials.** Do not send Authorization headers to the PRD endpoints.
- **Version header is mandatory.** Every request MUST send `x-v` as a positive
  integer. Use `x-v: 5` for `listBankingProducts` and `x-v: 7` for
  `getBankingProductDetail` (the current operation versions). Optionally send
  `x-min-v` to accept a lower bound. An unsupported version range returns `406`.
- **Tracing.** You may send `x-fapi-interaction-id` as an RFC 4122 UUID; it is
  echoed back on the response (a new one is generated if you omit it).
- **Errors** come back in the CDS envelope `{ "errors": [ { "code", "title",
  "detail", "meta" } ] }` — not RFC 9457 problem+json. See
  `errors/national-australia-bank-error-codes.yml`.

## Steps

1. **List products** — call `listBankingProducts` (`GET /banking/products`).
   Filter with the query params: `effective` (`CURRENT` | `FUTURE` | `ALL`,
   default `CURRENT`), `updated-since` (DateTimeString), `brand`, and
   `product-category`. Page with `page` (default 1) and `page-size` (default 25);
   read `meta.totalRecords` / `meta.totalPages` and follow `links.next` to walk
   the full catalogue.
2. **Pick a product** — take a `productId` from the `data.products[]` array.
3. **Get detail** — call `getBankingProductDetail`
   (`GET /banking/products/{productId}`) with that id and `x-v: 7` to retrieve the
   full fees, rates, eligibility, constraints, features and bundle information.
4. **Handle a missing product** — a `404` (`Invalid Resource` /
   `Unavailable Resource`) means the `productId` is not valid or currently
   unavailable; re-list to obtain a fresh id.
