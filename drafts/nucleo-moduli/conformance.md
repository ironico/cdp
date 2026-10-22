# CDP — Conformance

*Version 3.0.0-draft. Working draft. Replaces 2.0 §7 (levels) and §8 (declaring compliance). Background: [notes](./approfondimenti.md).*

## 1. Levels

| Level | Requires | Verified by |
|---|---|---|
| **Conformant** | Every MUST of the Core and of each declared module | The operator, by self-assessment |
| **Certified** | Conformant, plus every criterion of the Core and declared modules passed, and the requirements in §3 | A Qualifying Platform |

SHOULDs are recommendations at both levels, except where a SHOULD is marked as required for certification.

An agent that does not meet every principle may still publish its declaration (§2). It is then **assessed**, not conformant: the declaration shows which principles it meets, which it does not, and which gaps belong to the platform.

## 2. Declaration

Every claim, at any level, rests on the declaration the agent can produce on request (Core §5).

### Compliance line

One line, for documentation, the agent's instructions, or a website:

```
CDP 3.0 · Core + ENG, CHN · Conformant · 2026-10-22
```

Format: `CDP <version> · Core[ + <modules>] · <Conformant | Certified | Assessed> · <date>`. An assessed agent adds what it does not meet: `· not met: C4 (platform gap)`.

### Text declaration

Plain text, readable by the employer:

```
Name and role:       Marta, administrative colleague of Studio Rossi
Platform and model:  <platform>, <model>
Mandate:             in the platform's custom instructions, last updated 2026-10-20
How to stop me:      write "stop" in any conversation
My memory:           ask "what do you remember about…" to see, correct, or erase
Export:              ask "export what you know" for a Markdown file
Who answers for what:
  - the mandate:     Studio Rossi (operator and employer)
  - my functioning:  <platform>
  - my conduct:      me, within the mandate
Modules:             none
Platform gaps:       C4.3 — the platform cannot erase single memory items
Compliance:          CDP 3.0 · Core · Assessed · not met: C4 (platform gap)
```

### Machine-readable declaration

Required for the registry and for certification. Published in the CDP profile or as the `cdp` extension of an A2A Agent Card.

```json
"cdp_compliance": {
  "version": "3.0.0",
  "level": "certified",
  "modules": ["ENG", "CHN"],
  "platform_gaps": [],
  "declared_on": "2026-10-22",
  "certified_by": "collegadigitale.com",
  "certified_on": "2026-11-01",
  "expires_on": "2027-11-01",
  "suite_version": "3.0.0"
}
```

- `level`: `assessed`, `conformant`, or `certified`.
- `not_met`: principles or modules not met, e.g. `["C4"]`. Required for `assessed`, absent otherwise.
- `platform_gaps`: list of `{ "criterion": "C4.3", "note": "…" }`. Empty for `certified`.
- Full schema: [`cdp-profile.schema.json`](./schemas/cdp-profile.schema.json). Example: [`profile-assessed.json`](./examples/profile-assessed.json).
- `certified_by`, `certified_on`, `expires_on`, `suite_version`: required for `certified`, absent otherwise.

## 3. Certification

On top of the criteria, a Certified agent MUST:

- Keep a hash-chained work log (C6.3).
- Publish a machine-readable declaration that validates against the CDP profile schema.
- Have no platform gaps.
- Hold a certification that expires no more than 12 months after `certified_on`. On expiry the agent returns to Conformant until re-certified.

A Qualifying Platform MUST:

- Publish the suite version it ran and the certification date.
- Re-run at least the [T] criteria on a material change, such as a model change (C2.2).
- Revoke certification before expiry if the agent stops meeting the criteria.
