# Bold Commerce (bold-commerce)

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
> **Not from the company, and here with a question?** You are welcome here — we would rather be the
> front line and point you the right way than have a good report go nowhere. What this repository
> can answer is narrow, though, so it is worth knowing who you are actually looking for:
>
> - **A question about how the API works, an account, billing, or a bug in the service** — that is
>   the company's own support, not us. We profile this API; we do not operate it and cannot see
>   your account.
> - **A bug in an open-source project we only catalog** — file it on that project's own repository.
>   This has happened with a real and correct bug report that reached us instead of the people who
>   could fix it, which helped nobody.
> - **Anything about this listing itself** — the description, the tags, the rating, a missing or
>   wrong artifact — is ours. Open an issue here.
> - **Not sure, or something general about API Evangelist or APIs.io** — open an issue on the
>   [APIs.io Inbox](https://github.com/api-search/inbox) and we will route it.
>
> **This repository contains no software, and we will never ask you to download anything.** There is
> no build, release, installer, or binary here — only text and machine-readable API descriptions, so
> there is nothing here that can be "corrupt" or need "repairing". Any issue, comment, or email
> claiming otherwise and offering a download link is not from us and is hostile. Do not follow the
> link; it is a lure. Report it to GitHub and, if you like, tell us at
> [info@apievangelist.com](mailto:info@apievangelist.com) so we can take it down.
>
> **On a security or compliance team?** Email
> [info@apievangelist.com](mailto:info@apievangelist.com) with *security* in the subject line and
> you will get a person, not a form. We will tell you exactly which public URLs this profile was
> built from so your team can see the same surface we did, and we will take the listing down on
> request while you work through it.
>
> Full detail: **[Where this data comes from](https://apievangelist.com/about/where-our-data-comes-from)**
<!-- API-EVANGELIST-PROVENANCE:END -->

Bold Commerce builds modular e-commerce apps and headless commerce APIs for subscriptions, checkout, and pricing. Merchants and developers integrate Bold Subscriptions (recurring orders and branded customer portals), Bold Checkout (a headless, fully customizable checkout across Frontend, Backend, and Admin surfaces), and Bold Price Rules (discounts, promotions, and dynamic pricing), alongside supporting Products, Customers, and Shops APIs.

All requests are made against `https://api.boldcommerce.com` and authenticated with a Bearer token: an OAuth 2.0 access token for public integrations (authorization-code flow via the Developer Dashboard) or a scoped API access token for private integrations (generated in the Bold Account Center). The storefront checkout surface additionally scopes each order session with a JWT. Most paths are scoped to a `shop_identifier` GUID retrieved from the Shops API, and versioned endpoints accept a `Bold-API-Version-Date` header.

**Access model note:** Bold's APIs are not sold as a standalone metered API product. Access comes with the corresponding merchant app subscription (for example, Bold Subscriptions) and is gated by OAuth scopes and API access tokens. Bold Checkout and Bold Price Rules are generally packaged into platform / headless commerce agreements rather than a public self-service price. The endpoints in this catalog are modeled from Bold's public developer documentation; request and response schemas in the OpenAPI are representative rather than byte-for-byte official.

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/bold-commerce/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/bold-commerce/refs/heads/main/apis.yml)

## Tags

- E-Commerce
- Subscriptions
- Checkout
- Pricing
- Headless Commerce
- Shopify

## Timestamps

- **Created:** 2026-07-10
- **Modified:** 2026-07-10

## APIs

### Bold Subscriptions API

Create, retrieve, update, pause, cancel, and reactivate subscriptions; manage line items, intervals, discount codes, shipping addresses, orders (skip / unskip), and adjustments. Powers custom subscription rules, integrations, reporting, and branded customer portals.

- **Human URL:** [https://developer.boldcommerce.com/api/subscriptions](https://developer.boldcommerce.com/api/subscriptions)
- **Base URL:** `https://api.boldcommerce.com/subscriptions/v1`

#### Tags

- Subscriptions
- Recurring Orders
- Customer Portal

#### Properties

- [Documentation](https://developer.boldcommerce.com/api/subscriptions)
- [API Reference](https://developer.boldcommerce.com/api/subscriptions)
- [OpenAPI](openapi/bold-commerce-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/bold-commerce.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/bold-commerce.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Bold Checkout API

Headless storefront checkout - manage shipping and billing addresses, line items, discounts, shipping lines, taxes, customers, and payments against an order, returning full order and `application_state` context. A JWT scopes each order session on the storefront surface.

- **Human URL:** [https://developer.boldcommerce.com/api/checkout](https://developer.boldcommerce.com/api/checkout)
- **Base URL:** `https://api.boldcommerce.com/checkout/storefront`

#### Tags

- Checkout
- Headless
- Orders

#### Properties

- [Documentation](https://developer.boldcommerce.com/api/checkout)
- [Documentation](https://developer.boldcommerce.com/guides/checkout/quick-start)
- [OpenAPI](openapi/bold-commerce-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/bold-commerce.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/bold-commerce.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Bold Price Rules API

Create and manage discounts, promotions, and dynamic pricing through rulesets and rules, order conditions, bulk activate / deactivate operations, a storefront ruleset lookup, and a process endpoint that returns the final price for a line item in a cart. Scopes include `read_price_rulesets` and `write_price_rulesets`.

- **Human URL:** [https://developer.boldcommerce.com/api/price-rules](https://developer.boldcommerce.com/api/price-rules)
- **Base URL:** `https://api.boldcommerce.com/price_rules`

#### Tags

- Pricing
- Discounts
- Promotions

#### Properties

- [Documentation](https://developer.boldcommerce.com/api/price-rules)
- [API Reference](https://developer.boldcommerce.com/api/price-rules)
- [OpenAPI](openapi/bold-commerce-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/bold-commerce.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/bold-commerce.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Bold Products API

Read and manage the product catalog for a shop - list, retrieve, create, update, and delete products and variants scoped to a `shop_identifier`.

- **Human URL:** [https://developer.boldcommerce.com/api/products](https://developer.boldcommerce.com/api/products)
- **Base URL:** `https://api.boldcommerce.com/products/v2`

#### Tags

- Products
- Catalog
- Inventory

#### Properties

- [Documentation](https://developer.boldcommerce.com/api/products)
- [OpenAPI](openapi/bold-commerce-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/bold-commerce.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/bold-commerce.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Bold Customers API

List, retrieve, create, and update customer records tied to a shop, used across checkout, subscriptions, and pricing to associate orders and recurring plans with shoppers.

- **Human URL:** [https://developer.boldcommerce.com/api/customers](https://developer.boldcommerce.com/api/customers)
- **Base URL:** `https://api.boldcommerce.com/customers/v2`

#### Tags

- Customers
- Profiles

#### Properties

- [Documentation](https://developer.boldcommerce.com/api/customers)
- [OpenAPI](openapi/bold-commerce-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/bold-commerce.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/bold-commerce.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Bold Shops API

Retrieve shop configuration and the `shop_identifier` GUID required in the path of most Bold API requests, including shop name, domain, platform, and default currency.

- **Human URL:** [https://developer.boldcommerce.com/api/shops](https://developer.boldcommerce.com/api/shops)
- **Base URL:** `https://api.boldcommerce.com/shops/v1`

#### Tags

- Shops
- Platform
- Configuration

#### Properties

- [Documentation](https://developer.boldcommerce.com/api/shops)
- [OpenAPI](openapi/bold-commerce-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/bold-commerce.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/bold-commerce.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

## Common Properties

- [GitHub Organization](https://github.com/bold-commerce)
- [LinkedIn](https://www.linkedin.com/company/bold-commerce)
- [Website](https://boldcommerce.com)
- [Documentation](https://developer.boldcommerce.com)
- [Plans](plans/bold-commerce-plans-pricing.yml)
- [Rate Limits](rate-limits/bold-commerce-rate-limits.yml)
- [Fin Ops](finops/bold-commerce-finops.yml)

## Maintainers

**FN:** Kin Lane
**Email:** kin@apievangelist.com
