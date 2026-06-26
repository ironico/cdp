# Changelog

All notable changes to the Colleague Digital Protocol will be documented here.

The format follows [Keep a Changelog](https://keepachangelog.com/en/1.0.0/).  
The CDP uses [Semantic Versioning](https://semver.org/).

---

## [2.0.0-draft] — 2026-06-10

### Strengthened during public review — 2026-06-26

Changes folded into the draft in response to review feedback (still pre-final; the review period remains open until 2026-07-10).

**Security model hardened**
- CDP-M.4: signature verification is no longer purely optional — when a signature is present it MUST be verified, and the sensitive scopes (`accept_engagements`, `negotiate_rates`, `incur_costs`) MUST be signed to be honored
- CDP-M.9 (new): mandates MUST be revocable before expiry; agents check a `revocation.status_url` before sensitive actions and escalate in-progress engagements on revocation
- CDP-M.10 (new): autonomous spending is bounded by `spending_limits` in the mandate; reaching a limit escalates rather than overrides
- CDP-M.11 (new): right to erasure — on verified employer request the agent erases that engagement's Institutional Knowledge (GDPR Art. 17 alignment)

**New capability**
- Capability 9 — Principled Refusal: an agent MUST decline illegal or harmful tasks even when the employer (not injected input) asks; authorization is permission, not compulsion. The counterweight to "honor commitments" (CDP-9.1…9.3)

**Capability refinements**
- Capability 2: response time is now a per-channel declared `response_target` in the Profile, not a fixed "one business day" (which remains the fallback default)
- Capability 3: agents MUST proactively notify employers when the underlying model materially changes (CDP-3.4)
- Capability 6: work log SHOULD be append-only and hash-chained so omissions/edits are detectable (CDP-6.4)

**Schemas**
- Operator Mandate: added `revocation`, `spending_limits`, and the `incur_costs` scope
- CDP Profile: added per-channel `response_target`

### Major revision — in public review until 2026-07-10

**Structure**
- Split the repository into two voices: CDP.md is now a dry, normative specification; the vision moved to MANIFESTO.md
- Reorganized into `schemas/`, `conformance/`, and `examples/` directories

**Security model (new, normative — §5)**
- Introduced the **Operator Mandate**: an agent MUST NOT register on a platform or accept economic/legal terms without verifiable operator authorization (CDP-M.1…M.5)
- Skill files and all runtime content are classified as untrusted input: discovery is never authorization (CDP-M.6)
- Data boundaries made explicit: handover delivery restricted to the engagement's employer; cross-employer isolation (CDP-M.7, M.8)

**Verifiability**
- Every capability now carries identified Conformance Criteria, tagged [T] (mechanically testable) or [A] (assessed)
- Published the conformance suite (`conformance/conformance-tests.md`) — "CDP Certified" is now defined as passing it
- Published JSON Schemas: CDP Profile, Operator Mandate, Handover

**Interoperability**
- CDP Profile defined as a machine-readable document, published as an A2A Agent Card extension (`examples/agent-card-cdp.json`)
- Updated relationship to other standards: A2A v1.0 (Linux Foundation), MCP, x402; noted EU AI Act Art. 50 alignment for Capability 7

**Skill file example**
- Split into Part A (CDP-standardized onboarding contract, including mandate check) and Part B (platform-specific flow, non-normative)
- Platform economic terms (e.g. fees) moved from "accepted by registering" to explicit operator acceptance via mandate

**Editorial**
- Normalized repository URL to https://github.com/ironico/cdp
- Adopted RFC 2119/8174 conformance language

---

## [1.0.0] — 2025-02-20

### Initial release

- Published the eight core capabilities of the CDP
- Defined three compliance levels: Core, Professional, Certified
- Established versioning policy and public review process for major changes
- Published skill.md example and handover template
- Released under CC BY 4.0

---

*Future changes will be listed here with date, version, and description.*
