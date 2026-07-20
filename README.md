# National Australia Bank (national-australia-bank)

National Australia Bank (NAB) is one of Australia's "Big Four" banks and a major Authorised Deposit-taking Institution (ADI), headquartered in Melbourne and publicly listed on the Australian Securities Exchange (ASX:NAB) - a shareholder-owned institution rather than a customer-owned mutual. As a regulated ADI, NAB is a mandated data holder under Australia's Consumer Data Right (CDR / Open Banking) and exposes a public, unauthenticated Product Reference Data (PRD) API conforming to the DSB Consumer Data Standards (CDS).

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/national-australia-bank/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/national-australia-bank/refs/heads/main/apis.yml)

## Tags

- Financial
- Banks
- Open Banking
- CDR
- Consumer Banking
- Australia
- Product Reference Data
- ADI

## Timestamps

- **Created:** 2026-07-20
- **Modified:** 2026-07-20

## APIs

### National Australia Bank (NAB) CDR Product Reference Data API

NAB's public, unauthenticated Consumer Data Right (CDR) Product Reference Data API. `GET /banking/products` (and `/banking/products/{productId}`) returns NAB's openly published banking product catalogue - home loans, deposits, credit cards, business products and more - with fees, rates, eligibility and terms. Conforms to the DSB Consumer Data Standards (CDS) Banking API. Confirmed live returning HTTP 200 with an `x-v` response header and a `data.products` array (46 products, 10 pages).

- **Human URL:** [https://developer.nab.com.au/docs/open-banking](https://developer.nab.com.au/docs/open-banking)
- **Base URL:** `https://openbank.api.nab.com.au/cds-au/v1`

#### Tags

- CDR
- Open Banking
- Product Reference Data
- Banking
- Consumer Data Right

#### Properties

- [Documentation](https://developer.nab.com.au/docs/open-banking)
- [API Reference](https://consumerdatastandardsaustralia.github.io/standards/#get-products)
- [OpenAPI](openapi/national-australia-bank-cds-banking-products-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)

## Common Properties

- [Website](https://www.nab.com.au/)
- [Developer Portal](https://developer.nab.com.au/)
- [Documentation](https://developer.nab.com.au/docs/open-banking)
- [LinkedIn](https://www.linkedin.com/company/national-australia-bank)
- [Blog](https://news.nab.com.au/)
- [Privacy Policy](https://www.nab.com.au/common/privacy-policy)

## Maintainers

**FN:** Kin Lane
**Email:** kin@apievangelist.com
