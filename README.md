# reweke.it: sito vetrina (prototipo)

Sito statico, una sola pagina, senza dipendenze esterne (font self-hosted, nessun cookie, nessun tracciamento). Brand: Reweke Brand Identity Manual v1.0 (Plus Jakarta Sans per i titoli, Inter per il testo, Teal-Green #1A7A7A, Mint #4ECDC4, #F4F6F9). Stesso schema del sito di Asumi.

## File
| File | Ruolo |
|---|---|
| `index.html` | La pagina (CSS e JS inclusi, meta SEO, Open Graph, dati strutturati) |
| `privacy.html` | Informativa privacy: **bozza da validare** dal legale |
| `404.html` | Pagina di errore per GitHub Pages |
| `fonts/` | Plus Jakarta Sans e Inter (subset latino) |
| `assets/` | Logo teal e bianco (da `Reweke/resources/Logo Reweke - Restyling 2026 - Solo Logo.png`) |
| `favicon-*.png`, `apple-touch-icon.png`, `og-image.png` | Icone e anteprima social |
| `robots.txt`, `sitemap.xml`, `llms.txt`, `.nojekyll` | Indicizzazione e pubblicazione |
| `CNAME` | Da creare con dentro `reweke.it` solo quando si collega il dominio |

## Stato: STAGING online
URL di staging: https://reweke-it.github.io/web/ (repository `Reweke-it/web`). Il sito è `noindex` (meta robots e robots.txt) e ha l'etichetta "Staging" in basso a sinistra. **Al lancio**: togliere l'etichetta `.stg`, ripristinare robots (index, canonical `https://reweke.it/`, og:url e og:image su reweke.it, robots.txt con Sitemap) e collegare il dominio.

## Prima di pubblicare in produzione (da completare)
0. **Sezione MyReweke**: nel testo è presentata come disponibile. Prima del lancio il portale deve esserlo davvero (accesso clienti, dati reali, privacy completata).
1. **Dati societari nel footer** (sede legale, P.IVA, REA, capitale sociale) e nella privacy: oggi sono segnaposto gialli. La sede legale cambia con il trasferimento previsto.
2. **Servizi pubblicizzati**: verificare con il commercialista la SCIA da spedizioniere prima di pubblicare "Logistica e spedizioni in Italia" e "Import via mare" (vedi `Reweke/knowledge/vendita-in-transito-analisi-e-punti-aperti.md`).
3. **Dichiarazioni**: il deck aziendale usa cifre (-30% costi, report in 24 ore, aggiornamenti ogni 6 ore) e formule ("zero trader intermedi", partner nominati) non verificate o non coerenti con il modello di vendita in transito: nel sito **non** sono state usate. Aggiungerle solo se documentate.
4. **Contatto**: oggi solo `info@reweke.it` (mailto). Se serve un modulo, serve un servizio esterno o un backend, con informativa aggiornata.
5. **Informativa privacy**: far validare al legale il testo.
6. Il testo "Prima consulenza senza impegno" va confermato come offerta commerciale.

## Pubblicazione su GitHub Pages
1. Nuova organizzazione GitHub collegata all'account Kanzo-it (es. `Reweke-it`), repository `web` con il contenuto di questa cartella nella radice.
2. Settings, Pages: Deploy from a branch, `main`, `/ (root)`.
3. Quando c'è il controllo del dominio: creare `CNAME` con `reweke.it`, aggiungere il dominio tra i *Verified domains* dell'organizzazione (record TXT) e attivare Enforce HTTPS.

## DNS di reweke.it
Il dominio ospiterà anche la posta (Google Workspace) e i sottodomini delle app (es. my.reweke.it): non sostituire l'intera zona DNS, aggiungere solo questi record e lasciare MX, SPF, DKIM e gli altri sottodomini.

| Tipo | Nome | Valore |
|---|---|---|
| A | @ | 185.199.108.153 |
| A | @ | 185.199.109.153 |
| A | @ | 185.199.110.153 |
| A | @ | 185.199.111.153 |
| CNAME | www | `<organizzazione>.github.io` |

Verificare i valori sulla documentazione di GitHub Pages al momento della configurazione.

## Anteprima in locale
Aprire `index.html` nel browser, oppure dalla cartella `python -m http.server 8000` e visitare http://localhost:8000.
