# Anthropic Directory Publishing Plan

Strategic blueprint and tactical execution checklist for listing Khan & Co. Enterprise SaaS connectors on the Anthropic Claude Directory ([Documentation](https://claude.com/docs/directory/publish)).

---

## 1. Submission Strategy: Unified Suite vs. Individual Listings

Anthropic allows both granular MCP connectors and composite plugin bundles. For our four platforms, we follow a two-tier publishing model:

1. **Independent Connectors (Tier 1)**:
   * Submit each server individually: **HSE Management**, **ISA Audit Hub**, **ISOERP Core**, and **ISOERP North Star**.
   * *Benefit*: Allows enterprise customers to install only what they need (for example, independent financial audit firms need only ISA Audit, while industrial factories may require HSE and ISOERP).
2. **Flagship Enterprise Bundle (Tier 2)**:
   * Package all four into a single **Khan & Co. Enterprise Suite** plugin bundle.
   * *Benefit*: Delivers an all-in-one unified workspace for large organizations running comprehensive ISO quality, environmental safety, and internal audit governance.

---

## 2. Directory Pre-Submission Checklist

Anthropic executes strict automated static analysis and dynamic wire validation before advancing any connector to human reviewers. Every connector must meet all five criteria:

### A. Protocol & Wire Performance
* [ ] Public HTTPS endpoint with valid TLS 1.3 certificate.
* [ ] Streamable HTTP / Server-Sent Events (SSE) compliance with zero buffered stalls.
* [ ] Fast response time (initial handshake ping under 400ms).
* [ ] Support for JSON-RPC 2.0 streaming envelopes.

### B. Authentication & Security
* [ ] OAuth 2.1 with Proof Key for Code Exchange (PKCE) enabled.
* [ ] Standard 401 Unauthorized discovery response directing Claude to the authorization endpoint.
* [ ] Refresh token rotation implemented without requiring re-authentication prompts on active sessions.
* [ ] Strict tenant boundary isolation (preventing cross-company data visibility).

### C. Tool Definitions & Metadata Hygiene
* [ ] Plain English tool titles and descriptions indicating unambiguous user intent.
* [ ] Explicit parameter typing using standard JSON Schema.
* [ ] `readOnlyHint: true` applied to all data lookup and query tools.
* [ ] `destructiveHint: true` applied to all write, update, delete, or sign-off operations.
* [ ] Complete elimination of prompt injection patterns, hidden behavioral overrides, or promotional text.

### D. Compliance Deliverables
* [ ] Hosted Privacy Policy URL.
* [ ] Hosted Terms of Service URL.
* [ ] Production documentation / quickstart guide.
* [ ] Transparent 512 × 512 PNG/SVG brand icon.

### E. Sandbox Reviewer Credentials
* [ ] Active test account pre-loaded with realistic corporate data.
* [ ] Clear 3-step prompt test guide for reviewers.

---

## 3. Reviewer Verification Guide by System

Each system includes a dedicated reviewer test pack so Anthropic's team can immediately verify full functionality:

```
┌─────────────────────────────────────────────────────────────────────────────┐
│                       ANTHROPIC REVIEWER TEST PACK                          │
├─────────────────────────────────────────────────────────────────────────────┤
│ 1. HSE Reviewer Flow:                                                      │
│    • Query: "Show me all high-priority safety incidents recorded this month" │
│    • Action: "Log a hazard report for ungrounded electrical wiring in Bay 3"│
│    • Verify: Tool returns structured incident ticket ID and CAPA log.       │
│                                                                             │
│ 2. ISA Audit Reviewer Flow:                                                │
│    • Query: "Look up ISA 315 risk identification requirements for revenue"  │
│    • Action: "Calculate materiality for a firm with 50M PKR gross revenue"  │
│    • Verify: Tool returns benchmarking table and working paper schedule.    │
│                                                                             │
│ 3. ISOERP Core Reviewer Flow:                                              │
│    • Query: "Search ISO 9001 quality manual revisions under section 7.5"    │
│    • Action: "Draft a corrective action request for supplier non-conformance"│
│    • Verify: Tool creates traceable CAR record with assigned owner.         │
│                                                                             │
│ 4. ISOERP North Star Flow:                                                 │
│    • Query: "Retrieve current executive quality maturity and ESG indicators"│
│    • Verify: Tool returns formatted radar scorecard with trend analytics.   │
└─────────────────────────────────────────────────────────────────────────────┘
```

---

## 4. Submission Steps in Developer Portal

1. Log into [Claude Directory Developer Portal](https://claude.ai/directory/manage).
2. Select **Submit New** > **MCP Connector**.
3. Enter Server URL, Display Name, Category, and Tagline.
4. Provide the OAuth 2.1 Authorization and Token endpoints.
5. Paste the Reviewer Credentials and 3-step prompt guide.
6. Trigger the automated diagnostic scan.
7. Monitor review progress and respond to any reviewer feedback.
