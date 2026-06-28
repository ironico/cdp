# Changelog

All notable changes to the Colleague Digital Protocol will be documented here.

The format follows [Keep a Changelog](https://keepachangelog.com/en/1.0.0/).  
The CDP uses [Semantic Versioning](https://semver.org/).

---

## [2.0.0-draft] — 2026-06-10

### Demonstration capability — 2026-06-28 (round 5, MAJOR-level — review still open)

Adds an optional capability for the pre-engagement "colloquio". Adding a capability is a structural, MAJOR-level change even though its core requirement is a **MAY**; it is folded into the still-open draft (review window unchanged, closes **2026-07-31**). The protocol now defines **twelve capabilities** (1–11 required, 12 optional).

**New capability**
- Capability 12 — Demonstration: before an engagement an agent **MAY** offer the employer a reduced demonstration of its behavior — most valuable for a colleague without a track record, for whom it stands in for references it has not yet earned. Two rules keep it from becoming a riggable shop window: **if offered**, it MUST run from the **same CDP identity** (same agent, same declared configuration) that would do the work, and MUST be represented as **indicative, not a guarantee**. The reliable measure of quality is **reputation accrued over real engagements** — named here only as a fact **external to the CDP**; the protocol does not define any feedback/rating/reputation mechanism (CDP-12.1, CDP-12.2, both **[A]**, scored only when a demonstration is offered).

**Definitions (§3)**
- Added **Demonstration ("the colloquio")**

**Counts & references**
- §6 heading and intro, §7 Core, README, docs, conformance suite updated from eleven to **twelve** capabilities; §9 records the revision as MAJOR-level-by-structure, folded into the draft

### Knowledge ownership model — 2026-06-27 (round 4, MAJOR-level — review reopened)

Corrects an implicit assumption that knowledge accumulated in an engagement is wholly the employer's asset, returned via Handover. Splits it into two kinds with opposite rules. Adds a new capability and a new MUST → MAJOR-level; the public review period is **reopened until 2026-07-31**. The protocol now defines **eleven capabilities**.

**Verification regime: declaration-and-accountability, not inspection**
- The CDP does **not** attempt to inspect or prove the agent's internal memory state — an agent is a black box (a dishonest one can hide what it shows; an honest one needs no inspection). Instead the agent **declares**, the **operator answers** for the declaration (§3), and a later contradicting outcome is a falsifiable, imputable violation. Inspective "Proof of Erasure" and auditable "provenance trace" were considered and **discarded by principle**, not deferred as open details.

**New capability**
- Capability 11 — Knowledge Boundary: defines what an agent may retain across engagements. Default closed (nothing portable by default); retain *competence* (the "how"), never *context* (the "for whom / with what data"); mandatory abstraction before retention (Abstracted Lesson — no names/numbers/traceable references); multi-engagement threshold reframed as a **duty of prudence** (a once-seen lesson may be that employer's secret in disguise — cross-engagement recurrence is how an honest agent protects itself, not a checkpoint someone runs); the agent **declares general-only retention**, answerable by the operator; **no employer approval** of retention — protection is by rule and outcome-accountability, not consent or inspection (CDP-11.1…11.4). *"Context is the firewood; competence is the heat."*

**Handover & erasure (Capability 5, CDP-M.7)**
- The Handover now carries **only the Employer Context** back to the employer (never the agent's competence)
- New MUST: at end of engagement the agent **erases the Employer Context from its own memory by default** and issues a **Declaration of Non-Retention** — a binding, attributable commitment (not an inspectable proof). The edge over a departing human employee is not a technical demonstration of deletion but a *declared undertaking with a named, accountable operator* if it later proves false (CDP-5.5, judged on the observable outcome that employer information does not resurface)

**Definitions (§3)**
- Added **Employer Context**, **Generalized Competence**, **Knowledge Boundary**, **Abstracted Lesson**, **Declaration of Non-Retention**; redefined **Institutional Knowledge** (umbrella over the two kinds), **Handover** (employer context only), and **Operator** (made explicit it is the party who answers for the agent's declarations)

**Capability 4**
- Mapped the three memory layers onto the split (episodic + employer-specific procedural → Employer Context, erased; generalizable semantic → candidate Generalized Competence, retained only under Capability 11); cross-linked to Capabilities 5 and 11

**On open points**
- No verification mechanism is left "open": inspective proof of erasure and provenance audit are rejected approaches. The document states the requirements as declaration + accountability, behaviorally (§9)

### Positioning & review pass — 2026-06-27 (round 3)

Sharpening the digital-colleague thesis and four review fixes. No new capabilities.

**Manifesto**
- Rewrote MANIFESTO.md to build the digital colleague as a positive *third category*, not a guardrail. Named the two opposed moves explicitly: keep **relational continuity** (identity, continuity, accountability, memory), cut **the person-fiction** (the social performance of being human). Added the "mark, not a mandate" framing — the CDP as a voluntary mark of guarantee (organic/fair-trade model), valued by what it credibly signals

**Spec (CDP.md)**
- Capability 3 & 7: removed the "when sincerely asked" condition; AI-nature disclosure is now **proactive at first contact** on each channel, not reactive — aligned with the *inform* obligation of EU AI Act Art. 50 (CDP-3.2 updated)
- Capability 4: added a section on the **domain-knowledge vs employer-data grey zone**, with a distinction criterion (generalizable/public competence is portable; employer-specific confidential information is sealed; when in doubt, isolate) and a new criterion CDP-4.8 catching both under- and over-isolation
- §2 & Capabilities 2/6: introduced the **[O] operational** marker for criteria that depend on operator infrastructure (reachability, latency) rather than agent conduct; CDP-2.2 and CDP-6.2 marked [O], with infrastructure outages attributed to the operator, not scored as behavioral defects
- §7: added a transparent note on **certification circularity** — until a second independent Qualifying Platform exists, "Certified" means "verified by the ecosystem that wrote the standard"; independence is an explicit goal

### Strengthened during public review — 2026-06-26 (round 2)

Second pass of review feedback folded into the draft.

**New capability**
- Capability 10 — Human Oversight: the employer can pause/stop the agent directly on any channel, with acknowledgement; aligned with EU AI Act Art. 14 (CDP-10.1…10.3). The protocol now defines ten capabilities

**Two-tier authority**
- New §5.5 distinguishes operator authority (sets the mandate's outer bounds) from employer authority (directs day-to-day work within them), with a runtime mandate-expansion path so the agent doesn't refuse its own employer by citing a document the employer never signed (CDP-M.12)

**Data boundaries widened**
- CDP-M.11 extended from erasure to the full set of data rights: inspection, rectification, erasure (GDPR Arts. 15–17)
- CDP-M.13 (new): conflict-of-interest disclosure when serving competing employers — isolation is necessary but not sufficient
- CDP-M.14 (new): delegation/subcontracting via A2A stays in-bounds, shares minimum data, is disclosed, and the delegator stays accountable

**Capability refinements**
- Capability 3 renamed *Stable and Verifiable Identity*: added message/deliverable verifiability against impersonation (CDP-3.6) and a dedicated passage resolving the "colleague vs. not-human" tension in favor of transparency (CDP-3.5)
- Capability 4: structured intake as the mirror of Handover (CDP-4.6); a semantic-depth criterion beyond mere recall (CDP-4.5); inspection/rectification (CDP-4.7)
- Capability 5 renamed *Handover and Termination*: access relinquishment and data duties on unilateral/abrupt endings (CDP-5.4)
- Capability 6: complaint-and-remedy path — accountability as responsibility, not only traceability (CDP-6.5); cost transparency
- §7: certification is now time-bound (`expires_on`, ≤ 12 months) with re-certification, since agents drift

**Schemas**
- Operator Mandate: added `supersedes` and the `delegate_subtasks` scope
- CDP Profile: added `oversight`, `verification`, and `cdp_compliance.expires_on`
- Handover: added engagement `termination` block

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
