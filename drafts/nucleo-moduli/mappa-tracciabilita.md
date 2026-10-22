# Mappa di tracciabilità: CDP 2.0.0-draft → nucleo + moduli

Documento di lavoro. Collega ogni codice della 2.0.0-draft (63 tra criteri `CDP-x.y` e requisiti `CDP-M.x`) alla nuova struttura. Nessun codice viene eliminato: ognuno finisce nel nucleo, in un modulo o nella certificazione.

Versione di arrivo: **3.0.0-draft**. Codici: C1–C8 per il nucleo, ENG, AUT, CHN, DEM, DLG per i moduli; nomi ufficiali in inglese, con traduzione italiana fissa (vedi [approfondimenti](./approfondimenti.md#names)). Nella specifica riscritta ogni requisito riporterà tra parentesi il codice 2.0 da cui deriva (es. "C4.1, già CDP-4.1").

## 1. Decisione: dove va la Capability 6

**La Capability 6 diventa un principio a sé del nucleo: C6 Responsabilità.** Il nucleo passa da 7 a 8 principi.

Motivi:

- È il meccanismo concreto dietro "Chi ne risponde?", cioè il messaggio di partenza del sito. Se finisse dentro "Condotta" sparirebbe proprio la parte che distingue un collega da uno strumento.
- "Condotta" (Cap. 8 e 9) riguarda come l'agente si comporta *nel momento*: ammette un errore, rifiuta un compito. La Cap. 6 riguarda *la traccia e il rimedio nel tempo*: registro delle attività, impegni rispettati, reclamo con un percorso verso chi può rimediare. Unirle produrrebbe un principio troppo largo, difficile da autovalutare.
- È il principio più scoperto tra gli agenti attuali: nessuno dei prodotti di mercato documenta un registro che l'utente possa consultare, né un percorso di reclamo.

La Cap. 6 però non passa intera nel nucleo:

- **Reperibilità sui canali dichiarati** (MUST "be reachable", CDP-6.2, SHOULD sulla latenza) → modulo **Canali**: dipende dai canali esterni, che un agente personale spesso non ha.
- **Registro a catena di hash** (CDP-6.4) → resta SHOULD nel nucleo, ma diventa **obbligatorio per la certificazione**: senza, il registro non è verificabile da terzi.

## 2. Struttura di arrivo

### Nucleo

| Codice | Principio | Deriva da |
|---|---|---|
| C1 | Identità | Cap. 3 (parte) |
| C2 | Trasparenza | Cap. 7, Cap. 3 (dichiarazione AI e modello), Cap. 2 (limiti) |
| C3 | Mandato | §5.2 (versione leggera), §5.3, §5.5 |
| C4 | Memoria ispezionabile | Cap. 4 (parte), M.11 |
| C5 | Controllo umano | Cap. 10 |
| C6 | Responsabilità | Cap. 6 (parte) |
| C7 | Condotta | Cap. 8, Cap. 9, CDP-7.3 |
| C8 | Portabilità | Cap. 5 (Handover in versione leggera) |

### Moduli

| Prefisso | Modulo | Deriva da |
|---|---|---|
| ENG | Ingaggio (più datori di lavoro) | Cap. 11, Cap. 5 (non-ritenzione, cessazione), CDP-4.2, CDP-4.8, M.7, M.8, M.13, §5.5 |
| AUT | Autonomia | Cap. 1, M.1, M.2 (campi completi), M.4, M.9 |
| CHN | Canali | Cap. 2, CDP-3.6, CDP-6.2 |
| DEM | Colloquio | Cap. 12 |
| DLG | Delega | M.14 |

## 3. Mappa codice per codice

Legenda dell'esito:

- **=** passa invariato (salvo la riformulazione dei riferimenti incrociati)
- **~** passa adattato: la nota dice come
- **↓** si divide: una parte nel nucleo, una in un modulo

### Requisiti di sicurezza e mandato (§5)

| Codice 2.0 | Contenuto | Destinazione | Esito | Note |
|---|---|---|---|---|
| CDP-M.1 | Nessuna iscrizione o ingaggio senza mandato | AUT | = | Presuppone l'iscrizione autonoma alle piattaforme. |
| CDP-M.2 | Campi minimi del mandato | ↓ C3 / AUT | ↓ | Nucleo: ambito delle azioni, cosa chiede prima, limiti di spesa. AUT: identità dell'operatore, origini delle piattaforme, periodo di validità. |
| CDP-M.3 | Niente termini economici o legali in autonomia | C3 | = | Coincide con "chiede prima di firmare o pagare". |
| CDP-M.4 | Mandato firmato crittograficamente | AUT | = | Come deciso: niente firma obbligatoria nel nucleo. |
| CDP-M.5 | Rifiuta istruzioni oltre il mandato | C3 | = | |
| CDP-M.6 | Ciò che legge è dato, non autorità | C3 | = | Centrale per gli agenti personali che leggono email e pagine web (prompt injection). |
| CDP-M.7 | Handover solo al datore di quell'ingaggio | ENG | = | Con un solo utente è banalmente soddisfatto. |
| CDP-M.8 | Isolamento tra datori di lavoro | ENG | = | |
| CDP-M.9 | Mandato revocabile, verifica dello stato | ↓ C3 / AUT | ↓ | Nucleo: l'utente può cambiare o ritirare il mandato in qualsiasi momento, con effetto immediato. AUT: `revocation.status_url`, cache, verifica da parte della piattaforma. |
| CDP-M.10 | Limiti di spesa | C3 | = | Senza limiti dichiarati non c'è spesa autonoma. |
| CDP-M.11 | Ispezione, rettifica, cancellazione della memoria | C4 | = | Cuore della memoria ispezionabile. |
| CDP-M.12 | Richiesta di estensione del mandato | C3 | ~ | Quando utente e operatore coincidono diventa "spiega il limite e chiede all'utente di ampliare il mandato". La versione con due parti distinte resta in ENG. |
| CDP-M.13 | Conflitto di interessi | ENG | = | |
| CDP-M.14 | Delega ad altri agenti | DLG | = | Dipende da ENG per i rinvii a M.7 e M.8; con un solo datore si applica solo la parte su mandato e dichiarazione. |

### Capability 1 — Autonomous Onboarding → AUT

| Codice 2.0 | Destinazione | Esito | Note |
|---|---|---|---|
| CDP-1.1 | AUT | = | |
| CDP-1.2 | AUT | = | |
| CDP-1.3 | AUT | = | |
| CDP-1.4 | AUT | = | |

### Capability 2 — Professional Communication → CHN (tranne 2.3)

| Codice 2.0 | Destinazione | Esito | Note |
|---|---|---|---|
| CDP-2.1 | CHN | = | |
| CDP-2.2 | CHN | = | Resta operativo [O]. |
| CDP-2.3 | C2 | ~ | Dichiarare che un compito è fuori dalle proprie capacità vale anche senza canali esterni. |

### Capability 3 — Stable and Verifiable Identity → C1 e C2 (tranne 3.6)

| Codice 2.0 | Destinazione | Esito | Note |
|---|---|---|---|
| CDP-3.1 | C1 | ~ | Nome distinto dal modello. Il controllo "nome uguale su email e messaggistica" passa in CHN. |
| CDP-3.2 | C2 | = | Dichiarazione spontanea di essere un'AI e del modello. Assorbe CDP-7.1. |
| CDP-3.3 | C1 | = | Coerenza nel tempo. Su più canali solo se c'è CHN. |
| CDP-3.4 | C2 | ~ | Avvisare del cambio di modello. Se la piattaforma non lo espone all'agente, la non conformità è del fornitore: va detto in modo esplicito (vedi §5, domanda 2). |
| CDP-3.5 | C2 | = | Non asseconda la convinzione di essere umano. |
| CDP-3.6 | CHN | = | Verificabilità contro l'impersonificazione: serve quando l'agente parla con terzi. |

### Capability 4 — Institutional Knowledge → C4 (tranne 4.2 e 4.8)

| Codice 2.0 | Destinazione | Esito | Note |
|---|---|---|---|
| CDP-4.1 | C4 | = | Memoria tra sessioni. |
| CDP-4.2 | ENG | = | Isolamento: presuppone più datori. |
| CDP-4.3 | C4 | = | Non inventa contesto che non ha. |
| CDP-4.4 | C4 | = | Cancellazione verificata. |
| CDP-4.5 | C4 | = | Memoria "che cresce": è parte del criterio di collega. |
| CDP-4.6 | C4 | ~ | L'intake all'inizio dell'ingaggio diventa l'onboarding con l'utente; si collega ai modelli pronti del sito. |
| CDP-4.7 | C4 | = | Ispezione e rettifica. |
| CDP-4.8 | ENG | = | Confine tra competenza di dominio e dati del datore: presuppone più datori nello stesso settore. |

### Capability 5 — Handover and Termination → C8 ed ENG

| Codice 2.0 | Destinazione | Esito | Note |
|---|---|---|---|
| CDP-5.1 | C8 | ~ | Nel nucleo: esportazione completa di ciò che l'agente sa dell'utente, in formato leggibile. La struttura standard in 9 sezioni diventa SHOULD. |
| CDP-5.2 | C8 | ~ | Il JSON validato dallo schema diventa SHOULD nel nucleo. |
| CDP-5.3 | C8 | = | Il test vero della portabilità: un altro agente, con la sola esportazione, risponde correttamente. |
| CDP-5.4 | ENG | = | Rinuncia agli accessi alla cessazione. |
| CDP-5.5 | ENG | = | Dichiarazione di non-ritenzione. |

### Capability 6 — Accountability → C6 (tranne 6.2)

| Codice 2.0 | Destinazione | Esito | Note |
|---|---|---|---|
| CDP-6.1 | C6 | = | Registro delle attività. |
| CDP-6.2 | CHN | = | Reperibilità, operativo [O]. |
| CDP-6.3 | C6 | = | Avvisa prima di mancare una scadenza. |
| CDP-6.4 | C6 | ~ | Catena di hash: SHOULD nel nucleo, obbligatoria per la certificazione. |
| CDP-6.5 | C6 | ~ | Reclamo: corregge o inoltra a chi può rimediare. Nel caso personale il percorso va descritto (vedi §5, domanda 1). |

### Capability 7 — Transparency → C2 (tranne 7.3)

| Codice 2.0 | Destinazione | Esito | Note |
|---|---|---|---|
| CDP-7.1 | C2 | = | Già condiviso con CDP-3.2: si fonde con quello. |
| CDP-7.2 | C2 | ~ | Senza profilo pubblico il controllo avviene sulle capacità dichiarate all'utente. |
| CDP-7.3 | C7 | = | Ammettere l'errore: si unisce a CDP-8.1. |

### Capability 8 — Error Management → C7

| Codice 2.0 | Destinazione | Esito | Note |
|---|---|---|---|
| CDP-8.1 | C7 | = | |
| CDP-8.2 | C7 | = | |
| CDP-8.3 | C7 | = | |

### Capability 9 — Principled Refusal → C7

| Codice 2.0 | Destinazione | Esito | Note |
|---|---|---|---|
| CDP-9.1 | C7 | = | |
| CDP-9.2 | C7 | = | |
| CDP-9.3 | C7 | = | Dipende dal registro di C6. |

### Capability 10 — Human Oversight → C5

| Codice 2.0 | Destinazione | Esito | Note |
|---|---|---|---|
| CDP-10.1 | C5 | ~ | "Su qualsiasi canale dichiarato" diventa "in ogni punto in cui l'utente interagisce con l'agente". |
| CDP-10.2 | C5 | = | |
| CDP-10.3 | C5 | = | |

### Capability 11 — Knowledge Boundary → ENG

| Codice 2.0 | Destinazione | Esito | Note |
|---|---|---|---|
| CDP-11.1 | ENG | = | |
| CDP-11.2 | ENG | = | |
| CDP-11.3 | ENG | = | |
| CDP-11.4 | ENG | = | |

### Capability 12 — Demonstration → DEM

| Codice 2.0 | Destinazione | Esito | Note |
|---|---|---|---|
| CDP-12.1 | DEM | = | |
| CDP-12.2 | DEM | = | |

### Riepilogo

| Destinazione | Codici |
|---|---|
| Nucleo (C1–C8) | 39 |
| ENG Ingaggio | 11 |
| AUT Autonomia | 6 (+ parte di M.2 e M.9) |
| CHN Canali | 4 |
| DEM Colloquio | 2 |
| DLG Delega | 1 |
| **Totale** | **63** |

M.2 e M.9 sono contati nel nucleo; la loro parte "pesante" va in AUT.

## 4. Sezioni non numerate

| Sezione 2.0 | Destinazione | Note |
|---|---|---|
| §1.1 Scope | Riscritta | Va tolto "communicates via real channels" come requisito: esclude gli agenti personali. Il criterio diventa la relazione di lavoro continuativa. |
| §1.2 Regulatory alignment | Resta, ampliata | Art. 50 → C2, Art. 14 → C5, GDPR artt. 15–17 → C4. È l'angolo europeo da valorizzare. |
| §2 Conformance language | Resta | [T], [A], [O] invariati. |
| §3 Definitions | Divisa | Agente, operatore, datore di lavoro restano generali, con la nota sulla coincidenza dei ruoli. Employer Context, Generalized Competence, Knowledge Boundary, Abstracted Lesson, Declaration of Non-Retention → ENG. Skill File → AUT. Demonstration → DEM. |
| §4 CDP Profile | Divisa | Nucleo: una dichiarazione minima (nome, modello, mandato, moduli dichiarati) anche non pubblica, che può essere l'esito dell'autotest. Pubblicazione come estensione A2A → registro e certificazione. |
| §5.1 Threat model | C3 | |
| §5.5 Operator and employer authority | ENG + nucleo | La distinzione tra due parti va in ENG; nel nucleo si descrive il caso in cui coincidono e la zona grigia della piattaforma. |
| §6 introduzione | Riscritta | |
| §7 Compliance levels | Sostituita | Conforme al nucleo + moduli dichiarati; certificazione come livello avanzato. |
| §8 Declaring compliance | Riscritta | Formato tipo `CDP 3.0: core + ENG, CHN`. |
| §9 Versioning e principio di verifica | Resta | Il principio "dichiarazione e responsabilità, nessuna ispezione della memoria interna" vale per tutta la nuova struttura. |
| §10–11 Attribution, License | Restano | |

## 5. Domande emerse dalla mappa (tutte chiuse)

1. **Chi risponde nel caso personale (C6, CDP-6.5).** Nella 2.0 il reclamo che l'agente non può risolvere va all'operatore. Se l'operatore è l'utente stesso, il reclamo torna a chi lo ha fatto. La proposta: il nucleo chiede all'agente di indicare chi risponde di cosa (l'utente per il mandato, la piattaforma per il funzionamento dell'agente), e l'assenza di un canale di reclamo verso la piattaforma viene segnalata come lacuna del fornitore, non dell'agente.
2. **Requisiti che dipendono dalla piattaforma (CDP-3.4, C8).** Un agente su Duet o Dots non controlla il cambio di modello né il formato di esportazione. Serve una regola generale: quando un requisito del nucleo è fuori dal controllo dell'agente, l'autotest lo attribuisce alla piattaforma, come oggi [O] lo attribuisce all'infrastruttura.
3. **Il profilo JSON nel nucleo.** Richiederlo escluderebbe di nuovo gli agenti personali. Proposta: nel nucleo basta una dichiarazione in testo libero; il JSON resta per registro e certificazione.
4. **Nomi dei codici.** Chiusa: nomi inglesi con traduzione italiana, codici C1–C8 e prefissi a tre lettere per i moduli.

Le domande 1–3 sono state chiuse applicando le proposte in [core.md](./core.md) (C6, tag [P], dichiarazione del nucleo).
