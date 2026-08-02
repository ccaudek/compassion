# Aggiornamento del sito Quarto

Questa cartella contiene una revisione completa del sito mantenendo Quarto e i contenuti forniti.

## File da integrare dal repository originale

Prima del rendering, copia nella cartella del progetto questi file, non inclusi negli allegati ricevuti:

- `logo.jpeg`
- `ILTK-Logo.jpg`
- `images/favicon.ico`
- `materials/gusmano_1.docx`
- `materials/gusmano_2.docx`

Se nel repository sono ancora utilizzati, conserva anche gli altri contenuti presenti nelle cartelle `content/`, `images/`, `materials/` e `static/`.

## Anteprima locale

```bash
quarto preview
```

## Controllo accessibilità

```bash
quarto preview --profile accessibility
```

Apri gli strumenti di sviluppo del browser e controlla la console. Il profilo usa axe-core con le regole WCAG 2.2 AA e le regole di buona pratica.

## Pubblicazione con l'attuale flusso `docs/`

```bash
quarto render
git add _quarto.yml *.qmd *.scss _theme-rules.scss docs/
git commit -m "Rinnova design e struttura del sito"
git push
```

Nelle impostazioni del repository GitHub, GitHub Pages deve continuare a pubblicare la cartella `/docs` del branch principale.

## Verifiche consigliate prima del push

1. Aprire tutte le pagine da desktop e da telefono.
2. Controllare che i due loghi e il favicon siano visibili.
3. Provare i due download nella pagina Approfondimenti.
4. Provare ricerca, menu mobile e modalità chiara/scura.
5. Verificare date, quota, requisiti, ECM e nominativi prima della pubblicazione.

## Correzioni successive al primo test di anteprima

Sono state applicate anche queste correzioni:

- le sezioni inferiori della Home usano ora la colonna Quarto `column-page`, evitando che il contenuto resti confinato nella colonna stretta del corpo;
- la classe generica `narrow` è stata sostituita con `home-section--narrow` per evitare collisioni con classi del tema;
- il logo ILTK è incluso nel progetto sia come file JPEG originale sia come versione WebP ottimizzata e caricata in modo differito;
- è stato inserito uno spazio vuoto dopo le icone HTML nelle schede, affinché Pandoc interpreti correttamente le intestazioni Markdown `###`.

## Correzione layout verificata con output Quarto 1.9.38

La revisione V4 corregge un comportamento specifico di Pandoc/Quarto: una classe assegnata a un titolo Markdown viene copiata anche sul contenitore `<section>`. La precedente classe `section-heading`, che aveva `max-width: 19ch`, restringeva quindi non soltanto il titolo ma l'intera sezione, incluse griglie e paragrafi. Le classi sono state rimosse dai titoli e gli stili ora selezionano esplicitamente gli elementi `h2`.

Per la pagina Programma la griglia editoriale di Quarto viene disattivata soltanto su quella pagina, dato che non esiste un sommario laterale; il contenuto viene centrato in una colonna esplicita.
