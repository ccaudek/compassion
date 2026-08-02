# Correzioni layout v3

Questa revisione sostituisce il tentativo basato sulle classi `column-page`.

## Home

- `index.qmd` usa `page-layout: custom`, adatto a una landing page senza la griglia editoriale di Quarto.
- La hero usa `width: 100%` e non usa più `100vw` o margini negativi.
- Le sezioni successive sono normali blocchi centrati, larghi fino a 1180 px; le sezioni testuali arrivano fino a 960 px.
- Il contenitore del logo e l'elemento `picture` sono centrati esplicitamente.

## Programma

- Il sommario laterale è disattivato.
- Il contenuto è centrato in una colonna ampia fino a 1040 px, evitando il margine destro vuoto.

## Verifiche eseguite

- front matter YAML di tutti i file `.qmd`;
- configurazioni YAML del progetto;
- parsing Pandoc di tutte le pagine;
- bilanciamento dei delimitatori SCSS;
- assenza di `title: false`, classi `column-page` e titoli Markdown stampati come testo.
