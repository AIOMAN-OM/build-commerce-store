# Commerce acceptance controls

## Payments and orders

- Choose a payment provider supported for the merchant country, settlement currency and business type; verify official documentation. Do not hard-code a provider for all clients.
- Use hosted checkout or provider tokenization. Never store card numbers or CVV.
- Recalculate price, discounts, tax, shipping and currency on the server from trusted records. Use exact decimal or currency-aware minor-unit arithmetic, including currencies with three decimal places such as OMR.
- Create pending orders with immutable line-item price snapshots. Use payment/session identifiers and unique constraints to prevent duplication.
- Verify webhook signatures against the raw request body. Validate account, amount, currency, order mapping and event type. Support idempotency, retries, delayed/out-of-order events and reconciliation.
- Never treat a browser redirect, client-submitted paid flag or checkout creation as proof of payment. Issue digital entitlements only after verified successful payment.
- Model pending, paid, failed, canceled, refunded and partially refunded states with explicit transitions. Handle asynchronous methods and refunds according to provider behavior.
- Reserve/decrement stock atomically. Handle expiration and concurrent purchases without overselling. Use transactions or equivalent concurrency controls.
- Separate payment sandbox from live configuration. Report which was tested.

## Supabase and authorization

- Define migrations for profiles, products, categories, variants, orders, line items, payments, entitlements, coupons and audit events as needed; avoid unnecessary tables.
- Enable RLS on every exposed table and write policies for anonymous users, owners and staff. Keep public product reads limited to published content and safe columns.
- Store privileged roles in server-controlled claims or protected tables. Never trust user-editable profile metadata for administrator access.
- Prevent customers from writing prices, payment states, entitlements or roles. Check authorization in functions, RPCs, server routes and Storage policies.
- Keep paid assets in private buckets. Authorize each download against the authenticated buyer's current entitlement before issuing short-lived signed URLs. Prevent object-path guessing and cross-customer access.
- Treat refunds and chargebacks according to documented entitlement rules. Explain that authorized downloads cannot be reliably revoked once copied; do not promise piracy prevention.

## Required end-to-end cases

1. Browse/search/filter and add a valid variant to the cart on mobile and desktop.
2. Complete sandbox payment, verify exactly one paid order and correct fulfillment.
3. Replay a webhook; verify no duplicate order, stock decrement or entitlement.
4. Submit an invalid signature or altered client price; verify rejection.
5. Fail or cancel payment; verify no digital access and appropriate stock release.
6. Access another customer's order or private file; verify denial.
7. Attempt administrator operations as an anonymous user and customer; verify denial.
8. Test out-of-stock/concurrent purchase behavior and coupon validity.
9. Exercise refund or partial refund and verify totals and entitlement behavior.
10. Compare dashboard values with a small known dataset, including refunds, timezones and currency precision.

Record execution evidence and blockers. Mark a case as untested when it could not run.
