# RainStorm Studio UI

A React dashboard to observe and steer the loop with **minimal HITL**.

## Key Views
- **Loop Overview** — circular status with current node, trust level, pending approvals.
- **Demand** (RainScout) — top opportunities, reply/booked‑call metrics.
- **Build** (RainVibe) — patch sets, tests, preview URLs, security scans.
- **Ship** (RainShip) — changelogs, migrations, canary windows, approvals.
- **GTM** (RainWave) — brand kit, assets, copy, campaign calendar & sends.
- **Onboarding** (RainDock) — provisioning events, activation funnels, TTFV.
- **Health** (RainPulse) — SLOs, churn/expansion signals, playbooks.
- **Trust** (RainBeacon) — policies, receipts, risk scores, trust ramp.
- **Support** (RainRef) — inbox drafts, safe actions, help‑center drafts.

## HITL Gates
- Required for: release **promote** w/ risky diffs, price changes beyond guardrails, scaled outreach, sensitive support actions.  
- One‑click approvals with **receipt preview** and OPA decision reasons.

## Tracing & Audit
- Global `trace_id` drill‑down across apps.  
- Export **evidence packs** (zip) per action (release, price, outreach, support).

## Settings
- Connectors (Stripe, SendGrid, LinkedIn, Zendesk, HubSpot, Segment).  
- Webhooks & secrets; service JWTs; environment keys.
