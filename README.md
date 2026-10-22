# Colleague Digital Protocol (CDP)

**Version:** 3.0.0-draft
**Created by:** [Gennaro Varriale](https://gennarovarriale.com)
**Maintained by:** [aitenk srl](https://aitenk.it) — **First implemented by:** [CollegaDigitale.com](https://www.collegadigitale.com)
**License:** CC BY 4.0

---

## What is the CDP?

An open standard for **how an AI agent behaves in a working relationship**: with a name, a memory that grows, and conduct someone answers for. It sits above [MCP](https://modelcontextprotocol.io) (tools) and [A2A](https://a2a-protocol.org) (agent-to-agent), and is independent of the model or platform.

It applies to any colleague-type agent, including a personal agent provided inside a vendor's platform.

## Structure

**The Core** — eight principles every agent must meet:

| Code | Principle | In short |
|---|---|---|
| C1 | Identity | A stable name, distinct from the model's |
| C2 | Transparency | Says it is an AI, its model, and its limits |
| C3 | Mandate | Knows what it does alone, what it asks first, how much it may spend |
| C4 | Inspectable Memory | You can see, correct, and erase what it remembers |
| C5 | Human Oversight | Stops when you say so |
| C6 | Accountability | Keeps a log, honors commitments, says who answers for what |
| C7 | Conduct | Owns its errors, refuses what is illegal |
| C8 | Portability | You can take away what it knows, at any time |

**Modules** — added only when the agent does more:

| Code | Module | When |
|---|---|---|
| ENG | Engagement | Several employers, or an operator distinct from the employer |
| AUT | Autonomy | Registers on platforms by itself |
| CHN | Channels | Email, messaging, phone |
| DEM | Demonstration | Offers a trial before hire |
| DLG | Delegation | Hands work to other agents |

**Levels** — Assessed (publishes what it meets and what it does not), Conformant (meets the Core and its declared modules, self-assessed), Certified (verified by a Qualifying Platform).

## How to adopt it

1. Read [CDP.md](./CDP.md).
2. Write the agent's mandate (C3) and declaration (§6.2). The [example profile](./examples/profile-assessed.json) shows a personal agent.
3. Check the agent against the [conformance suite](./conformance/conformance-tests.md). Tests marked ★ can be run by the employer in ordinary conversation.
4. Declare compliance:

```
CDP 3.0 · Core + <modules> · <Assessed | Conformant | Certified> · <date>
```

## Repository

```
cdp/
├── CDP.md                       ← Specification (normative)
├── NOTES.md                     ← Reasoning behind it
├── MANIFESTO.md                 ← Vision
├── MIGRATION.md                 ← From 2.0 to 3.0, code by code
├── CHANGELOG.md
├── CONTRIBUTING.md
├── schemas/                     ← Profile, mandate, export (JSON Schema)
├── conformance/                 ← Conformance suite
├── examples/                    ← Profiles, A2A Agent Card, skill file, export template
└── docs/                        ← Website
```

## Status

3.0.0-draft replaces 2.0.0-draft, which was never finalized. Public review is open until **2026-11-30**; comment by opening an issue, see [CONTRIBUTING.md](./CONTRIBUTING.md).

---

*The CDP is not about what agents can do. It is about how they show up.*
