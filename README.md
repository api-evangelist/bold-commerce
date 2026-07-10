# Bold Commerce (bold-commerce)

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
