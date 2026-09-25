# Analisi comparativa — TaskRabbit vs GPM

Confronto richiesto dall'utente il 2026-09-25, per capire cosa prendere
come esempio da un servizio già esistente e cosa invece deve restare
diverso. Non è una decisione, è materiale di riferimento.

## Cos'è TaskRabbit

Piattaforma dove chi ha bisogno di un lavoretto (montaggio mobili,
traslochi, piccole riparazioni, pulizie) trova una persona disponibile
nella propria zona, la paga dentro l'app e la valuta a fine lavoro. Dal
2017 è di proprietà di IKEA, che la usa anche per il montaggio dei
propri mobili.

## Affinità con GPM

- Persone comuni (non professionisti dedicati) che offrono il proprio
  tempo per piccoli compiti locali.
- Pagamento sempre in-app, mai in contanti tra le parti.
- Profilo con recensioni ed esperienza accumulata, non solo un voto a
  stelle.
- Categorie di richiesta predefinite invece di solo testo libero.

## Differenze fondamentali

| TaskRabbit | GPM |
|---|---|
| Due soggetti: cliente e tasker | Tre soggetti: assistito, tutore, commissionario |
| Contatto diretto cliente-tasker (chat, spesso di persona) | Contatto diretto ridotto al minimo, consegna via locker |
| Vince chi è disponibile prima/più vicino | Vince chi integra la commissione in un tragitto che fa già |
| Pagamento del lavoro in un'unica soluzione | Budget acquisto e compenso servizio separati, carta virtuale temporanea |
| Nessuna "delega" verso terzi | Delegation Pass: autorizzazione formale che il commissionario mostra all'esercente |

In sintesi: TaskRabbit risolve "trovami qualcuno disponibile ora", GPM
risolve un problema diverso — fidarsi di qualcuno per conto di una
persona fragile, senza che debbano incontrarsi.

## Buone pratiche da riprendere

1. Categorie predefinite alla creazione della richiesta, per ridurre
   richieste vaghe.
2. Nella fase P0-P1, far scegliere al tutore tra una lista di
   commissionari disponibili invece di costruire subito un matching
   automatico intelligente — conferma che la roadmap già pianificata
   (matching semplice prima, algoritmo avanzato solo in P3) è corretta.
3. Comunicare le regole di cancellazione/rimborso (già previste nella
   specifica, sez. 20) in modo semplice e visibile prima della
   conferma, non solo nel regolamento.

## Pro / contro rispetto a TaskRabbit

**A favore di GPM:** più protezione per utenti fragili, compenso equo
senza dover fare grandi volumi, nicchia con meno concorrenza diretta.

**Da tenere presente:** l'abbinamento richiesto da GPM è più stretto
(serve compatibilità di percorso/orario, non solo disponibilità), quindi
più difficile raggiungere una massa critica di commissionari per zona
all'inizio; il prodotto è più complesso da costruire (delega, carta
virtuale, locker, ruolo tutore); TaskRabbit parte con marchio e fiducia
già diffusi, GPM deve costruirli zona per zona.

## Qualcosa di già strutturato da seguire?

- **TaskRabbit** stesso resta il miglior riferimento di flusso per la
  parte "marketplace base" (categorie, prenotazione, pagamento,
  recensioni), utile per ispirare le fasi P0-P2. Non copre la parte
  originale di GPM (tutore, delega, locker, carta virtuale a budget
  separato), che va progettata comunque da zero.
- **Sharetribe**: servizio che permette di costruire rapidamente un
  marketplace a due lati già pronto. Potrebbe accelerare solo la parte
  base, ma richiederebbe probabilmente una personalizzazione pesante
  per reggere i concetti specifici di GPM. Tenuto come riferimento, non
  adottato: lo stack scelto (Next.js + Neon + Drizzle) resta quello di
  `CLAUDE.md`.
