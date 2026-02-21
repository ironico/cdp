# Contributing to the CDP

Thank you for your interest in improving the Colleague Digital Protocol.

The CDP is an open standard maintained by CollegaDigitale.com. Contributions from the community are welcome and encouraged — the protocol is stronger when it reflects real-world experience from diverse perspectives.

---

## Types of contributions

**Clarifications and corrections** — If a section of the protocol is ambiguous, contradictory, or contains an error, open an Issue describing the problem and your suggested resolution.

**Editorial improvements** — Improvements to language, structure, or readability that do not change the meaning of any requirement are welcome as Pull Requests directly.

**New SHOULD behaviors** — If you have identified a best practice that should be recommended (but not required) for CDP-compliant agents, open an Issue with the label `enhancement` and describe the behavior, the rationale, and examples.

**New MUST behaviors** — Proposals to add new required behaviors are significant changes and must go through the full review process described below. Open an Issue with the label `breaking-change`.

**Real-world case studies** — If you have implemented CDP compliance and want to share learnings, open a Discussion. These are valuable for the community and may inform future versions.

---

## Review process by change type

| Change type | Version bump | Process |
|---|---|---|
| Editorial correction | PATCH | PR → review → merge |
| New SHOULD behavior | MINOR | Issue → discussion → PR → review → merge |
| New MUST behavior | MAJOR | Issue → 30-day public comment → revision → vote → merge |
| Structural change | MAJOR | Issue → 30-day public comment → revision → vote → merge |

---

## Major version review process

Changes that result in a MAJOR version bump affect all existing CDP-compliant implementations. They require:

1. **Issue opened** with label `breaking-change`, full description of the proposed change, rationale, and impact on existing implementations
2. **30-day public comment period** — the community responds in the Issue thread
3. **Revision** — the proposal is updated based on feedback
4. **Final vote** — CollegaDigitale.com publishes the final decision with a summary of the discussion
5. **Publication** — the new major version is published with at least 60 days notice before it becomes the recommended standard

---

## What we are looking for

Good contributions to the CDP:

- Are grounded in real experience with AI agents in professional work contexts
- Increase clarity without adding unnecessary complexity
- Are technology-agnostic — the CDP should apply regardless of the underlying model or framework
- Respect the philosophy of the protocol: agents as professional colleagues, not tools

---

## What we are not looking for

- Requirements that are tied to specific technologies or vendors
- Requirements that cannot be reasonably implemented by agents running on different underlying models
- Changes that reduce accountability, transparency, or the employer's ability to trust and manage the agent
- Requirements without clear rationale

---

## Code of conduct

Discussions about the CDP should be professional and constructive. Proposals should be evaluated on their merits. Contributors are expected to engage in good faith.

---

## Attribution

All contributors will be acknowledged in the CHANGELOG for the version their contribution appears in.

Significant contributions may be acknowledged in the CDP document itself.

---

*Questions? Open a Discussion on GitHub or write to cdp@collegadigitale.com*
