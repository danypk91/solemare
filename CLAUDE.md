# Claude Code — Bagni Sole Mare

## Regole commit
- **Mai** aggiungere `Co-Authored-By` nei commit. L'utente non vuole attribuzione a Claude nei messaggi di commit.

## Progetto
- **Stack**: Astro 5 + Tailwind CSS v4 (Lightning CSS) + TypeScript
- **Build**: `npx astro build` / `npx astro dev`
- **Pagine**: `index.astro`, `menu.astro`, `prezzi.astro`
- **Layout**: `Layout.astro` con View Transitions (`ClientRouter`)
- **Dati**: JSON in `src/data/` (siteConfig, servizi, menu, prezzi)

## Cose da ricordare
- **Lightning CSS** (usato da Tailwind v4) corrompe i data URI SVG nei file CSS. Usare SVG inline nell'HTML invece di `background-image: url("data:image/svg+xml,...")` nel CSS.
- **Onde animate hero**: 3 SVG separati con colori **opachi** (`#93d1fd`, `#bfe3fe`, `white`). Mai usare `fill-opacity` su layer sovrapposti — causa artefatti di compositing visibili come forme geometriche.
- **Header**: non wrappare in `<div transition:name>` — crea un box visibile. L'header è fuori da `<main>` quindi persiste automaticamente nelle View Transitions.
- **Mobile**: cerchi decorativi più piccoli, onde altezza 70px (100px da md), hero `min-h-[70vh]` (85vh da md).
