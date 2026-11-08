# Approved default commerce design

Apply this design to new stores unless the user supplies a different identity or asks to preserve an existing design. Treat it as the user's default, not a universally best style. Keep the skill general across merchants, countries, currencies and catalog types.

## Design direction

Use an elegant Arabic-first storefront direction with a clear browsing and product-detail structure. If the client supplies a reference store, use it only for interaction patterns; do not copy its logo, product files, text, screenshots, reviews or trust claims. This specification is self-contained.

- Use warm ivory surfaces, dark navy typography and restrained copper/gold accents. Defaults: background #FAF9F6, text #192E38, accent #A97850, borders #E6E5DF, muted text #707979. Choose measured accessible color variants when needed.
- Pair IBM Plex Sans Arabic for Arabic UI with its Latin face or a compatible readable Latin font. Use 400/500/600 weights, generous line height and a clear hierarchy. Respect font licences; bundle permitted assets where practical.
- Use spacious editorial composition, modest 4–8px corner radii, fine borders and restrained shadows. Avoid crowded badges, heavy gradients and fabricated ratings.
- Apply this palette exactly in previews and demos as well as full builds. Do not substitute other dominant colors (for example green hero banners or blue prices) unless the client supplies a different identity.
- Offer an optional dark theme with equivalent readable contrast; suggested dark background #142128, surface #1C2B32, text #E8E5DC, accent #D1AB7F. Test text on every surface; do not recolor product artwork or the brand logo merely to switch theme.

## Default icons and buttons

Apply the reference-style controls by default: thin consistent outline icons (approximately 1.65px strokes), a shopping-cart icon for the basket, a globe for locale, and sun/moon theme controls. Use catalogue-relevant icons such as book, clapperboard and package/pen rather than decorative unrelated symbols. Place category icons inside softly rounded ivory tiles with a fine warm-gold border and subtle shadow.

Use pill-shaped primary action buttons with gold #D1AD2F, hover #BC9824, dark accessible text #292208 and a subtle gold shadow. Keep secondary actions pill-shaped with a light outline, transparent background and dark text; supply equivalent dark-theme contrast. Header account buttons use a modest 6px radius. Place a straight directional arrow in the main browse action, a cart icon in Add to cart, and an eye icon beside View details. Use gold selected filter pills, fine outlined circular gallery arrows and wishlist controls, and clear keyboard-focus rings. Keep all meaningful hit areas usable on mobile. Preserve the official Omani rial symbol and the customer's identity. Explicit brand overrides take precedence.

## Shared navigation

Include a slim announcement strip, logo, Home/Products/About/Contact links, language and theme controls, account and cart count. Replace desktop navigation with an accessible mobile menu. Preserve the cart, selected product edition, locale and theme through navigation. Use meaningful links for routes and real buttons for actions.

Default the storefront to Arabic RTL with an English LTR option unless language requirements specify otherwise. Translate navigation, product titles and descriptions, errors, empty states, cart, checkout, account, support and administrative labels. Store preference locally when appropriate. Make bidi numbers and prices stable in both directions. Do not claim a translated product file exists merely because its UI is translated.

## Home and catalog

1. Open with a spacious hero: concise brand statement, supportive sentence, product or brand imagery, and a clear browse action. Keep client branding editable; do not hard-code any previous client's brand.
2. Provide concise, truthful category/fulfillment information.
3. Add category cards, latest/selected products, search, category filters, sorting and a result count. Preserve category links from the home page.
4. Use three product columns on desktop and two on small phones when readable. Each card includes relevant artwork/image, type, category, title, correctly formatted price, optional wishlist and a link to product details.
5. Add a short three-step purchase explanation and About/support links. Describe downloads as immediate only if verified fulfillment actually supports that claim.

## Independent product detail

Use a stable route per product, shareable URL, breadcrumb and title metadata. Show a gallery and purchase panel in two desktop columns, stacked on mobile.

- Support multiple images, selected thumbnails, previous/next controls and user-controlled video previews with a poster and accessible name. Use actual product media when supplied. Label illustrative previews and sample data clearly. Never autoplay with sound.
- Include product title, full description, type/format/specifications, current price and actual availability.
- Render genuine variants as accessible radio choices: language editions for digital files, or stock-backed color/size options for physical products. Do not silently invent saleable variants or files. Retain the selected variant and quantity in separate cart lines. Validate variants, price and aggregate stock on the server.
- Provide quantity controls, Add to cart, Buy now, wishlist and share link. Buy now carries the selected variant into order review; it never pretends payment succeeded.
- Add expandable product details, delivery/licence/returns information and relevant products. Do not fabricate reviews or expose private paid files in the preview gallery.

## Cart, checkout and account

Use independent cart and order-review pages. Show the selected edition/finish, quantity, unit/line price, editable quantities and removal. Present shipping and tax status honestly; an unconfigured amount is not a free service. Use OMR precision of three decimal places when Oman is the merchant country.

For Oman, use the new Omani rial symbol from a verified official design, preferably a bundled vector rendered at its original proportions with clear spacing before the numeral. Provide an accessible “Omani rials / ريال عماني” label, isolate bidi order, and retain OMR for API/system currency codes. Verify current official artwork/guidelines when implementing; do not substitute the Saudi, Iranian or generic rial glyph. Do not fall back to the text abbreviation ر.ع. or "RO" as the displayed price symbol for Omani stores, including quick previews; use it only inside the accessible label when the vector is unavailable and state that limitation. Do not force OMR or Oman's symbol for other countries.

Account space includes a buyer library, order history and wishlist. Enable authentication, protected orders and expiring downloads only with genuine backend authorization. Keep setup blockers explicit. A UI library page is not proof of a working entitlement system.

## Administration and verification

Keep the administrative design consistent, with overview, products, orders, customers and settings. Build real access controls and persistent operations when integrations are available. If only a preview is possible, visibly label temporary edits and absent data; never call it a complete operational admin panel.

Verify desktop/mobile layouts, both locales and themes, direct product links and not-found behavior, gallery controls, editions, quantity limits, cart persistence and price precision. Test payment and delivery separately from visual success. Retain commerce-controls.md and security-and-operations.md as the required controls; this design does not weaken them.
