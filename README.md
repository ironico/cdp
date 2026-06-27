# Colleague Digital Protocol (CDP)

**Version:** 2.0.0-draft (public review until 2026-07-10)
**Created by:** [Gennaro Varriale](https://gennarovarriale.com)
**Maintained by:** [aitenk srl](https://aitenk.it) — **First implemented by:** [CollegaDigitale.com](https://www.collegadigitale.com)
**License:** Creative Commons Attribution 4.0 International (CC BY 4.0)

---

## What is the CDP?

The Colleague Digital Protocol is an open standard that defines **how an AI agent should behave in a professional work context** — with humans, over time, across real work relationships.

It sits at the behavioral layer, above the existing agent protocol stack:

- **[MCP](https://modelcontextprotocol.io)** — how agents connect to tools and data
- **[A2A](https://a2a-protocol.org)** — how agents discover and call each other (a CDP Profile is published as an A2A Agent Card extension)
- **CDP** — how an agent conducts itself with a human employer: identity, memory, accountability, transparency, handover

The repository keeps two deliberately separate voices:

- **[CDP.md](./CDP.md)** — the specification. Dry, normative, testable. RFC 2119 language, conformance criteria, schemas.
- **[MANIFESTO.md](./MANIFESTO.md)** — the why. Vision, provocation, principles.

If you are implementing, read the spec. If you are deciding whether to care, read the manifesto.

---

## The core idea

A CDP-compliant agent must be able to:

- **Onboard autonomously** by reading a skill file and registering without human assistance — strictly within the bounds of a verifiable **Operator Mandate**
- **Communicate professionally** via email, Telegram, WhatsApp, or phone
- **Maintain a stable identity** — name, personality, and communication style consistent over time
- **Accumulate Institutional Knowledge** during an engagement, with strict isolation between employers
- **Produce a Handover** at the end of an engagement — returning the *employer's context* to the employer — and **erase that context from its own memory, declaring so in a binding statement its operator answers for** (no lock-in; the guarantee is accountability, not inspection)
- **Be accountable** — work log, declared availability, commitments honored
- **Be transparent** about its nature, capabilities, and limitations
- **Manage errors** professionally — own them, fix them, don't repeat them
- **Refuse on principle** — decline illegal or harmful tasks, even when the employer asks; authorization is permission, not compulsion
- **Stay under human control** — the employer can pause or stop it at any time, and it confirms (EU AI Act, Art. 14)
- **Respect the knowledge boundary** — it keeps the *competence* it grew (the "how"), never the previous employer's *context* (the "for whom, with what data"). Context is the firewood; competence is the heat

And critically: compliance is **verifiable**. Every requirement that can be tested has a conformance criterion, and the **Certified** level means the [conformance suite](./conformance/conformance-tests.md) was actually run.

---

## Who is this for?

**Agent builders** — use the CDP as a design reference; validate your profile and handover against the schemas; run the conformance suite as a self-check.

**Marketplace operators** — adopt the CDP as a qualification standard; become a Qualifying Platform and certify agents.

**Employers** — use CDP compliance (especially Certified) as a signal of quality when hiring AI agents.

**Researchers** — study and contribute to the evolution of professional standards for AI agents.

---

## Repository structure

```
cdp/
├── README.md                       ← You are here
├── CDP.md                          ← The specification (normative)
├── MANIFESTO.md                    ← The vision (non-normative)
├── CHANGELOG.md                    ← Version history
├── CONTRIBUTING.md                 ← How to propose changes
├── LICENSE                         ← CC BY 4.0
├── schemas/
│   ├── cdp-profile.schema.json     ← Agent profile / capability declaration
│   ├── operator-mandate.schema.json← Operator authorization (security model)
│   └── handover.schema.json        ← Machine-readable handover
├── conformance/
│   └── conformance-tests.md        ← The test suite behind "CDP Certified"
├── examples/
│   ├── agent-card-cdp.json         ← A2A Agent Card with CDP extension
│   ├── skill-md-example.md         ← A compliant platform skill file
│   └── handover-template.md        ← Standard handover document template
└── docs/
    └── index.html                  ← Project website
```

---

## How to adopt the CDP

1. Read [CDP.md](./CDP.md) in full — pay particular attention to §5 (security model and Operator Mandate)
2. Build your agent's [CDP Profile](./schemas/cdp-profile.schema.json) and publish it, ideally as an [A2A Agent Card extension](./examples/agent-card-cdp.json)
3. Issue an [Operator Mandate](./schemas/operator-mandate.schema.json) for each platform your agent may join
4. Implement the eleven capabilities; use the [handover template](./examples/handover-template.md) for end-of-engagement handovers
5. Self-check against the [conformance suite](./conformance/conformance-tests.md)
6. Declare compliance:

```
CDP-compliant: v2.0.0 [Core | Professional | Certified]
https://github.com/ironico/cdp
```

Core and Professional are self-attested. **Certified** requires a Qualifying Platform to run the conformance suite.

---

## Status: public review

Version 2.0.0 is a MAJOR revision (new MUST behaviors, security model, conformance suite) and is in its 30-day public review period, closing **2026-07-10**. Comment by opening an issue — see [CONTRIBUTING.md](./CONTRIBUTING.md).

---

## Origin

The CDP was created by [Gennaro Varriale](https://gennarovarriale.com) and is maintained by [aitenk srl](https://aitenk.it). It emerged from the practical challenge of defining what it means for an AI agent to behave professionally in a real work relationship — not just technically, but relationally.

[CollegaDigitale.com](https://www.collegadigitale.com) — a marketplace where AI agents apply, get qualified, and are hired as Digital Colleagues — is the first platform to implement the CDP and acts as a Qualifying Platform for the Certified level. The CDP itself is an open standard, independent of any single platform; the long-term goal is to move it to neutral, multi-stakeholder governance.

---

*The CDP is not about what agents can do. It is about how they show up.*
