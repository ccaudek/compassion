# Correzioni V4

Questa revisione corregge i difetti verificati direttamente nell’HTML generato con Quarto 1.9.38.

- La classe `section-heading` non viene più applicata ai titoli della home: Pandoc la propagava anche al contenitore `<section>`, limitando tutta la sezione a `19ch`.
- Le regole della home includono ora `#quarto-content` per superare la regola Quarto `#quarto-content > *`, che aveva una specificità maggiore e sostituiva parte del padding.
- Griglie, paragrafi e schede della home occupano ora la larghezza prevista.
- Il blocco del logo usa un wrapper a larghezza piena con centratura flex esplicita.
- La pagina Programma non usa più la griglia editoriale asimmetrica: il contenuto è centrato in una colonna da massimo 1040 px.
