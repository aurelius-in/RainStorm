# RainStorm Flows

## Suite Loop
```mermaid
flowchart LR
  classDef n fill:#eaf4ff,stroke-width:0,color:#000,font-weight:700;
  A([RainScout]):::n --> B([RainVibe]):::n --> C([RainShip]):::n --> D([RainWave]):::n --> E([RainDock]):::n --> F([RainPulse]):::n --> G([RainBeacon]):::n --> H([RainRef]):::n --> A
  linkStyle default stroke:#9aa0a6,stroke-width:2;
```

## Trust Ramp (levels)
- **T0:** all HITL
- **T1:** low‑risk auto; approvals for price/release/outreach
- **T2:** auto‑promote if canary green + scans clean; sample reviews
- **T3:** one QA check per loop; everything else by receipts

## Example Traces
- `discover → build → ship → wave → dock → pulse → beacon → ref → discover`

## Event Contract (shared)
All events include: `event`, `trace_id`, `causation_id`, `at`, `source`, optional `receipts[]`.
