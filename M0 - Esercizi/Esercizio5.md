# Esercizio 5 - Censimento dei sistemi di intelligenza artificiale di una giornata

| Sistema / servizio | Decisione che prende (verbo + oggetto) | Dati in ingresso | Tipo di apprendimento e perché | Cosa succede se sbaglia e chi ne subisce la conseguenza |
|---|---|---|---|---|
| Sblocco del telefono con il volto | Riconosce il volto del proprietario | Immagine della faccia dalla fotocamera frontale | Supervisionato: è stato addestrato con molte foto etichettate "stesso volto / volto diverso" | Non mi riconosce e devo inserire il codice (fastidio per me); più raramente si sblocca per la persona sbagliata (rischio per la privacy) |
| Correttore e suggerimenti della tastiera | Prevede la parola successiva | Le lettere e le parole appena scritte | Supervisionato: la parola giusta è l'etichetta, presa da testi già scritti | Suggerisce una parola sbagliata; se non me ne accorgo il messaggio è scritto male e lo subisce chi lo legge |
| Raccomandazioni di YouTube / Spotify | Sceglie i video o le canzoni da mostrarmi | Cronologia di ascolti, "mi piace", tempo di visione, dati di utenti simili | Non supervisionato (raggruppa utenti simili) con parti di apprendimento per rinforzo (impara dai miei click) | Mi propone cose che non mi interessano e perdo tempo; nel lungo periodo può chiudermi in una "bolla" di contenuti simili |
| Filtro antispam della posta elettronica | Classifica un messaggio come spam o non spam | Testo, mittente, link e allegati dell'email | Supervisionato (classificazione): esempi di email già segnate come spam o no | Una email importante finisce nello spam e la perdo; oppure una email truffa arriva in posta e posso cadere in una frode |
| Navigatore (Google Maps) | Stima il tempo di arrivo e sceglie il percorso | Posizione GPS, traffico in tempo reale, storico del traffico | Supervisionato (regressione sul tempo di percorrenza) | Stima sbagliata: arrivo in ritardo o faccio una strada più lunga; lo subisco io |
| Assistente vocale (Siri, Alexa, Google Assistant) | Trascrive il comando vocale e sceglie l'azione da eseguire | Registrazione della mia voce | Supervisionato: audio abbinato al testo corretto | Capisce male e chiama la persona sbagliata o non esegue il comando; subisco io un disturbo |
| Sistema anti-frode della banca / carta di credito | Blocca o approva un pagamento | Importo, luogo, orario, tipo di negozio, storico delle spese | Non supervisionato (trova operazioni "anomale") e supervisionato (casi di frode già noti) | **Errore serio.** Falso positivo: mi blocca un pagamento necessario (es. non riesco a pagare all'estero). Falso negativo: lascia passare una frode e perdo denaro. Lo subisce il cliente, ma anche la banca |

**Sistema più opaco (3 righe):**

1. Il sistema più opaco è secondo me il **sistema anti-frode della banca**: non so quali dati usa, quanto pesa ciascuno e quale soglia fa scattare il blocco.
2. Anche quando un pagamento viene bloccato, di solito ricevo solo un avviso generico e nessuna spiegazione del motivo per cui la mia operazione è stata giudicata "sospetta".
3. Al contrario nel correttore della tastiera vedo subito cosa ha deciso e posso controllarlo, mentre qui la decisione è nascosta e difficile da contestare.

---

