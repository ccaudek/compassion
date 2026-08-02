# Verifica tecnica

## Controlli completati

- `_quarto.yml` e `_quarto-accessibility.yml`: sintassi YAML valida.
- Tutti i file `.qmd`: sintassi Markdown/Pandoc valida.
- Collegamenti interni tra le pagine: verificati.
- Tema chiaro/scuro, navigazione responsive, focus da tastiera e riduzione delle animazioni: inclusi.
- Copia originale degli allegati: conservata nella cartella `originali/`.

## Asset da recuperare dal repository

Gli allegati ricevuti non contenevano i seguenti file, già richiamati dal sito:

- `logo.jpeg`
- `ILTK-Logo.jpg`
- `images/favicon.ico`
- `materials/gusmano_1.docx`
- `materials/gusmano_2.docx`

Il rendering finale va eseguito dopo averli copiati nella nuova cartella, mantenendo questi percorsi.

## Controllo editoriale richiesto

Nei contenuti forniti compare una possibile discrepanza sulla quota associativa dell'Istituto Lama Tzong Khapa: nella pagina introduttiva è indicata come **20–30 euro**, mentre nelle FAQ è indicata come **20 euro**. Il testo non è stato uniformato automaticamente.

## Limite della verifica in questo ambiente

La CLI Quarto non era disponibile e l'installazione del pacchetto binario è stata bloccata dall'ambiente. Di conseguenza non è stato possibile eseguire qui il comando `quarto render`. La struttura è stata comunque validata tramite parser YAML e Pandoc; resta necessario un rendering locale prima del push.

## Verifica delle correzioni di layout e Markdown

- Tutte le pagine `.qmd` vengono convertite correttamente con Pandoc 3.1.11.1.
- Le intestazioni delle schede vengono prodotte come elementi HTML `<h3>` e non restano come testo letterale `###`.
- Le sezioni inferiori della Home hanno la classe Quarto `column-page`.
- `ILTK-Logo.jpg` è presente nella radice del progetto.
- `images/iltk-logo.webp` è presente come asset ottimizzato.
- Le parentesi graffe del foglio SCSS risultano bilanciate.

Rimane consigliato eseguire `quarto preview` localmente per il controllo visivo finale con la versione di Quarto installata sul sistema di pubblicazione.

## Verifica V4 su output fornito dall'utente

- Analizzato `docs/index.html` generato con Quarto 1.9.38.
- Identificata la propagazione di `.section-heading` dal titolo al contenitore `<section>`.
- Rimosso il vincolo `max-width: 19ch` dal contenitore della sezione.
- Verificati i selettori ad alta specificità di Quarto (`#quarto-content > *`).
- Resa esplicita la centratura della pagina Programma e del logo ILTK.
