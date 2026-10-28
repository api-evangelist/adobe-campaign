# Adobe Campaign

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

Adobe Campaign is Adobe's enterprise cross-channel campaign management and marketing automation platform, orchestrating email, SMS, push, direct mail and web messaging against a customer-owned marketing database. It ships two distinct programmable surfaces: a JSON REST API on https://mc.adobe.io/{ORGANIZATION}/campaign covering profiles, services and subscriptions, custom resources, workflows, privacy requests and transactional messaging, authenticated with an Adobe IMS OAuth Server-to-Server bearer token plus an X-Api-Key; and the Campaign Classic SOAP-over-HTTP surface on the customer's own instance host, authenticated with a session-token pair from xtk:session#Logon. Campaign v8 is the current generation, Campaign Classic v7 is the legacy on-premise line, and Adobe has deprecated Campaign Standard in favour of Adobe Journey Optimizer. The data model is extended per tenant, so the deployed shape must be discovered at runtime rather than assumed from a specification.

**Areas:** Campaign Management · Customer Experience · Email Marketing · Marketing Automation · Multi-Channel Marketing · Transactional Messaging · Customer Data · Adobe Experience Cloud · SMS · Push Notifications · Workflow Automation · Privacy

## Adobe Campaign on APIs.io

Everything profiled for Adobe Campaign is published on APIs.io rather than in this repository. Start at the provider page — **[apis.io/providers/adobe-campaign/](https://apis.io/providers/adobe-campaign/)** — or go straight to one of the APIs or properties below.

### APIs (20)

- [Adobe Campaign Classic JavaScript SDK](https://apis.io/apis/adobe-campaign/classic-javascript-sdk/) — An open-source JavaScript SDK that wraps Adobe Campaign Classic SOAP APIs in a simple, expressive, JavaScript-idiomatic interface. The SDK supports…
- [Adobe I/O Campaign Standard SDK](https://apis.io/apis/adobe-campaign/io-campaign-standard-sdk/) — A Node.js JavaScript SDK wrapping Adobe Campaign Standard REST APIs for use in Adobe I/O Runtime and App Builder applications. Provides convenience methods…
- [Adobe Experience Platform Mobile SDK - Campaign Extensions](https://apis.io/apis/adobe-campaign/experience-platform-mobile-sdk---campaign-extensions/) — Native mobile SDK extensions for iOS and Android that integrate Adobe Campaign push notifications, in-app messaging, and local notifications into mobile…
- [Adobe Campaign Custom Resources API](https://apis.io/apis/adobe-campaign/adobe-campaign-custom-resources-api/) — Access custom resources defined in Campaign Standard, both profile-linked and standalone.
- [Adobe Campaign Data Management API](https://apis.io/apis/adobe-campaign/adobe-campaign-data-management-api/) — Write, update, and delete data records using the xtk:session#Write method. Supports insert, insertOrUpdate, update, and delete operations via the _operation…
- [Adobe Campaign Delivery API](https://apis.io/apis/adobe-campaign/adobe-campaign-delivery-api/) — Prepare and submit message deliveries including email, SMS, and push notifications.
- [Adobe Campaign Marketing History API](https://apis.io/apis/adobe-campaign/adobe-campaign-marketing-history-api/) — Retrieve marketing event history for profiles including delivery logs and mirror page links.
- [Adobe Campaign Metadata API](https://apis.io/apis/adobe-campaign/adobe-campaign-metadata-api/) — Discover resource schemas, fields, filters, and data policies for Campaign Standard resources.
- [Adobe Campaign Organizational Units API](https://apis.io/apis/adobe-campaign/adobe-campaign-organizational-units-api/) — Retrieve organizational unit structures used for access control and data partitioning.
- [Adobe Campaign Privacy API](https://apis.io/apis/adobe-campaign/adobe-campaign-privacy-api/) — Create GDPR and CCPA privacy access and deletion requests for data subject compliance.
- [Adobe Campaign ProfileAndServices API](https://apis.io/apis/adobe-campaign/adobe-campaign-profileandservices-api/) — The ProfileAndServices API from Adobe Campaign — 2 operation(s) for profileandservices.
- [Adobe Campaign Profiles API](https://apis.io/apis/adobe-campaign/adobe-campaign-profiles-api/) — Manage recipient profiles including creation, retrieval, update, and deletion of contact records.
- [Adobe Campaign Query Definition API](https://apis.io/apis/adobe-campaign/adobe-campaign-query-definition-api/) — Execute queries against Campaign schemas using the xtk:queryDef interface. Supports get, getIfExists, select, and count operations with XPath field…
- [Adobe Campaign Real-Time Events API](https://apis.io/apis/adobe-campaign/adobe-campaign-real-time-events-api/) — Push real-time transactional events for immediate or batched processing by the Message Center execution instances.
- [Adobe Campaign Session Management API](https://apis.io/apis/adobe-campaign/adobe-campaign-session-management-api/) — Authenticate and manage server sessions. Logon returns session and security tokens required for all subsequent API calls.
- [Adobe Campaign Subscription API](https://apis.io/apis/adobe-campaign/adobe-campaign-subscription-api/) — Subscribe and unsubscribe recipients to and from information services.
- [Adobe Campaign Subscriptions API](https://apis.io/apis/adobe-campaign/adobe-campaign-subscriptions-api/) — Subscribe and unsubscribe profiles to and from services.
- [Adobe Campaign Transactional Messages API](https://apis.io/apis/adobe-campaign/adobe-campaign-transactional-messages-api/) — Trigger and monitor transactional messages across email, SMS, and push notification channels.
- [Adobe Campaign Workflow API](https://apis.io/apis/adobe-campaign/adobe-campaign-workflow-api/) — Start, stop, and signal workflows. PostEvent sends asynchronous signals to trigger workflow transitions.
- [Adobe Campaign Workflows API](https://apis.io/apis/adobe-campaign/adobe-campaign-workflows-api/) — Control workflow execution including starting, pausing, resuming, and stopping marketing workflows.

### Published properties

Each property below is a page on APIs.io carrying the machine-readable artifact and what it says.

#### AsyncAPI (1)

Event-driven and webhook contracts.

- [Adobe Campaign Transactional Messaging Events](https://apis.io/asyncapis/adobe-campaign/adobe-campaign-transactional-messaging-asyncapi-original/)

#### Event channels (5)

Individual events and webhooks the provider emits.

- [batchEvent](https://apis.io/channels/adobe-campaign/batchevent/)
- [transactionalEvent/email](https://apis.io/channels/adobe-campaign/transactionalevent-email/)
- [transactionalEvent/push](https://apis.io/channels/adobe-campaign/transactionalevent-push/)
- [transactionalEvent/sms](https://apis.io/channels/adobe-campaign/transactionalevent-sms/)
- [transactionalEvent/status](https://apis.io/channels/adobe-campaign/transactionalevent-status/)

#### MCP servers (1)

Model Context Protocol servers that expose the API to agents.

- [adobe-campaign](https://apis.io/servers/adobe-campaign/adobe-campaign/)

#### Agentic access (1)

Which operations an agent can call, which act, and which need a human in the loop.

- [Adobe Campaign Agentic Access](https://apis.io/agentic-access/adobe-campaign/adobe-campaign-agentic-access/)

#### JSON Schema (30)

The data models the API reads and writes.

- [DeliveryRequest](https://apis.io/schemas/adobe-campaign/adobe-campaign-classic-delivery-request/)
- [PushEventRequest](https://apis.io/schemas/adobe-campaign/adobe-campaign-classic-push-event-request/)
- [PushEventResponse](https://apis.io/schemas/adobe-campaign/adobe-campaign-classic-push-event-response/)
- [PushEventsRequest](https://apis.io/schemas/adobe-campaign/adobe-campaign-classic-push-events-request/)
- [QueryDefinition](https://apis.io/schemas/adobe-campaign/adobe-campaign-classic-query-definition/)
- [QueryResult](https://apis.io/schemas/adobe-campaign/adobe-campaign-classic-query-result/)
- [SessionLogonRequest](https://apis.io/schemas/adobe-campaign/adobe-campaign-classic-session-logon-request/)
- [SessionLogonResponse](https://apis.io/schemas/adobe-campaign/adobe-campaign-classic-session-logon-response/)
- [SOAPFault](https://apis.io/schemas/adobe-campaign/adobe-campaign-classic-soap-fault/)
- [SubscriptionRequest](https://apis.io/schemas/adobe-campaign/adobe-campaign-classic-subscription-request/)
- [WorkflowPostEventRequest](https://apis.io/schemas/adobe-campaign/adobe-campaign-classic-workflow-post-event-request/)
- [WorkflowRequest](https://apis.io/schemas/adobe-campaign/adobe-campaign-classic-workflow-request/)
- [WriteCollectionRequest](https://apis.io/schemas/adobe-campaign/adobe-campaign-classic-write-collection-request/)
- [WriteRequest](https://apis.io/schemas/adobe-campaign/adobe-campaign-classic-write-request/)
- [WriteResponse](https://apis.io/schemas/adobe-campaign/adobe-campaign-classic-write-response/)
- [MarketingHistory](https://apis.io/schemas/adobe-campaign/adobe-campaign-standard-marketing-history/)
- [OrgUnit](https://apis.io/schemas/adobe-campaign/adobe-campaign-standard-org-unit/)
- [PrivacyRequest](https://apis.io/schemas/adobe-campaign/adobe-campaign-standard-privacy-request/)
- [PrivacyRequestResponse](https://apis.io/schemas/adobe-campaign/adobe-campaign-standard-privacy-request-response/)
- [Profile](https://apis.io/schemas/adobe-campaign/adobe-campaign-standard-profile/)
- [ProfileCreate](https://apis.io/schemas/adobe-campaign/adobe-campaign-standard-profile-create/)
- [ProfileUpdate](https://apis.io/schemas/adobe-campaign/adobe-campaign-standard-profile-update/)
- [Service](https://apis.io/schemas/adobe-campaign/adobe-campaign-standard-service/)
- [ServiceCreate](https://apis.io/schemas/adobe-campaign/adobe-campaign-standard-service-create/)
- [ServiceUpdate](https://apis.io/schemas/adobe-campaign/adobe-campaign-standard-service-update/)
- …and 5 more published on APIs.io

#### JSON Structure (30)

Data models expressed in JSON Structure.

- [Adobe Campaign Classic Delivery Request Structure](https://apis.io/json-structure/adobe-campaign/adobe-campaign-classic-delivery-request-structure/)
- [Adobe Campaign Classic Push Event Request Structure](https://apis.io/json-structure/adobe-campaign/adobe-campaign-classic-push-event-request-structure/)
- [Adobe Campaign Classic Push Event Response Structure](https://apis.io/json-structure/adobe-campaign/adobe-campaign-classic-push-event-response-structure/)
- [Adobe Campaign Classic Push Events Request Structure](https://apis.io/json-structure/adobe-campaign/adobe-campaign-classic-push-events-request-structure/)
- [Adobe Campaign Classic Query Definition Structure](https://apis.io/json-structure/adobe-campaign/adobe-campaign-classic-query-definition-structure/)
- [Adobe Campaign Classic Query Result Structure](https://apis.io/json-structure/adobe-campaign/adobe-campaign-classic-query-result-structure/)
- [Adobe Campaign Classic Session Logon Request Structure](https://apis.io/json-structure/adobe-campaign/adobe-campaign-classic-session-logon-request-structure/)
- [Adobe Campaign Classic Session Logon Response Structure](https://apis.io/json-structure/adobe-campaign/adobe-campaign-classic-session-logon-response-structure/)
- [Adobe Campaign Classic Soap Fault Structure](https://apis.io/json-structure/adobe-campaign/adobe-campaign-classic-soap-fault-structure/)
- [Adobe Campaign Classic Subscription Request Structure](https://apis.io/json-structure/adobe-campaign/adobe-campaign-classic-subscription-request-structure/)
- [Adobe Campaign Classic Workflow Post Event Request Structure](https://apis.io/json-structure/adobe-campaign/adobe-campaign-classic-workflow-post-event-request-structure/)
- [Adobe Campaign Classic Workflow Request Structure](https://apis.io/json-structure/adobe-campaign/adobe-campaign-classic-workflow-request-structure/)
- [Adobe Campaign Classic Write Collection Request Structure](https://apis.io/json-structure/adobe-campaign/adobe-campaign-classic-write-collection-request-structure/)
- [Adobe Campaign Classic Write Request Structure](https://apis.io/json-structure/adobe-campaign/adobe-campaign-classic-write-request-structure/)
- [Adobe Campaign Classic Write Response Structure](https://apis.io/json-structure/adobe-campaign/adobe-campaign-classic-write-response-structure/)
- [Adobe Campaign Standard Marketing History Structure](https://apis.io/json-structure/adobe-campaign/adobe-campaign-standard-marketing-history-structure/)
- [Adobe Campaign Standard Org Unit Structure](https://apis.io/json-structure/adobe-campaign/adobe-campaign-standard-org-unit-structure/)
- [Adobe Campaign Standard Privacy Request Response Structure](https://apis.io/json-structure/adobe-campaign/adobe-campaign-standard-privacy-request-response-structure/)
- [Adobe Campaign Standard Privacy Request Structure](https://apis.io/json-structure/adobe-campaign/adobe-campaign-standard-privacy-request-structure/)
- [Adobe Campaign Standard Profile Create Structure](https://apis.io/json-structure/adobe-campaign/adobe-campaign-standard-profile-create-structure/)
- [Adobe Campaign Standard Profile Structure](https://apis.io/json-structure/adobe-campaign/adobe-campaign-standard-profile-structure/)
- [Adobe Campaign Standard Profile Update Structure](https://apis.io/json-structure/adobe-campaign/adobe-campaign-standard-profile-update-structure/)
- [Adobe Campaign Standard Service Create Structure](https://apis.io/json-structure/adobe-campaign/adobe-campaign-standard-service-create-structure/)
- [Adobe Campaign Standard Service Structure](https://apis.io/json-structure/adobe-campaign/adobe-campaign-standard-service-structure/)
- [Adobe Campaign Standard Service Update Structure](https://apis.io/json-structure/adobe-campaign/adobe-campaign-standard-service-update-structure/)
- …and 5 more published on APIs.io

#### JSON-LD (1)

Linked-data contexts for the provider's vocabulary.

- [Adobe Campaign Context](https://apis.io/jsonld/adobe-campaign/adobe-campaign-context/)

#### Vocabulary (1)

The provider's domain terms, defined.

- [Adobe Campaign Vocabulary](https://apis.io/vocabularies/adobe-campaign/adobe-campaign-vocabulary/)

#### Examples (30)

Example requests and responses.

- [Adobe Campaign Classic Delivery Request Example](https://apis.io/examples/adobe-campaign/adobe-campaign-classic-delivery-request-example/)
- [Adobe Campaign Classic Push Event Request Example](https://apis.io/examples/adobe-campaign/adobe-campaign-classic-push-event-request-example/)
- [Adobe Campaign Classic Push Event Response Example](https://apis.io/examples/adobe-campaign/adobe-campaign-classic-push-event-response-example/)
- [Adobe Campaign Classic Push Events Request Example](https://apis.io/examples/adobe-campaign/adobe-campaign-classic-push-events-request-example/)
- [Adobe Campaign Classic Query Definition Example](https://apis.io/examples/adobe-campaign/adobe-campaign-classic-query-definition-example/)
- [Adobe Campaign Classic Query Result Example](https://apis.io/examples/adobe-campaign/adobe-campaign-classic-query-result-example/)
- [Adobe Campaign Classic Session Logon Request Example](https://apis.io/examples/adobe-campaign/adobe-campaign-classic-session-logon-request-example/)
- [Adobe Campaign Classic Session Logon Response Example](https://apis.io/examples/adobe-campaign/adobe-campaign-classic-session-logon-response-example/)
- [Adobe Campaign Classic Soap Fault Example](https://apis.io/examples/adobe-campaign/adobe-campaign-classic-soap-fault-example/)
- [Adobe Campaign Classic Subscription Request Example](https://apis.io/examples/adobe-campaign/adobe-campaign-classic-subscription-request-example/)
- [Adobe Campaign Classic Workflow Post Event Request Example](https://apis.io/examples/adobe-campaign/adobe-campaign-classic-workflow-post-event-request-example/)
- [Adobe Campaign Classic Workflow Request Example](https://apis.io/examples/adobe-campaign/adobe-campaign-classic-workflow-request-example/)
- [Adobe Campaign Classic Write Collection Request Example](https://apis.io/examples/adobe-campaign/adobe-campaign-classic-write-collection-request-example/)
- [Adobe Campaign Classic Write Request Example](https://apis.io/examples/adobe-campaign/adobe-campaign-classic-write-request-example/)
- [Adobe Campaign Classic Write Response Example](https://apis.io/examples/adobe-campaign/adobe-campaign-classic-write-response-example/)
- [Adobe Campaign Standard Marketing History Example](https://apis.io/examples/adobe-campaign/adobe-campaign-standard-marketing-history-example/)
- [Adobe Campaign Standard Org Unit Example](https://apis.io/examples/adobe-campaign/adobe-campaign-standard-org-unit-example/)
- [Adobe Campaign Standard Privacy Request Example](https://apis.io/examples/adobe-campaign/adobe-campaign-standard-privacy-request-example/)
- [Adobe Campaign Standard Privacy Request Response Example](https://apis.io/examples/adobe-campaign/adobe-campaign-standard-privacy-request-response-example/)
- [Adobe Campaign Standard Profile Create Example](https://apis.io/examples/adobe-campaign/adobe-campaign-standard-profile-create-example/)
- [Adobe Campaign Standard Profile Example](https://apis.io/examples/adobe-campaign/adobe-campaign-standard-profile-example/)
- [Adobe Campaign Standard Profile Update Example](https://apis.io/examples/adobe-campaign/adobe-campaign-standard-profile-update-example/)
- [Adobe Campaign Standard Service Create Example](https://apis.io/examples/adobe-campaign/adobe-campaign-standard-service-create-example/)
- [Adobe Campaign Standard Service Example](https://apis.io/examples/adobe-campaign/adobe-campaign-standard-service-example/)
- [Adobe Campaign Standard Service Update Example](https://apis.io/examples/adobe-campaign/adobe-campaign-standard-service-update-example/)
- …and 5 more published on APIs.io

#### Collections (17)

Postman and Open Collection request collections.

- [Adobe Campaign Classic Custom Resources API](https://apis.io/collections/adobe-campaign/open-adobe-campaign-custom-resources-api/)
- [Adobe Campaign Classic Custom Resources Data Management API](https://apis.io/collections/adobe-campaign/open-adobe-campaign-data-management-api/)
- [Adobe Campaign Classic Custom Resources Delivery API](https://apis.io/collections/adobe-campaign/open-adobe-campaign-delivery-api/)
- [Adobe Campaign Classic Custom Resources Marketing History API](https://apis.io/collections/adobe-campaign/open-adobe-campaign-marketing-history-api/)
- [Adobe Campaign Classic Custom Resources Metadata API](https://apis.io/collections/adobe-campaign/open-adobe-campaign-metadata-api/)
- [Adobe Campaign Classic Custom Resources Organizational Units API](https://apis.io/collections/adobe-campaign/open-adobe-campaign-organizational-units-api/)
- [Adobe Campaign Classic Custom Resources Privacy API](https://apis.io/collections/adobe-campaign/open-adobe-campaign-privacy-api/)
- [Adobe Campaign Classic Custom Resources ProfileAndServices API](https://apis.io/collections/adobe-campaign/open-adobe-campaign-profileandservices-api/)
- [Adobe Campaign Classic Custom Resources Profiles API](https://apis.io/collections/adobe-campaign/open-adobe-campaign-profiles-api/)
- [Adobe Campaign Classic Custom Resources Query Definition API](https://apis.io/collections/adobe-campaign/open-adobe-campaign-query-definition-api/)
- [Adobe Campaign Classic Custom Resources Real-Time Events API](https://apis.io/collections/adobe-campaign/open-adobe-campaign-real-time-events-api/)
- [Adobe Campaign Classic Custom Resources Session Management API](https://apis.io/collections/adobe-campaign/open-adobe-campaign-session-management-api/)
- [Adobe Campaign Classic Custom Resources Subscription API](https://apis.io/collections/adobe-campaign/open-adobe-campaign-subscription-api/)
- [Adobe Campaign Classic Custom Resources Subscriptions API](https://apis.io/collections/adobe-campaign/open-adobe-campaign-subscriptions-api/)
- [Adobe Campaign Classic Custom Resources Transactional Messages API](https://apis.io/collections/adobe-campaign/open-adobe-campaign-transactional-messages-api/)
- [Adobe Campaign Classic Custom Resources Workflow API](https://apis.io/collections/adobe-campaign/open-adobe-campaign-workflow-api/)
- [Adobe Campaign Classic Custom Resources Workflows API](https://apis.io/collections/adobe-campaign/open-adobe-campaign-workflows-api/)

#### Overlays (34)

OpenAPI overlays, including conversational phrasing for each operation.

- [Adobe Campaign Custom Resources Api Overlay](https://apis.io/overlays/adobe-campaign/adobe-campaign-custom-resources-api-overlay/)
- [Adobe Campaign Custom Resources Api Phrasing Overlay](https://apis.io/overlays/adobe-campaign/adobe-campaign-custom-resources-api-phrasing-overlay/)
- [Adobe Campaign Data Management Api Overlay](https://apis.io/overlays/adobe-campaign/adobe-campaign-data-management-api-overlay/)
- [Adobe Campaign Data Management Api Phrasing Overlay](https://apis.io/overlays/adobe-campaign/adobe-campaign-data-management-api-phrasing-overlay/)
- [Adobe Campaign Delivery Api Overlay](https://apis.io/overlays/adobe-campaign/adobe-campaign-delivery-api-overlay/)
- [Adobe Campaign Delivery Api Phrasing Overlay](https://apis.io/overlays/adobe-campaign/adobe-campaign-delivery-api-phrasing-overlay/)
- [Adobe Campaign Marketing History Api Overlay](https://apis.io/overlays/adobe-campaign/adobe-campaign-marketing-history-api-overlay/)
- [Adobe Campaign Marketing History Api Phrasing Overlay](https://apis.io/overlays/adobe-campaign/adobe-campaign-marketing-history-api-phrasing-overlay/)
- [Adobe Campaign Metadata Api Overlay](https://apis.io/overlays/adobe-campaign/adobe-campaign-metadata-api-overlay/)
- [Adobe Campaign Metadata Api Phrasing Overlay](https://apis.io/overlays/adobe-campaign/adobe-campaign-metadata-api-phrasing-overlay/)
- [Adobe Campaign Organizational Units Api Overlay](https://apis.io/overlays/adobe-campaign/adobe-campaign-organizational-units-api-overlay/)
- [Adobe Campaign Organizational Units Api Phrasing Overlay](https://apis.io/overlays/adobe-campaign/adobe-campaign-organizational-units-api-phrasing-overlay/)
- [Adobe Campaign Privacy Api Overlay](https://apis.io/overlays/adobe-campaign/adobe-campaign-privacy-api-overlay/)
- [Adobe Campaign Privacy Api Phrasing Overlay](https://apis.io/overlays/adobe-campaign/adobe-campaign-privacy-api-phrasing-overlay/)
- [Adobe Campaign Profileandservices Api Overlay](https://apis.io/overlays/adobe-campaign/adobe-campaign-profileandservices-api-overlay/)
- [Adobe Campaign Profileandservices Api Phrasing Overlay](https://apis.io/overlays/adobe-campaign/adobe-campaign-profileandservices-api-phrasing-overlay/)
- [Adobe Campaign Profiles Api Overlay](https://apis.io/overlays/adobe-campaign/adobe-campaign-profiles-api-overlay/)
- [Adobe Campaign Profiles Api Phrasing Overlay](https://apis.io/overlays/adobe-campaign/adobe-campaign-profiles-api-phrasing-overlay/)
- [Adobe Campaign Query Definition Api Overlay](https://apis.io/overlays/adobe-campaign/adobe-campaign-query-definition-api-overlay/)
- [Adobe Campaign Query Definition Api Phrasing Overlay](https://apis.io/overlays/adobe-campaign/adobe-campaign-query-definition-api-phrasing-overlay/)
- [Adobe Campaign Real Time Events Api Overlay](https://apis.io/overlays/adobe-campaign/adobe-campaign-real-time-events-api-overlay/)
- [Adobe Campaign Real Time Events Api Phrasing Overlay](https://apis.io/overlays/adobe-campaign/adobe-campaign-real-time-events-api-phrasing-overlay/)
- [Adobe Campaign Session Management Api Overlay](https://apis.io/overlays/adobe-campaign/adobe-campaign-session-management-api-overlay/)
- [Adobe Campaign Session Management Api Phrasing Overlay](https://apis.io/overlays/adobe-campaign/adobe-campaign-session-management-api-phrasing-overlay/)
- [Adobe Campaign Subscription Api Overlay](https://apis.io/overlays/adobe-campaign/adobe-campaign-subscription-api-overlay/)
- …and 9 more published on APIs.io

#### Governance rules (3)

Spectral rulesets for the provider's contracts.

- [Adobe Campaign — asyncapi rules](https://apis.io/rules/adobe-campaign/adobe-campaign-asyncapi-spectral-rules/)
- [Adobe Campaign — jsonschema rules](https://apis.io/rules/adobe-campaign/adobe-campaign-jsonschema-spectral-rules/)
- [Adobe Campaign API Rules](https://apis.io/rules/adobe-campaign/adobe-campaign-spectral-rules/)

#### Security (4)

Authentication, trust centre, and vulnerability disclosure.

- [Adobe Campaign Authentication](https://apis.io/security/adobe-campaign/adobe-campaign-authentication/)
- [Adobe Campaign Domain Security](https://apis.io/security/adobe-campaign/adobe-campaign-domain-security/)
- [Adobe Campaign Trust Center](https://apis.io/security/adobe-campaign/adobe-campaign-trust-center/)
- [Adobe Campaign Vulnerability Disclosure](https://apis.io/security/adobe-campaign/adobe-campaign-vulnerability-disclosure/)

#### OAuth scopes (1)

The permissions the API asks for.

- [Adobe Campaign Scopes](https://apis.io/scopes/adobe-campaign/adobe-campaign-scopes/)

#### Plans and pricing (1)

Published plans, tiers and prices.

- [Adobe Campaign Plans Pricing](https://apis.io/plans/adobe-campaign/adobe-campaign-plans-pricing/)

#### Rate limits (1)

Published request limits.

- [Adobe Campaign Rate Limits](https://apis.io/rate-limits/adobe-campaign/adobe-campaign-rate-limits/)

#### FinOps (1)

What the API costs to run, by operation.

- [Adobe Campaign Finops](https://apis.io/finops/adobe-campaign/adobe-campaign-finops/)

## Where to find this API

Links to the company's own pages. This repository publishes no copy of their specifications — the canonical document is theirs and lives at the URLs below.

- [Website](https://www.adobe.com/)
- [Documentation](https://experienceleague.adobe.com/en/docs/campaign/campaign-v8/campaign-home)
- [Getting started](https://experienceleague.adobe.com/docs/campaign-learn/tutorials/overview.html)
- [API reference](https://experienceleague.adobe.com/en/docs/campaign/campaign-v8/developer/apis/get-started-apis)
- [Pricing](https://business.adobe.com/products/campaign/adobe-campaign.html)
- [Sign up](https://developer.adobe.com/console)
- [Support](https://experienceleague.adobe.com/docs/customer-one/using/home.html)
- [Blog](https://business.adobe.com/blog/)
- [Terms of service](https://www.adobe.com/legal/terms.html)
- [Privacy policy](https://www.adobe.com/privacy.html)
- [GitHub](https://github.com/adobe)
- [Status](https://status.adobe.com/)

## API Evangelist rating

**Kin Score 70.7** — exemplar · rubric 0.25.0 · scored 2026-10-23

| Facet | Score |
|---|---|
| Discoverability | 73.2 |
| Contract quality | 68.2 |
| Contract governance | 31.8 |
| Operational transparency | 65.8 |
| Developer ergonomics | 73.2 |
| Access clarity | 76.3 |

**Agent readiness 31.5** — agent-ready

| Agent-readiness dimension | Result |
|---|---|
| Spec Presence | yes |
| Agentic Access | derived (partial credit) |
| Reversibility Documented | — |
| MCP Server | — |
| Auth Clarity | bearer (partial credit) |
| Idempotency | — |
| Error Semantics | derived (partial credit) |
| OpenAPI Examples | verified |
| Rate Limit Signal | documented (partial credit) |
| Event Surface Described | derived (partial credit) |
| Agent Skills | derived (partial credit) |
| Well Known Catalog | — |
| Consent Identity | — |
| Agent Card | — |
| Dry Run Mode | — |
| Delegated Identity | — |
| Protected Resource Metadata | — |
| Dynamic Client Registration | — |
| Agentic Commerce | — |
| Pagination Ratio | paginated |
| Operation Distinctiveness | distinct |

**Regulatory alignment 44.2** — Telecommunications

The rubric is published at [github.com/api-evangelist/kin-score](https://github.com/api-evangelist/kin-score). The per-check breakdown behind these numbers — which checks were earned, partial or missed — along with score history and how this provider compares to its peers, is available at [apis.io/providers/adobe-campaign/](https://apis.io/providers/adobe-campaign/).

## How this profile is made

API Evangelist profiles a company's public API surface the way a developer would find it: the website, developer portal and documentation, the specifications it publishes, its public repositories, and its pricing, status and changelog pages. From that it derives the properties above — contracts split per API, workflows, schemas, collections, governance rules, plans and rate limits — and scores them against the published [Kin Score rubric](https://github.com/api-evangelist/kin-score).

The artifacts are published on [APIs.io](https://apis.io), not in this repository. This repository is the public record for Adobe Campaign: the place to say something is wrong, missing or out of date, and to ask for a re-score or a removal.

## Open an issue

- **Something about this listing** — a wrong description, a missing API, a stale artifact or a question about the rating: [open an issue on this repository](https://github.com/api-evangelist/adobe-campaign/issues/new).
- **A new API, or one that is not in the catalog yet** — [submit it on APIs.io](https://apis.io/add/).
- **Anything else** — [the APIs.io inbox](https://github.com/api-search/inbox/issues/new) or [info@apievangelist.com](mailto:info@apievangelist.com).
