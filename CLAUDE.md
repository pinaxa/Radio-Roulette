# CLAUDE.md — Radio Roulette

Web radio a sorte + looper/campionatore, in **un solo file HTML** senza build e
senza dipendenze.

## Regole non negoziabili

- **`Radio Roulette.html` è l'unico file del progetto** e si itera solo su quello.
  Si chiamava `index_studio_en.html` fino al 2026-09-08. Gli snapshot precedenti
  (una versione italiana e una più vecchia) non sono stati portati qui apposta:
  vivevano nella cartella `python_work`, ora dismessa.
- **Deve continuare a funzionare da `file://`**: gira dentro il device Max for Live
  "HTML INSTRUMENTS" in Ableton Live. Niente moduli ES esterni, niente bundler,
  niente fetch di risorse locali: tutto inline in un unico documento.
- **Tutto il colore sta nei token CSS.** Cinque temi (Default, Sepia, Midnight,
  Ember, Phosphor) ridefiniscono gli stessi token; un tema è un attributo
  `data-theme` su `<html>`. Anche il canvas della forma d'onda rilegge i token via
  `skinColors()`: non scrivere colori letterali da nessuna parte.

## Funzionamento

- Stazioni dalla API pubblica **Radio Browser** (mirror multipli in fallback),
  filtrabili per genere, paese, nome, bitrate minimo, solo HTTPS, solo
  "capture-ready" (stazioni i cui header CORS permettono la cattura).
- Capture del flusso in un buffer con vista a forma d'onda, loop / one-shot,
  lunghezza in beat (1/2/4/8/16), Auto BPM o tap tempo, lock-to-beat.
- Export dello stem su file: il flusso d'uso è trascinarlo in iZotope RX.

Scorciatoie: `space` play/pause · `N` next · `F` favourite · `C` capture ·
`L` loop · `O` one shot · `E` export · `B` auto BPM · `T` tap.

## Idea aperta

"YouTube Roulette": stessa interfaccia con sorgente YouTube da URL. Fattibilità
già analizzata — l'audio dell'iframe non è raggiungibile dalla pagina, quindi
servirebbe un'altra strada.
