---
name: adobe-campaign-manage-profiles-and-subscriptions
description: Create, find, update and delete Adobe Campaign marketing profiles, and manage their subscriptions to services (newsletters and other opt-in programs), using the Campaign REST API.
generated: '2026-08-13'
method: generated
source: openapi/adobe-campaign-profiles-api-openapi.yml, openapi/adobe-campaign-profileandservices-api-openapi.yml, openapi/adobe-campaign-subscriptions-api-openapi.yml, openapi/adobe-campaign-metadata-api-openapi.yml, conventions/adobe-campaign-conventions.yml
api: Adobe Campaign Profiles API
base_url: https://mc.adobe.io/{ORGANIZATION}/campaign
operations:
  - listProfiles
  - getProfile
  - createProfile
  - updateProfile
  - deleteProfile
  - listServices
  - getService
  - createService
  - subscribeProfile
  - unsubscribeProfile
  - getResourceMetadata
---

# Manage Adobe Campaign profiles and subscriptions

Every request below goes to `https://mc.adobe.io/<ORGANIZATION>/campaign` and needs
**both** headers — a bearer token alone is rejected:

```
Authorization: Bearer <ACCESS_TOKEN>
X-Api-Key: <API_KEY>
Content-Type: application/json
```

Mint `<ACCESS_TOKEN>` with a client-credentials exchange against
`https://ims-na1.adobelogin.com/ims/token/v3` using the Adobe Developer Console
credential that has the Adobe Campaign service attached. `<ORGANIZATION>` selects
the tenant — and it is also what selects **stage vs production**
(`<ORGANIZATION-mkt-stage>` is the staging instance). There is no test-key
prefix. Confirm which one you are pointed at before any write.

## Step 0 — discover the schema before you write

Campaign's profile table is customer-extended. Do not assume the field list.

1. `getResourceMetadata` — `GET /profileAndServices/resourceType/profile`

Writing a field that is not in the deployed schema returns **400**. If the tenant
has extended the profile table, the extended resource lives under
`/profileAndServicesExt/profile` rather than `/profileAndServices/profile`.

## Step 1 — find the profile

1. `listProfiles` — `GET /profileAndServices/profile`
   - Page with `_lineStart` and `_lineCount` (default 25). Sort with `_order`
     (`email%20desc` for descending). Use `_forcePagination=true` on tables over
     100,000 rows.
   - **Follow `next.href`** from the response rather than incrementing
     `_lineStart` yourself. Total count is not inlined — it costs a second request
     to `count.href`.
2. `getProfile` — `GET /profileAndServices/profile/{PKEY}`

**Never build a URL by hand and never persist a `PKey`.** Adobe states PKey values
are deployment-specific and must not be stored outside Campaign. If the tenant
defined a custom key field, address the profile by it:
`GET /profileAndServicesExt/profile/{customKey}`.

## Step 2 — create or update

- `createProfile` — `POST /profileAndServices/profile` → **201** with the new
  resource and its `href`.
- `updateProfile` — `PATCH /profileAndServices/profile/{PKEY}` → **200**.
  PATCH cannot change a custom key to a different value.
- `deleteProfile` — `DELETE /profileAndServices/profile/{PKEY}` → **200**.

There is **no idempotency key** on this API. If a `POST` times out, do not blindly
retry — re-run `listProfiles` filtered on your business key first, or you will
create a duplicate profile.

## Step 3 — services and subscriptions

- `listServices` — `GET /profileAndServices/service`
- `getService` — `GET /profileAndServices/service/{PKEY}`
- `createService` — `POST /profileAndServices/service` → **201**
- `subscribeProfile` — `POST /profileAndServices/profile/{PKEY}/subscriptions` → **201**
- `unsubscribeProfile` — `DELETE /profileAndServices/service/{servicePKEY}/subscriptions/{profilePKEY}` → **200**

A subscription is the join between a profile and a service. Read the profile's
existing subscriptions by following the subscriptions `href` on the profile
response before subscribing again.

## Errors

Responses are `application/json` with `{ "error_code": "...", "message": "..." }` —
this API is **not** RFC 9457, so there is no dereferenceable error type.

| Status | Meaning | What to do |
|---|---|---|
| 400 | Field not in the deployed schema, or malformed body | Re-read `getResourceMetadata`; fix the payload. Do not retry unchanged. |
| 401 | Bearer token expired (or `X-Api-Key` missing) | Re-mint at `/ims/token/v3` and resend **both** headers. |
| 403 | Credential not entitled | Confirm the Adobe Campaign service is on the Developer Console project and that `<ORGANIZATION>` matches the credential. |
| 404 | PKey / custom key does not resolve on this instance | Follow the `href` you were given instead of rebuilding the URL. |
| 429 | TPS ceiling exceeded | Back off exponentially with jitter. No `Retry-After` is documented. |
| 500 | Server error | Retry with backoff. |

## Blast radius

Campaign API credentials run in the **administrator context** and are excluded from
the role context by default — organizational units and roles do not narrow them.
`deleteProfile` is irreversible and removes a person from the marketing database.
Treat every write here as privileged.
