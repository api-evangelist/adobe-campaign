---
name: adobe-campaign-privacy-and-data-subject-requests
description: File a GDPR/CCPA data subject access or deletion request against Adobe Campaign, and read a profile's marketing history to answer what was sent to a person and how they reacted.
generated: '2026-08-13'
method: generated
source: openapi/adobe-campaign-privacy-api-openapi.yml, openapi/adobe-campaign-marketing-history-api-openapi.yml, openapi/adobe-campaign-profiles-api-openapi.yml, data-model/adobe-campaign-data-model.yml
api: Adobe Campaign Privacy API
base_url: https://mc.adobe.io/{ORGANIZATION}/campaign
operations:
  - createPrivacyRequest
  - getMarketingHistory
  - getProfile
  - deleteProfile
---

# Adobe Campaign privacy and data subject requests

Adobe Campaign exposes a dedicated privacy endpoint for data subject rights. Use
it rather than deleting profile rows directly — the privacy tool is what Campaign
audits.

## Step 1 — resolve the person

`getProfile` — `GET /profileAndServices/profile/{PKEY}` or, where the tenant
defined one, by custom key: `GET /profileAndServicesExt/profile/{customKey}`.

Do not persist the returned `PKey` in your own systems; Adobe states it is
deployment-specific and must not be stored externally. Key your records on your
own business identifier.

## Step 2 — answer "what did you send me?"

`getMarketingHistory` — `GET /profileAndServices/history/{PKEY}` → **200**

Returns the delivery and tracking log for that profile: messages sent across all
channels, plus reactions (opens, clicks).

**This history is not permanent.** Delivery logs (`NmsBroadLogRcp`) and tracking
logs (`NmsTrackingLogRcp`) are purged on a configurable retention schedule, and
Adobe recommends exporting them regularly. If you are answering a subject access
request that reaches further back than the retention window, the API cannot
produce it — say so rather than reporting an empty history as "nothing was sent".

## Step 3 — file the request

`createPrivacyRequest` — `POST /privacy/privacyTool` → **201**

Responses: **400** on a malformed request, **401** on an expired token, **500** on
a server error.

## Do not substitute deleteProfile

`deleteProfile` (`DELETE /profileAndServices/profile/{PKEY}`) removes the row. It
is not the same act as a privacy request: it produces no privacy audit record and
does not reach the data the privacy tool is designed to reach. Use
`createPrivacyRequest` for a right-to-erasure, and `deleteProfile` only for
ordinary data hygiene.

## Blast radius

Campaign API credentials run in the administrator context and are excluded from
the role context by default, so nothing in the API narrows what a privacy caller
can see. Every operation in this skill touches personal data of an identified
person. Log the requester and the legal basis on your side; the API records
neither.

## Reference

- Campaign privacy documentation: https://experienceleague.adobe.com/en/docs/campaign/campaign-v8/privacy/privacy
- Adobe Privacy Policy: https://www.adobe.com/privacy/policy.html
