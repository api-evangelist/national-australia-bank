---
name: national-australia-bank-read-consented-account-data
description: As a CDR-accredited data recipient holding a valid consumer consent, read a NAB customer's accounts, balances and transactions through the DSB Consumer Data Standards Banking APIs NAB implements as a mandated data holder.
api: openapi/national-australia-bank-banking-accounts-api-openapi.yml
operations: [listBankingAccounts, getBankingAccountDetail, listBankingBalancesBulk, getBankingBalance, listBankingTransactions, getBankingTransactionDetail]
specs:
  - openapi/national-australia-bank-banking-accounts-api-openapi.yml
  - openapi/national-australia-bank-banking-account-balances-api-openapi.yml
  - openapi/national-australia-bank-banking-account-transactions-api-openapi.yml
generated: '2026-10-20'
method: generated
---

# Read consented NAB account data (CDR)

**Not public.** These endpoints are only callable by an ACCC-accredited data recipient
with an active consumer consent (CDR FAPI profile, MTLS, consent-scoped access token).
NAB does not publicly document its authenticated resource base URL; the specs keep the
DSB placeholder `mtls.dh.example.com`. See `authentication/national-australia-bank-authentication.yml`.

## Rules
- Send `x-v` on every call (spec `x-version`: listBankingAccounts 3, getBankingAccountDetail 5,
  listBankingBalancesBulk 2, listBankingTransactions 2, getBankingTransactionDetail 3); 406 if unsupported.
- All operations are reads; no idempotency contract exists (see `conventions/`). POST
  variants such as `listBankingBalancesSpecificAccounts` only filter by a body list of accountIds.
- Errors use the CDS `{ "errors": [ {code, title, detail, meta} ] }` envelope (`errors/`).
- Page with `page` / `page-size`, follow `links.next`.

## Steps
1. `listBankingAccounts` - list consented accounts; keep each `accountId`.
2. `getBankingAccountDetail` - detail for one account.
3. `listBankingBalancesBulk` (all) or `getBankingBalance` (one) - balances.
4. `listBankingTransactions` with `oldest-time` / `newest-time` filters; then
   `getBankingTransactionDetail` for a transaction where `isDetailAvailable` is true.
