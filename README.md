# National Australia Bank (national-australia-bank)

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
