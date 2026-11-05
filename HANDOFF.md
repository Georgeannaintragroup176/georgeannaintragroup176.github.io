# Handoff — sito portfolio Stefano Di Carlo (lighting designer)

## Obiettivo
Sito portfolio personale, bilingue IT/EN, stile scuro e drammatico da concerto.
Hosting gratuito su GitHub Pages. Contenuti modificabili da interfaccia grafica con Pages CMS.

## Account e repository
- Account GitHub dedicato al lavoro: `stefanodicarlold` (NON usare l'altro account GitHub dell'utente).
- Repository: https://github.com/stefanodicarlold/stefanodicarlold.github.io (pubblico, attualmente vuoto)
- Indirizzo finale del sito: https://stefanodicarlold.github.io

## Cosa fare adesso
1. Copiare nella root del repository tutti i file dello zip `sito-stefano-di-carlo.zip`
   (il contenuto della cartella `sito-ld/`, non la cartella stessa), inclusi `.pages.yml` e `.nojekyll`.
2. Commit e push su `main`.
3. Attivare GitHub Pages: Settings → Pages → Deploy from a branch → `main` / `(root)`
   (oppure via API: `gh api -X POST repos/stefanodicarlold/stefanodicarlold.github.io/pages -f "source[branch]=main" -f "source[path]=/"`).
4. Verificare che https://stefanodicarlold.github.io carichi senza errori in console e che i contenuti JSON appaiano.
5. Guidare l'utente su https://app.pagescms.org (login con l'account stefanodicarlold, selezionare il repo).

## Struttura del sito (sito statico, nessuna build)
- `index.html` — grafica + JS. Carica i contenuti via `fetch` da `content/site.json` e `content/projects.json`
  (quindi non funziona aprendolo da file:// — serve un server o GitHub Pages).
  Fallback: se esiste `window.__SITE__ = {site, projects}` usa quello invece del fetch.
- `content/site.json` — hero, about, stats, skills (gruppi con voci e livello 0-100), contact.
  Campi bilingue con suffisso `_it` / `_en`. Nei testi `**grassetto**` e riga vuota = nuovo paragrafo.
- `content/projects.json` — array di lavori: artist, title_it/en, role_it/en, year,
  description_it/en, cover, gallery[], video (URL YouTube/Vimeo → embed automatico), visible.
- `images/` — media caricati da Pages CMS (`media.input: images`, `output: images`, percorsi relativi).
- `.pages.yml` — configurazione Pages CMS (due voci: "Lavori / Work" e "Testi del sito / Site texts").
- `.nojekyll` — evita l'elaborazione Jekyll su GitHub Pages.
- `LEGGIMI.md` — istruzioni per l'utente in italiano.

## Design (da mantenere: all'utente piace com'è)
- Palette: bg #0a0a0c, raised #131317 / #1b1b20, testo #e9e7e2, dim #8d8b91, faint #55535a,
  ambra #ff8c1a (accento principale), ciano #00d9ff, magenta #ff2f9e, linee #28282e.
- Font: Oswald (titoli), Inter (testo), JetBrains Mono (etichette/dati).
- Metafora console luci: sezioni "CUE 01–04", lavori come cue list espandibile (accordion con
  foto, galleria + lightbox, video), competenze come fader animati, fasci di luce animati nell'hero.
- Lingua: ?lang=it|en, poi localStorage, poi lingua del browser. Toggle IT/EN nell'header.
- Responsive testato a 1440px e 390px, nessun errore in console; rispetta prefers-reduced-motion.

## Ancora da fare
- Email, Instagram, LinkedIn, telefono veri (ora c'è `info@stefanodicarlo.com` come segnaposto).
- Foto e video reali degli show (ora placeholder a fasci di luce), anni e descrizioni dei tour.
- Eventuale dominio personalizzato più avanti.
