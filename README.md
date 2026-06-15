# Rocket Lawyer (rocket-lawyer)

Rocket Lawyer is a San Francisco, California online legal technology company that has helped over 20 million businesses and individuals get online legal help. Founded in 2008, Rocket Lawyer offers self-service lawyer-vetted legal documents (contracts, NDAs, leases, wills, living trusts, power of attorney, business formation paperwork) plus DIY business services (LLC and corporation formation, registered agent service, DBA filings, annual reports, trademark registration), RocketTax tax preparation, and an "Ask a Legal Pro" attorney network for live consultations and document review. The platform is anchored by a membership model — Standard, Plus, and Pro tiers — that bundles unlimited documents, e-signatures, Rocket Copilot AI contract review, and varying numbers of Legal Pro questions and live consultations. Rocket Lawyer also operates a partner developer program with public REST APIs — exposed through an Apigee-backed developer portal at developer.rocketlawyer.com — that lets third parties embed lawyer-vetted document creation, electronic signature, and event-driven workflows into their own products. Four APIs are published with OpenAPI 3.0 specifications and live sandbox + production environments: the Authentication API (OAuth 2.0 access / service / scoped tokens), the RocketDocument v2 API (interview-driven document creation), the RocketSign and Binders API (electronic signature and document bundle management), and the Events API (subscription + pull-based event notifications). Both Embedded UX components and a "build your own UX" path are supported, and partner onboarding is managed through api@rocketlawyer.com and a self-service developer portal.

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/rocket-lawyer/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/rocket-lawyer/refs/heads/main/apis.yml)

## Scope

- **Type:** Index
- **Position:** Provider
- **Access:** 3rd-Party

## Tags

- Legal
- Legal Technology
- LegalTech
- Legal Documents
- Electronic Signature
- eSignature
- Document Creation
- Document Management
- Business Formation
- LLC Formation
- Registered Agent
- Trademark
- Wills
- Estate Planning
- Attorney Network
- Small Business
- Membership
- Embedded UX
- Partner API
- Apigee
- OpenAPI

## Timestamps

- **Created:** 2026-05-25
- **Modified:** 2026-05-25

## APIs

### Rocket Lawyer Authentication API

OAuth 2.0 authentication mechanism for accessing Rocket Lawyer partner APIs. Issues three token types — Access Tokens (server-to-server, 10-hour TTL), Service Tokens (backend-to-frontend delegation, 1-year TTL scoped by purpose / interviewId / UPID), and Scoped Access Tokens (front-end calls, derived from a Service Token). Supports `client_credentials` and `authorization_code` grant types. Apps can be created with either backend or frontend scope from the Rocket Lawyer Developer Portal.

- **Human URL:** [https://developer.rocketlawyer.com/docs/partner-auth-service-product-sandbox/1/overview](https://developer.rocketlawyer.com/docs/partner-auth-service-product-sandbox/1/overview)
- **Base URL:** `https://api.rocketlawyer.com/partners/v1/auth`

#### Tags

- Authentication
- OAuth
- Access Tokens
- Service Tokens

#### Properties

- [Documentation](https://developer.rocketlawyer.com/docs/partner-auth-service-product-sandbox/1/overview)
- [OpenAPI](openapi/rocket-lawyer-authentication-api-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/rocket-lawyer-authentication-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/rocket-lawyer-authentication-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Rocket Lawyer RocketDocument v2 API

Create and customize lawyer-vetted legal documents on behalf of your customers. Drives a stateful Interview that walks an end-user through the questions for a chosen Template (NDAs, leases, operating agreements, wills, etc.), captures answers (including tagged-answer reuse across documents), renders preview / thumbnail / final documents, and exposes the resulting Document for download. Pairs with the Embedded UX component or a build-your-own front end driven by Service / Scoped Access Tokens.

- **Human URL:** [https://developer.rocketlawyer.com/docs/rocketdoc-api-product-sandbox/1/overview](https://developer.rocketlawyer.com/docs/rocketdoc-api-product-sandbox/1/overview)
- **Base URL:** `https://api.rocketlawyer.com/rocketdoc/v2`

#### Tags

- Legal Documents
- Document Creation
- Document Templates
- Interviews
- Legal Technology

#### Properties

- [Documentation](https://developer.rocketlawyer.com/rocketdocument-v2-embedded-ux)
- [Documentation](https://developer.rocketlawyer.com/rocketdocument-v2-build-your-own-ux)
- [Release Notes](https://developer.rocketlawyer.com/rocketdocument-v2-release-notes)
- [OpenAPI](openapi/rocket-lawyer-rocketdocument-api-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/rocket-lawyer-rocketdocument-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/rocket-lawyer-rocketdocument-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Rocket Lawyer RocketSign and Binders API

Bundle one or more documents into a Binder and run them through Rocket Lawyer's electronic signature workflow. Manage binder lifecycle (status, locks), parties (signers, viewers, owners), documents and their pages / inputs, and orchestrate signature requests — invitations, signatures, reminders, finalisations, cancellations, declines, and viewer access. Supports email invites, embedded signing, and a single-call multi-document signing flow.

- **Human URL:** [https://developer.rocketlawyer.com/docs/binders-product-document-manager-sandbox/1/overview](https://developer.rocketlawyer.com/docs/binders-product-document-manager-sandbox/1/overview)
- **Base URL:** `https://api.rocketlawyer.com/document-manager/v1`

#### Tags

- Electronic Signature
- eSignature
- RocketSign
- Binders
- Document Management
- Legal Documents

#### Properties

- [Documentation](https://developer.rocketlawyer.com/rocketsign-embedded-ux)
- [OpenAPI](openapi/rocket-lawyer-rocketsign-binders-api-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/rocket-lawyer-rocketsign-binders-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/rocket-lawyer-rocketsign-binders-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Rocket Lawyer Events API

Subscribe to and consume notifications about activity within your tenant (interviews started / completed, documents signed, binders finalised, etc.). Provides Subscription Management (create, get, update, delete subscriptions) and a pull-based Event Consumption model with eventPulls, eventAcknowledgements, and seekRequests so partners can resume from a known position.

- **Human URL:** [https://developer.rocketlawyer.com/docs/partner-event-api-subscription-product-sandbox/1/overview](https://developer.rocketlawyer.com/docs/partner-event-api-subscription-product-sandbox/1/overview)
- **Base URL:** `https://api.rocketlawyer.com/events/v1`

#### Tags

- Events
- Webhooks
- Notifications
- Subscriptions
- Event Pull

#### Properties

- [Documentation](https://developer.rocketlawyer.com/docs/partner-event-api-subscription-product-sandbox/1/overview)
- [OpenAPI](openapi/rocket-lawyer-events-api-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/rocket-lawyer-events-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/rocket-lawyer-events-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

## Common Properties

- [Website](https://www.rocketlawyer.com)
- [Portal](https://developer.rocketlawyer.com/)
- [Getting Started](https://developer.rocketlawyer.com/welcome-guide)
- [Documentation](https://developer.rocketlawyer.com/welcome-guide)
- [Documentation](https://docs.rocketlawyer.net/)
- [Documentation](https://developer.rocketlawyer.com/rocketdocument-v2-embedded-ux)
- [Documentation](https://developer.rocketlawyer.com/rocketdocument-v2-build-your-own-ux)
- [Documentation](https://developer.rocketlawyer.com/rocketsign-embedded-ux)
- [Release Notes](https://developer.rocketlawyer.com/rocketdocument-v2-release-notes)
- [Glossary](https://developer.rocketlawyer.com/glossary)
- [Sign Up](https://developer.rocketlawyer.com/accounts/create)
- [Login](https://developer.rocketlawyer.com/accounts/login)
- [Contact](https://www.rocketlawyer.com/developers)
- [Terms of Service](https://developer.rocketlawyer.com/terms)
- [Developer Terms Of Service](https://www.rocketlawyer.com/developer-terms-and-conditions)
- [Support](https://www.rocketlawyer.com/help)
- [Postman](https://www.postman.com/rocket-lawyer/workspaces) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Postman](https://documenter.getpostman.com/view/36551580/2sAXjGbtoR) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Legal Documents](https://www.rocketlawyer.com/legal-documents)
- [Business Formation](https://www.rocketlawyer.com/business/business-operations/start-a-business)
- [Rocket Sign](https://www.rocketlawyer.com/rocketsign-digital-signatures)
- [Pricing](https://www.rocketlawyer.com/pricing)
- [About](https://www.rocketlawyer.com/about-us)
- [Press](https://www.rocketlawyer.com/news)
- [Careers](https://www.rocketlawyer.com/about-us/careers)
- [Blog](https://www.rocketlawyer.com/blog)
- [Privacy Policy](https://www.rocketlawyer.com/privacy)
- [GitHub Organization](https://github.com/rocketlawyer)
- [LinkedIn](https://www.linkedin.com/company/rocket-lawyer)
- [Twitter](https://twitter.com/rocketlawyer)
- [Facebook](https://www.facebook.com/RocketLawyer)
- [YouTube](https://www.youtube.com/user/rocketlawyer)

## Maintainers

**FN:** Kin Lane
**Email:** kin@apievangelist.com
