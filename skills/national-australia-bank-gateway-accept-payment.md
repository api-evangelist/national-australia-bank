---
name: national-australia-bank-gateway-accept-payment
description: Authorise, capture, refund, void or reverse a card payment on NAB Gateway (a white-label of the Cybersource / Visa Acceptance REST platform) and look the transaction up afterwards.
api: openapi/national-australia-bank-gateway-payments-api-openapi.yml
operations: [createPayment, capturePayment, refundPayment, voidPayment, authReversal, getTransaction]
generated: '2026-10-20'
method: generated
---

# Accept a payment on NAB Gateway

The spec is the Cybersource merged spec served by NAB's portal
(nabgateway-developer.nab.com.au); its servers[] are Cybersource hosts
(`apitest.cybersource.com` for test). The spec declares no securityDefinitions;
authentication follows the portal's Cybersource guides (merchant ID plus HTTP-signature
or JWT keys). See `authentication/`.

## Rules
- These are money-moving POSTs. `createPayment` declares no idempotency header (only
  `postRegistration` / `patchRegistration` carry the optional `v-c-idempotency-id`), so
  never blindly retry: on a timeout, look the transaction up before resubmitting.
- Keep the `id` returned by `createPayment`; every follow-on call uses it in the path.

## Steps
1. `createPayment` (`POST /pts/v2/payments`) - authorise (optionally with capture).
2. `capturePayment` (`POST /pts/v2/payments/{id}/captures`) - settle an authorisation.
3. To undo: `authReversal` (`POST /pts/v2/payments/{id}/reversals`) before capture,
   `voidPayment` (`POST /pts/v2/payments/{id}/voids`) before settlement, or
   `refundPayment` (`POST /pts/v2/payments/{id}/refunds`) after.
4. `getTransaction` (`GET /tss/v2/transactions/{id}`) - confirm final state.
