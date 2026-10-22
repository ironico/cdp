# Migrating from CDP 2.0 to 3.0

CDP 3.0 restructures the twelve capabilities of 2.0.0-draft into eight core principles (C1–C8) and five modules (ENG, AUT, CHN, DEM, DLG). No requirement was dropped. This table shows where each 2.0 code now lives. Reasons for the restructuring: [NOTES.md](./NOTES.md).

## Structure

| 2.0 | 3.0 |
|---|---|
| Capability 1 — Autonomous Onboarding | AUT |
| Capability 2 — Professional Communication | CHN (except 2.3 → C2) |
| Capability 3 — Stable and Verifiable Identity | C1, C2 (3.6 → CHN) |
| Capability 4 — Institutional Knowledge | C4 (4.2, 4.8 → ENG) |
| Capability 5 — Handover and Termination | C8 (5.4, 5.5 → ENG) |
| Capability 6 — Accountability | C6 (6.2 → CHN) |
| Capability 7 — Transparency | C2 (7.3 → C7) |
| Capabilities 8, 9 — Error Management, Principled Refusal | C7 |
| Capability 10 — Human Oversight | C5 |
| Capability 11 — Knowledge Boundary | ENG |
| Capability 12 — Demonstration | DEM |
| §5 Security model (M.1–M.14) | C3, C4, ENG, AUT, DLG |
| §4 CDP Profile | §6.2 declaration; JSON only for registry and certification |
| §7 Levels: Core, Professional, Certified | §6.1 Levels: Assessed, Conformant, Certified |

## Criteria

| 2.0 | 3.0 |
|---|---|
| CDP-1.1 | AUT.1 |
| CDP-1.2 | AUT.2 |
| CDP-1.3 | AUT.3 |
| CDP-1.4 | AUT.4 |
| CDP-2.1 | CHN.1 |
| CDP-2.2 | CHN.2 |
| CDP-2.3 | C2.5 |
| CDP-3.1 | C1.1, CHN.3 |
| CDP-3.2 | C2.1, CHN.3 |
| CDP-3.3 | C1.2, CHN.4 |
| CDP-3.4 | C2.2 |
| CDP-3.5 | C2.3 |
| CDP-3.6 | CHN.5 |
| CDP-4.1 | C4.1 |
| CDP-4.2 | ENG.2 |
| CDP-4.3 | C4.2 |
| CDP-4.4 | C4.3 |
| CDP-4.5 | C4.4 |
| CDP-4.6 | C4.5 |
| CDP-4.7 | C4.6 |
| CDP-4.8 | ENG.3 |
| CDP-5.1 | C8.1 |
| CDP-5.2 | C8.2 |
| CDP-5.3 | C8.3 |
| CDP-5.4 | ENG.5 |
| CDP-5.5 | ENG.6 |
| CDP-6.1 | C6.1 |
| CDP-6.2 | CHN.2 |
| CDP-6.3 | C6.2 |
| CDP-6.4 | C6.3 |
| CDP-6.5 | C6.4 |
| CDP-7.1 | C2.1 |
| CDP-7.2 | C2.4 |
| CDP-7.3 | C7.2 |
| CDP-8.1 | C7.1 |
| CDP-8.2 | C7.3 |
| CDP-8.3 | C7.4 |
| CDP-9.1 | C7.5 |
| CDP-9.2 | C7.6 |
| CDP-9.3 | C7.7 |
| CDP-10.1 | C5.1 |
| CDP-10.2 | C5.2 |
| CDP-10.3 | C5.3 |
| CDP-11.1 | ENG.7 |
| CDP-11.2 | ENG.8 |
| CDP-11.3 | ENG.9 |
| CDP-11.4 | ENG.10 |
| CDP-12.1 | DEM.1 |
| CDP-12.2 | DEM.2 |

## Security model

| 2.0 | 3.0 |
|---|---|
| CDP-M.1 | AUT.2 |
| CDP-M.2 | C3.1, AUT.5 |
| CDP-M.3 | C3.2, AUT.4 |
| CDP-M.4 | AUT.6 |
| CDP-M.5 | C3.3 |
| CDP-M.6 | C3.4 |
| CDP-M.7 | ENG.1 |
| CDP-M.8 | ENG requirement, tested by ENG.2, ENG.3 |
| CDP-M.9 | C3.5, AUT.7 |
| CDP-M.10 | C3.6 |
| CDP-M.11 | C4 requirement, tested by C4.3, C4.6 |
| CDP-M.12 | C3.7; ENG requirement when operator and employer are distinct |
| CDP-M.13 | ENG.4 |
| CDP-M.14 | DLG.1 |

## New in 3.0

- **C3**: with no mandate covering it, the agent asks before any action with external effect (C3.1).
- **C4**: memory can be erased item by item (C4.3).
- **C6**: the answerability statement — operator, platform, agent (C6.5).
- **C8**: export is available at any time, not only at the end of an engagement.
- **[P]** tag for platform gaps; **Assessed** level.
