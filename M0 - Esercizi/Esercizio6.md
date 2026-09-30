# Esercizio 6 - Il ciclo di vita applicato a un caso concreto

**Progetto:** prevedere il consumo elettrico mensile dell'edificio dell'istituto per l'anno successivo, per programmare la spesa.

**Elementi principali del problema**

- **Istanza:** un mese di un certo anno (per esempio "marzo 2024").
- **Attributi:** mese, anno, temperatura media del mese, giorni di lezione, giorni di chiusura, numero di studenti presenti, ore di riscaldamento/raffrescamento, presenza di eventi o lavori, consumo del mese precedente.
- **Etichetta:** il consumo elettrico del mese in kWh.
- **Categoria del problema:** **regressione**, perché l'etichetta è un numero continuo (kWh) e non una classe.

## 1. Definizione del problema
Si stabilisce che cosa si vuole prevedere: il consumo in kWh di ciascuno dei 12 mesi dell'anno prossimo. Si decide come verrà usato il risultato (preparare il bilancio) e quale errore è accettabile, per esempio sbagliare al massimo del 10% per mese. Si sceglie anche un modo semplice per confrontarsi: usare il consumo dello stesso mese dell'anno prima.

## 2. Raccolta dei dati
Si recuperano le bollette e le letture del contatore degli ultimi anni (idealmente almeno 3-5). Si aggiungono i dati di contorno: temperature mensili dalla stazione meteo, calendario scolastico, numero di studenti e ore di apertura. Ogni mese diventa una riga della tabella.

## 3. Preparazione dei dati
Si controlla e si pulisce la tabella. Difetti ragionevolmente attesi in registrazioni raccolte negli anni da persone diverse:
- **valori mancanti:** mesi in cui nessuno ha annotato la lettura;
- **errori di trascrizione:** cifre invertite, virgola sbagliata, kWh scambiati con euro;
- **formati e unità diversi:** date scritte in modi diversi, consumi a volte in kWh e a volte in MWh;
- **duplicati** dello stesso mese o letture fatte in giorni diversi del mese, quindi periodi non confrontabili;
- **valori anomali** dovuti a guasti, conguagli o periodi di chiusura (per esempio il 2020).

Si correggono o si eliminano questi problemi e si divide il dataset in due parti: addestramento (anni passati) e test (l'ultimo anno).

## 4. Scelta del modello
Si parte dal modello più semplice possibile, una regressione lineare, perché i dati sono pochi (circa 12 righe per anno). Eventualmente si confronta con un albero di regressione. Si preferisce un modello facile da spiegare a chi deve decidere la spesa.

## 5. Addestramento
Il modello viene addestrato sui mesi degli anni passati, così impara la relazione fra attributi (temperatura, giorni di lezione...) e consumo. Si regola qualche parametro semplice e si evita che il modello "impari a memoria" i dati (sovradattamento), dato che gli esempi sono pochi.

## 6. Valutazione
Si fanno le previsioni sull'anno di test, che il modello non ha visto, e si confrontano con i consumi reali. Si calcola l'errore medio (per esempio in kWh e in percentuale) e lo si confronta con il metodo semplice "stesso mese dell'anno scorso". Se il modello non fa meglio, non vale la pena usarlo.

## 7. Utilizzo e monitoraggio
Il modello viene usato per stimare i 12 mesi dell'anno prossimo, usando come temperature quelle medie storiche. Ogni mese si confronta la previsione con la bolletta reale e si annotano gli scostamenti. A fine anno si aggiungono i nuovi dati e si riaddestra il modello, soprattutto se cambiano l'edificio, gli impianti o il numero di studenti.