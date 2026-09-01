Ghe Pensi Mi

# SPECIFICA DI PROGETTO — Piattaforma di commissioni assistite locali

## 1. Visione

Il progetto è una piattaforma che permette a persone anziane, fragili o con difficoltà di autonomia di delegare commissioni quotidiane a persone fidate della propria comunità locale.

Non è un servizio di delivery tradizionale.

L'obiettivo non è ottimizzare la velocità delle consegne, ma **coordinare attività che le persone stanno già svolgendo**, creando un collegamento tra:

* chi ha bisogno di una commissione;
* un familiare/tutore che può supervisionarla e finanziarla;
* un commissionario locale che può eseguirla;
* esercizi e servizi del territorio;
* un locker che consente di eliminare il contatto fisico diretto.

### Principio fondante

> **Non ottimizziamo le persone. Coordiniamo le loro abitudini.**

Esempio:

Luca esce dal lavoro alle 17:30 e passa ogni giorno davanti a una lavanderia. Mario, anziano che vive nel suo quartiere, deve ritirare un cappotto.

La piattaforma permette a Luca di ritirarlo lungo il suo tragitto, ottenendo una remunerazione per una deviazione minima.

Non viene creato un viaggio dedicato.

---

# 2. Problema

Una persona anziana che vive sola può avere difficoltà a svolgere attività banali:

* fare piccoli acquisti;
* ritirare oggetti;
* andare in farmacia;
* ritirare documenti;
* portare qualcosa in lavanderia;
* fare commissioni presso uffici;
* consegnare o recuperare piccoli oggetti.

I servizi di delivery tradizionali non risolvono completamente il problema perché:

* sono pensati principalmente per acquisti digitali;
* richiedono spesso contatto con un rider;
* sono ottimizzati per la rapidità;
* incentivano il volume delle consegne;
* non tengono conto delle relazioni di fiducia;
* possono richiedere che la persona fragile interagisca con sconosciuti;
* non sono ideali per commissioni non commerciali.

La piattaforma deve quindi permettere di **delegare un'azione**, non semplicemente acquistare e ricevere un prodotto.

---

# 3. Utenti

## 3.1 Persona assistita

È la persona che beneficia del servizio.

Può:

* creare commissioni;
* descrivere ciò che necessita;
* vedere lo stato;
* scegliere commissionari preferiti;
* ricevere notifiche;
* ritirare il risultato dal locker.

Non deve necessariamente gestire:

* pagamenti;
* budget;
* autorizzazioni;
* selezione complessa del commissionario.

L'interfaccia deve essere estremamente semplice.

---

## 3.2 Tutore

Normalmente:

* figlio/a;
* familiare;
* persona delegata;
* caregiver.

Il tutore ha funzioni più avanzate.

Può:

* creare commissioni per conto dell'assistito;
* modificare richieste poco chiare;
* correggere le istruzioni;
* autorizzare il budget;
* scegliere il commissionario;
* impostare preferenze;
* monitorare lo stato;
* gestire il budget;
* ricevere notifiche;
* intervenire in caso di problemi.

Il tutore non deve necessariamente essere fisicamente presente.

---

## 3.3 Commissionario

È la persona che esegue la commissione.

Non deve essere necessariamente un rider professionale.

Può essere:

* lavoratore dipendente;
* studente;
* pensionato;
* libero professionista;
* persona che desidera un'attività secondaria;
* commissionario professionale.

Il modello è pensato per essere compatibile con una **seconda occupazione flessibile**.

Il commissionario dichiara la propria disponibilità e accetta soltanto commissioni compatibili con la propria vita.

---

# 4. Filosofia del lavoro

Il sistema deve evitare la cultura del delivery on-demand.

Non devono esistere incentivi alla:

* velocità;
* quantità di commissioni;
* disponibilità continua;
* risposta immediata;
* competizione tra commissionari.

Una commissione ha una **scadenza**, non necessariamente un orario immediato.

Esempio:

> Ritira il cappotto entro le 19:00.

Luca può accettare alle 9:00 e andare in lavanderia alle 17:45.

La commissione è perfettamente riuscita.

### Metrica fondamentale

**Rispetto della scadenza.**

Non:

> "Ha impiegato 38 minuti."

Ma:

> "Ha completato entro le 19:00."

---

# 5. Flessibilità dei commissionari

Il commissionario può dichiarare:

> Lun–Ven: 17:30–20:00
> Sabato: 09:00–18:00

Il sistema propone soltanto commissioni compatibili.

Non esiste necessariamente uno stato:

> ONLINE / OFFLINE

Il commissionario comunica piuttosto:

> **Quando sono disponibile.**

---

# 6. Località e prossimità

Il matching privilegia fortemente i commissionari locali.

Non viene cercato semplicemente:

> il rider più vicino.

Viene cercato:

> **il commissionario che può integrare naturalmente la commissione nella propria vita.**

Il sistema considera:

* zona di residenza;
* zona di lavoro;
* percorsi abituali;
* disponibilità;
* destinazioni;
* scadenze;
* commissioni già accettate;
* preferenze dell'assistito;
* fiducia accumulata.

---

# 7. Traiettorie dichiarate

Il commissionario può dichiarare percorsi abituali.

Esempio:

> Casa → lavoro: 08:00
> Lavoro → casa: 17:30–19:00
> Percorso abituale: zona A → zona B

Non è necessario tracciare continuamente il GPS.

La piattaforma può utilizzare informazioni dichiarate e aggiornate volontariamente.

Obiettivo:

**coordinare percorsi già esistenti.**

---

# 8. Aggregazione delle commissioni

Il sistema può proporre più commissioni compatibili con lo stesso tragitto.

Esempio:

> 3 commissioni compatibili con il tuo percorso.
>
> Tempo aggiuntivo stimato: 18 minuti.
>
> Compenso complessivo: €23.
>
> Tutte le scadenze rispettate.

Il commissionario può:

* accettarle tutte;
* accettarne alcune;
* rifiutarle.

L'aggregazione è uno strumento di efficienza, non un incentivo a massimizzare il numero di commissioni.

---

# 9. La commissione

La commissione è l'unità fondamentale della piattaforma.

Contiene:

```text
Commissione
├── Assistito
├── Tutore
├── Tipo
├── Richiesta originale
├── Istruzioni operative
├── Luogo
├── Finestra temporale
├── Budget acquisto
├── Compenso commissionario
├── Autorizzazione
├── Commissionario
├── Stato
├── Destinazione
└── Storico
```

---

# 10. Origine della commissione

Esistono due modalità.

## A. Creata dall'assistito

Esempio:

> "Mi serve il latte."

Il tutore riceve la richiesta.

Può:

* approvarla;
* modificarla;
* chiedere chiarimenti;
* respingerla.

## B. Creata direttamente dal tutore

Esempio:

> "A papà serve il dentifricio."

Il tutore crea direttamente la commissione.

Non è necessaria una seconda approvazione.

Questo permette anche un'assistenza preventiva.

---

# 11. Modifica da parte del tutore

Il tutore non si limita ad approvare.

Può trasformare una richiesta vaga in istruzioni precise.

### Richiesta originale

> "Prendi il latte e quella medicina."

### Modifica del tutore

> "Compra 2 litri di latte parzialmente scremato. Ritira presso Farmacia Rossi il prodotto già preparato per Mario."

La piattaforma conserva entrambe le versioni.

### Storico

```text
09:12 — richiesta creata
09:15 — tutore modifica istruzioni
09:16 — budget autorizzato
09:18 — commissione assegnata
```

Il commissionario riceve soltanto le **istruzioni operative necessarie**.

---

# 12. Minimizzazione delle informazioni

Il commissionario deve ricevere il minor numero possibile di informazioni personali.

Deve sapere solo ciò che è necessario per eseguire la commissione.

### Può sapere

* luogo;
* attività da svolgere;
* codice;
* eventuali istruzioni operative;
* budget;
* scadenza;
* destinazione.

### Normalmente non deve sapere

* informazioni sanitarie;
* motivazioni della commissione;
* situazione familiare;
* dettagli personali dell'assistito;
* informazioni non necessarie sul destinatario.

Principio:

> **Need to know.**

---

# 13. Interazione con gli esercenti

Il negoziante, la lavanderia, l'ufficio o altro esercente **non devono necessariamente essere utenti della piattaforma**.

Non serve:

* account;
* API;
* app;
* registrazione;
* integrazione.

Il commissionario interagisce con l'esercente nel mondo reale.

Esempio:

> "Devo ritirare il cappotto di Mario Rossi."

La lavanderia può conoscere già Mario, ma non necessariamente il commissionario.

---

# 14. Delegation Pass

Per le commissioni che richiedono un ritiro o una delega, la piattaforma genera una prova di autorizzazione.

Può contenere:

* nome del delegante;
* commissionario autorizzato;
* luogo;
* tipo di operazione;
* codice;
* QR;
* validità;
* eventuale firma digitale.

Esempio:

> **DELEGA DI RITIRO**
>
> Mario Rossi autorizza il portatore della presente delega a ritirare il bene associato alla commissione #48291.
>
> Codice verifica: 839271
>
> Validità: 31/08/2026 – 19:00.

Il commissionario la mostra sul proprio telefono.

---

# 15. Verifica della delega

Possibili livelli:

### QR

L'esercente scansiona il codice.

### Codice

L'esercente legge il codice.

### Delega visiva

Il commissionario mostra la delega.

### Verifica remota

Se l'esercente non è convinto:

> chiama un numero del sistema.

La piattaforma verifica la validità.

Il tutore può eventualmente confermare direttamente.

---

# 16. Nessun obbligo per l'esercente

L'esercente può comunque rifiutarsi di consegnare il bene.

Il sistema deve prevedere questo caso.

Il commissionario segnala:

> **Commissione non completata**

Motivazione:

* delega non accettata;
* bene non disponibile;
* esercizio chiuso;
* informazioni insufficienti;
* ordine non trovato;
* altro.

Il commissionario può aggiungere una nota.

---

# 17. Gestione del fallimento

La commissione non viene necessariamente chiusa.

Può tornare in uno stato:

> **Richiede intervento**

Il tutore riceve:

> La lavanderia richiede una delega cartacea.

Azioni:

* invia nuova autorizzazione;
* modifica istruzioni;
* contatta esercente;
* annulla commissione.

Il commissionario può quindi riprovare.

---

# 18. Pagamento del commissionario

Il commissionario deve essere **adeguatamente retribuito**.

Il modello non deve obbligarlo a fare molte commissioni per ottenere un guadagno dignitoso.

Principio:

> **Poche commissioni, remunerazione equa, minima deviazione.**

Il compenso può essere composto da:

* compenso base;
* eventuale compenso per deviazione;
* eventuale rimborso chilometrico;
* eventuale compenso per complessità.

Non deve essere basato esclusivamente sul numero di consegne.

---

# 19. Fallimento e pagamento

Il commissionario viene pagato per il lavoro effettivamente svolto, non esclusivamente per il risultato.

Se:

1. accetta;
2. raggiunge il luogo;
3. presenta correttamente l'autorizzazione;
4. l'esercente rifiuta comunque;

il commissionario deve ricevere un compenso per il tentativo.

Il costo sostenuto dall'assistito/tutore può invece essere:

* rimborsato;
* rimborsato parzialmente;
* trattenuto;

a seconda della causa del fallimento.

---

# 20. Cause di fallimento

### Errore dell'assistito/tutore

Esempio:

> indicazione errata.

Il compenso del commissionario può essere mantenuto.

### Errore della piattaforma

Il cliente deve essere tutelato.

### Rifiuto dell'esercente

Il commissionario viene remunerato per il lavoro svolto.

### Bene non disponibile

La commissione viene chiusa o modificata.

### Commissionario non esegue correttamente

Il sistema gestisce contestazione e compenso secondo le proprie regole.

---

# 21. Acquisti

Il sistema non deve presupporre che l'acquisto avvenga online.

Esempio:

> "Compra 2 litri di latte."

Il commissionario:

1. va al supermercato;
2. compra il prodotto;
3. paga;
4. porta la spesa al locker.

Non serve alcuna integrazione con il supermercato.

---

# 22. Carta virtuale

Per gli acquisti si utilizza una carta virtuale temporanea associata alla commissione.

Esempio:

> Budget autorizzato: €35.

La carta:

* è legata alla commissione;
* ha limite di spesa;
* ha validità temporale limitata;
* può essere bloccata;
* non costituisce un credito personale del commissionario.

Se il commissionario spende €27:

> €27 utilizzati
> €8 non utilizzati

La differenza non rimane disponibile al commissionario.

---

# 23. Separazione economica

Il pagamento dovrebbe essere separato in:

```text
Budget acquisto
        +
Compenso servizio
```

Esempio:

> Acquisto massimo: €40
> Servizio: €8
>
> Totale autorizzabile: €48

I €40 servono all'acquisto.

Gli €8 costituiscono il compenso/costo del servizio.

---

# 24. Commissioni senza acquisto

Il sistema deve supportare commissioni con costo prodotto pari a zero.

Esempi:

> Ritira il cappotto.

> Porta questo documento.

> Ritira un pacco.

> Consegna un oggetto.

In questi casi:

> Acquisto: €0
> Servizio: €7

---

# 25. Locker

Il locker è un componente centrale dell'architettura fisica.

La sua funzione principale è eliminare il contatto diretto tra:

* persona fragile;
* commissionario.

Il commissionario deposita.

L'assistito preleva successivamente.

Quindi:

```text
ESERCENTE
    ↓
COMMISSIONARIO
    ↓
LOCKER
    ↓
ASSISTITO
```

Nessuno deve necessariamente entrare in casa.

---

# 26. Il locker come punto neutrale

Il locker non deve necessariamente essere di proprietà della piattaforma.

Per l'MVP possono essere utilizzati:

* locker esistenti;
* punti di ritiro;
* strutture convenzionate.

Successivamente è possibile sviluppare una rete proprietaria.

---

# 27. Accesso al locker

Possibili sistemi:

* PIN;
* QR;
* apertura tramite app;
* codice temporaneo;
* apertura autorizzata dal tutore.

Il tutore potrebbe, per esempio, ricevere:

> Commissione consegnata.

e successivamente autorizzare l'apertura.

---

# 28. Consegna al tutore

Il locker non deve necessariamente essere il punto finale.

Esempio:

```text
Negozio
  ↓
Commissionario
  ↓
Locker
  ↓
Tutore
  ↓
Assistito
```

Il tutore può recuperare personalmente l'oggetto e portarlo all'assistito.

Questo è utile quando il familiare passa comunque dalla zona.

---

# 29. Sistema di fiducia

La fiducia è una componente strutturale.

Il sistema deve permettere all'assistito di conoscere progressivamente i commissionari che hanno già effettuato commissioni con successo.

Non è necessario un semplice rating tipo Uber.

Il profilo deve mostrare soprattutto **esperienza e affidabilità**.

Esempio:

> **Luca**
>
> Commissionario verificato
>
> ★ 4,9
>
> 127 commissioni completate
>
> 98% entro la scadenza
>
> 43 commissioni per persone assistite
>
> Identità verificata
>
> Formazione completata

Nessun dato sensibile.

---

# 30. Commissionari preferiti

L'assistito può creare una propria rete:

> **I miei commissionari**

Esempio:

```text
Luca ★4,9
12 commissioni

Anna ★5,0
7 commissioni

Marco ★4,8
1 commissione
```

Quando crea una commissione:

> Preferisci un commissionario specifico?

* Luca
* Anna
* Qualsiasi commissionario verificato

---

# 31. Preferenza vs vincolo

È possibile distinguere:

### Preferenza

> "Preferisco Luca."

Se Luca non è disponibile, il sistema propone altri commissionari.

### Vincolo

> "Solo Luca."

La commissione rimane in attesa se Luca non è disponibile.

Il secondo livello può essere limitato per evitare commissioni irrealizzabili.

---

# 32. Fiducia locale

Il sistema deve favorire commissionari che appartengono alla stessa zona.

La fiducia quindi si costruisce su più livelli:

```text
Assistito
   ↓
conosce virtualmente Luca
   ↓
Luca esegue commissioni
   ↓
Luca diventa commissionario abituale
   ↓
l'assistito si fida
   ↓
l'esercente impara a riconoscere Luca
```

Il rapporto con l'esercente può quindi migliorare spontaneamente.

---

# 33. Nessuna gamification della performance

Da evitare:

* classifiche;
* "top rider";
* streak;
* bonus per numero di commissioni;
* bonus per velocità;
* timer;
* accettazione entro pochi secondi;
* ranking pubblico;
* obiettivi giornalieri.

Il sistema non deve creare una cultura del:

> "Devo fare più commissioni degli altri."

---

# 34. Metriche corrette

Le metriche principali dovrebbero essere:

### Per il commissionario

* affidabilità;
* rispetto delle scadenze;
* qualità;
* continuità;
* commissioni completate;
* contestazioni.

### Per il sistema

* percentuale di commissioni completate;
* distanza aggiuntiva generata;
* percentuale di commissioni integrate in tragitti esistenti;
* tempo medio aggiuntivo;
* rifiuti degli esercenti;
* utilizzo dei locker;
* soddisfazione degli assistiti.

Non:

> commissioni/ora.

---

# 35. Matching

Il motore di matching dovrebbe considerare:

```text
Compatibilità =
prossimità
+
tragitto
+
disponibilità
+
scadenza
+
fiducia
+
preferenza assistito
+
tipo di commissione
+
commissioni già assegnate
```

La distanza non è necessariamente la variabile dominante.

Un commissionario più lontano ma che passa naturalmente dal luogo può essere migliore.

---

# 36. Esempio completo — lavanderia

### Assistito

> "Devo ritirare il cappotto."

### Tutore

Corregge:

> "Ritira il cappotto blu lasciato lunedì presso Lavanderia Rossi."

Autorizza.

### Sistema

Trova Luca.

Luca passa ogni giorno davanti alla lavanderia alle 18:00.

### Luca

Riceve:

> Lavanderia Rossi
> Ritira cappotto
> Entro 19:00
> Consegna Locker 04

Riceve anche la delega digitale.

### Lavanderia

Luca mostra la delega.

La lavanderia consegna il cappotto.

### Luca

Deposita nel Locker 04.

### Assistito

Riceve:

> Il tuo cappotto è disponibile al Locker 04.

---

# 37. Esempio — acquisto

### Tutore

Crea:

> Compra 2 litri di latte parzialmente scremato.

Budget:

> €5

Servizio:

> €7

### Sistema

Trova Anna, che passa dal supermercato tornando dal lavoro.

### Anna

Compra:

> €3,20

La carta virtuale viene utilizzata per €3,20.

Deposita la spesa nel locker.

L'assistito riceve una notifica.

---

# 38. Esempio — commissione creata dal tutore

Il figlio pensa:

> "A papà serve il dentifricio."

Apre l'app.

Seleziona:

> Papà → Nuova commissione.

Inserisce:

> Compra dentifricio.

Imposta:

> Entro domani alle 19:00.

Il sistema ricerca un commissionario compatibile.

Non serve alcuna azione da parte del padre.

---

# 39. Esempio — fallimento

Luca arriva alla lavanderia.

La lavanderia dice:

> "Non accettiamo questa delega."

Luca seleziona:

> Ritiro rifiutato → delega non accettata.

Il sistema informa il tutore.

Il compenso relativo al tentativo di Luca viene mantenuto secondo le regole del servizio.

Il tutore può:

> [Invia nuova delega]

oppure

> [Contatta lavanderia]

oppure

> [Annulla]

---

# 40. Esempio — commissione aggregata

Luca termina il lavoro alle 17:30.

Il sistema sa che il suo percorso abituale passa vicino a:

* farmacia;
* lavanderia;
* supermercato.

Gli propone:

> **3 commissioni compatibili**
>
> Deviazione stimata: 15 minuti
>
> Compenso: €22
>
> Scadenze: tutte entro oggi

Luca può accettare.

Non è obbligato a farlo.

---

# 41. Privacy

La privacy deve essere progettata come principio architetturale.

Il sistema deve minimizzare:

* dati personali;
* posizione;
* informazioni sanitarie;
* contatti diretti;
* informazioni economiche;
* informazioni familiari.

Il commissionario non deve ricevere il numero di telefono dell'assistito.

Le comunicazioni devono avvenire tramite sistema/proxy.

---

# 42. Nessun contatto obbligatorio

Il modello deve funzionare senza:

* telefonate;
* messaggi personali;
* incontro fisico;
* ingresso in casa.

L'assistito può affidare una commissione a Luca senza mai parlargli.

La fiducia deriva da:

* profilo;
* verifiche;
* storico;
* commissioni precedenti;
* preferenza personale.

---

# 43. Architettura software

## Frontend

Tre esperienze distinte:

### App assistito

Interfaccia estremamente semplice.

Funzioni:

* nuova commissione;
* stato;
* locker;
* commissionari preferiti;
* notifiche.

### App tutore

Funzioni:

* gestione assistiti;
* creazione commissioni;
* modifica;
* autorizzazione;
* budget;
* storico;
* gestione commissionari;
* gestione emergenze.

### App commissionario

Funzioni:

* disponibilità;
* commissioni compatibili;
* accettazione;
* istruzioni;
* deleghe;
* pagamento;
* navigazione;
* segnalazione problemi;
* consegna locker.

---

# 44. Backend

Componenti principali:

```text
API Gateway
│
├── Identity Service
├── User/Profile Service
├── Guardian Service
├── Commission Engine
├── Matching Engine
├── Trust Service
├── Payment Service
├── Virtual Card Service
├── Locker Service
├── Notification Service
├── Communication Proxy
├── Audit Service
└── Admin Console
```

---

# 45. Commission Engine

È il cuore dell'applicazione.

Gestisce la macchina a stati:

```text
DRAFT
 ↓
SUBMITTED
 ↓
NEEDS_APPROVAL
 ↓
APPROVED
 ↓
MATCHING
 ↓
ASSIGNED
 ↓
ACCEPTED
 ↓
IN_PROGRESS
 ↓
AT_DESTINATION
 ↓
COMPLETED
 ↓
LOCKER_DELIVERED
 ↓
CLOSED
```

Con percorsi alternativi:

```text
NEEDS_CLARIFICATION
FAILED
REJECTED_BY_MERCHANT
CANCELLED
DISPUTED
```

---

# 46. Matching Engine

Il motore non deve essere real-time come un servizio di food delivery.

Può lavorare su finestre temporali.

Input:

```text
Commissione:
luogo A
scadenza 19:00
durata stimata 15 min
```

Confronta:

```text
Commissionario:
zona
disponibilità
tragitto
preferenze
fiducia
commissioni esistenti
```

Output:

> commissionari compatibili.

---

# 47. Payment architecture

Il sistema deve mantenere separati:

```text
FUNDS
│
├── acquisto autorizzato
│
└── compenso servizio
```

La carta virtuale è creata per la singola commissione.

Possibili integrazioni tecniche:

* provider di issuing di carte virtuali;
* PSP;
* account wallet;
* escrow/preauthorization, dove legalmente appropriato.

La scelta del provider deve essere fatta in fase di progettazione tecnica e legale.

---

# 48. Locker Service

Il backend deve gestire:

* locker;
* scomparti;
* apertura;
* PIN/QR;
* stato;
* assegnazione;
* timestamp;
* eventuale fotografia/prova di deposito;
* notifiche.

Stato:

```text
RESERVED
 ↓
OPEN_FOR_DELIVERY
 ↓
OCCUPIED
 ↓
READY_FOR_PICKUP
 ↓
OPENED
 ↓
EMPTY
```

---

# 49. Audit trail

Ogni commissione deve avere un registro degli eventi.

Esempio:

```text
09:12 richiesta creata
09:15 tutore modifica
09:16 budget autorizzato
09:18 commissionario assegnato
09:21 commissionario accetta
17:42 arrivo
17:49 acquisto effettuato
18:02 locker aperto
18:04 deposito
18:05 assistito notificato
```

Questo è importante per:

* sicurezza;
* dispute;
* assistenza;
* accountability;
* eventuali esigenze legali.

---

# 50. Sicurezza

Componenti essenziali:

* verifica identità commissionari;
* background check ove necessario;
* autenticazione forte;
* autorizzazioni granulari;
* carte virtuali temporanee;
* token monouso;
* QR temporanei;
* audit log;
* comunicazioni proxy;
* minimizzazione dei dati;
* gestione delle contestazioni.

---

# 51. Categorie di commissioni

Per l'MVP:

### Basso rischio

* piccoli acquisti;
* lavanderia;
* piccoli ritiri;
* consegne;
* prodotti quotidiani.

### Medio rischio

* documenti;
* oggetti di valore;
* commissioni con delega.

### Alto/regolamentato

* farmaci;
* denaro;
* documenti particolarmente sensibili;
* beni soggetti a normative specifiche.

Le categorie regolamentate richiedono workflow dedicati.

---

# 52. Farmacia e prodotti regolamentati

Il concetto generale è compatibile con commissioni in farmacia, ma non deve essere dato per scontato che tutte le modalità siano legalmente equivalenti.

Prima del lancio bisogna verificare:

* normativa italiana;
* deleghe;
* farmaci soggetti a prescrizione;
* privacy sanitaria;
* responsabilità del commissionario;
* responsabilità della piattaforma.

Per l'MVP è preferibile partire da commissioni non regolamentate.

---

# 53. Modello economico

Il modello deve sostenere tre soggetti:

```text
CLIENTE
   ↓
Piattaforma
   ↓
Commissionario
```

Il prezzo può essere:

> Costo servizio + eventuale costo acquisto.

Il costo del servizio deve essere sufficientemente elevato da consentire una remunerazione dignitosa al commissionario senza richiedere volumi elevati.

---

# 54. Principio economico

Il progetto deve evitare:

> **"Guadagno di più se faccio più commissioni."**

e preferire:

> **"Guadagno bene quando faccio una commissione che si integra naturalmente nella mia giornata."**

Questo è fondamentale per la filosofia del prodotto.

---

# 55. Beneficio ambientale

La piattaforma non deve promettere "delivery sostenibile" in senso assoluto.

Il beneficio deriva dalla riduzione degli spostamenti dedicati.

Esempio:

### Senza sistema

4 km dedicati per recuperare un cappotto.

### Con sistema

Luca percorre comunque il tragitto casa-lavoro.

La commissione introduce una deviazione minima.

Obiettivo:

> **ridurre la mobilità aggiuntiva generata dalle commissioni.**

---

# 56. Beneficio sociale

Il progetto crea una rete locale in cui:

* gli anziani mantengono autonomia;
* i familiari mantengono controllo senza essere fisicamente presenti;
* le persone possono ottenere un reddito complementare;
* gli esercenti incontrano commissionari abituali;
* vengono valorizzati i percorsi già esistenti.

La piattaforma diventa quindi un **sistema di coordinamento sociale locale**, non soltanto logistico.

---

# 57. Principi UX

## Assistito

**Semplicità estrema.**

Pochissime azioni.

> "Cosa ti serve?"

Possibilità di:

* scrivere;
* parlare;
* scegliere richieste frequenti.

## Tutore

**Controllo.**

Dashboard completa.

## Commissionario

**Chiarezza.**

Solo ciò che serve per eseguire la commissione.

---

# 58. Principi fondamentali del progetto

### 1. Autonomia

La persona fragile continua a decidere cosa vuole.

### 2. Supervisione

Il tutore può intervenire senza sostituirsi completamente all'assistito.

### 3. Privacy

Ogni soggetto riceve solo le informazioni necessarie.

### 4. Fiducia

La continuità dei rapporti vale più della velocità.

### 5. Prossimità

Si privilegiano commissionari locali.

### 6. Flessibilità

Il commissionario decide quando può lavorare.

### 7. Remunerazione equa

Il sistema non deve spingere verso grandi volumi.

### 8. Tempo come finestra

Conta la scadenza, non la rapidità.

### 9. Interoperabilità fisica

Gli esercenti non devono essere obbligati ad aderire alla piattaforma.

### 10. Coordinamento

Il valore della piattaforma deriva dall'intersezione tra attività già esistenti.

---

# 59. MVP

Non costruire immediatamente tutta l'infrastruttura.

## Fase 1

Validare:

* creazione commissione;
* modifica tutore;
* autorizzazione;
* matching locale;
* assegnazione;
* delega digitale;
* pagamento;
* consegna.

Locker esistenti o punti fisici convenzionati.

## Fase 2

Aggiungere:

* commissionari preferiti;
* matching basato sui tragitti;
* aggregazione commissioni;
* trust profile;
* disponibilità ricorrente.

## Fase 3

Aggiungere:

* rete di locker proprietaria;
* apertura automatizzata;
* gestione avanzata dei percorsi;
* automazione del matching;
* integrazione con ulteriori servizi.

---

# 60. Principale ipotesi da validare

Il rischio più importante non è tecnologico.

È capire se esiste realmente una rete sufficiente di persone disposte a dire:

> "Comunque oggi passo da lì. Per €7 posso fare questa commissione."

Se la risposta è sì, il modello ha una caratteristica molto interessante:

**la capacità logistica viene creata utilizzando tempo e percorsi che esistono già.**

---

# 61. Definizione sintetica del prodotto

> **Una piattaforma di commissioni locali per persone anziane o fragili, che permette di delegare attività quotidiane a commissionari verificati e progressivamente fidati. Il tutore può creare, modificare e autorizzare le commissioni e il relativo budget. Il commissionario riceve solo le informazioni necessarie, può utilizzare una carta virtuale temporanea per gli acquisti e consegna il risultato tramite locker, evitando il contatto diretto con la persona assistita.**
>
> **Il sistema privilegia persone locali, percorsi già esistenti e finestre temporali flessibili invece della velocità. L'obiettivo non è massimizzare il numero di consegne, ma coordinare le abitudini di persone diverse creando una rete di fiducia, autonomia e remunerazione equa.**

# 62. Frase guida del progetto

> **Non facciamo correre le persone per fare commissioni. Facciamo incontrare commissioni e persone che stanno già andando nella stessa direzione.**

SPECIFICA INFRASTRUTTURALE:

Di seguito la specifica infrastrutturale di **Ghe Pensi Mi (GPM)**, separata da Nomad e costruita attorno a **GitHub, Vercel e Neon** come stack principale.

# GHE PENSI MI — Specifica infrastrutturale

## 1. Obiettivo

GPM deve essere progettato come una piattaforma web/mobile moderna, inizialmente semplice da sviluppare e gestire, ma con un'architettura sufficientemente solida da supportare successivamente:

* persone assistite;
* tutori;
* commissionari;
* matching geografico;
* pagamenti;
* carte virtuali;
* locker;
* deleghe;
* notifiche;
* sistema di fiducia;
* audit e gestione delle dispute.

Lo stack deve privilegiare:

> **GitHub + Vercel + Neon + TypeScript**

con servizi esterni specializzati soltanto quando necessario.

---

# 2. Architettura generale

```text
                         ┌─────────────────────┐
                         │       GPM APP       │
                         │                     │
                         │ React / Next.js     │
                         │ PWA / Mobile        │
                         └──────────┬──────────┘
                                    │
                                  HTTPS
                                    │
                                    ▼
                         ┌─────────────────────┐
                         │       VERCEL        │
                         │                     │
                         │ Next.js             │
                         │ API / Server        │
                         │ Server Actions      │
                         │ Cron Jobs           │
                         └──────────┬──────────┘
                                    │
                    ┌───────────────┼───────────────┐
                    │               │               │
                    ▼               ▼               ▼
              ┌──────────┐   ┌───────────┐   ┌──────────┐
              │   NEON   │   │  Storage  │   │ External │
              │PostgreSQL│   │ / Files   │   │ Services │
              └──────────┘   └───────────┘   └──────────┘
                                   
                              ┌───────────────┐
                              │ Payments      │
                              │ Maps          │
                              │ Notifications │
                              │ Locker        │
                              └───────────────┘

                         ┌─────────────────────┐
                         │       GITHUB        │
                         │                     │
                         │ Repository          │
                         │ Issues              │
                         │ Actions             │
                         │ CI/CD               │
                         └─────────────────────┘
```

---

# 3. Principio architetturale

Per GPM non utilizzerei inizialmente una struttura a microservizi.

La scelta consigliata è:

> **Monolite modulare.**

Un'unica applicazione backend, organizzata in moduli indipendenti.

Questo riduce:

* complessità;
* costi;
* infrastruttura;
* debugging;
* deployment;
* numero di servizi da mantenere.

La separazione logica deve però essere presente fin dall'inizio.

---

# 4. Stack principale

| Livello       | Tecnologia                               |
| ------------- | ---------------------------------------- |
| Linguaggio    | TypeScript                               |
| Framework     | Next.js                                  |
| Frontend      | React                                    |
| Styling       | Tailwind CSS                             |
| Backend       | Next.js Server / API                     |
| Database      | Neon PostgreSQL                          |
| ORM           | Drizzle ORM oppure Prisma                |
| Repository    | GitHub                                   |
| Hosting       | Vercel                                   |
| CI/CD         | Vercel + GitHub                          |
| Auth          | Auth.js / Clerk / provider equivalente   |
| Maps          | Mapbox                                   |
| Payments      | Stripe o provider specializzato          |
| Notifications | Web Push / Firebase / provider email-SMS |
| Monitoring    | Sentry                                   |
| Analytics     | PostHog                                  |
| Testing       | Vitest + Playwright                      |
| Validation    | Zod                                      |

Per mantenere lo stack leggero, sceglierei **Drizzle + Neon**.

---

# 5. Repository GitHub

Un unico repository:

```text
ghe-pensi-mi/
│
├── apps/
│   └── web/
│
├── packages/
│   ├── db/
│   ├── auth/
│   ├── commissions/
│   ├── matching/
│   ├── payments/
│   ├── lockers/
│   ├── notifications/
│   ├── trust/
│   └── shared/
│
├── tests/
│
├── docs/
│
├── public/
│
├── drizzle/
│
├── .github/
│   └── workflows/
│
├── package.json
├── turbo.json
└── README.md
```

Per l'MVP si può anche evitare Turborepo e mantenere una struttura Next.js più semplice.

L'importante è non introdurre complessità prima che serva.

---

# 6. Branching

Utilizzerei:

```text
main
│
├── develop
│
├── feature/commission-flow
├── feature/matching
├── feature/locker
└── fix/payment-error
```

Per un progetto piccolo può essere sufficiente:

```text
main
│
├── feature/*
└── fix/*
```

Ogni modifica passa attraverso Pull Request.

---

# 7. GitHub Actions

GitHub Actions deve eseguire automaticamente:

```text
Pull Request
     │
     ├── TypeScript check
     ├── ESLint
     ├── Unit tests
     ├── Build
     └── E2E tests
             │
             ▼
        PR approvabile
```

Esempio di pipeline:

```text
npm install
↓
lint
↓
typecheck
↓
test
↓
build
↓
Playwright
```

Vercel crea automaticamente una Preview Deployment per ogni Pull Request.

---

# 8. Ambienti

Tre ambienti:

```text
Development
     ↓
Preview
     ↓
Production
```

### Development

Locale.

### Preview

Ogni branch/PR.

Database Neon dedicato o branch database.

### Production

Ambiente reale.

Questo è particolarmente utile con Neon perché il database può essere gestito in modo coerente con il workflow Git.

---

# 9. Neon PostgreSQL

Neon è il database centrale di GPM.

Tutte le informazioni strutturate passano da PostgreSQL.

Non utilizzerei Redis come database principale.

---

# 10. Database

Schema concettuale:

```text
users
profiles
guardian_relations

commissions
commission_instructions
commission_events
commission_assignments

commissioner_profiles
commissioner_availability
commissioner_routes

trust_profiles
trust_events

payment_authorizations
purchases
payouts

delegations

lockers
locker_compartments
locker_reservations
locker_accesses

notifications

disputes

audit_logs
```

---

# 11. Relazioni fondamentali

```text
User
 │
 ├── AssistedProfile
 │
 ├── GuardianProfile
 │
 └── CommissionerProfile

Guardian
 │
 └── AssistedUser

AssistedUser
 │
 └── Commission
       │
       ├── Instructions
       ├── Assignment
       ├── Payment
       ├── Delegation
       ├── Locker
       └── Events
```

La `Commission` rimane l'entità centrale.

---

# 12. Event sourcing leggero

Non implementerei un vero event-sourcing completo.

Utilizzerei invece uno storico eventi:

```text
commission_events
```

Esempio:

```text
commission.created
commission.modified
commission.approved
commission.assigned
commission.accepted
commission.arrived
commission.purchase_completed
commission.failed
commission.locker_deposited
commission.completed
```

Ogni evento contiene:

```text
id
commission_id
actor_id
event_type
timestamp
metadata
```

Questo permette di ricostruire la storia della commissione.

---

# 13. State machine

La logica della commissione deve essere centralizzata.

```text
DRAFT
 ↓
SUBMITTED
 ↓
NEEDS_APPROVAL
 ↓
APPROVED
 ↓
MATCHING
 ↓
ASSIGNED
 ↓
ACCEPTED
 ↓
IN_PROGRESS
 ↓
COMPLETED
```

Stati alternativi:

```text
NEEDS_CLARIFICATION
CANCELLED
FAILED
MERCHANT_REFUSED
DISPUTED
EXPIRED
```

Il database non deve permettere transizioni arbitrarie.

---

# 14. Backend modulare

La struttura applicativa:

```text
src/
├── modules/
│   ├── auth/
│   ├── users/
│   ├── guardians/
│   ├── commissions/
│   ├── matching/
│   ├── commissioners/
│   ├── trust/
│   ├── payments/
│   ├── delegations/
│   ├── lockers/
│   ├── notifications/
│   └── disputes/
│
├── lib/
│   ├── db/
│   ├── auth/
│   ├── permissions/
│   └── security/
│
└── app/
```

Ogni modulo dovrebbe contenere:

```text
module/
├── service.ts
├── repository.ts
├── schema.ts
├── types.ts
└── tests/
```

---

# 15. API

Per l'MVP utilizzerei principalmente:

* Server Actions per operazioni interne all'app;
* Route Handlers per API esterne/webhook;
* REST dove serve interoperabilità.

Esempio:

```text
POST /api/commissions
GET  /api/commissions/:id
PATCH /api/commissions/:id

POST /api/commissions/:id/approve
POST /api/commissions/:id/accept
POST /api/commissions/:id/fail

GET /api/commissioners
POST /api/commissioners/:id/favorite

POST /api/delegations/:id/verify

POST /api/lockers/:id/reserve
POST /api/lockers/:id/open

POST /api/webhooks/payment
POST /api/webhooks/locker
```

---

# 16. Autenticazione

GPM necessita di autenticazione differenziata.

Ruoli:

```text
ASSISTED
GUARDIAN
COMMISSIONER
ADMIN
```

Un utente può avere più ruoli.

Esempio:

```text
User
 ├── Guardian
 └── Commissioner
```

Le autorizzazioni non devono dipendere solamente dal ruolo.

Serve anche una relazione:

> "Questo tutore è autorizzato a gestire questo assistito."

---

# 17. Authorization

Implementare RBAC + relationship-based access control.

Esempio:

```text
Guardian A
   ↓
authorized
   ↓
Assisted B
```

Guardian A può vedere le commissioni di B.

Guardian C no.

Il commissionario vede soltanto le commissioni assegnategli.

---

# 18. Sicurezza

Ogni endpoint deve verificare:

```text
authentication
↓
authorization
↓
resource ownership
↓
operation permission
```

Non:

```text
if loggedIn === true
```

---

# 19. Pagamenti

Il sistema di pagamento deve essere isolato in un modulo:

```text
payments/
├── payment.service.ts
├── authorization.service.ts
├── payout.service.ts
├── provider.ts
└── webhooks.ts
```

Il provider esterno gestisce i dati finanziari sensibili.

GPM conserva solamente:

* identificativi;
* importi;
* stato;
* commissione associata;
* timestamp.

Non memorizzare dati completi delle carte.

---

# 20. Carta virtuale

La carta virtuale viene astratta tramite:

```text
VirtualCardProvider
```

con implementazioni:

```text
MockVirtualCardProvider
ProductionVirtualCardProvider
```

Questo permette di sviluppare il prodotto prima di avere deciso definitivamente il provider finanziario.

---

# 21. Mappe e geolocalizzazione

Il sistema utilizzerà Mapbox o equivalente per:

* geocoding;
* reverse geocoding;
* distanza;
* percorsi;
* compatibilità geografica.

Non memorizzerei continuamente la posizione GPS del commissionario.

Il modello preferito è:

> **percorso dichiarato + disponibilità temporale.**

---

# 22. Matching Engine

Modulo indipendente:

```text
matching/
├── matching.service.ts
├── geographic.ts
├── temporal.ts
├── trust.ts
└── scoring.ts
```

Input:

```text
Commission
+
Commissioner availability
+
Commissioner routes
+
Trust
```

Output:

```text
Candidate[]
```

L'MVP può usare un algoritmo deterministico.

L'AI potrà essere aggiunta successivamente.

---

# 23. Background jobs

Alcune attività non devono essere eseguite durante una normale richiesta HTTP.

Esempi:

* ricerca commissionari;
* notifiche;
* scadenze;
* chiusura commissioni;
* riconciliazione pagamenti;
* verifica locker;
* reminder.

Su Vercel si possono utilizzare Cron Jobs e/o un servizio di job queue quando la complessità lo richiederà.

Per l'MVP:

> **Vercel Cron + database**

è sufficiente per molti processi.

---

# 24. Locker abstraction

Il backend non deve conoscere il produttore del locker.

```text
LockerProvider
│
├── MockLockerProvider
├── PartnerLockerProvider
└── GPMLockerProvider
```

API concettuale:

```text
reserveLocker()
assignCompartment()
generateAccessCode()
openLocker()
confirmDeposit()
confirmPickup()
```

---

# 25. Delegation service

Modulo:

```text
delegations/
├── delegation.service.ts
├── signing.ts
├── verification.ts
└── qr.ts
```

Una delega contiene:

```text
commission_id
commissioner_id
location
action
valid_from
valid_until
nonce
signature
```

La firma impedisce la modifica fraudolenta della delega.

---

# 26. Pagina pubblica di verifica

Questa è una delle poche parti che dovrebbe essere accessibile senza login.

Esempio:

```text
gpm.it/verify/8X92KD
```

Mostra:

```text
AUTORIZZAZIONE VALIDA

Commissionario:
Luca

Operazione:
Ritiro cappotto

Esercente:
Lavanderia Rossi

Valida fino:
19:00

✓ Verificata da GPM
```

Non deve mostrare dati personali superflui.

---

# 27. Comunicazioni

Tutti i contatti devono passare da un layer:

```text
communication/
```

Questo consente successivamente:

* messaggistica;
* telefonate proxy;
* SMS;
* notifiche.

Il numero di telefono dell'assistito non viene comunicato al commissionario.

---

# 28. Notifications

Un servizio centralizzato:

```text
notifications/
├── notification.service.ts
├── push.ts
├── email.ts
└── sms.ts
```

Ogni evento importante genera una notifica.

Esempio:

```text
commission.locker_deposited
        ↓
NotificationService
        ↓
Push assistito
Push tutore
```

---

# 29. File storage

Per:

* deleghe;
* eventuali documenti;
* ricevute;
* fotografie di deposito;
* documentazione amministrativa.

Utilizzare storage object-based, ad esempio:

* Vercel Blob;
* Cloudflare R2;
* AWS S3.

Il database conserva soltanto il riferimento al file.

---

# 30. Audit

Separare:

```text
commission_events
```

da:

```text
audit_logs
```

Gli eventi descrivono il funzionamento della commissione.

Gli audit log descrivono operazioni sensibili.

Esempio:

```text
ADMIN_VIEWED_USER
GUARDIAN_CHANGED_BUDGET
PAYMENT_REFUNDED
COMMISSIONER_SUSPENDED
LOCKER_FORCE_OPENED
```

---

# 31. Monitoring

Utilizzerei **Sentry** per:

* errori frontend;
* errori backend;
* performance;
* crash;
* tracing.

Dashboard minima:

```text
Errors
Latency
Failed payments
Failed locker operations
Failed notifications
Commission failures
```

---

# 32. Analytics

**PostHog** per analytics di prodotto.

Eventi:

```text
commission_created
commission_approved
commission_accepted
commission_completed
locker_used
commissioner_favorited
commission_failed
```

Non inviare dati personali non necessari agli analytics.

---

# 33. Testing

Tre livelli.

### Unit

Vitest.

Testare soprattutto:

* state machine;
* matching;
* autorizzazioni;
* calcolo compensi;
* budget;
* deleghe.

### Integration

Database Neon/test DB.

Testare:

* creazione commissione;
* autorizzazione;
* assegnazione;
* pagamento.

### E2E

Playwright.

Scenari fondamentali:

```text
Guardian creates commission
        ↓
Commissioner accepts
        ↓
Commission completed
        ↓
Locker deposit
        ↓
Assisted user notified
```

---

# 34. Test più importante

Uno scenario completo deve poter essere eseguito automaticamente:

```text
Tutore
 ↓
crea commissione
 ↓
modifica istruzioni
 ↓
autorizza €30
 ↓
matching
 ↓
commissionario accetta
 ↓
genera delega
 ↓
acquisto simulato €18
 ↓
deposito locker simulato
 ↓
assistito riceve notifica
 ↓
commissione CLOSED
```

Questo sarà il **golden path** del sistema.

---

# 35. Environment variables

Mai inserire secret nel repository.

Esempio:

```text
DATABASE_URL

AUTH_SECRET

STRIPE_SECRET_KEY
STRIPE_WEBHOOK_SECRET

MAPBOX_TOKEN

SENTRY_DSN

POSTHOG_KEY

STORAGE_ACCESS_KEY
STORAGE_SECRET_KEY

NOTIFICATION_API_KEY
```

GitHub Secrets + Vercel Environment Variables.

---

# 36. Development locale

Per iniziare:

```text
Developer
   │
   ├── VS Code
   ├── Git
   └── Node.js
          │
          ▼
      Next.js
          │
          ▼
      Neon Dev DB
```

Non è necessario avere un server locale complesso.

---

# 37. Deployment

Il workflow ideale:

```text
Developer
   ↓
GitHub branch
   ↓
Pull Request
   ↓
GitHub Actions
   ↓
Vercel Preview
   ↓
Test
   ↓
Merge main
   ↓
Vercel Production
```

Database:

```text
Schema change
   ↓
Migration
   ↓
Neon
```

---

# 38. Neon Branching

Per feature importanti:

```text
production
│
├── preview-feature-matching
├── preview-locker
└── preview-payments
```

Ogni ambiente può lavorare su un database isolato.

Questo riduce drasticamente il rischio di rompere dati reali durante lo sviluppo.

---

# 39. Costi iniziali

Per un MVP a basso traffico l'architettura può essere molto economica perché:

* GitHub può ospitare il codice;
* Vercel gestisce deployment/frontend/backend;
* Neon gestisce PostgreSQL;
* molte funzioni sono serverless.

I costi che probabilmente cresceranno per primi non saranno necessariamente hosting/database, ma:

* pagamenti;
* SMS;
* mappe/geocoding;
* storage;
* notifiche;
* eventuale issuing delle carte virtuali;
* infrastruttura locker.

---

# 40. Cosa evitare

Non introdurre inizialmente:

### Kubernetes

Inutile per l'MVP.

### Microservizi

Troppa complessità.

### Redis

Non necessario finché non emerge un caso concreto.

### Kafka

Assolutamente prematuro.

### AI matching

Prima validare l'algoritmo deterministico.

### GPS tracking continuo

Contrario al modello di privacy e non necessario.

### Database NoSQL

PostgreSQL è molto più adatto alle relazioni tra utenti, commissioni, autorizzazioni e transazioni.

---

# 41. Evoluzione futura

L'architettura deve permettere successivamente:

```text
                GPM
                 │
       ┌─────────┼─────────┐
       │         │         │
     MOBILE    WEB       API
       │         │         │
       └─────────┼─────────┘
                 │
              Backend
                 │
       ┌─────────┼─────────┐
       │         │         │
    Matching  Payments   Trust
       │         │         │
       └─────────┼─────────┘
                 │
              Database
                 │
        ┌────────┼────────┐
        │        │        │
      Lockers  Maps     External
```

Quando il traffico crescerà, i singoli moduli potranno essere estratti in servizi indipendenti.

Non è necessario farlo prima.

---

# 42. Architettura MVP definitiva

La prima versione dovrebbe essere sostanzialmente:

```text
                 GitHub
                    │
                    ▼
              ┌───────────┐
              │  Vercel   │
              │           │
              │ Next.js   │
              │ React     │
              │ API       │
              └─────┬─────┘
                    │
                    ▼
              ┌───────────┐
              │   Neon    │
              │PostgreSQL │
              └───────────┘
                    │
       ┌────────────┼────────────┐
       ▼            ▼            ▼
    Stripe       Mapbox      Storage
       │
       ▼
   Payments

       ┌────────────────────────┐
       │       Services         │
       │                        │
       │ Notifications          │
       │ Locker API             │
       │ Monitoring             │
       └────────────────────────┘
```

---

# 43. Stack finale consigliato

### Core

**TypeScript + Next.js + React**

### Database

**Neon PostgreSQL**

### ORM

**Drizzle**

### Repository

**GitHub**

### Deployment

**Vercel**

### Validation

**Zod**

### Testing

**Vitest + Playwright**

### Maps

**Mapbox**

### Payments

**Stripe / provider specializzato**

### Monitoring

**Sentry**

### Analytics

**PostHog**

### Storage

**Vercel Blob o S3-compatible**

### Jobs

**Vercel Cron inizialmente**

### Locker

**Adapter proprietario, inizialmente Mock**

---

# 44. Priorità di sviluppo

## P0 — Fondamenta

* GitHub repository;
* Next.js;
* TypeScript;
* Neon;
* Drizzle;
* autenticazione;
* utenti e ruoli;
* authorization.

## P1 — Commissione

* creazione;
* modifica;
* approvazione;
* state machine;
* storico;
* assegnazione manuale.

## P2 — Commissionario

* profilo;
* disponibilità;
* accettazione;
* completamento;
* trust profile.

## P3 — Matching

* geografia;
* disponibilità;
* tragitti dichiarati;
* matching automatico.

## P4 — Denaro

* budget;
* pagamento;
* compenso;
* sandbox virtual card.

## P5 — Locker

* locker simulato;
* prenotazione;
* deposito;
* ritiro.

## P6 — Deleghe

* generazione;
* QR;
* pagina pubblica di verifica.

## P7 — Produzione

* notifiche;
* monitoring;
* audit;
* dispute;
* sicurezza;
* privacy;
* backup;
* procedure operative.

---

# 45. Obiettivo tecnico dell'MVP

L'MVP non deve dimostrare di poter gestire migliaia di commissioni.

Deve dimostrare che questa sequenza funziona:

```text
PERSONA ASSISTITA
        │
        ▼
     RICHIESTA
        │
        ▼
      TUTORE
        │
   modifica/autorizza
        │
        ▼
     COMMISSIONE
        │
        ▼
     MATCHING
        │
        ▼
   COMMISSIONARIO
        │
        ├──── acquisto
        │
        └──── ritiro
                │
                ▼
              LOCKER
                │
                ▼
        PERSONA ASSISTITA
```

Con contemporaneamente:

```text
Privacy ✓
Autorizzazione ✓
Pagamento ✓
Delegazione ✓
Tracciabilità ✓
Fiducia ✓
Scadenza ✓
```

Se questo flusso funziona bene, l'infrastruttura è già una base sufficiente per costruire il resto di GPM.

## 46. Principio architetturale finale

La tecnologia deve rimanere subordinata al modello sociale di GPM.

**GitHub** gestisce il ciclo di sviluppo.

**Vercel** esegue l'applicazione.

**Neon** conserva lo stato e la storia del sistema.

I servizi esterni gestiscono ciò che GPM non deve reinventare: pagamenti, mappe, notifiche, storage e successivamente locker.

Il cuore proprietario rimane invece:

> **Commission Engine + Matching Engine + Trust System + Authorization Model.**

Sono queste le componenti che costituiscono il vero prodotto GPM.

La criticità principale è che GPM mette insieme **identità, persone vulnerabili, denaro, carte virtuali, deleghe fisiche e beni reali**. Va quindi progettato come sistema *security-first*, non come semplice marketplace.

# GHE PENSI MI — Specifica di sicurezza

## 1. Obiettivo

La sicurezza di GPM deve proteggere contemporaneamente:

1. la persona assistita;
2. il tutore;
3. il commissionario;
4. gli esercenti;
5. il denaro;
6. le carte virtuali;
7. le deleghe;
8. i dati personali;
9. i locker;
10. l'integrità delle commissioni.

Il principio generale è:

> **Nessun singolo account, dispositivo, token o componente deve essere sufficiente per trasformare una richiesta in un'azione finanziaria o fisica ad alto impatto.**

---

# 2. Modello delle minacce

I principali attaccanti da considerare sono:

### Attaccante esterno

Non possiede un account GPM.

Obiettivi:

* rubare account;
* creare commissioni;
* sottrarre dati;
* ottenere accesso alle carte;
* aprire locker;
* falsificare deleghe.

### Account compromesso

L'attaccante ha ottenuto:

* password;
* sessione;
* token;
* dispositivo.

È particolarmente pericoloso perché opera apparentemente come utente legittimo.

### Commissionario fraudolento

È un utente apparentemente legittimo che cerca di:

* ottenere denaro;
* utilizzare una carta virtuale;
* appropriarsi di acquisti;
* falsificare completamenti;
* aggirare le deleghe.

### Tutore fraudolento

Si presenta come familiare/tutore senza esserlo realmente.

Potrebbe:

* accedere all'account dell'assistito;
* generare commissioni;
* spendere il budget;
* ottenere informazioni personali.

### Insider

Dipendente/amministratore con accesso ai sistemi.

Può rappresentare una minaccia particolarmente grave perché possiede privilegi elevati.

### Esercente fraudolento

Potrebbe tentare di:

* utilizzare una delega oltre il previsto;
* falsificare un ritiro;
* ottenere informazioni sull'assistito.

---

# 3. Principio fondamentale: separazione delle responsabilità

Una commissione non dovrebbe essere un'unica autorizzazione.

Deve esistere una catena:

```text
RICHIESTA
   ↓
AUTORIZZAZIONE
   ↓
MATCHING
   ↓
ASSEGNAZIONE
   ↓
AUTORIZZAZIONE OPERATIVA
   ↓
EVENTUALE AUTORIZZAZIONE FINANZIARIA
   ↓
ESECUZIONE
   ↓
VERIFICA
   ↓
CHIUSURA
```

Ogni fase deve avere controlli indipendenti.

---

# 4. Identità fraudolente

## Rischio

Una persona potrebbe creare un account commissionario utilizzando:

* nome falso;
* documento contraffatto;
* identità rubata;
* numero telefonico temporaneo;
* account multipli.

Questo è particolarmente grave perché il commissionario può entrare fisicamente in contatto con beni di terzi.

## Contromisure

Il commissionario deve avere un processo di verifica dell'identità più rigoroso rispetto all'assistito.

Possibili requisiti:

* verifica documento;
* selfie/liveness dove appropriato;
* verifica numero telefonico;
* verifica email;
* verifica conto di pagamento;
* controllo di unicità dell'identità;
* eventuale verifica aggiuntiva prima dell'abilitazione.

L'identità reale non deve essere necessariamente mostrata all'assistito.

Il sistema può mostrare:

> Luca
> Identità verificata
> Commissionario dal 2026

---

# 5. Account multipli

Un commissionario potrebbe creare:

```text
Luca
Luca92
Luca Milano
```

per manipolare:

* ranking;
* commissioni;
* incentivi;
* recensioni;
* sistema di fiducia.

La piattaforma dovrebbe rilevare segnali di duplicazione:

* identità;
* numero di telefono;
* metodo di pagamento;
* dispositivo;
* pattern comportamentali;
* dati di verifica.

Non necessariamente bloccare automaticamente: generare un alert.

---

# 6. Account dell'assistito

L'account dell'anziano è un obiettivo particolarmente delicato.

Un attaccante potrebbe:

> accedere all'account → creare commissione → utilizzare il budget.

Per questo l'accesso dovrebbe essere semplice ma non debole.

Possibili sistemi:

* passkey;
* PIN;
* autenticazione biometrica del dispositivo;
* recovery tramite tutore;
* autenticazione forte per operazioni sensibili.

L'assistito non dovrebbe dover gestire password complesse.

---

# 7. Account del tutore

Il tutore è probabilmente l'account più importante del sistema.

Un account tutore compromesso può consentire:

```text
accesso assistito
+
creazione commissioni
+
modifica richieste
+
autorizzazione denaro
+
accesso allo storico
```

Per questo:

> **MFA obbligatoria per i tutori.**

Preferenza:

1. passkey;
2. autenticazione tramite dispositivo;
3. TOTP;
4. SMS soltanto come fallback.

---

# 8. Collegamento tutore → assistito

Non deve essere sufficiente dichiarare:

> "Sono il figlio di Mario."

La relazione deve essere verificata.

Possibili procedure:

### Invito

L'assistito genera un codice/invito.

### Conferma reciproca

Il tutore richiede accesso.

L'assistito conferma.

### Verifica amministrativa

Per casi particolari.

### Deleghe documentali

Da utilizzare quando necessario.

Il database deve rappresentare esplicitamente:

```text
Guardian A
    ↓
AUTHORIZED_FOR
    ↓
Assisted B
```

---

# 9. Escalation dei privilegi

Un nuovo tutore non dovrebbe immediatamente poter:

* modificare dati sensibili;
* spendere grandi importi;
* cambiare altri tutori;
* modificare metodi di pagamento.

Possibile modello:

```text
NEW GUARDIAN
     ↓
LIMITED
     ↓
VERIFIED
     ↓
FULL ACCESS
```

---

# 10. Creazione fraudolenta di commissioni

## Attacco

Un account compromesso crea:

> Compra €200 di prodotti.

Oppure:

> Compra 10 prodotti da €30.

Il sistema potrebbe diventare un mezzo per trasferire denaro a un attaccante.

## Contromisure

Limiti:

* budget massimo per commissione;
* budget giornaliero;
* budget mensile;
* numero massimo di commissioni;
* categorie consentite;
* importo massimo per categoria.

Esempio:

```text
Singola commissione: €50
Giornaliero: €100
Settimanale: €250
```

I limiti devono essere configurabili dal tutore.

---

# 11. Anomaly detection

Il sistema deve individuare pattern anomali.

Esempio:

```text
Normalmente:
€10–30
1 commissione/settimana

Improvvisamente:
€300
12 commissioni
nuovo commissionario
nuovo esercente
```

La commissione viene sospesa:

> **Verifica necessaria.**

Non è necessario usare AI.

Regole deterministiche sono sufficienti inizialmente.

---

# 12. Creazione fraudolenta da parte del commissionario

Un commissionario potrebbe cercare di indurre il sistema a creare una commissione a proprio vantaggio.

Esempio:

> "Il cliente ha richiesto un acquisto aggiuntivo."

Non deve poter modificare autonomamente:

* richiesta;
* budget;
* destinatario;
* compenso.

Il commissionario può soltanto:

> **segnalare una necessità di modifica.**

Il tutore decide.

---

# 13. Modifica della commissione

Ogni modifica importante deve produrre un nuovo evento.

```text
REQUEST_CREATED
        ↓
INSTRUCTIONS_CHANGED
        ↓
GUARDIAN_APPROVED
```

Il commissionario deve sapere quale sia la **versione attualmente valida**.

Le versioni precedenti non devono poter essere sovrascritte.

---

# 14. Race conditions

Possibile attacco:

```text
Tutore modifica budget
        +
commissionario esegue acquisto
        +
sistema aggiorna contemporaneamente
```

Potrebbero verificarsi autorizzazioni duplicate.

Il database deve utilizzare:

* transaction;
* row locking dove necessario;
* idempotency key;
* versioning.

Una stessa autorizzazione non deve poter essere consumata due volte.

---

# 15. Carta virtuale: rischio principale

Questa è una delle componenti più delicate.

GPM **non dovrebbe mai memorizzare direttamente i dati completi della carta**, se può evitarlo.

La carta deve essere emessa e gestita da un provider specializzato.

GPM conserva:

```text
virtual_card_id
commission_id
status
spending_limit
expiration
provider_reference
```

Non:

```text
PAN
CVV
PIN
```

---

# 16. Principio "token instead of card data"

Architettura:

```text
GPM
 │
 │ virtual_card_id
 ▼
Payment Provider
 │
 └── dati sensibili della carta
```

GPM conosce l'esistenza della carta.

Il provider conosce i dati finanziari.

Questo riduce enormemente il rischio.

---

# 17. Carta temporanea

Ogni carta deve essere:

* associata a una commissione;
* limitata nell'importo;
* limitata temporalmente;
* eventualmente limitata per merchant/category;
* disattivata al termine;
* revocabile.

Esempio:

```text
CARD
Commissione #4812
Limit: €40
Valid: 10:00–19:00
Status: ACTIVE
```

Dopo:

```text
EXPIRED
```

---

# 18. Non usare una carta globale del commissionario

Da evitare:

> "Luca ha una carta GPM con €500."

Meglio:

> "Luca ha una carta temporanea per la commissione #4812 con limite €35."

Se la carta viene compromessa, l'impatto è limitato.

---

# 19. Merchant controls

Se il provider lo permette, la carta dovrebbe essere limitata anche al contesto della commissione.

Possibili restrizioni:

* MCC;
* merchant;
* paese;
* importo;
* numero transazioni;
* periodo temporale.

Esempio:

```text
max €35
max 2 transazioni
validità 3 ore
categoria supermercato
```

---

# 20. Frode tramite carta virtuale

Possibile attacco:

1. commissionario ottiene carta;
2. utilizza la carta per acquisti personali;
3. dichiara acquisto diverso;
4. deposita un altro prodotto.

Contromisure:

* limite stretto;
* scadenza;
* restrizioni merchant;
* ricevuta;
* verifica importo;
* eventuale fotografia della ricevuta;
* riconciliazione automatica;
* contestazione.

Il commissionario non dovrebbe poter aumentare autonomamente il limite.

---

# 21. Doppia spesa

Scenario:

```text
Budget: €30

Transazione 1: €25
Transazione 2: €25
```

Il provider deve rifiutare la seconda.

Il limite deve essere imposto **a livello della carta/provider**, non soltanto nel database GPM.

Questo è fondamentale.

---

# 22. Webhook dei pagamenti

Non fidarsi mai di:

```text
POST /payment-success
```

inviato dal client.

Il browser/app non può dichiarare:

> "Pagamento riuscito."

La conferma deve arrivare dal provider tramite webhook autenticato.

```text
Payment Provider
       ↓
signed webhook
       ↓
GPM backend
       ↓
verify signature
       ↓
update transaction
```

---

# 23. Replay attack

Un attaccante potrebbe catturare un webhook valido e reinviarlo.

Ogni webhook deve avere:

* signature;
* timestamp;
* event ID.

GPM deve registrare gli eventi già elaborati.

Se:

```text
event_id = 123
```

è già stato processato:

> ignorare il secondo evento.

---

# 24. Idempotenza

Operazioni finanziarie importanti devono essere idempotenti.

Esempio:

```text
POST /commission/4812/pay
Idempotency-Key: ABC123
```

Se arriva due volte:

> una sola operazione effettiva.

---

# 25. Furto della sessione

Un attaccante potrebbe rubare una sessione web.

Contromisure:

* cookie HttpOnly;
* Secure;
* SameSite;
* session rotation;
* expiration;
* revoca sessioni;
* rilevamento dispositivi;
* re-authentication per operazioni sensibili.

---

# 26. Operazioni ad alto rischio

Anche con sessione valida, richiedere nuovamente autenticazione per:

* aggiungere tutore;
* cambiare metodo di pagamento;
* aumentare budget;
* modificare limiti;
* trasferire denaro;
* cambiare dati sensibili.

Questo protegge dal caso:

> dispositivo già autenticato ma utilizzato da un'altra persona.

---

# 27. API Security

Tutte le API devono verificare:

```text
Authentication
       ↓
Authorization
       ↓
Ownership
       ↓
Input validation
       ↓
Business rules
```

Esempio:

```text
GET /commission/123
```

non deve essere sufficiente per vedere la commissione.

Il backend deve verificare:

> L'utente corrente è autorizzato a vedere la commissione 123?

---

# 28. IDOR / Broken Access Control

Rischio enorme.

Attacco:

```text
/commission/123
/commission/124
/commission/125
```

L'attaccante potrebbe semplicemente cambiare l'ID.

Gli ID pubblici dovrebbero essere non enumerabili, ma soprattutto:

> **l'autorizzazione deve essere verificata lato server.**

Cambiare UUID non deve mai permettere accesso a una risorsa.

---

# 29. Input validation

Tutti gli input devono essere validati con schema.

Esempio concettuale:

```text
budget:
number
min: 0
max: guardian_limit
```

Non accettare direttamente JSON proveniente dal client.

Utilizzare Zod o equivalente.

---

# 30. Prompt injection / AI

Se GPM utilizzerà AI per interpretare richieste:

> "Compra due litri di latte."

il testo utente è **dato non attendibile**.

Un testo malevolo non deve poter indurre l'AI a:

* aumentare budget;
* autorizzare pagamenti;
* cambiare destinatario;
* modificare permessi.

L'AI deve produrre una proposta strutturata:

```text
interpretation
```

e mai:

```text
authorization
```

---

# 31. Regola fondamentale per l'AI

```text
AI
 ↓
PROPOSAL
 ↓
VALIDATION
 ↓
BUSINESS RULES
 ↓
HUMAN AUTHORIZATION
```

Mai:

```text
AI → PAYMENT
```

---

# 32. Delega fraudolenta

Un attaccante potrebbe creare:

> "Luca è autorizzato a ritirare il cappotto."

senza che il tutore lo abbia realmente autorizzato.

La delega deve essere:

* generata server-side;
* firmata;
* legata alla commissione;
* legata al commissionario;
* legata all'esercente/luogo quando possibile;
* temporalmente limitata;
* revocabile.

---

# 33. QR code

Il QR non deve contenere direttamente informazioni sensibili.

Non:

```text
Mario Rossi
indirizzo
telefono
commissione
```

Meglio:

```text
opaque_token
```

Il server restituisce soltanto le informazioni necessarie alla verifica.

---

# 34. Screenshot della delega

Un commissionario potrebbe fare uno screenshot e riutilizzarlo.

Per questo la delega deve avere:

* scadenza;
* nonce;
* stato;
* commissionario specifico;
* possibilmente verifica online.

Una delega utilizzata può diventare:

```text
USED
```

e non essere riutilizzabile.

---

# 35. Offline verification

Bisogna decidere attentamente se la delega debba funzionare offline.

Per le operazioni sensibili è preferibile:

> **verifica online.**

Se la lavanderia non ha internet, si può prevedere un fallback più debole, ma non dovrebbe essere il meccanismo principale.

---

# 36. Locker security

Il locker introduce un'altra superficie d'attacco.

Rischi:

* codice rubato;
* QR intercettato;
* apertura abusiva;
* locker sbagliato;
* manomissione fisica;
* sostituzione del contenuto.

Il codice di apertura deve essere:

* temporaneo;
* monouso;
* associato all'utente;
* associato allo scomparto;
* revocabile.

---

# 37. Consegna nel locker

Il commissionario deve ottenere:

> Locker 04 → apri.

Non:

> Tutti i locker della struttura.

Il backend autorizza esclusivamente:

```text
commission_id
+
locker_id
+
compartment_id
+
commissioner_id
```

---

# 38. Conferma di deposito

La commissione non deve diventare:

> COMPLETED

quando il commissionario dice:

> "Ho consegnato."

Meglio:

```text
Commissioner
     ↓
deposit initiated
     ↓
locker confirms closed
     ↓
deposit confirmed
     ↓
notification
```

Dove possibile, la conferma deve provenire dal locker.

---

# 39. Foto del deposito

Può essere utile una prova fotografica, ma introduce nuovi rischi privacy.

Se utilizzata:

* conservazione limitata;
* accesso ristretto;
* cancellazione automatica;
* niente volti quando possibile;
* niente informazioni inutili.

La foto deve dimostrare:

> "Il bene è nel locker."

non:

> "Ecco tutto ciò che circonda il luogo."

---

# 40. Furto durante la commissione

Il commissionario potrebbe dichiarare:

> "Ho acquistato il prodotto."

ma non consegnarlo.

Possibili contromisure:

* ricevuta;
* transazione verificata;
* conferma locker;
* timestamp;
* storico affidabilità;
* contestazione;
* eventuale fotografia.

Non eliminano il rischio, ma permettono di ricostruire l'evento.

---

# 41. Commissionario che prende il bene dal locker

Dopo il deposito, l'accesso deve essere consentito esclusivamente al destinatario autorizzato.

Una volta:

```text
LOCKER_DELIVERED
```

il commissionario perde immediatamente l'autorizzazione.

---

# 42. Furto dell'account dell'assistito

Se l'assistito perde il telefono:

* il tutore deve poter revocare il dispositivo;
* il locker non deve essere apribile soltanto perché il telefono era autenticato;
* le sessioni devono essere revocabili.

Il tutore deve poter eseguire:

> **Blocca accesso assistito**

---

# 43. Furto del telefono del commissionario

Stessa logica.

Il commissionario deve poter essere disconnesso remotamente.

Le deleghe già emesse devono poter essere revocate.

Le carte virtuali attive devono poter essere:

> **immediatamente bloccate.**

---

# 44. Insider threat

Un amministratore potrebbe avere accesso a:

* dati degli assistiti;
* commissioni;
* pagamenti;
* documenti.

Soluzione:

### Least privilege

Ogni admin vede solo ciò che serve.

### Audit

Ogni accesso sensibile viene registrato.

### Separazione

Chi gestisce supporto non deve necessariamente poter:

* emettere rimborsi;
* modificare pagamenti;
* vedere documenti di identità.

---

# 45. Accesso al database

Mai utilizzare credenziali database amministrative dall'applicazione.

Separare:

```text
Application DB user
```

da:

```text
Migration/Admin DB user
```

Il primo ha solo i privilegi necessari.

---

# 46. Secret management

Secret come:

```text
DATABASE_URL
PAYMENT_SECRET
WEBHOOK_SECRET
AUTH_SECRET
MAPBOX_SECRET
```

non devono mai essere:

* nel repository;
* nel frontend;
* nei log;
* nei messaggi di errore.

Devono essere gestiti tramite environment secrets di Vercel/GitHub o secret manager appropriato.

---

# 47. Frontend security

Il frontend è considerato non affidabile.

Qualunque valore mostrato nell'app può essere manipolato.

Quindi:

> **mai fidarsi del client.**

Esempio:

```text
client:
budget = 1000
```

non significa che l'utente abbia davvero €1000.

Il server deve recuperare il limite dal database e verificare.

---

# 48. XSS

Particolare attenzione alle richieste degli utenti.

Esempio:

> "Compra <script>..."

Il testo deve essere trattato come contenuto, mai come HTML.

Utilizzare:

* escaping;
* sanitizzazione dove necessario;
* Content Security Policy.

---

# 49. CSRF

Per operazioni web con cookie/sessione:

* SameSite;
* CSRF protection;
* controllo origin;
* token quando necessario.

Particolarmente importante per operazioni finanziarie.

---

# 50. Rate limiting

Applicarlo almeno a:

```text
login
OTP
password reset
commission creation
payment operations
locker opening
delegation verification
API pubbliche
```

Esempio:

> massimo 5 tentativi OTP / 15 minuti.

---

# 51. Brute force

Codici come:

> 123456

sono pericolosi.

Per PIN/OTP:

* limite tentativi;
* expiration;
* lockout temporaneo;
* rate limiting;
* invalidazione dopo utilizzo.

---

# 52. Notification security

Le notifiche push non devono contenere informazioni sensibili.

Non:

> "La Tachipirina di tuo padre è nel locker."

Meglio:

> "Una commissione è stata completata."

I dettagli sono disponibili dopo autenticazione.

---

# 53. Logging

I log non devono contenere:

* PAN;
* CVV;
* password;
* token;
* documenti;
* dati sanitari;
* contenuti completi delle richieste quando non necessari.

Da loggare invece:

```text
event
user_id
commission_id
timestamp
result
error_code
```

con identificativi pseudonimizzati quando possibile.

---

# 54. Data retention

Non conservare dati indefinitamente.

Definire policy separate per:

* commissioni;
* ricevute;
* deleghe;
* documenti;
* audit;
* log;
* immagini;
* dati finanziari.

Le informazioni necessarie per obblighi legali devono essere separate dai dati operativi eliminabili.

---

# 55. Backup

Neon deve essere configurato con una strategia di backup e recovery adeguata al livello di servizio.

Test fondamentali:

> Non basta avere backup.

Bisogna testare:

> **restore.**

Almeno periodicamente:

```text
Backup
 ↓
Restore database
 ↓
Verifica integrità
```

---

# 56. Disaster recovery

Definire:

### RPO

Quanto dato possiamo perdere?

### RTO

Quanto tempo possiamo impiegare per ripristinare il servizio?

Per un MVP possono essere relativamente permissivi.

Per il servizio reale devono essere definiti formalmente.

---

# 57. Supply chain

GitHub e npm introducono rischi.

Proteggere:

* dipendenze;
* GitHub Actions;
* secrets;
* branch principali.

Utilizzare:

* Dependabot;
* lockfile;
* dependency scanning;
* secret scanning;
* CodeQL;
* branch protection.

---

# 58. GitHub Actions security

Le pipeline CI/CD devono essere considerate parte della superficie d'attacco.

Un workflow compromesso potrebbe ottenere:

> DATABASE_URL
> PAYMENT_SECRET
> Vercel token

Quindi:

* permessi minimi;
* action versionate;
* niente secret inutili nelle PR;
* workflow separati per fork;
* protected environments;
* approvazione manuale per deployment sensibili.

---

# 59. Vercel security

Separare:

```text
Preview
Development
Production
```

I secret di produzione non devono essere disponibili alle Preview Deployment.

Una PR compromessa non deve poter accedere:

> al database production.

---

# 60. Neon security

Separare database/branch per ambiente.

```text
Production
Preview
Development
```

L'accesso production deve essere molto più ristretto.

Le migration production devono passare da pipeline controllata.

---

# 61. Test di sicurezza applicativa

Prima del pilota:

### Authentication

* bypass login;
* brute force;
* session hijacking;
* token replay;
* password reset abuse.

### Authorization

* accesso a commissioni di altri utenti;
* accesso a assistiti non autorizzati;
* privilege escalation;
* IDOR.

### Payments

* doppio pagamento;
* modifica importo;
* modifica commissione;
* replay webhook;
* carta oltre limite;
* carta scaduta.

### Locker

* apertura locker errato;
* riutilizzo PIN;
* replay QR;
* accesso dopo completamento.

### Deleghe

* modifica;
* replay;
* screenshot;
* delega scaduta;
* delega per commissionario diverso.

---

# 62. Test automatici di sicurezza

Esempi:

```text
TEST:
Guardian A cannot access Assisted B

TEST:
Commissioner cannot modify budget

TEST:
Commissioner cannot approve own commission

TEST:
Expired delegation cannot be verified

TEST:
Used delegation cannot be reused

TEST:
Virtual card cannot exceed commission budget

TEST:
Second payment is rejected

TEST:
Locker cannot be opened after authorization expires
```

Questi test devono essere parte della CI.

---

# 63. Penetration test

Prima del lancio commerciale sarebbe opportuno effettuare un penetration test indipendente.

Focus:

```text
Web application
API
Authentication
Authorization
Payment flows
Locker API
Delegation verification
Admin console
Mobile app
```

---

# 64. Threat modeling

Per ogni nuova funzionalità:

```text
Asset
 ↓
Threat
 ↓
Attack vector
 ↓
Impact
 ↓
Likelihood
 ↓
Mitigation
 ↓
Test
```

Esempio:

```text
ASSET
€40 budget

THREAT
commissioner uses funds fraudulently

VECTOR
stolen virtual card

IMPACT
€40 loss

MITIGATION
single-use/limited card

TEST
multiple transaction test
```

---

# 65. Security severity

Utilizzare almeno:

### Critical

Compromissione massiva o accesso a denaro.

### High

Accesso a dati personali sensibili o furto significativo.

### Medium

Violazione limitata.

### Low

Problemi senza impatto sostanziale.

Le vulnerabilità Critical/High devono bloccare il deployment.

---

# 66. Security incident

Deve esistere una procedura:

```text
Detection
 ↓
Containment
 ↓
Investigation
 ↓
Revocation
 ↓
Recovery
 ↓
Notification
 ↓
Post-mortem
```

Esempio:

> Sono state compromesse carte virtuali.

Azioni immediate:

1. bloccare tutte le carte interessate;
2. impedire nuove transazioni;
3. identificare commissioni coinvolte;
4. revocare sessioni sospette;
5. preservare log;
6. analizzare l'attacco;
7. gestire rimborsi/contestazioni;
8. valutare eventuali obblighi di notifica.

---

# 67. Kill switches

GPM deve poter disattivare rapidamente:

```text
ALL PAYMENTS
ALL VIRTUAL CARDS
ALL LOCKERS
ALL NEW COMMISSIONS
SPECIFIC COMMISSIONER
SPECIFIC GUARDIAN
SPECIFIC ASSISTED USER
```

Questo è particolarmente importante per un sistema che combina software e beni fisici.

---

# 68. Security dashboard

L'admin dovrebbe avere una sezione:

> **Security**

con:

* account sospetti;
* transazioni anomale;
* commissioni sospette;
* login falliti;
* dispositivi;
* carte attive;
* deleghe attive;
* locker access;
* dispute;
* incidenti.

---

# 69. Trust system e sicurezza

Il sistema di fiducia non deve diventare un meccanismo per bypassare la sicurezza.

Esempio:

> Luca ha 500 commissioni completate.

Non significa:

> Luca può spendere €500 senza controlli.

La reputazione riduce il rischio operativo, ma non sostituisce:

* autenticazione;
* autorizzazione;
* limiti;
* verifica.

---

# 70. Il problema del "trusted commissioner"

Anche un commissionario molto affidabile potrebbe essere:

* account compromesso;
* dispositivo rubato;
* persona sotto coercizione;
* vittima di phishing.

Per questo le operazioni finanziarie continuano a richiedere controlli.

La fiducia è:

> **un segnale di rischio**, non una credenziale.

---

# 71. Anti-frode comportamentale

Nel tempo GPM può costruire un profilo:

```text
Commissionario normalmente:
€10–30
1–3 commissioni/settimana
zona Milano nord
```

Anomalia:

```text
€300
5 commissioni
zona completamente diversa
nuovo dispositivo
```

→ sospensione preventiva o verifica.

Questo può essere successivamente implementato con sistemi antifrode più sofisticati.

---

# 72. Privacy by design

La sicurezza non consiste soltanto nel proteggere i dati.

Consiste anche nel **non raccoglierli inutilmente**.

Esempio:

Il commissionario deve sapere:

> "Ritira il cappotto presso Lavanderia Rossi."

Non deve sapere:

> "Mario ha 82 anni, vive solo e sua figlia vive a 30 km."

Il secondo dato non serve.

---

# 73. Minimizzazione dei dati per ruolo

```text
ASSISTITO
↓
proprie commissioni

TUTORE
↓
assistiti autorizzati

COMMISSIONARIO
↓
commissioni assegnate

ESERCENTE
↓
verifica delega

ADMIN
↓
solo dati necessari al compito
```

---

# 74. Sicurezza del sistema di comunicazione

La piattaforma dovrebbe impedire l'esposizione dei contatti personali.

Il commissionario non dovrebbe ottenere automaticamente:

* telefono;
* email;
* indirizzo completo dell'assistito.

Per la consegna al locker spesso non serve nemmeno conoscere l'indirizzo di casa.

---

# 75. Indirizzi

Gli indirizzi sono dati particolarmente delicati.

Dove possibile:

> **mostrare soltanto il punto necessario alla commissione.**

Per una lavanderia:

> indirizzo lavanderia.

Non:

> indirizzo dell'assistito.

Per il locker:

> posizione locker.

Questo riduce enormemente il rischio.

---

# 76. Threat model della commissione completa

```text
TUTORE
 │
 │ account compromesso?
 ▼
COMMISSIONE
 │
 │ manipolazione?
 ▼
MATCHING
 │
 │ falso commissioner?
 ▼
COMMISSIONARIO
 │
 ├── carta rubata?
 │
 ├── delega falsificata?
 │
 └── bene sottratto?
 │
 ▼
ESERCENTE
 │
 │ ritiro fraudolento?
 ▼
LOCKER
 │
 │ accesso abusivo?
 ▼
ASSISTITO
```

Ogni freccia rappresenta un controllo di sicurezza.

---

# 77. Security gates

Una commissione dovrebbe superare una serie di gate:

```text
GATE 1
Identità

GATE 2
Relazione tutore-assistito

GATE 3
Autorizzazione commissione

GATE 4
Validità commissionario

GATE 5
Budget

GATE 6
Carta virtuale

GATE 7
Delega

GATE 8
Locker

GATE 9
Chiusura

GATE 10
Pagamento commissionario
```

---

# 78. Principio di fail-safe

Quando un componente critico non è verificabile:

> **non procedere automaticamente.**

Esempi:

Pagamento non verificabile:

> blocca.

Delega non verificabile:

> rifiuta.

Locker non conferma deposito:

> non segnare completato.

Identità sospetta:

> sospendi.

Questo è preferibile a:

> "probabilmente va bene."

---

# 79. Principio di sicurezza finale

Il sistema deve assumere che:

* il client possa essere compromesso;
* un account possa essere rubato;
* un commissionario possa essere fraudolento;
* una carta possa essere copiata;
* un QR possa essere fotografato;
* un webhook possa essere ripetuto;
* un amministratore possa sbagliare;
* un database possa essere esposto.

La sicurezza deriva quindi dalla **combinazione di più barriere indipendenti**, non dalla fiducia in un singolo componente.

---

# 80. Architettura di sicurezza finale

```text
                         ┌──────────────────┐
                         │     USER         │
                         └────────┬─────────┘
                                  │
                            MFA / Passkey
                                  │
                                  ▼
                         ┌──────────────────┐
                         │     VERCEL       │
                         │                  │
                         │ Auth             │
                         │ Authorization    │
                         │ Rate limiting    │
                         │ Validation       │
                         └────────┬─────────┘
                                  │
                    ┌─────────────┼─────────────┐
                    │             │             │
                    ▼             ▼             ▼
                 COMMISSION     TRUST        PAYMENTS
                    │                           │
                    │                      Provider
                    │                           │
                    │                    Virtual Card
                    │                           │
                    └─────────────┬─────────────┘
                                  │
                             AUDIT LOG
                                  │
                         ┌────────┴────────┐
                         ▼                 ▼
                    DELEGATION          LOCKER
                         │                 │
                         ▼                 ▼
                    ESERCENTE          ASSISTITO
```

---

# 81. Priorità assolute per l'MVP

Non tutte le misure devono essere implementate contemporaneamente.

## P0 — obbligatorie

* MFA tutore;
* verifica identità commissionario;
* authorization server-side;
* state machine;
* audit trail;
* limiti di budget;
* virtual card gestita da provider;
* nessun PAN/CVV nel database GPM;
* webhook verificati;
* idempotency;
* deleghe firmate;
* token temporanei;
* locker authorization;
* rate limiting;
* secret management;
* backup;
* logging sicuro.

## P1

* anomaly detection;
* device management;
* revoca remota;
* kill switch;
* security dashboard;
* transaction monitoring;
* gestione avanzata dispute.

## P2

* fraud detection comportamentale;
* risk scoring;
* automazione;
* penetration testing continuo;
* hardware security avanzata;
* sistemi antifrode ML.

---

# 82. Test di accettazione security-critical

Prima di mettere GPM in mano a utenti reali devono passare almeno questi test:

```text
[ ] Un tutore non può accedere a un altro assistito
[ ] Un commissionario non può vedere commissioni non assegnate
[ ] Un commissionario non può modificare il budget
[ ] Un commissionario non può modificare la richiesta
[ ] Un assistito non può impersonare un tutore
[ ] Un tutore non verificato non può effettuare operazioni sensibili
[ ] Una carta non può superare il budget
[ ] Una carta scaduta non funziona
[ ] Una carta revocata non funziona
[ ] Una transazione non può essere eseguita due volte
[ ] Un webhook duplicato non produce un secondo pagamento
[ ] Una delega scaduta viene rifiutata
[ ] Una delega utilizzata non può essere riutilizzata
[ ] Una delega per Luca non funziona per Marco
[ ] Un QR non permette accesso ad altri locker
[ ] Un locker non può essere aperto dopo la scadenza
[ ] Il commissionario non riceve dati personali inutili
[ ] Le notifiche non espongono dati sensibili
[ ] Le Preview Vercel non accedono ai secret production
[ ] I log non contengono dati finanziari sensibili
[ ] Un admin non può effettuare operazioni fuori dal proprio ruolo
[ ] Le sessioni possono essere revocate
[ ] Un account compromesso può essere bloccato rapidamente
[ ] È possibile bloccare tutte le carte attive
[ ] È possibile bloccare globalmente i pagamenti
[ ] È possibile ripristinare il database da backup
```

---

# 83. Obiettivo di sicurezza

L'obiettivo non è rendere GPM "impossibile da attaccare".

È fare in modo che:

> **un singolo errore o compromissione non possa trasformarsi facilmente in una perdita di denaro, in un furto di identità o in un rischio fisico per una persona vulnerabile.**

La struttura ideale è quindi:

**identità verificata → privilegi minimi → commissione limitata → budget limitato → carta temporanea → delega temporanea → locker autorizzato → audit completo → possibilità di revoca immediata.**

Questa catena è particolarmente importante per GPM perché il sistema non gestisce soltanto dati digitali: **un'autorizzazione digitale produce un'azione nel mondo fisico.**


# Proposta integrazione specifica sui pagamenti

## 1. Obiettivo

GPM utilizza un sistema di pagamento basato su:

* carta virtuale temporanea;
* carta associata al metodo di pagamento del tutore;
* preautorizzazione dell'importo massimo;
* utilizzo limitato alla singola commissione;
* validità temporale limitata;
* vincoli sul merchant e sulla categoria commerciale;
* blocco esplicito di categorie di pagamento incompatibili con GPM;
* cattura esclusivamente dell'importo effettivamente necessario.

Il commissionario non riceve quindi un budget monetario.

Riceve esclusivamente una **credenziale temporanea per effettuare una specifica operazione autorizzata**.

---

# 2. Principio fondamentale

Il sistema deve applicare contemporaneamente:

```text
COMMISSIONE
     +
IMPORTO MASSIMO
     +
FINESTRA TEMPORALE
     +
NUMERO TRANSAZIONI
     +
MERCHANT / CATEGORIA
     +
AREA GEOGRAFICA
     +
CATEGORIE VIETATE
```

Una transazione è consentita soltanto se soddisfa **tutti** i vincoli.

---

# 3. Esempio

Il tutore autorizza:

> Compra 2 L di latte, massimo €5, consegna al locker entro le 19:00.

GPM crea:

```text
Commissione: #4821
Importo massimo: €5
Validità: 14:00–19:00
Transazioni: 1
Tipo: acquisto fisico
Merchant: supermercato
Paese: Italia
```

Il pagamento può quindi essere effettuato esclusivamente entro queste condizioni.

---

# 4. Carta virtuale temporanea

Ogni commissione con acquisto genera una carta distinta.

```text
Carta #C82731
       │
       └── Commissione #4821
```

La carta deve essere:

* temporanea;
* monouso;
* limitata economicamente;
* legata alla commissione;
* revocabile;
* automaticamente invalidata al completamento o alla scadenza.

Non deve esistere un:

> "saldo GPM del commissionario".

---

# 5. Preautorizzazione

La carta viene associata a una preautorizzazione.

Esempio:

```text
Importo massimo: €50
Preautorizzazione: €50
```

Se l'acquisto costa €43,80:

```text
Cattura: €43,80
Rilascio: €6,20
```

Il residuo non rimane a disposizione del commissionario.

---

# 6. Vincoli della transazione

Ogni autorizzazione deve poter definire:

```text
max_amount
valid_from
valid_until
max_transactions
allowed_merchant
allowed_mcc
allowed_country
allowed_channel
blocked_mcc
blocked_country
```

Non tutti i provider offriranno necessariamente tutti questi parametri, ma GPM deve considerarli requisiti preferenziali nella scelta del provider.

---

# 7. Merchant specifico

Quando il merchant è noto, deve essere possibile vincolare il pagamento.

Esempio:

```text
Commissione:
Compra farmaco

Merchant consentito:
Farmacia Rossi

Importo massimo:
€20

Transazioni:
1

Paese:
Italia
```

Tentativo presso un merchant diverso:

> **DENIED**

---

# 8. Categorie di merchant

Quando il merchant non è predeterminabile, si può utilizzare il **Merchant Category Code (MCC)** o un meccanismo equivalente del payment provider.

Esempio:

```text
ALLOWED
Supermercati
Farmacie
Negozi alimentari

BLOCKED
Benzinai
Scommesse
Casinò
Gaming
Trasferimenti di denaro
```

Il sistema deve preferire restrizioni a livello provider rispetto a semplici controlli GPM.

---

# 9. Categorie vietate globalmente

GPM deve prevedere una **denylist globale** applicata a tutte le carte virtuali.

Tra le categorie da escludere:

### Pagamenti online

```text
E-commerce
Digital goods
Online marketplaces
Servizi digitali
```

L'obiettivo è che la carta sia utilizzabile esclusivamente per commissioni fisiche autorizzate.

> Nota: la possibilità tecnica di distinguere sempre "online" e "fisico" dipende dal payment provider e dai dati disponibili sulla transazione. Il requisito deve quindi essere verificato prima della scelta del provider.

---

### Carburante

Bloccare:

```text
Benzinai
Distributori
Fuel stations
Automated fuel pumps
```

Questo evita utilizzi impropri della carta per carburante.

---

### Scommesse e gioco d'azzardo

Bloccare:

```text
Scommesse sportive
Casinò
Poker
Lotterie
Gaming d'azzardo
Gambling
```

---

### Trasferimento di denaro

Bloccare:

```text
Money transfer
Cash advance
ATM
Wire transfer
Servizi assimilabili
```

La carta non deve poter essere trasformata in denaro liquido.

---

### Criptovalute e strumenti finanziari

Bloccare, salvo eventuali future eccezioni esplicitamente autorizzate:

```text
Cryptocurrency exchanges
Broker
Trading platforms
Acquisto titoli
Servizi finanziari non pertinenti
```

---

### Servizi per adulti

Bloccare le categorie commerciali pertinenti.

---

### Merchant esteri

Per il modello standard GPM:

```text
allowed_country = IT
```

Qualunque transazione effettuata presso un merchant estero viene rifiutata.

---

# 10. Lista iniziale delle categorie vietate

La policy globale può partire da:

```text
BLOCKED

Online / e-commerce
ATM / cash withdrawal
Money transfer
Gambling / betting / casino
Cryptocurrency
Financial services
Fuel / petrol stations
Adult services
High-risk digital goods
Foreign merchants
```

La lista deve essere mantenuta come **policy centrale di GPM**, ma implementata materialmente anche presso il payment provider quando possibile.

---

# 11. Denylist prima dell'allowlist

Il modello di sicurezza preferito è:

> **default deny**

Non:

> "tutto è consentito tranne ciò che abbiamo ricordato di bloccare."

La transazione deve essere consentita solo se:

```text
merchant allowed
AND
country allowed
AND
channel allowed
AND
MCC allowed
AND
amount allowed
AND
time allowed
AND
transaction count allowed
```

---

# 12. Policy globale + policy della commissione

Devono esistere due livelli.

### Policy GPM

Applicata a tutte le carte.

```text
NO gambling
NO ATM
NO foreign
NO fuel
NO crypto
NO online
```

### Policy della singola commissione

Esempio:

```text
Commissione #4821

Allowed MCC:
Grocery

Allowed merchant:
Supermercato Rossi

Max:
€20

Country:
IT

Valid:
14:00–19:00

Transactions:
1
```

La policy della commissione può essere **più restrittiva**, mai meno restrittiva della policy globale.

---

# 13. Nessuna possibilità di override dal commissionario

Il commissionario non può:

* cambiare merchant;
* cambiare paese;
* modificare MCC;
* aumentare il budget;
* prolungare la validità;
* trasformare la carta in una carta generica.

Nemmeno il frontend deve poterlo fare.

Ogni modifica deve passare dal tutore e dal backend.

---

# 14. Modifica della commissione

Se il tutore cambia:

> "Compra il latte al supermercato Rossi"

in:

> "Compra il latte alla Coop"

non deve essere modificata silenziosamente l'autorizzazione esistente.

Procedura:

```text
AUTHORIZATION #1
       ↓
RELEASE / CANCEL
       ↓
AUTHORIZATION #2
       ↓
NEW CARD / UPDATED TOKEN
```

La precedente credenziale viene invalidata.

---

# 15. Aumento del budget

Esempio:

```text
Autorizzato: €5
Prezzo: €7
```

Il pagamento viene rifiutato.

Il commissionario può chiedere:

> "Il prodotto costa €7."

Il tutore può autorizzare una nuova somma.

Non deve esistere un meccanismo attraverso il quale il commissionario possa semplicemente "sforare".

---

# 16. Transazione non prevista

Scenario:

Il commissionario utilizza la carta presso un supermercato ma acquista anche:

> €25 di prodotti personali.

Se il totale supera il limite:

```text
€30 > €5
```

→ **DENIED**

Il limite economico deve essere verificato dal payment provider.

---

# 17. Merchant non autorizzato

Scenario:

La carta è stata generata per:

> Farmacia Rossi.

Il commissionario tenta di utilizzarla:

> Amazon.

Risultato:

```text
TRANSACTION DENIED
```

Se il provider non consente merchant locking, GPM deve compensare con altri vincoli e considerare questa limitazione nella scelta del provider.

---

# 18. Utilizzo online

Una carta destinata ad acquisti fisici deve essere configurata, quando tecnicamente possibile, per rifiutare:

```text
e-commerce
card-not-present
```

Questo riduce drasticamente il rischio che i dati della carta possano essere utilizzati da remoto.

La protezione deve essere implementata **a livello del provider**, non semplicemente nell'app.

---

# 19. Transazioni estere

Policy standard:

```text
Country = IT
```

Tentativo:

```text
France
Germany
Switzerland
USA
etc.
```

→ **DENIED**

Eventuali commissioni internazionali devono essere una funzionalità separata e richiedere una policy specifica.

---

# 20. Distributori automatici

Particolare attenzione deve essere riservata ai terminali automatici.

Esempio:

```text
fuel pump
vending machine
ATM
```

Queste categorie possono avere modalità di autorizzazione particolari e preautorizzazioni proprie.

GPM deve quindi utilizzare una policy conservativa:

> **bloccare le categorie MCC associate a cash withdrawal, fuel e terminali ad alto rischio.**

---

# 21. Preautorizzazioni anomale

Alcuni merchant possono effettuare preautorizzazioni superiori al prezzo finale.

Questo può creare problemi.

GPM deve verificare:

```text
authorization amount
capture amount
final amount
```

e impedire che un merchant possa catturare un importo superiore a quanto autorizzato.

---

# 22. No cash

La carta GPM non deve poter essere utilizzata per ottenere contante.

Bloccare:

* ATM;
* cash advance;
* cash withdrawal;
* money transfer;
* servizi equivalenti.

Il commissionario deve poter ottenere esclusivamente:

> beni o servizi autorizzati.

Mai:

> denaro.

---

# 23. Geografia

Oltre al paese, quando tecnicamente possibile può essere utilizzata una restrizione geografica.

Esempio:

```text
Country: IT
Region: Lombardia
```

Tuttavia il geofencing deve essere considerato un controllo secondario.

La posizione fisica del telefono del commissionario non deve essere considerata una prova sufficiente della posizione del merchant.

La fonte primaria deve essere il dato del payment provider.

---

# 24. Carta rubata

Se un attaccante ottiene i dati della carta:

```text
PAN
CVV
expiry
```

deve comunque incontrare tutti i controlli:

```text
merchant
MCC
country
channel
amount
time
transaction count
```

La carta deve inoltre scadere rapidamente.

L'obiettivo è rendere il credential rubato di valore minimo.

---

# 25. Carta compromessa

Il tutore deve poter eseguire:

> **Blocca pagamento**

con effetto immediato.

Il sistema deve:

1. bloccare la carta;
2. revocare l'autorizzazione;
3. impedire nuove transazioni;
4. registrare l'evento;
5. notificare il tutore.

---

# 26. Kill switch globale

GPM deve poter disabilitare:

```text
ALL CARD ISSUANCE
ALL CARD AUTHORIZATIONS
ALL CAPTURES
ALL ACTIVE CARDS
```

Questo permette di reagire rapidamente a:

* vulnerabilità del provider;
* compromissione API;
* frode sistemica;
* errore di configurazione;
* incidente di sicurezza.

---

# 27. Separazione del rischio

La sicurezza deve essere distribuita tra:

```text
TUTORE
   ↓
GPM
   ↓
PAYMENT PROVIDER
   ↓
MERCHANT
```

Nessun singolo componente dovrebbe poter aggirare tutti i controlli.

In particolare:

> **il frontend GPM non deve essere una fonte di verità finanziaria.**

---

# 28. Il payment provider come seconda barriera

GPM deve applicare i propri controlli:

```text
GPM
 ↓
commission rules
 ↓
budget
 ↓
authorization
```

Il payment provider deve applicare:

```text
Provider
 ↓
amount limit
 ↓
merchant restrictions
 ↓
MCC restrictions
 ↓
country restrictions
 ↓
channel restrictions
 ↓
transaction limit
```

In caso di compromissione di GPM, la seconda barriera deve continuare a funzionare.

---

# 29. Reconciliation

GPM deve confrontare periodicamente:

```text
GPM
   ↕
Payment Provider
```

per individuare:

* transazioni mancanti;
* transazioni duplicate;
* importi inattesi;
* merchant inattesi;
* paese inatteso;
* catture superiori all'autorizzazione;
* autorizzazioni ancora aperte.

---

# 30. Audit

Per ogni pagamento:

```text
Commission ID
Guardian ID
Commissioner ID
Virtual Card ID
Authorization ID
Merchant
MCC
Country
Amount authorized
Amount captured
Timestamp
Status
```

I dati della carta vera e propria non devono essere inseriti nei log.

---

# 31. Test di sicurezza specifici

Prima del lancio devono essere testati almeno:

### Importo

```text
€5 autorizzati
→ €5 OK
→ €5,01 DENIED
```

### Seconda transazione

```text
€5 autorizzati
→ transazione #1 OK
→ transazione #2 DENIED
```

### Merchant

```text
Merchant autorizzato → OK
Merchant diverso → DENIED
```

### MCC

```text
Supermercato → OK
Benzinaio → DENIED
Scommesse → DENIED
ATM → DENIED
```

### Country

```text
Italia → OK
Francia → DENIED
USA → DENIED
```

### Online

```text
POS fisico → OK
E-commerce → DENIED
```

### Scadenza

```text
14:00–19:00
18:59 → OK
19:01 → DENIED
```

### Revoca

```text
REVOCATED
→ qualsiasi nuova transazione DENIED
```

---

# 32. Test di bypass

È particolarmente importante tentare di aggirare i vincoli modificando:

* request HTTP;
* JSON;
* ID commissione;
* ID carta;
* importo;
* merchant;
* country;
* timestamp;
* ruolo dell'utente.

Il risultato deve essere sempre:

> il backend rifiuta l'operazione.

---

# 33. Requisito per la scelta del payment provider

La selezione del provider deve quindi includere una **security capability matrix**.

| Funzionalità               | Priorità |
| -------------------------- | -------: |
| Virtual card               |       P0 |
| Preauthorization           |       P0 |
| Authorization/capture      |       P0 |
| Spending limit             |       P0 |
| Expiration                 |       P0 |
| Revocation                 |       P0 |
| Single transaction         |       P0 |
| Webhook firmati            |       P0 |
| MCC restrictions           |       P0 |
| Country restrictions       |       P0 |
| Merchant restrictions      |    P1/P0 |
| Online/offline restriction |       P1 |
| Cash/ATM blocking          |       P0 |
| Fuel blocking              |       P0 |
| Gambling blocking          |       P0 |
| API idempotency            |       P0 |
| Fraud monitoring           |       P1 |

---

# 34. Principio "zero residual value"

Al termine della commissione:

```text
Carta
   ↓
Transazione
   ↓
Cattura
   ↓
Residuo rilasciato
   ↓
Carta revocata
```

Il commissionario deve terminare la commissione con:

```text
valore residuo della carta = €0
```

Non deve esistere un credito recuperabile o riutilizzabile.

---

# 35. Architettura aggiornata

```text
                         TUTORE
                            │
                     approva €50
                            │
                            ▼
                    ┌──────────────┐
                    │     GPM      │
                    │              │
                    │ Commission   │
                    │ Authorization│
                    └──────┬───────┘
                           │
                    Payment API
                           │
                           ▼
                ┌─────────────────────┐
                │  PAYMENT PROVIDER   │
                │                     │
                │ Preauthorization    │
                │ Virtual Card        │
                │ Amount Limit        │
                │ Merchant Lock       │
                │ MCC Allow/Deny      │
                │ Country Lock        │
                │ Channel Lock        │
                │ Transaction Limit   │
                │ Expiration          │
                └──────────┬──────────┘
                           │
                     temporary card
                           │
                           ▼
                    COMMISSIONARIO
                           │
                           ▼
                       ESERCENTE
```

---

# 36. Regola definitiva

Una transazione GPM è valida soltanto se:

```text
COMMISSIONE VALIDA
        AND
TUTORE AUTORIZZATO
        AND
CARTA VALIDA
        AND
IMPORTO ≤ LIMITE
        AND
TRANSAZIONE ≤ NUMERO CONSENTITO
        AND
MERCHANT CONSENTITO
        AND
MCC CONSENTITO
        AND
COUNTRY CONSENTITO
        AND
CHANNEL CONSENTITO
        AND
NON PRESENTE IN DENYLIST
        AND
FINESTRA TEMPORALE VALIDA
```

Altrimenti:

> **TRANSACTION DENIED**

---

# 37. Filosofia del sistema

La carta virtuale GPM non deve essere concepita come:

> **una carta di pagamento affidata a un estraneo.**

Deve essere concepita come:

> **un'autorizzazione digitale temporanea a compiere una specifica azione finanziaria per conto di una persona assistita.**

Il commissionario possiede quindi il **minimo potere operativo necessario**.

La combinazione di:

**preautorizzazione + carta usa e getta + importo massimo + una sola transazione + merchant/MCC restriction + country restriction + blocco dei canali online + denylist globale + scadenza + revoca immediata**

costituisce la barriera principale contro l'utilizzo improprio dei fondi GPM.


Sì. Lo integrerei come **sistema antifrode e trust & safety**, evitando però una penalizzazione automatica sulla base della sola segnalazione: la prima segnalazione deve attivare una **sospensione preventiva e una verifica**, non una condanna.

### Integrazione alla specifica

# Sistema antifrode, sospensione e gestione degli abusi

## 1. Obiettivo

GPM deve prevedere un sistema centralizzato per gestire:

* tentativi di frode;
* uso improprio della piattaforma;
* identità false;
* commissioni fraudolente;
* pagamenti fraudolenti;
* manipolazione delle commissioni;
* abuso dei sistemi di pagamento;
* false contestazioni;
* uso improprio del ruolo di tutore;
* comportamenti fraudolenti del commissionario;
* comportamenti fraudolenti dell'utente assistito.

Il sistema deve applicarsi a tutti i ruoli:

```text
UTENTE
TUTORE
COMMISSIONARIO
```

---

# 2. Principio fondamentale

Una **segnalazione non equivale a una frode accertata**.

Il primo evento deve attivare:

> **sospensione preventiva + verifica interna**

e non il blocco definitivo automatico.

Flusso:

```text
SEGNALAZIONE
     ↓
SOSPENSIONE PREVENTIVA
     ↓
VERIFICA INTERNA
     ↓
┌───────────────┐
│               │
FRODE           NESSUNA FRODE
CONFERMATA      CONFERMATA
│               │
▼               ▼
BLOCCO          RIATTIVAZIONE
DEFINITIVO
```

---

# 3. Sospensione preventiva

Al primo evento classificato come potenzialmente fraudolento GPM può sospendere temporaneamente l'account.

Durante la sospensione:

### Utente

Non può:

* creare nuove commissioni;
* effettuare nuovi pagamenti;
* modificare commissioni finanziarie;
* utilizzare crediti o funzionalità economiche.

### Tutore

Non può:

* creare nuove commissioni;
* autorizzare pagamenti;
* modificare autorizzazioni finanziarie;
* generare nuove carte virtuali.

### Commissionario

Non può:

* accettare nuove commissioni;
* visualizzare nuove informazioni sugli assistiti;
* utilizzare carte virtuali;
* completare commissioni finanziarie.

Le commissioni già in corso devono essere gestite separatamente per evitare di lasciare una persona fragile senza assistenza.

---

# 4. Protezione dell'assistito

La sospensione del tutore o del commissionario non deve automaticamente danneggiare l'utente fragile.

Esempio:

```text
TUTORE A
   ↓
Utente fragile
   ↓
Commissione in corso
```

Se Tutore A viene sospeso:

```text
Tutore A → SUSPENDED
             │
             ▼
     Commissione #4821
             │
       ┌─────┴─────┐
       ▼           ▼
    sicura       rischio
       │           │
       ▼           ▼
   completa      blocca
```

GPM deve poter trasferire la gestione a un altro tutore autorizzato o annullare la commissione in sicurezza.

---

# 5. Tipologie di frode

Il sistema deve classificare gli eventi.

## Frode finanziaria

Esempi:

* acquisti personali con carta GPM;
* tentativi di superamento del budget;
* utilizzo della carta fuori dalla commissione;
* tentativi di ottenere denaro;
* manipolazione di ricevute;
* doppia richiesta di rimborso.

## Frode identitaria

Esempi:

* identità falsa;
* account multipli;
* impersonificazione;
* documenti falsificati;
* account creati per aggirare un blocco.

## Frode nella commissione

Esempi:

* dichiarare di aver completato una commissione mai eseguita;
* falsificare un ritiro;
* dichiarare un acquisto diverso da quello effettuato;
* appropriazione di beni acquistati.

## Frode del tutore

Esempi:

* utilizzo non autorizzato del metodo di pagamento;
* creazione fraudolenta di commissioni;
* manipolazione delle richieste dell'assistito;
* utilizzo del sistema per ottenere beni o servizi per sé.

## Frode dell'utente

Esempi:

* falsa dichiarazione;
* richieste fraudolente;
* contestazioni intenzionalmente false;
* tentativi di ottenere rimborsi indebiti.

---

# 6. Livelli di gravità

Non tutte le anomalie devono essere trattate allo stesso modo.

### Livello 1 — Anomalia

Esempio:

> ricevuta poco leggibile.

Nessuna sospensione automatica.

Richiesta di chiarimento.

### Livello 2 — Comportamento sospetto

Esempio:

> transazione incompatibile con la commissione.

Possibile sospensione preventiva.

### Livello 3 — Potenziale frode

Esempio:

> utilizzo della carta presso un merchant non compatibile attraverso un tentativo deliberato di bypass.

Sospensione preventiva + verifica.

### Livello 4 — Frode confermata

Esempio:

> evidenza chiara di appropriazione o utilizzo fraudolento dei fondi.

Blocco definitivo.

---

# 7. Verifica interna

La verifica deve essere effettuata da un processo separato dal normale flusso operativo.

Devono essere analizzati, quando pertinenti:

* log della commissione;
* messaggi;
* autorizzazioni del tutore;
* eventi della carta;
* dati della transazione;
* merchant;
* MCC;
* importo;
* timestamp;
* ricevuta;
* eventi del locker;
* cronologia dell'account;
* eventuali precedenti.

Il sistema deve conservare una **catena di evidenze**.

---

# 8. Decisione

Ogni caso deve terminare con uno stato esplicito:

```text
OPEN
UNDER_REVIEW
CLEARED
WARNING
SUSPENDED
FRAUD_CONFIRMED
PERMANENTLY_BLOCKED
```

Non utilizzare soltanto:

```text
user.banned = true
```

---

# 9. Frode confermata

Se la frode viene confermata:

```text
FRAUD_CONFIRMED
       ↓
PERMANENTLY_BLOCKED
```

Il blocco deve impedire:

* nuovo accesso;
* nuove commissioni;
* nuovi pagamenti;
* nuova emissione di carte;
* nuova registrazione con lo stesso account.

---

# 10. Prevenzione della ricreazione dell'account

Un utente bloccato non deve poter semplicemente:

```text
delete account
     ↓
create new account
```

Il sistema deve utilizzare segnali antifrode e identificativi tecnici appropriati per individuare tentativi di rientro.

Questo deve essere progettato nel rispetto della normativa applicabile sulla protezione dei dati.

Non è necessario conservare più dati personali del necessario.

---

# 11. Blocco della carta

In caso di frode finanziaria:

```text
FRODE CONFERMATA
       ↓
REVOKE ALL ACTIVE CARDS
       ↓
RELEASE / CANCEL AUTHORIZATIONS
       ↓
BLOCK NEW CARD ISSUANCE
```

Il blocco deve essere effettuato anche presso il payment provider.

---

# 12. Blocco delle commissioni

Se il soggetto è un commissionario:

```text
Commissionario
     ↓
Frode confermata
     ↓
Permanent block
     ↓
Tutte le commissioni attive
     ↓
CANCEL / REASSIGN
```

Le commissioni ancora in corso devono essere assegnate ad altri commissionari quando possibile.

---

# 13. Tutore fraudolento

Il tutore rappresenta un ruolo particolarmente delicato perché può autorizzare transazioni finanziarie.

In caso di frode confermata:

```text
Tutor
 ↓
Block financial authority
 ↓
Revoke active authorizations
 ↓
Revoke virtual cards
 ↓
Permanent block
```

Se l'utente fragile ha altri tutori autorizzati, questi possono continuare a gestirne il profilo.

---

# 14. Utente fraudolento

Se la frode è attribuita direttamente all'utente:

```text
User
 ↓
Suspend
 ↓
Investigation
 ↓
Confirmed fraud
 ↓
Permanent block
```

La sospensione dell'utente non deve necessariamente comportare la sospensione degli altri soggetti collegati, se non esistono evidenze che li coinvolgano.

---

# 15. Commissionario fraudolento

Il commissionario rappresenta un rischio particolare perché può avere accesso fisico a:

* beni;
* esercizi commerciali;
* locker;
* credenziali temporanee di pagamento.

In caso di frode confermata:

```text
REVOKE COMMISSIONER
        +
REVOKE ACTIVE CARDS
        +
CANCEL ACTIVE JOBS
        +
BLOCK ACCOUNT
```

Eventuali compensi già maturati devono essere gestiti separatamente dalle somme oggetto di contestazione.

---

# 16. Segnalazioni degli utenti

Utente, tutore ed eventualmente esercente devono poter segnalare:

> **Segnala problema / sospetta frode**

La segnalazione deve generare un caso antifrode.

Non deve generare automaticamente:

> "utente colpevole".

---

# 17. False segnalazioni

Anche il sistema di segnalazione può essere abusato.

GPM deve quindi monitorare:

* segnalazioni ripetute;
* segnalazioni sistematicamente false;
* tentativi di danneggiare un commissionario;
* segnalazioni coordinate tra account.

Anche l'abuso deliberato del sistema di segnalazione può diventare un evento di trust & safety.

---

# 18. Sistema di rischio

GPM può utilizzare un risk score interno.

Esempio:

```text
RISK SCORE

0–20     normale
21–50    monitoraggio
51–70    verifica
71–90    sospensione
91–100   blocco / review prioritaria
```

Il punteggio non deve essere mostrato agli utenti.

Non deve essere l'unico elemento utilizzato per determinare una frode.

Deve servire principalmente a:

> **prioritizzare le verifiche.**

---

# 19. Nessun "rating sociale" pubblico

Il sistema antifrode deve essere separato dal sistema di fiducia del commissionario.

Un commissionario non deve vedere:

> "Michele = rischio 73."

L'utente deve vedere soltanto informazioni utili alla fiducia, ad esempio:

* commissioni completate;
* anzianità sulla piattaforma;
* area di attività;
* eventuali badge;
* numero di assistiti serviti.

Gli indicatori antifrode devono rimanere riservati.

---

# 20. Azione legale

In caso di frode confermata, GPM deve poter conservare le evidenze necessarie e, quando appropriato:

* collaborare con payment provider;
* avviare procedure di recupero;
* contestare transazioni;
* fornire documentazione alle autorità competenti;
* intraprendere azioni legali.

L'azione legale non deve essere automatica per ogni violazione.

Deve essere valutata in funzione di:

* gravità;
* importo;
* intenzionalità;
* reiterazione;
* danno arrecato;
* obblighi normativi.

---

# 21. Preservazione delle evidenze

Quando viene aperto un caso:

```text
CASE #92831
```

GPM deve congelare gli elementi rilevanti:

```text
Commission
Payment
Authorization
Messages
Audit logs
Receipt
Locker events
Account events
```

Gli elementi devono essere protetti da modifiche successive.

---

# 22. Separazione delle responsabilità

La persona che effettua normalmente la moderazione operativa non dovrebbe poter:

* cancellare le evidenze;
* modificare retroattivamente i log;
* modificare una transazione finanziaria;
* rimuovere un blocco senza autorizzazione.

Le operazioni sensibili devono richiedere:

* permessi specifici;
* audit;
* eventualmente approvazione di secondo livello.

---

# 23. Ricorso

Un blocco definitivo deve prevedere, quando appropriato, un meccanismo di contestazione.

L'utente può richiedere:

> **Revisione della decisione**

Il caso viene riesaminato.

Questo è particolarmente importante perché GPM opera in un contesto nel quale possono verificarsi:

* errori di identificazione;
* transazioni anomale legittime;
* errori del merchant;
* errori del payment provider;
* incomprensioni nella commissione.

---

# 24. Principio "one strike → review", non "one strike → ban"

La regola fondamentale è:

```text
PRIMA SEGNALAZIONE
       ↓
SUSPEND
       ↓
REVIEW
       ↓
┌───────────────────────┐
│                       │
FRODE                   │
CONFERMATA              │
│                       │
▼                       ▼
BAN                    CLEAR
```

Quindi:

> **la prima segnalazione produce una sospensione e una verifica, non automaticamente un blocco definitivo.**

---

# 25. Reiterazione

Se la verifica non conferma la frode ma vengono rilevate ripetute anomalie:

```text
ANOMALIA
   ↓
ANOMALIA
   ↓
ANOMALIA
   ↓
ENHANCED REVIEW
```

GPM può applicare limitazioni progressive.

Esempio:

```text
warning
   ↓
temporary restriction
   ↓
enhanced verification
   ↓
suspension
```

Questo evita di trattare allo stesso modo un errore occasionale e un comportamento sistematico.

---

# 26. Frodi particolarmente gravi

Alcuni eventi possono richiedere una risposta immediata senza attendere il normale processo di revisione, ad esempio:

* furto deliberato di fondi;
* utilizzo intenzionale della carta per ottenere contante;
* appropriazione di beni di una persona fragile;
* impersonificazione deliberata;
* compromissione sistematica degli account;
* frode organizzata;
* minaccia o ricatto;
* tentativo di aggirare deliberatamente i sistemi di sicurezza.

In questi casi:

```text
IMMEDIATE FREEZE
       ↓
SECURITY REVIEW
       ↓
FRAUD INVESTIGATION
```

---

# 27. Protezione dei dati

Il sistema antifrode deve applicare il principio:

> **conservare le evidenze necessarie, non tutti i dati possibili.**

I dati finanziari devono essere referenziati tramite gli identificativi del payment provider.

GPM non deve conservare inutilmente:

* PAN;
* CVV;
* dati completi della carta;
* documenti non necessari;
* informazioni personali non pertinenti.

---

# 28. Notifiche

In caso di sospensione:

> "Il tuo account è temporaneamente sospeso mentre verifichiamo un'attività anomala."

Non devono essere rivelati dettagli che consentano di aggirare i sistemi antifrode.

In caso di riattivazione:

> "La verifica è stata completata e il tuo account è nuovamente attivo."

In caso di blocco definitivo:

> "Il tuo account è stato definitivamente sospeso a seguito della verifica di una violazione grave delle regole della piattaforma."

---

# 29. Sistema indipendente

Il modulo deve essere separato logicamente dal core delle commissioni.

```text
                 GPM
                  │
       ┌──────────┴──────────┐
       ▼                     ▼
 COMMISSION ENGINE       TRUST & SAFETY
                             │
                     ┌───────┴────────┐
                     ▼                ▼
                  FRAUD           ACCOUNT
                DETECTION        ENFORCEMENT
                     │                │
                     └───────┬────────┘
                             ▼
                           AUDIT
```

---

# 30. Principio finale

GPM deve essere costruito secondo una logica di:

> **fiducia verificata, non fiducia cieca.**

Il sistema permette alle persone di collaborare senza conoscersi personalmente, ma ogni partecipante deve sapere che:

1. le azioni sono tracciabili;
2. il denaro è fortemente limitato;
3. le credenziali sono temporanee;
4. i comportamenti anomali vengono verificati;
5. una frode confermata comporta l'esclusione definitiva;
6. nei casi gravi GPM può tutelare i propri utenti anche attraverso strumenti legali.

La sicurezza deve quindi funzionare su più livelli:

```text
PREVENZIONE
     ↓
LIMITAZIONE DEL DANNO
     ↓
RILEVAMENTO
     ↓
SOSPENSIONE
     ↓
VERIFICA
     ↓
DECISIONE
     ↓
BLOCCO / RIATTIVAZIONE
     ↓
EVENTUALE AZIONE LEGALE
```

L'obiettivo non è creare una piattaforma punitiva, ma fare in modo che **il costo e la possibilità di una frode siano molto inferiori ai benefici ottenibili**, proteggendo contemporaneamente utenti fragili, tutori, commissionari ed esercenti.


