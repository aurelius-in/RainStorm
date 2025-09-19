# RainStorm Engine APIs (v1)

Minimal, swappable surfaces across the Rain‑suite. All POSTs accept `Idempotency-Key`; all calls carry `X-Trace-Id` and return signed `receipt_id` when applicable.

## RainScout
- `POST /signals/search {query,sources,filters}` → `{opportunities[], trace_id}`
- `POST /outreach/sequence {audience,template,throttle,consent}` → `{sequence_id}`
- `GET /outreach/:id/results` → `{sent,opens,replies,bookings}`
- `GET /report/:trace_id` → `{ranked_opportunities, evidence_pack_url}`

## RainVibe
- `POST /build/scaffold {spec}` → `{job_id}`
- `POST /build/patch {diffs[]}` → `{job_id}`
- `GET /build/job/:id` → `{status, preview_url, tests}`

## RainShip
- `POST /pricing/suggest {inputs,constraints}` → `{plans[], guardrail_hits[], receipt_id}`
- `POST /release/prepare {version, artifacts}` → `{release_id, requires_hitl, diff_summary, receipt_id}`
- `POST /release/promote {release_id, env, canary, slo}` → `202 {job_id}`
- `POST /release/rollback {release_id, reason}` → `{status, receipt_id}`

## RainWave
- `POST /brand/kit {logo_url, colors[], fonts[]}` → `{tokens}`
- `POST /assets/generate {campaign, variants[]}` → `{job_id}`
- `POST /copy/generate {campaign, tone, variants[]}` → `{copy}`
- `POST /campaign/plan {calendar[]}` → `{campaign_id}`
- `POST /campaign/schedule {campaign_id}` → `{status}`

## RainDock
- `POST /provision {account, plan, entitlements}` → `{account_id, api_key, receipt_id}`
- `POST /keys/rotate {account_id}` → `{api_key, receipt_id}`
- `POST /checklists/assign {account_id, template_id}` → `{checklist_id}`
- `POST /events {account_id, event, props}` → `202`
- `GET /activation/:account_id` → `{status, ttfv_minutes, receipt_id}`

## RainPulse
- `POST /events` → usage events (OTel/Segment gateway)
- `GET /metrics/health?account_id=...` → `{score, risks[], expansion[]}`
- Webhooks: `churn.signal`, `expansion.signal`, `slo.breach`

## RainBeacon
- `POST /policy/evaluate {action, inputs}` → `{allow|hitl|block, reasons[]}`
- `GET /audit/evidence/:receipt_id` → zipped receipts + artifacts

## RainRef
- `POST /tickets/ingest {source,id,subject,body,user_id}` → `{ticket_id}`
- `POST /answer/draft {ticket_id}` → `{reply, sources[], confidence}`
- `POST /action/execute {ticket_id, action, params}` → `{status, receipt_id}`
- `POST /kb/sync {docs[]}` → `{status}`

