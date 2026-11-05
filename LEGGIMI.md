# Sito Stefano Di Carlo — come è fatto

- `index.html` — la grafica del sito. Non serve toccarlo per aggiornare i contenuti.
- `content/site.json` — testi (IT/EN), numeri, competenze, contatti.
- `content/projects.json` — i lavori: artista, ruolo, anno, foto, galleria, video.
- `images/` — le foto che carichi dal pannello finiscono qui.
- `.pages.yml` — configurazione del pannello di gestione (Pages CMS).

## Mettere online (una volta sola)

1. Su GitHub crea un repository nuovo, **pubblico** (es. `sito`).
2. "Add file" → "Upload files" → trascina tutto il contenuto di questa cartella
   (incluse le cartelle `content` e `images`). Conferma con "Commit changes".
   Se `.pages.yml` non compare tra i file caricati (su Mac i file che iniziano
   col punto sono nascosti), crealo con "Add file" → "Create new file" e incolla il contenuto.
3. Settings → Pages → Source: "Deploy from a branch" → Branch: `main`, cartella `/ (root)` → Save.
4. Dopo un minuto il sito è online su `https://TUONOMEUTENTE.github.io/sito/`.

## Modificare i contenuti

1. Vai su https://app.pagescms.org e accedi con lo stesso account GitHub.
2. Scegli il repository del sito.
3. A sinistra trovi "Lavori / Work" e "Testi del sito / Site texts".
4. Modifica, carica le foto, premi Save. Il sito si aggiorna da solo in 1-2 minuti.

Note:
- Nei testi puoi usare `**parole**` per il grassetto, e una riga vuota per andare a capo con un nuovo paragrafo.
- Per i video incolla il link normale di YouTube o Vimeo.
- Per nascondere un lavoro senza cancellarlo togli la spunta "Mostra sul sito".
- Le foto: meglio JPG sotto i 500 KB (esportale a ~2000 px di lato lungo), il sito resta veloce.
- Aprendo `index.html` con doppio clic dal computer i contenuti non si caricano: il sito va visto dal suo indirizzo web.
