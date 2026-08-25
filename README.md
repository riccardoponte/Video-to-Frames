# Estrattore di Screenshot Video

Applicazione web che estrae automaticamente uno screenshot per ogni secondo di un video caricato, interamente lato client: nessun server coinvolto, nessun caricamento online.

## Panoramica

L'app è una pagina singola (`index.html`) che permette di caricare un file video, riprodurne l'anteprima e generare una sequenza di screenshot (uno per ogni secondo di durata), scaricabili singolarmente, in blocco oppure raccolti in un unico PDF.

## Funzionalità

### Caricamento video
* Selezione del file tramite clic oppure trascinamento (drag & drop) nell'area dedicata.
* Anteprima del video con player integrato.
* Informazioni sul file caricato: nome, durata, risoluzione, dimensione in MB e numero di screenshot previsti.

### Estrazione screenshot
* Cattura automatica di un fotogramma per ogni secondo del video, tramite `<canvas>`.
* Barra di avanzamento con percentuale e conteggio degli screenshot generati.
* Griglia dei risultati con anteprima di ogni screenshot e relativo timestamp (mm:ss).
* Visualizzazione ingrandita (lightbox) cliccando su uno screenshot.

### Download dei risultati
* Download del singolo screenshot in formato PNG.
* Download di tutti gli screenshot in blocco, in formato PNG.
* Generazione e download di un unico file PDF contenente tutti gli screenshot, uno per pagina (formato A4, immagini in JPEG compresso), costruito internamente senza librerie esterne.

## Formato video in ingresso

Qualsiasi formato video supportato nativamente dal browser (tramite l'elemento HTML `<video>`), ad esempio MP4, WebM, Ogg.

## Tecnologie utilizzate

L'applicazione non utilizza librerie esterne: HTML, CSS e JavaScript puro (vanilla).

* **Canvas API** per l'estrazione dei fotogrammi dal video.
* **Generazione manuale del PDF**: il file viene costruito byte per byte seguendo la specifica PDF 1.4, incorporando le immagini come stream JPEG (`DCTDecode`), senza dipendere da alcuna libreria di terze parti.

## Come si usa

1. Apri il file `index.html` in un browser moderno (Chrome, Firefox, Edge, Safari).
2. Carica un video trascinandolo nell'apposita area oppure cliccando per selezionarlo dal file system.
3. Controlla l'anteprima e le informazioni del video, poi premi "Estrai Screenshot".
4. Attendi il completamento della barra di avanzamento: verranno generati gli screenshot e, subito dopo, il PDF riepilogativo.
5. Scarica i risultati con i pulsanti "Scarica PDF" o "Scarica PNG" (tutti gli screenshot), oppure scarica singolarmente uno screenshot dalla griglia.

## Privacy

Nessun video o immagine viene inviato a un server: l'intera elaborazione, dall'estrazione dei fotogrammi alla generazione del PDF, avviene nel browser dell'utente.

## Struttura del progetto

```
index.html   # applicazione completa: markup, stile e logica in un unico file
```

## Note

Il progetto non richiede alcun build step né dipendenze da installare: basta aprire il file HTML per utilizzarlo, sia in locale che pubblicato su qualsiasi hosting statico. Video molto lunghi o ad alta risoluzione possono richiedere più tempo ed memoria del browser, poiché ogni fotogramma viene mantenuto in memoria fino al download.
