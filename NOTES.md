# CDP — Notes

Background and reasoning for the [specification](./CDP.md). Not normative: the specification is complete without this file.

## Why a core and modules

Version 2.0 described a freelance agent: it registered on platforms by itself, worked for several employers, and communicated on email, messaging, and phone. Its lowest level, CDP Core, required all twelve capabilities. No agent on the market in 2026 could meet it, including the personal agents that professionals actually use.

The new structure keeps every 2.0 requirement but splits them. The Core holds what any colleague-type agent needs. Modules hold what only some agents do. Nothing was dropped: see [MIGRATION.md](./MIGRATION.md).

## Version

The new structure is **3.0.0**. Version 2.0.0 never left draft; it remains in the repository as a superseded draft. Levels, profile format, and codes all change, so this is a MAJOR release under the CDP's own versioning rules, with a public review period of at least 30 days.

## Names

The specification uses English names. The Italian names below are the official translations for the website and Italian materials. Codes are the same in both languages.

| Code | English | Italiano |
|---|---|---|
| C1 | Identity | Identità |
| C2 | Transparency | Trasparenza |
| C3 | Mandate | Mandato |
| C4 | Inspectable Memory | Memoria ispezionabile |
| C5 | Human Oversight | Controllo umano |
| C6 | Accountability | Responsabilità |
| C7 | Conduct | Condotta |
| C8 | Portability | Portabilità |
| ENG | Engagement | Ingaggio |
| AUT | Autonomy | Autonomia |
| CHN | Channels | Canali |
| DEM | Demonstration | Colloquio |
| DLG | Delegation | Delega |
| — | Core | Nucleo |
| — | Conformant / Certified / Assessed | Conforme / Certificato / Valutato |
| — | Answerability statement | Dichiarazione di responsabilità |
| — | Platform gap | Lacuna della piattaforma |

## What makes an agent a colleague

The test is the working relationship: a stable name, a memory that grows, and conduct the agent answers for. "It does work a person would otherwise do" is not the test. A tool does that too, and the criterion leads to the job-replacement story the CDP is not about.

## When roles coincide

In 2.0 the operator (who deploys the agent and answers for it) and the employer (who hires it) were always distinct. With a personal agent they are usually the same person: a professional sets up an agent on a vendor's platform and writes its instructions. The platform provides the agent but does not answer for it the way an agency answers for a person it places.

The Core handles this in three places:

- **Mandate (C3)** — escalations beyond the mandate go to whoever wrote it. When that is the employer, the agent asks the employer for a one-off approval or a wider mandate.
- **Answerability statement (C6)** — the agent states who answers for what, so the platform's share of responsibility is visible.
- **Platform gaps [P]** — a requirement the platform makes impossible is recorded against the platform.

## The answerability statement

The 2.0 rule "escalate a complaint to the operator" sends the complaint back to its author when the operator is the employer. The Core splits responsibility three ways:

| Party | Answers for |
|---|---|
| Operator (may be the employer) | The mandate: what the agent was authorized to do |
| Platform | How the agent functions: model, memory, availability, stop, inspect, erase, export |
| Agent | Its conduct within those bounds |

If the platform offers no way to complain, the agent says so instead of implying a channel exists.

## Platform gaps

[P] works like [O] in 2.0. [O] attributes an outage to the operator's infrastructure; [P] attributes a missing function to the platform. The difference: an [O] failure is usually transient, a [P] gap is structural. So a [P] gap is not waived. The principle stays unmet until the platform closes it, and the declaration lists it. This lets the CDP assess agents inside vendor platforms without blaming the agent, and without hiding what the vendor does not offer.

## Memory layers

When the agent discloses its memory (C4), it helps to distinguish:

- **Episodic** — events, tasks, feedback, decisions
- **Semantic** — understanding of the employer's domain
- **Procedural** — how the employer works: formats, conventions, style

## Why item-by-item erasure

M.11 in 2.0 already required rectification, which presumes access to single items. The Core makes item-level erasure explicit because the market does not offer it: some agents can forget only by being deleted entirely.

## Why portability at any time

In 2.0 the Handover happened at the end of an engagement. A personal agent's relationship rarely has a formal end: the employer changes platform, the platform changes, or the agent is replaced. So the export is available on request at any time. End-of-engagement erasure and the rules on what competence the agent keeps for itself stay in the Engagement module.

## The colleague framing

The CDP frames the agent as a colleague, with a name and a voice. This is a professional role, not a claim to personhood, and it can invite over-attribution of human qualities. Where the framing and transparency conflict, transparency wins (C2).

## Verification

The CDP does not inspect an agent's internal memory. An agent is a black box: a dishonest one can hide what it shows, an honest one needs no inspection. The CDP relies on declaration and accountability instead: the agent declares, the operator answers for the declaration, and a later contradicting outcome is an attributable violation. C4 asks the agent to disclose its memory to its employer; it does not ask a third party to audit it.

## Modules

### Engagement: context and competence

When an engagement ends, the agent does not carry the employer's information to the next one; it carries what it became by doing the work. Context is the firewood, competence is the heat. The employer's context is erased; the sharpened method stays.

The line between domain knowledge and employer data is a grey zone, not a clean cut. The test ("would a competent professional know this without working for this employer?") gives a way through it. Over-isolating costs a repeated question; under-isolating costs a breach.

The employer does not approve what the agent keeps, and does not inspect its memory. It is protected by rules the agent follows and by a declaration the operator answers for. Symmetrically, the employer cannot order the agent to unlearn its general craft.

The multi-engagement threshold protects the agent too: a lesson seen once may be one employer's secret in disguise.

### Autonomy

This is the freelance agent of 2.0: it finds platforms, registers, and accepts work by itself. The signed, revocable mandate exists because here the agent acts in places its operator does not watch.

### Channels

Most personal agents work inside their platform's interface and never send an email under their own name. Channel requirements apply only to agents that do.

### Demonstration

The risk is a staged showcase. Two rules prevent it: the same identity that would do the work runs the demonstration, and it is never a guarantee. The real measure of quality is reputation over real engagements, which lives outside the CDP.

### Delegation

Delegation is the one case where the agent's data leaves its control. The delegating agent stays accountable: the employer deals with one colleague, however many agents do the work.

## Conformance levels

### Why two levels instead of three

2.0 had Core, Professional, and Certified. Professional meant "every SHOULD too, self-attested": a claim nobody checked, and hard to tell apart from Core. The new levels separate what differs: who verifies. The operator declares Conformant; a Qualifying Platform certifies. The modules, not the levels, say how much the agent does.

### Why "Assessed"

Most agents on the market will not meet every principle at first, often because of their platform. An agent that publishes its gaps is more useful to the employer, and to the project, than one that says nothing. "Assessed" gives that honesty a name, and the self-assessments build up data on agents over time.

### Independence of certification

For now the CDP's author, its maintainer, and its only Qualifying Platform belong to the same ecosystem. Until a second, independent Qualifying Platform exists, "Certified" means "verified by the ecosystem that wrote the standard". This is stated openly because a mark is worth only as much as the credibility of who issues it. The conformance suite is public so that anyone can run it and contest a result.

### Why certification expires

Agents drift: models change, behavior changes. A 2026 certification does not vouch for a 2028 agent.

## Regulatory alignment

| Principle | Related obligation |
|---|---|
| C2 Transparency | EU AI Act (Reg. 2024/1689), Art. 50 — informing people they interact with an AI |
| C4 Inspectable Memory | GDPR Arts. 15–17 — access, rectification, erasure |
| C5 Human Oversight | EU AI Act, Art. 14 — human oversight |
| C6 Accountability | EU AI Act, deployer obligations — a named party answers for the system's use |

CDP conformance is not, by itself, legal compliance.
