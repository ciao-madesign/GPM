# Piano di lavoro — GPM

Questo file tiene traccia di **cosa è stato deciso, quando e perché**, e
di **cosa manca ancora da decidere**. Va aggiornato ad ogni passo
importante, non solo alla fine.

---

## Stato attuale

**Fase 0 — Impostazione della repository.**

Non è stata scritta ancora nessuna riga di codice applicativo. È stata
organizzata solo la documentazione di base.

---

## Decisioni prese

### 2026-09-01 — Struttura iniziale della repository

**Cosa è stato fatto:**
- Caricata la specifica completa del progetto in
  `docs/specifiche/specifica-completa.md` (copia integrale, invariata),
  così resta un riferimento unico e consultabile.
- Creato `README.md` con una spiegazione semplice del progetto per chi
  non programma.
- Creato `CLAUDE.md` con le regole di lavoro per le sessioni future
  (niente codice senza permesso, documentare le decisioni, non
  rileggere tutta la specifica ogni volta, ecc.).
- Creato questo file (`docs/PIANO-DI-LAVORO.md`).

**Perché:** l'utente ha chiesto di preparare le basi del progetto su
GitHub prima di iniziare a programmare, con un metodo di lavoro
tracciabile e a basso consumo di risorse.

**Cosa NON è stato fatto (di proposito):** nessuno scaffolding di codice
(niente `package.json`, niente progetto Next.js). La specifica
infrastrutturale propone uno stack preciso (Next.js + TypeScript + Neon
+ Drizzle + Vercel), ma l'avvio tecnico vero e proprio è rimandato a
quando l'utente darà il via libera.

### 2026-09-01 — Scelto Clerk per il login

**Decisione:** usare **Clerk** per gestire l'accesso di assistiti,
tutori e commissionari, al posto della soluzione "fai-da-te" (Auth.js).

**Perché:** la specifica di sicurezza richiede doppia autenticazione
obbligatoria per i tutori (l'account più delicato, perché può muovere
soldi) e un accesso semplice ma robusto per l'assistito (idealmente
impronta/riconoscimento del volto, non password complesse). Clerk
offre già pronte queste funzioni, riducendo il rischio di errori di
sicurezza fatti in casa. Ha un piano gratuito ampio, sufficiente per
l'MVP.

**Alternativa scartata:** Auth.js — gratuito, ma avremmo dovuto
costruire a mano le protezioni più delicate (MFA, gestione sessioni,
recupero accesso tramite tutore), con più lavoro e più rischio.

### 2026-09-01 — Pagamenti e carta virtuale: decisione rimandata

**Decisione:** non scegliamo ora il fornitore per i pagamenti e la
carta virtuale. Se ne riparla in fase **P4** (gestione del denaro).

**Perché:** è la parte più delicata dal punto di vista legale e
finanziario (la specifica lo indica esplicitamente, sez. 47). Ha senso
valutarla con calma quando saremo vicini a costruirla davvero.

**Candidati da valutare più avanti:** Stripe Issuing, Lithic, Marqeta —
va verificato chi supporta l'emissione di carte virtuali in Italia/UE
con i limiti di spesa richiesti dalla specifica.

### 2026-09-01 — Confermate 4 migliorie allo stack

**Decisione:** l'utente ha confermato queste 4 proposte, che diventano
scelte definitive (non più "da confermare"):

| Scelta | Perché |
|---|---|
| **shadcn/ui** (componenti grafici pronti, basati su Tailwind) | Componenti già accessibili (testo grande, buon contrasto, aree cliccabili ampie) e completamente modificabili — importante perché una parte degli utenti è anziana. |
| **Resend** per le email | Servizio semplice ed economico per inviare email (conferme, notifiche), si integra bene con Next.js. |
| **SMS rimandati** dopo l'MVP | Gli SMS hanno un costo per ogni invio. Per iniziare bastano notifiche push (gratuite) ed email; si aggiungono gli SMS solo se si rivelano necessari. |
| **Niente monorepo/Turborepo** | Un'unica app Next.js è più semplice da gestire per l'MVP. Anche la specifica infrastrutturale lo suggerisce come opzione valida per iniziare. |

---

## Roadmap prevista (dalla specifica, sezione 44)

Ordine di sviluppo consigliato, dal più semplice/fondamentale al più
avanzato. Non sono scadenze, solo l'ordine logico dei pezzi.

| Fase | Contenuto |
|---|---|
| P0 | Fondamenta: repository, Next.js, database, login, ruoli utente |
| P1 | Gestione della "commissione" (creazione, modifica, approvazione) |
| P2 | Profilo e disponibilità del commissionario |
| P3 | Abbinamento automatico (matching) tra commissioni e commissionari |
| P4 | Gestione del denaro: budget, pagamenti, carta virtuale |
| P5 | Locker (armadietto di consegna) |
| P6 | Deleghe digitali (l'autorizzazione che il commissionario mostra all'esercente) |
| P7 | Rifinitura per l'uso reale: notifiche, sicurezza, gestione dispute |

---

## Proposte alternative / opzioni ancora aperte

Qui vanno registrate le alternative valutate prima di scegliere, così si
può sempre tornare indietro se una scelta si rivela sbagliata.

*(Nessuna proposta alternativa ancora discussa — verrà aggiornato man
mano che si presentano scelte con più opzioni valide, es. provider di
pagamento, provider di carte virtuali, provider locker, sistema di
autenticazione.)*

---

## Domande aperte da decidere insieme all'utente

Queste sono cose che la specifica lascia intenzionalmente aperte e che
andranno chiarite prima o durante lo sviluppo:

1. Con che nome/dominio vogliamo pubblicare il progetto?
2. Quale provider useremo per le carte virtuali e i pagamenti (Stripe o
   altro)? Va scelto con attenzione perché gestisce soldi veri.
3. Per l'MVP, quali locker useremo: armadietti già esistenti sul
   territorio o punti di ritiro convenzionati (negozi disponibili a
   fare da punto di appoggio)?
4. Le commissioni in farmacia sono rimandate a dopo l'MVP per motivi
   legali (prescrizioni, privacy sanitaria) — da confermare che vada
   bene aspettare.
5. Quando iniziamo a scrivere il primo codice (fase P0), su quale parte
   vuoi vedere i risultati per prima?

---

## Prossimo passo proposto

Prima di scrivere codice, servono due conferme dell'utente:

1. **Conferma dello stack tecnico** riassunto in `CLAUDE.md` (Next.js +
   TypeScript + Neon + Drizzle + Vercel). È la scelta consigliata dalla
   specifica: economica, semplice da mantenere, senza microservizi.
2. **Via libera per iniziare la Fase P0** (impostare il progetto tecnico
   vero e proprio: struttura del codice, connessione al database,
   login).

Fino a quel momento, la repository resta solo documentazione.
