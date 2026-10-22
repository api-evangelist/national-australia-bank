---
name: national-australia-bank-gateway-invoices-and-pay-by-link
description: Create, send, list and cancel invoices and create or update Pay by Link payment links on NAB Gateway (Cybersource platform) - the same operations the Visa Acceptance local MCP server exposes as tools.
api: openapi/national-australia-bank-gateway-payments-api-openapi.yml
operations: [createInvoice, getAllInvoices, getInvoice, updateInvoice, performSendAction, performCancelAction, createPaymentLink, getAllPaymentLinks, getPaymentLink, updatePaymentLink]
generated: '2026-10-20'
method: generated
---

# Invoices and Pay by Link on NAB Gateway

An agent can reach these through the Visa Acceptance Agent Toolkit MCP server
(`npx -y @visaacceptance/mcp`, local stdio, pilot, third-party - linked from the NAB Gateway
portal's llms.txt), whose tools map 1:1 here (`mcp/national-australia-bank-tool-crosswalk.yml`),
or by calling REST directly.

## Steps
1. `createInvoice` (`POST /invoicing/v2/invoices`) - tool `invoices.create`.
2. `performSendAction` (`POST /invoicing/v2/invoices/{id}/delivery`) - tool `invoices.send`.
3. `getAllInvoices` / `getInvoice` to track; `updateInvoice` to amend;
   `performCancelAction` (`POST /invoicing/v2/invoices/{id}/cancelation`) to cancel.
4. `createPaymentLink` (`POST /ipl/v2/payment-links`) - tool `paymentLinks.create`;
   `getAllPaymentLinks`, `getPaymentLink`, `updatePaymentLink` (PATCH) to manage.

## Rules
- No idempotency header on these operations: check `getAllInvoices` / `getAllPaymentLinks`
  before retrying a create.
