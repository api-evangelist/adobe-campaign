---
name: adobe-campaign-control-workflows-and-deliveries
description: Start, stop, resume and signal Adobe Campaign workflows, and submit or prepare-and-start a delivery, across both the Campaign REST surface and the Campaign Classic SOAP surface.
generated: '2026-08-13'
method: generated
source: openapi/adobe-campaign-workflows-api-openapi.yml, openapi/adobe-campaign-workflow-api-openapi.yml, openapi/adobe-campaign-delivery-api-openapi.yml, agentic-access/adobe-campaign-agentic-access.yml
api: Adobe Campaign Workflows API
operations:
  - controlWorkflow
  - workflowStart
  - workflowStop
  - workflowPostEvent
  - submitDelivery
  - deliveryPrepareAndStart
---

# Control Adobe Campaign workflows and deliveries

Workflows are the orchestration engine of Adobe Campaign. A delivery is a real
send. **Both of the delivery operations in this skill dispatch messages to real
recipients and are irreversible.** Do not automate them without a human approval
step.

## Two surfaces, two hosts, two auth models

| Surface | Host | Auth |
|---|---|---|
| Campaign REST | `https://mc.adobe.io/<ORGANIZATION>/campaign` | `Authorization: Bearer` **and** `X-Api-Key` |
| Campaign Classic SOAP | `https://{instance}.campaign.adobe.com/nl/jsp/soaprouter.jsp` | `X-Security-Token` header **and** `__sessiontoken` cookie |

Pick the surface your instance actually runs. The Classic operations below will
404 on `mc.adobe.io`.

## Workflows — REST

`controlWorkflow` — `POST /workflow/execution/{workflowID}/commands`

Commands are sent in the body rather than as distinct endpoints, so the same
operation covers start, pause, resume and stop. Responses: **200** on accept,
**400** on an unrecognised command, **404** when `{workflowID}` does not resolve.

## Workflows — Campaign Classic

- `workflowStart` — `POST /nl/jsp/soaprouter.jsp/xtk-workflow/Start`
- `workflowStop` — `POST /nl/jsp/soaprouter.jsp/xtk-workflow/Stop`
- `workflowPostEvent` — `POST /nl/jsp/soaprouter.jsp/xtk-workflow/PostEvent`

`workflowPostEvent` signals a waiting activity inside a running workflow — this is
how an external system hands control back to Campaign mid-flow.

Every Classic operation returns **200** or **500**. A 500 carries a SOAP Fault and
may be a permission or schema error that will never succeed on retry; read
`faultstring` before retrying.

## Deliveries — Campaign Classic

- `submitDelivery` — `POST /nl/jsp/soaprouter.jsp/nms-delivery/SubmitDelivery`
- `deliveryPrepareAndStart` — `POST /nl/jsp/soaprouter.jsp/nms-delivery/PrepareAndStart`

`deliveryPrepareAndStart` computes the target **and starts the send in one call**.
There is no dry-run parameter and no confirmation step. The safe pattern is to
validate the delivery in the Campaign Client Console with proofs and seed
addresses first, then call the API only to execute an already-reviewed delivery.

## Before you automate any of this

1. **No idempotency key exists.** A retried `submitDelivery` after a timeout can
   send the campaign twice.
2. **Credentials are broadly privileged.** Campaign API callers run in the
   administrator context and are excluded from the role context by default.
3. **Escalate on side effects.** Adobe's own published guidance for agents
   operating against Adobe products is that they must run under the authenticated
   user's permissions and should pause for a human where side effects, privileged
   data access or contractual interpretation are implied. Starting a delivery is
   all three.
4. Check `agentic-access/adobe-campaign-agentic-access.yml` for the per-operation
   consequence classification before wiring a tool.

## Errors

| Status | Meaning |
|---|---|
| 400 | Unrecognised command or malformed body (REST only) |
| 401 | Token or session expired |
| 404 | Workflow or delivery id does not resolve on this instance |
| 429 | API-layer TPS ceiling exceeded — back off with jitter |
| 500 | Server error (REST) / any failure at all (Classic SOAP Fault) |
