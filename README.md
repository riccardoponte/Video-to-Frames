🌐 **Lingua / Language:** [🇮🇹 Italiano](#italiano) · [🇬🇧 English](#english)

---

<a id="italiano"></a>

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

---

<a id="english"></a>

# Video Screenshot Extractor

A web application that automatically extracts one screenshot per second from an uploaded video, entirely client-side: no server involved, no online uploads.

## Overview

The app is a single-page application (`index.html`) that allows you to upload a video file, preview it, and generate a sequence of screenshots (one for each second of duration), downloadable individually, in bulk, or collected into a single PDF.

## Features

### Video Upload
* File selection via click or drag & drop into the designated area.
* Video preview with built-in player.
* Uploaded file information: name, duration, resolution, size in MB, and expected number of screenshots.

### Screenshot Extraction
* Automatic frame capture for every second of the video using `<canvas>`.
* Progress bar with percentage and count of generated screenshots.
* Results grid with previews of each screenshot and its corresponding timestamp (mm:ss).
* Enlarged view (lightbox) when clicking on a screenshot.

### Downloading Results
* Download individual screenshots in PNG format.
* Download all screenshots in bulk in PNG format.
* Generation and download of a single PDF file containing all screenshots, one per page (A4 format, JPEG compressed images), built internally without external libraries.

## Input Video Formats

Any video format natively supported by the browser (via the HTML `<video>` element), such as MP4, WebM, Ogg.

## Technologies Used

The application uses no external libraries: pure vanilla HTML, CSS, and JavaScript.

* **Canvas API** for extracting frames from the video.
* **Manual PDF generation**: the file is constructed byte-by-byte following the PDF 1.4 specification, embedding images as JPEG streams (`DCTDecode`), without relying on any third-party library.

## How to Use

1. Open `index.html` in a modern browser (Chrome, Firefox, Edge, Safari).
2. Upload a video by dragging it into the designated area or clicking to select it from the file system.
3. Check the video preview and information, then click "Estrai Screenshot" (Extract Screenshots).
4. Wait for the progress bar to finish: screenshots will be generated and, immediately after, the summary PDF.
5. Download the results using the "Scarica PDF" (Download PDF) or "Scarica PNG" (Download PNG - all screenshots) buttons, or download individual screenshots from the grid.

## Privacy

No video or image is sent to a server: the entire processing, from frame extraction to PDF generation, takes place within the user's browser.

## Project Structure

```
index.html   # complete application: markup, styles, and logic in a single file
```

## Notes

The project requires no build step or dependencies to install: simply open the HTML file to use it, either locally or hosted on any static hosting service. Very long or high-resolution videos may require more time and browser memory, as each frame is held in memory until downloaded.
