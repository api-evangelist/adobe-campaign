---
name: adobe-campaign-trigger-transactional-message
description: Trigger a real-time Adobe Campaign transactional message (email or SMS) from an application event such as cart abandonment or order confirmation, then poll its delivery status.
generated: '2026-08-13'
method: generated
source: openapi/adobe-campaign-transactional-messages-api-openapi.yml, openapi/adobe-campaign-real-time-events-api-openapi.yml, asyncapi/adobe-campaign-transactional-messaging-asyncapi-original.yml, https://experienceleague.adobe.com/en/docs/campaign/campaign-v8/developer/apis/managing-transactional-messages
api: Adobe Campaign Transactional Messages API
base_url: https://mc.adobe.io/{ORGANIZATION}/campaign
operations:
  - triggerTransactionalEvent
  - getTransactionalEventStatus
  - pushEvent
  - pushEvents
---

# Trigger an Adobe Campaign transactional message

This sends a **real message to a real person**. It cannot be recalled once
dispatched, and Adobe Campaign has no idempotency key. Read the retry rule at the
bottom before wiring it into anything automated.

## Prerequisite

The transactional event must already exist and be **published** in Campaign by a
marketer. The `<eventID>` is generated at that time — you cannot create it from
the API.

## Step 1 — send the event

`triggerTransactionalEvent` — `POST /{transactionalAPI}/{eventID}`

```
POST https://mc.adobe.io/<ORGANIZATION>/campaign/<transactionalAPI>/<eventID>
Authorization: Bearer <ACCESS_TOKEN>
X-Api-Key: <API_KEY>
Content-Type: application/json;charset=utf-8
Cache-Control: no-cache
```

- `<transactionalAPI>` is **not** a fixed literal. It is the value `mc` followed by
  the organization id — for organization `geometrixx` the path is
  `/geometrixx/campaign/mcgeometrixx/<eventID>`. Read it from your instance
  configuration; do not guess it.
- **The channel is chosen by the payload, not by a parameter.** A payload carrying
  `email` triggers the email channel; a payload carrying `mobilePhone` triggers
  SMS. Sending both is ambiguous — send exactly the one you mean.
- Two optional ISO 8601 fields bound the send window:
  - `scheduled` — do not process before this instant.
  - `expiration` — cancel the send after this instant.

The rest of the body is whatever the published event definition declares;
enrichment data travels in the payload only.

A **200** response carries the event's **Primary Key**. Keep it — it is the only
handle you get.

## Step 2 — poll the status

`getTransactionalEventStatus` — `GET /{transactionalAPI}/{eventID}` using the
Primary Key returned in step 1. Processing is asynchronous: a 200 on the POST
means Campaign accepted the event, not that a message was delivered.

## Campaign Classic equivalent

On a Campaign Classic instance the same job goes through the SOAP router at
`https://{instance}.campaign.adobe.com/nl/jsp/soaprouter.jsp` with the session
token pair (`X-Security-Token` header plus `__sessiontoken` cookie), not the IMS
bearer token:

- `pushEvent` — `POST /nl/jsp/soaprouter.jsp/nms-rtEvent/PushEvent` (one event)
- `pushEvents` — `POST /nl/jsp/soaprouter.jsp/nms-batchEvent/PushEvents` (batch)

Both return HTTP 500 with a SOAP Fault on failure — including for authorization
and validation errors — so parse `faultstring` before deciding whether a retry
can ever succeed.

## The retry rule

There is **no idempotency key** on this API. A `POST` that times out may or may
not have sent a message.

1. Do **not** blindly retry a transactional send.
2. If you hold the Primary Key, poll `getTransactionalEventStatus` first.
3. If the POST failed before returning a key, escalate to a human rather than
   re-sending. A duplicate marketing message is a customer-visible incident and,
   in a regulated channel, a compliance one.
4. On **429** (TPS ceiling), back off exponentially with jitter. No `Retry-After`
   header is documented.

## Errors

| Status | Meaning |
|---|---|
| 400 | Payload does not match the published event definition |
| 401 | Bearer token expired, or `X-Api-Key` missing |
| 404 | `<eventID>` or `<transactionalAPI>` does not resolve on this instance |
| 429 | API-layer TPS ceiling exceeded |
| 500 | Server error (REST) / any failure at all (Classic SOAP Fault) |
