# CLAUDE.md — Guida per le sessioni AI su GPM

Questo file serve a chi (umano o AI) riprende in mano il progetto, per
non dover rileggere tutto da capo.

## Chi è l'utente

Il proprietario del progetto **non è un programmatore**. Va sempre
informato con linguaggio semplice, senza gergo tecnico non spiegato.
Non dare per scontato che capisca termini come "endpoint", "ORM",
"webhook" ecc. senza una breve spiegazione in parole semplici.

## Regole di lavoro (valide per ogni sessione)

1. **Minimizzare i token.** Non rileggere `docs/specifiche/specifica-completa.md`
   per intero: è un documento lungo (~7000 righe). Usare `Grep`/ricerca per
   sezione (i titoli sono numerati, es. `# 22. Carta virtuale`) e leggere
   solo le righe rilevanti per il compito in corso.
2. **Mai scrivere codice applicativo senza permesso.** Prima di creare o
   modificare codice (non documentazione), spiegare in italiano semplice
   cosa si vuole fare, perché, e aspettare conferma dell'utente.
3. **Documentare ogni decisione.** Ogni scelta tecnica o di prodotto
   (anche piccola, se cambia il comportamento del sistema) va aggiunta a
   `docs/PIANO-DI-LAVORO.md` con data, motivazione e alternative scartate.
4. **Proposte alternative.** Se esistono più modi ragionevoli di fare una
   cosa, presentarli come opzioni distinte nel piano (sezione "Proposte
   alternative") prima di scegliere, invece di decidere da soli.
5. **Non aggiungere complessità non richiesta.** Niente microservizi,
   niente Kubernetes, niente Redis/Kafka finché non emerge un bisogno
   concreto (vedi spec, sezione 40 "Cosa evitare").
6. **Seguire l'ordine di priorità** definito nella specifica: P0
   (fondamenta) → P1 (commissione) → P2 (commissionario) → P3 (matching)
   → P4 (denaro) → P5 (locker) → P6 (deleghe) → P7 (produzione). Dettagli
   in `docs/specifiche/specifica-completa.md`, sezione 44.

## Riassunto del progetto (per non rileggere tutto)

GPM è una piattaforma che coordina commissioni quotidiane (spesa,
farmacia, lavanderia, ritiri) tra:

- **Assistito**: persona anziana/fragile che ha bisogno della commissione.
- **Tutore**: familiare che modifica/autorizza le richieste e il budget.
- **Commissionario**: persona che esegue la commissione, spesso
  integrandola in un tragitto che fa già (non è un rider dedicato).
- **Locker**: armadietto per consegnare senza contatto diretto.

Principio guida: *"Non ottimizziamo le persone, coordiniamo le loro
abitudini."* Conta il rispetto della scadenza, non la velocità. Niente
gamification, niente classifiche, niente incentivi al volume.

L'entità centrale del sistema è la **Commissione** (commission), che
passa attraverso una macchina a stati (DRAFT → SUBMITTED → ... →
CLOSED, con rami alternativi per fallimenti/dispute). Vedi spec sez. 45
e 13 (parte infrastrutturale).

## Stack tecnico scelto (da specifica)

| Livello | Scelta |
|---|---|
| Linguaggio | TypeScript |
| Framework | Next.js (React) |
| Stile | Tailwind CSS |
| Database | Neon (PostgreSQL) |
| ORM | Drizzle |
| Hosting/CI-CD | Vercel + GitHub Actions |
| Autenticazione | Auth.js / Clerk (da confermare) |
| Mappe | Mapbox |
| Pagamenti | Stripe o provider specializzato in carte virtuali (da confermare) |
| Notifiche | Web Push / provider email-SMS |
| Monitoraggio | Sentry |
| Analytics | PostHog |
| Test | Vitest (unit/integration) + Playwright (E2E) |
| Validazione dati | Zod |

Architettura: **monolite modulare** (un'unica app Next.js organizzata in
moduli indipendenti: commissions, matching, payments, lockers, trust,
delegations, notifications...). Niente microservizi per l'MVP. Vedi spec
sez. 3-4 e 14 (parte infrastrutturale).

## Principi di sicurezza da non violare (riassunto)

- **Need to know**: ogni ruolo vede solo le informazioni che gli servono
  (es. il commissionario non vede dati sanitari o il telefono
  dell'assistito).
- La **carta virtuale** non deve mai contenere dati bancari reali lato
  GPM: solo un riferimento (`virtual_card_id`) verso il provider esterno.
  Limiti di spesa imposti anche lato provider, non solo nel database GPM.
- Ogni webhook di pagamento va verificato con firma, mai fidarsi di una
  chiamata diretta dal client ("pagamento riuscito").
- Ogni endpoint API deve controllare autenticazione + autorizzazione +
  proprietà della risorsa, non solo "utente loggato".
- Se in futuro si userà l'AI per interpretare richieste testuali, l'AI
  può solo proporre un'interpretazione strutturata, mai autorizzare da
  sola un pagamento o un permesso.

Dettagli completi nella specifica, sezioni sulla sicurezza (cercare
"Specifica di sicurezza" nel file).

## File di riferimento

- `docs/specifiche/specifica-completa.md` — specifica di prodotto,
  infrastruttura, sicurezza, gestione carte/pagamenti, gestione frodi.
  Fonte di verità: in caso di dubbio, questo file vince.
- `docs/PIANO-DI-LAVORO.md` — diario di decisioni, stato di avanzamento,
  domande aperte, proposte alternative.
