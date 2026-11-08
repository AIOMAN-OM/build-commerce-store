---
name: build-commerce-store
description: Build and update complete ecommerce stores for different clients selling physical or digital products, books, films, videos, or mixed catalogs. Use for requests to design or implement an online store with professional product cards, checkout and payments, Supabase, administrator dashboards, analytics, AI insights, backups, security checks, and delivery reports. يدعم طلبات إنشاء وتصميم وتحديث متجر إلكتروني متكامل بالعربية والإنجليزية.
---

# Build a complete commerce store

Respond conversationally in the user's language. Build functioning stores, not decorative mockups. Adapt to each client; do not embed a fixed country, payment provider, visual identity, or catalog. Start with a small number of questions and continue work that does not depend on the answers.

## Discover the project

1. Reuse facts already provided. Ask first what is sold (digital, physical, mixed), the merchant's country and currency, and any brand identity or reference store. Ask only unresolved, consequential questions, in small batches.
2. Determine audience, languages and RTL requirements, fulfillment model, variants, shipping, and whether a single merchant or marketplace is intended. Default to one merchant; treat multi-vendor payouts as additional scope.
3. Apply the approved default design in [default-store-design.md](references/default-store-design.md) when creating a store without an explicit alternative identity. Read it before implementation. Use its storefront structure, independent product pages, media gallery, edition selection, bilingual navigation, light/dark themes and accessible product cards. Adapt the brand and catalog to the client; explicit user preferences and an existing store identity take precedence. Do not ask the user to choose a style again when the default applies.
4. Capture required integrations, existing code or hosting, available Supabase project, payment eligibility, budget constraints, AI provider, and backup expectations. Never request credentials in chat; use supported secret management.
5. Use a representative example, such as selling PDF books and protected video downloads, to confirm purchase and delivery behavior. Provide a compact scope and implementation sequence.

## Select tools and architecture

- Follow applicable Sites skills when creating a new website through Sites. Preserve the stack of an existing repository. Read applicable Supabase skills before any Supabase work and deployment/authentication/provider skills when their tasks arise.
- Use official current documentation for APIs, payment eligibility, supported currencies, security settings, and plan-dependent backup capabilities. Do not invent integrations or assume an account is connected.
- Prefer maintainable typed code, server-side validation, versioned database migrations, clear service boundaries, and reusable accessible components. Isolate client-specific branding and settings.
- Connect Supabase Database, Auth, and Storage as appropriate. Use separate development and production configurations. Keep service-role keys and provider secrets on the server.
- Distinguish implemented, tested, simulated, and blocked integrations. If credentials are unavailable, complete reviewable code and sandbox flows, list the missing setup, and never describe the store as operational.

## Implement the store

- Build responsive home, category, independent shareable product detail, search/filter/sort, cart, checkout, account, order history, and support pages. Add wishlist/reviews when useful. Use clear product cards with readable titles, accessible images, price/currency, availability, and purposeful actions.
- Support Arabic RTL and English LTR when requested, including mixed-direction numbers, currency formatting, mobile navigation, keyboard use, contrast, focus, and empty/loading/error/success states.
- Choose fonts that support the actual language and have suitable licenses. Optimize images, fonts, metadata, structured product data, and performance. Do not fabricate reviews, sales, or trust badges.
- Support product variants, stock and shipping for physical goods. Support controlled downloads, entitlements, file versions and previews for digital goods. Clarify streaming versus downloading for films/videos; use appropriate media hosting rather than assuming Supabase provides DRM or a streaming platform.
- Build configurable contact, shipping, returns/refunds and privacy pages using supplied business facts. Flag legal/tax content for jurisdiction-specific review without inventing obligations.

## Implement operations and reporting

- Build real administrator workflows for products, categories, media, stock, orders, fulfillment, customers, coupons, and settings. Support role-based access, audit events, pagination, validation, and reversible status changes.
- Enforce permissions on the server and database; hiding a button is insufficient. Support MFA for privileged users where available.
- Build indicators for paid revenue, orders, refunds, average order value, top products and trends. Add conversion only when a valid event source and denominator exist. Define date range, timezone, currency and refund treatment; never sum currencies without conversion rules.
- Provide filtered reports and safe exports; prevent spreadsheet formula injection in user-controlled CSV fields. Distinguish sample data from actual commerce data.
- Add AI analysis on request: summarize verified aggregate metrics, identify anomalies and propose evidence-based actions. Link conclusions to periods and numbers, label uncertainty, minimize personal data, and keep AI recommendations advisory. Do not autonomously change prices, issue refunds or contact customers from AI output.

## Verify payment, data and delivery

Read [commerce-controls.md](references/commerce-controls.md) before implementing checkout, database permissions or digital delivery. Use its acceptance scenarios throughout implementation.

## Review security and reliability

Read [security-and-operations.md](references/security-and-operations.md) before review, backups or release. Perform checks supported by the available environment, fix detected issues within authorized scope, and rerun affected checks. Never promise complete security or claim every vulnerability has been eliminated.

## Deliver and maintain

1. Verify representative customer and administrator journeys end to end with test accounts and sandbox payment events. Exercise failures and permission boundaries, not only the happy path.
2. Deliver the source, migrations, configuration example without secrets, implementation status, test evidence, security findings and fixes, known limitations, and deployment/rollback instructions through the project's normal delivery mechanism.
3. Include backup coverage, restore evidence or untested status, maintenance recommendations and prioritized next steps. Do not claim a scheduled backup or monitoring job exists without creating and verifying it.
4. Treat production publishing and real payment activation according to existing user authorization and applicable tool policies. Do all preparatory implementation and review before requesting any required final approval.
5. For updates, inspect the existing project, preserve orders and entitlements, use compatible migrations, back up affected data, validate changes and provide rollback. Never wipe production data to simplify implementation.
