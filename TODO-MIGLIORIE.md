# Bagni Sole Mare — Migliorie UI/UX

Piano di miglioramenti per il sito. Organizzato per area e priorità.

---

## 1. Header & Navigazione

### 1.1 Stile desktop
- **Indicatore pagina attiva**: aggiungere underline animata (2px) sotto il link attivo, con colore `mare-600` e transizione smooth
- **Hover links**: aggiungere effetto hover più visibile — underline che entra da sinistra con `transition: width`, non solo cambio colore
- **Icone nei link**: aggiungere piccole icone accanto ai testi di navigazione (casa per Home, lista per Menu, tag per Prezzi)
- **Bottone "Chiama"**: aggiungere leggero effetto `shadow-md` e `hover:shadow-lg` + micro-animazione `hover:-translate-y-0.5`

### 1.2 Stile mobile
- **Animazione apertura**: il menu mobile ora appare/scompare con `hidden` secco. Sostituire con transizione slide-down (`max-height` + `opacity` + `transition`)
- **Sfondo overlay**: quando il menu mobile è aperto, aggiungere un overlay semi-trasparente scuro dietro (`bg-black/20`) che al click chiude il menu
- **Link con icone**: nel menu mobile aggiungere le stesse icone dei link desktop, più grandi e colorate
- **Separatori tra i link**: aggiungere divider leggeri `border-b border-gray-100` tra le voci

### 1.3 Comportamento scroll
- **Shadow dinamica**: l'header dovrebbe avere `shadow-none` quando si è in cima alla pagina e `shadow-md` quando si scrolla verso il basso (gestito con JS `scroll` event)
- **Riduzione al scroll** (opzionale): ridurre altezza header da `h-16` a `h-14` dopo 50px di scroll, con transizione smooth

### 1.4 Logo
- **Migliorare il logo SVG**: il logo attuale (cerchio + onda) è generico. Valutare un SVG più caratteristico (ombrellone + sole) o usare un'immagine logo reale se disponibile

---

## 2. Pagina Menu Bar (`/menu`)

### 2.1 Hero della pagina
- **Aggiungere icona decorativa**: SVG grande di un cocktail o tazza di caffè sopra il titolo, con opacità `0.15` o come elemento decorativo
- **Aggiungere sottotitolo più descrittivo**: es. "Bevande fresche, caffetteria, cocktail e snack direttamente in spiaggia"
- **Elemento decorativo wave**: aggiungere SVG wave separator nella parte bassa dell'hero (come fatto nella Hero della home)

### 2.2 Quick nav (tab categorie)
- **Stato attivo**: al click/scroll evidenziare il tab della categoria corrente con `bg-mare-600 text-white` invece di `bg-mare-50 text-mare-700`
- **Icone nei tab**: aggiungere emoji o piccole icone SVG prima del nome categoria (es. ☕ Caffetteria, 🍹 Cocktail)
- **Scroll indicator**: se i tab escono dallo schermo su mobile, aggiungere un gradiente di fade sui bordi per indicare che si può scrollare

### 2.3 MenuItem — Singola voce del menu
Attualmente è solo `nome ........... prezzo` con un `border-b`. Troppo basico.

- **Descrizione opzionale**: aggiungere un campo `descrizione` nel JSON per alcune voci (es. "Focaccia ligure" → "Con olio EVO e sale grosso"). Mostrare sotto il nome in testo grigio piccolo
- **Badge**: supportare badge opzionali nel JSON (es. `"badge": "Novità"` o `"badge": "Popolare"`). Renderizzare come pill colorata accanto al nome
- **Dots/line filler**: aggiungere una linea punteggiata (`border-dotted`) tra nome e prezzo per migliorare la leggibilità (stile menù ristorante classico)
- **Hover effect**: leggero `bg-mare-50/50` al passaggio del mouse sulla riga

### 2.4 MenuCategory — Sezione categoria
- **Card container**: wrappare ogni categoria in un card `bg-white rounded-2xl shadow-sm border border-gray-100 p-6` per separarle visivamente
- **Icona nel titolo**: usare il campo `icona` già presente nel JSON per renderizzare un'icona SVG accanto al titolo della categoria
- **Contatore voci**: aggiungere un badge con il numero di voci (es. "8 voci") accanto al titolo, piccolo e in grigio

### 2.5 Layout generale
- **Background**: la pagina usa `bg-white` uniforme. Aggiungere `bg-sabbia-50` come sfondo della sezione menu per creare contrasto con i card bianchi
- **Footer della pagina**: migliorare la nota allergeni — metterla in un card con icona info, non solo testo grigio perso in fondo

---

## 3. Pagina Prezzi & Contatti (`/prezzi`)

### 3.1 Abbonamenti — Card evidenziato
- **Card "Più Popolare"**: evidenziare l'abbonamento "Stagionale Standard" (o quello consigliato) con:
  - Bordo colorato `border-2 border-mare-500` invece di `border-gray-100`
  - Badge "Più scelto" in alto a destra del card
  - Sfondo leggero `bg-mare-50` invece di `bg-white`
  - Scala leggermente più grande `scale-[1.02]`
- **Icone per tipo abbonamento**: aggiungere icone (calendario, stella, ticket) per differenziare visivamente i piani

### 3.2 Tabelle prezzi
- **Header tabella**: aggiungere un badge colorato per la stagione (es. "Bassa Stagione" in verde, "Alta Stagione" in arancione/rosso)
- **Riga evidenziata**: la riga del pacchetto più venduto dovrebbe avere sfondo leggermente diverso

### 3.3 Sezione Contatti
- La sezione contatti è già ben fatta. Miglioramenti minori:
- **Icona animata WhatsApp**: leggero pulse/bounce sull'icona WhatsApp per attirare attenzione
- **Orari**: aggiungere indicazione "Aperto ora" / "Chiuso" basata sull'orario corrente (opzionale, richiede JS client-side)

---

## 4. Pagina Home (`/`)

### 4.1 Sezione "Chi Siamo"
- Funziona bene. Possibili miglioramenti:
- **Immagine/foto**: aggiungere una foto dello stabilimento accanto al testo (layout 2 colonne su desktop)
- **Contatore numeri**: es. "20+ anni di attività", "200+ posti spiaggia" — piccoli badge sotto il testo

### 4.2 Sezione Servizi
- Le ServiceCard sono già buone. Miglioramenti minori:
- **Hover più evidente**: aggiungere `hover:-translate-y-1` per effetto "sollevamento" al hover
- **Colore icona**: le icone potrebbero usare colori diversi per servizio (mare per spiaggia, sabbia per bar, verde per area bimbi)

### 4.3 CTA Finale
- Ben fatta. Nessuna modifica urgente necessaria.

---

## 5. Footer

### 5.1 Miglioramenti
- **Mappa mini**: aggiungere una mini-mappa o link diretto a Google Maps nella colonna indirizzo
- **Link rapidi**: aggiungere colonna con link interni (Home, Menu, Prezzi, Contatti)
- **Newsletter** (opzionale): campo email per iscrizione, se desiderato
- **Icone social più grandi**: portare da `w-9 h-9` a `w-10 h-10` con effetto hover più marcato

---

## 6. Miglioramenti generali

### 6.1 Pagine mancanti
- **Galleria fotografica**: pagina dedicata con foto della spiaggia, bar, servizi, tramonto. Fondamentale per un bagno/spiaggia. Griglia responsive con lightbox per ingrandire
- **Recensioni/Testimonianze**: sezione nella home o pagina dedicata con recensioni da Google/TripAdvisor

### 6.2 Animazioni & micro-interazioni
- **Scroll progress bar**: barra colorata sottile in cima alla pagina che indica lo scroll progress (opzionale)
- **Back to top button**: bottone che appare dopo un certo scroll, per tornare in cima
- **Skeleton loading** (opzionale): per la mappa Google e immagini pesanti

### 6.3 Accessibilità
- **Skip to content**: link nascosto per screen reader che salta alla navigazione
- **Focus styles**: verificare che tutti gli elementi interattivi abbiano focus ring visibile
- **aria-current="page"**: aggiungere al link di navigazione attivo

### 6.4 SEO
- **Breadcrumbs**: aggiungere breadcrumb nelle pagine interne (Menu, Prezzi)
- **Structured data menu**: aggiungere schema.org per il menu del ristorante
- **Pagina 404**: creare una pagina 404 personalizzata con link alla home

---

## Priorità di implementazione

| Priorità | Area | Descrizione |
|----------|------|-------------|
| **Alta** | Header | Indicatore attivo, animazione mobile menu, shadow scroll |
| **Alta** | Menu | Card categorie, dots filler, icone, sfondo sabbia |
| **Alta** | Menu | Quick nav con stato attivo che segue lo scroll |
| **Media** | Prezzi | Card abbonamento evidenziato "Più scelto" |
| **Media** | Menu | Badge (Popolare/Novità) e descrizioni opzionali |
| **Media** | Header | Icone nei link navigazione |
| **Media** | Home | Foto nella sezione Chi Siamo |
| **Bassa** | Footer | Link rapidi, mini-mappa |
| **Bassa** | Generale | Galleria foto (richiede foto reali) |
| **Bassa** | Generale | Back to top, scroll progress |
| **Bassa** | Generale | Pagina 404, breadcrumbs |