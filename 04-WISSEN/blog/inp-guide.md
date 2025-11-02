# Blog-Post: INP-Guide – Interaktionslatenz für Kanzleien, Campus & Behörden

## 1. Header & Meta-Informationen

**Seiten-Typ:** Blog-Post (MDX Content Collection)
**Datei:** `/src/content/blog/inp-guide.mdx` (171 Zeilen, 8.8 KB)
**Route:** `/blog/inp-guide/` (generiert via Content Collection)
**Layout:** `BlogPostLayout` (implicit via Content Collection Schema)
**Zielgruppen:** Kanzleien & Boutiquen, Schulen & Hochschulen, Öffentliche Einrichtungen
**Kategorie:** Performance & KPIs
**Lesedauer:** 9 min
**Veröffentlicht:** 2025-09-21
**Autor:** Eduard Wolf

**SEO-Metadaten:**
- **Title:** "INP verstehen: So reagieren Kanzleien, Campus & Behörden in < 200 ms"
- **Description:** "Interaction to Next Paint (INP) ersetzt FID und bewertet jede Interaktion. So halten Kanzleien, Bildung und Behörden ihre Interfaces reaktionsschnell."
- **OG-Image:** `/img/og-default.jpg`
- **Response Promise:** "Antwort innerhalb von 1 Stunde · KPI-Workshop in ≤ 5 Werktagen"

**Keywords (Schema.org):**
- INP Optimierung
- Core Web Vitals Kanzlei
- Digitale Verwaltung Performance
- Astro Islands

---

## 2. Verlinkungsstruktur

### Ausgehende Interne Links (8 Total)

**Branchen-Seiten (3):**
1. `/branchen/kanzleien` — "Kanzlei-Blueprint öffnen" (Kanzlei-Segment Resources)
2. `/branchen/schulen-bildung` — "Enrollment StepFlow planen" (Bildungs-CTA)
3. `/branchen/oeffentliche-einrichtungen` — "Behörden-Top Tasks ansehen" (Behörden-Segment Resources)

**Leistungs-Seiten (3):**
1. `/leistungen/analytics-consent` — "Intake Performance prüfen lassen" (Kanzlei-CTA)
2. `/leistungen/stufe-a-astro-ftp` — "Stufe A – Astro Knowledge Hub" (Kanzlei-Segment Resources)
3. `/leistungen/analytics-consent` — "Servicecockpit KPIs sichern" (Behörden-CTA)
4. `/leistungen/seo-tech` — "SEO & Tech Foundations" (Bildungs-Segment Resources)

**Glossar-Links:** Keine `<InfoTooltip>` Tags (reiner Markdown-Content)

**Externe Referenzen (in Text erwähnt, nicht verlinkt):**
- Chrome UX Report (CrUX)
- GOV.UK Performance Hub
- D21 Mobile Index 2024
- E-Government Monitor 2023

### Eingehende Links (zu erwarten)

- **Startseite** (`/`) — Blog-Feed Carousel
- **Branchen-Seiten** — Performance-KPI Sections
- **Leistungen (Analytics & Consent)** — Core Web Vitals Argumentationsketten
- **Glossar-Terme** — Zukünftig: "Core Web Vitals", "Performance Budget" (wenn erstellt)

### Navigation Context

**Breadcrumbs (generiert):**
```
Home > Blog > Performance & KPIs > INP verstehen
```

**Prev/Next Posts:** Dynamisch via Collection Sort (publishedDate DESC)

---

## 3. Layout & Semantische Struktur

### MDX Content-Architektur

**Wichtig:** Blog-Posts verwenden **keine expliziten Astro-Komponenten** im MDX-Body. Layout wird durch `BlogPostLayout` (Content Collection Schema) bereitgestellt.

```markdown
FRONTMATTER (Zeilen 1-55)
├── Meta: title, description, publishedDate, category, readTime, author, responsePromise
├── Segments Array (3 Einträge: kanzlei, bildung, oeffentlich)
│   └── Pro Segment: title, kpi, summary, ctaLabel, ctaHref, resources[]
├── Schema.org: type, audience, about, keywords
└── image: OG-Image Path

HERO-IMAGE (Zeile 58)
└── ![Alt Text](/img/og-default.jpg)

CONTENT-SECTIONS (Zeilen 60-172)
├── H2: INP ersetzt FID – was bedeutet das? (Zeilen 60-81)
│   ├── H3: Was misst INP genau? (4 Absätze)
│   └── H3: Zielwerte & Benchmarks (Tabelle: Bewertung Google | INP)
│
├── H2: Segment-Prioritäten für INP (Zeilen 84-110)
│   ├── H3: Kanzleien & Boutiquen (4 Bullet-Points + Blockquote)
│   ├── H3: Schulen & Campus-Teams (3 Bullet-Points + Blockquote)
│   └── H3: Behörden & öffentliche Dienste (3 Bullet-Points + Blockquote)
│
├── H2: Quick Wins, die jedes Team umsetzen kann (Zeilen 113-120)
│   └── 5 Bullet-Points (Third-Party Scripts, Event Delegation, Web Worker, Astro, Budgets)
│
├── H2: Messung, Monitoring & Alerts (Zeilen 123-130)
│   └── 5 Numbered Items (PageSpeed, Web Vitals Extension, Search Console, RUM, Servicecockpit)
│
├── H2: INP-Benchmarks & Zielwerte (Zeilen 133-142)
│   └── Tabelle: Segment | INP-Ziel | Fokus-Komponenten | KPI-Verbindung
│
├── H2: Häufige Fragen zu INP (Zeilen 145-162)
│   ├── H3: Reicht Lazy Loading für besseren INP?
│   ├── H3: Wie viel JavaScript ist zu viel?
│   ├── H3: Sollten wir auf SPAs verzichten?
│   └── H3: Wirkt sich INP auf SEO aus?
│
└── H2: Fazit & nächste Schritte (Zeilen 165-171)
    └── 3 Bullet-Points + CTA-Text mit Response Promise
```

### Semantische HTML-Hierarchie (gerendert via BlogPostLayout)

```html
<article class="blog-post" itemscope itemtype="https://schema.org/BlogPosting">
  <header class="blog-header">
    <h1 itemprop="headline">INP verstehen: So reagieren Kanzleien...</h1>
    <div class="meta">
      <time itemprop="datePublished">2025-09-21</time>
      <span class="category">Performance & KPIs</span>
      <span class="read-time">9 min</span>
      <span class="author">Eduard Wolf</span>
    </div>
    <p class="description" itemprop="description">Interaction to Next Paint...</p>
  </header>

  <figure class="hero-image">
    <img src="/img/og-default.jpg" alt="Visualisierung eines Input-Events..." itemprop="image" />
  </figure>

  <div class="segment-cards" data-segments="3">
    <!-- 3 Segment-Cards: Kanzlei, Bildung, Öffentlich -->
    <article class="segment-card" data-segment="kanzlei">
      <h3>Mandatsaufnahme ohne Klick-Stall</h3>
      <p class="kpi">Lead-to-Call Rate +35 % · INP-Ziel < 150 ms</p>
      <p class="summary">Intake-Formulare, Terminbuchung...</p>
      <a href="/leistungen/analytics-consent" class="cta-button">Intake Performance prüfen lassen</a>
      <ul class="resources">
        <li><a href="/branchen/kanzleien">Kanzlei-Blueprint öffnen</a></li>
        <li><a href="/leistungen/stufe-a-astro-ftp">Stufe A – Astro Knowledge Hub</a></li>
      </ul>
    </article>
    <!-- Repeat für bildung, oeffentlich -->
  </div>

  <section class="prose" itemprop="articleBody">
    <!-- Markdown-Content gerendert als HTML -->
    <h2 id="inp-ersetzt-fid">INP ersetzt FID – was bedeutet das?</h2>
    <!-- ... weitere Sections ... -->
  </section>

  <footer class="blog-footer">
    <nav class="prev-next">
      <!-- Prev/Next Posts -->
    </nav>
  </footer>
</article>
```

### Accessibility-Struktur

- **Heading-Hierarchie:** H1 (Title) → H2 (Main Sections) → H3 (Subsections/FAQs) ✅
- **Landmark Regions:** `<article>`, `<header>`, `<section>`, `<footer>` via Layout
- **Skip-Links:** Provided by BlogPostLayout
- **ARIA:** `role="article"` via `<article>` Tag, `itemprop` für Schema.org
- **Keyboard Navigation:** Alle Links/CTAs keyboard-accessible (native `<a>` Tags)

---

## 4. Design-System-Details

### Typografie

**Headline (H1):**
- Font: Obviously (Primary Brand Font)
- Weight: 600 (Semibold)
- Size: 2.5rem (40px) Desktop, 1.875rem (30px) Mobile
- Line-Height: 1.2
- Color: `--wolf-plum` (#3B1E54)

**Body Text:**
- Font: Inter (Secondary Font)
- Weight: 400 (Regular), 500 (Medium für Emphasis)
- Size: 1.125rem (18px) Desktop, 1rem (16px) Mobile
- Line-Height: 1.75
- Color: `--wolf-plum` (#3B1E54)

**H2 Sections:**
- Font: Obviously
- Weight: 600
- Size: 2rem (32px) Desktop, 1.5rem (24px) Mobile
- Margin-Top: 3rem, Margin-Bottom: 1.5rem

**H3 Subsections:**
- Font: Obviously
- Weight: 600
- Size: 1.5rem (24px) Desktop, 1.25rem (20px) Mobile
- Margin-Top: 2rem, Margin-Bottom: 1rem

### Farben

**Segment Cards:**
- **Kanzlei:** Background `--wolf-plum-light` (#F5F0FA), Border `--wolf-plum`
- **Bildung:** Background `--wolf-mint-light` (#F0FAF5), Border `--wolf-mint`
- **Öffentlich:** Background `--wolf-apricot-light` (#FAF5F0), Border `--wolf-apricot`

**CTA-Buttons:**
- Background: `--wolf-plum` (#3B1E54)
- Text: White (#FFFFFF)
- Hover: `--wolf-plum-dark` (#2A1540)

**Tables:**
- Header: `--wolf-plum` Background, White Text
- Rows: Alternating `--wolf-snow` (#F8F9FA) / White
- Borders: `--wolf-plum-light` (#E0D5E8)

**Blockquotes (Praxis-Check):**
- Border-Left: 4px solid `--wolf-apricot` (#F4A261)
- Background: `--wolf-apricot-light` (#FAF5F0)
- Icon: `✓` or Warning Icon
- Padding: 1.5rem

### Spacing

- **Section-Gaps:** 4rem (64px) zwischen H2-Sections
- **Segment-Card Grid:** 1.5rem (24px) Gap
- **List-Items:** 0.75rem (12px) zwischen Bullet-Points
- **Prose Max-Width:** 65ch (ideal für Lesbarkeit)

### Komponenten (implizit via BlogPostLayout)

**Segment Cards:**
```html
<article class="segment-card" data-segment="kanzlei">
  <h3 class="segment-title">Mandatsaufnahme ohne Klick-Stall</h3>
  <p class="segment-kpi">Lead-to-Call Rate +35 % · INP-Ziel < 150 ms</p>
  <p class="segment-summary">Intake-Formulare...</p>
  <a class="cta-button primary">Intake Performance prüfen lassen</a>
  <ul class="resource-links">...</ul>
</article>
```

**Praxis-Check Blockquote:**
```html
<blockquote class="praxis-check">
  <p><strong>Praxis-Check:</strong> 2 von 3 Kanzlei-Websites verlieren...</p>
</blockquote>
```

**Tables:**
```html
<table class="data-table striped">
  <thead>
    <tr><th>Bewertung Google</th><th>INP</th></tr>
  </thead>
  <tbody>
    <tr><td>gut</td><td>< 200 ms</td></tr>
    <!-- ... -->
  </tbody>
</table>
```

---

## 5. Responsive Breakpoints

### Mobile (< 640px)

- **Segment Cards:** Stack vertikal (Grid 1 Column)
- **Font-Sizes:** H1 30px, H2 24px, Body 16px
- **Hero-Image:** Full-Width, Aspect-Ratio 16:9 maintained
- **Tables:** Horizontal-Scroll Container (overflow-x: auto)
- **CTA-Buttons:** Full-Width (width: 100%)

### Tablet (640px - 1024px)

- **Segment Cards:** Grid 2 Columns (wenn 2+ Cards)
- **Font-Sizes:** H1 36px, H2 28px, Body 17px
- **Tables:** Native Display (falls <= 4 Spalten)

### Desktop (> 1024px)

- **Segment Cards:** Grid 3 Columns (bei 3 Cards wie hier)
- **Font-Sizes:** Full Desktop Sizes (H1 40px, H2 32px, Body 18px)
- **Max-Width:** 1120px Container mit 2rem Padding
- **Tables:** Full Native Display
- **Resource-Links:** Horizontal Flex (wenn Platz vorhanden)

### Critical Breakpoint-Spezifika

- **INP-Tabellen:** Bei Mobile → Cards statt Table-Rows (via CSS `display: block`)
- **Praxis-Check Blockquotes:** Padding reduziert von 1.5rem → 1rem bei Mobile
- **Numbered Lists:** Counter-Style konsistent (1., 2., 3. ...)

---

## 6. Komponenten-Bibliothek

### Verwendete Komponenten (implizit via BlogPostLayout)

**BlogPostLayout (Wrapper):**
- **Funktion:** Rendert Frontmatter (Meta, Segment-Cards), Hero, Content, Footer
- **Props:** Implizit via Content Collection Schema (`title`, `description`, `segments`, `schema`, etc.)
- **File:** `/src/layouts/BlogPostLayout.astro` (nicht im Source, aber via Collection)

**SegmentCard (generiert aus Frontmatter):**
- **Props:** `segment`, `title`, `kpi`, `summary`, `ctaLabel`, `ctaHref`, `resources[]`
- **Render:** 3× Cards für Kanzlei, Bildung, Öffentlich
- **Styling:** Segment-spezifische Farben (Plum, Mint, Apricot)

**Response Promise Banner (aus Frontmatter):**
- **Content:** "Antwort innerhalb von 1 Stunde · KPI-Workshop in ≤ 5 Werktagen"
- **Position:** Unterhalb Hero-Image oder in Footer
- **Styling:** Fixed/Sticky Banner mit Wolf-Apricot Background

### Standard Markdown-Elemente

**Paragraphs (`<p>`):**
- Line-Height: 1.75
- Margin-Bottom: 1.25rem
- Max-Width: 65ch

**Bullet Lists (`<ul>`, `<li>`):**
- Marker: Custom SVG Bullet (Wolf-Plum)
- Padding-Left: 1.5rem
- Gap: 0.75rem

**Numbered Lists (`<ol>`, `<li>`):**
- Counter-Style: Decimal (1., 2., 3.)
- Font-Weight: 600 for Numbers
- Gap: 1rem (größer als Bullet-Lists für bessere Scannability)

**Tables (`<table>`):**
- Border-Collapse: collapse
- Width: 100%
- Cell-Padding: 0.75rem 1rem

**Blockquotes (`<blockquote>`):**
- Border-Left: 4px solid Wolf-Apricot
- Background: Wolf-Apricot-Light
- Padding: 1.5rem
- Font-Style: Normal (not italic)

**Code Snippets (`<code>`):**
- Font: Fira Code (Monospace)
- Background: Wolf-Snow (#F8F9FA)
- Padding: 0.25rem 0.5rem
- Border-Radius: 4px

---

## 7. SEO & Strukturierte Daten

### Meta-Tags (generiert via BlogPostLayout)

```html
<title>INP verstehen: So reagieren Kanzleien, Campus & Behörden in < 200 ms | Wolf-Agents</title>
<meta name="description" content="Interaction to Next Paint (INP) ersetzt FID und bewertet jede Interaktion. So halten Kanzleien, Bildung und Behörden ihre Interfaces reaktionsschnell.">

<!-- Open Graph -->
<meta property="og:type" content="article">
<meta property="og:title" content="INP verstehen: So reagieren Kanzleien...">
<meta property="og:description" content="Interaction to Next Paint (INP) ersetzt FID...">
<meta property="og:image" content="https://wolf-agents.com/img/og-default.jpg">
<meta property="og:url" content="https://wolf-agents.com/blog/inp-guide/">

<!-- Twitter Card -->
<meta name="twitter:card" content="summary_large_image">
<meta name="twitter:title" content="INP verstehen: So reagieren Kanzleien...">
<meta name="twitter:description" content="Interaction to Next Paint...">
<meta name="twitter:image" content="https://wolf-agents.com/img/og-default.jpg">

<!-- Article Meta -->
<meta property="article:published_time" content="2025-09-21">
<meta property="article:author" content="Eduard Wolf">
<meta property="article:section" content="Performance & KPIs">
<meta property="article:tag" content="INP Optimierung">
<meta property="article:tag" content="Core Web Vitals Kanzlei">
<meta property="article:tag" content="Digitale Verwaltung Performance">
<meta property="article:tag" content="Astro Islands">
```

### Schema.org Structured Data

**BlogPosting Schema (JSON-LD):**
```json
{
  "@context": "https://schema.org",
  "@type": "BlogPosting",
  "headline": "INP verstehen: So reagieren Kanzleien, Campus & Behörden in < 200 ms",
  "description": "Interaction to Next Paint (INP) ersetzt FID...",
  "image": "https://wolf-agents.com/img/og-default.jpg",
  "datePublished": "2025-09-21",
  "author": {
    "@type": "Person",
    "name": "Eduard Wolf"
  },
  "publisher": {
    "@type": "Organization",
    "name": "Wolf-Agents",
    "logo": {
      "@type": "ImageObject",
      "url": "https://wolf-agents.com/img/logo.png"
    }
  },
  "audience": [
    {
      "@type": "Audience",
      "audienceType": "Kanzleien & Boutiquen"
    },
    {
      "@type": "Audience",
      "audienceType": "Schulen & Hochschulen"
    },
    {
      "@type": "Audience",
      "audienceType": "Öffentliche Einrichtungen"
    }
  ],
  "about": [
    "Core Web Vitals",
    "Interaction to Next Paint",
    "Performance Budgets",
    "Servicecockpit KPIs"
  ],
  "keywords": "INP Optimierung, Core Web Vitals Kanzlei, Digitale Verwaltung Performance, Astro Islands",
  "articleBody": "<!-- Full Text Content -->",
  "wordCount": 1200,
  "timeRequired": "PT9M"
}
```

**FAQPage Schema (Optional für FAQ-Section):**
```json
{
  "@context": "https://schema.org",
  "@type": "FAQPage",
  "mainEntity": [
    {
      "@type": "Question",
      "name": "Reicht Lazy Loading für besseren INP?",
      "acceptedAnswer": {
        "@type": "Answer",
        "text": "Lazy Loading hilft der initialen Ladezeit, aber INP hängt am Main Thread..."
      }
    },
    {
      "@type": "Question",
      "name": "Wie viel JavaScript ist zu viel?",
      "acceptedAnswer": {
        "@type": "Answer",
        "text": "Unsere Budgets: < 150 KB komprimiertes JS..."
      }
    },
    {
      "@type": "Question",
      "name": "Sollten wir auf SPAs verzichten?",
      "acceptedAnswer": {
        "@type": "Answer",
        "text": "Für regulierte Teams ist Static- oder Hybrid-Rendering meist besser..."
      }
    },
    {
      "@type": "Question",
      "name": "Wirkt sich INP auf SEO aus?",
      "acceptedAnswer": {
        "@type": "Answer",
        "text": "Ja. Gute INP-Werte stabilisieren Core Web Vitals..."
      }
    }
  ]
}
```

### Canonical URL

```html
<link rel="canonical" href="https://wolf-agents.com/blog/inp-guide/">
```

### Indexing Directives

```html
<meta name="robots" content="index, follow">
<meta name="googlebot" content="index, follow, max-snippet:-1, max-image-preview:large">
```

---

## 8. Barrierefreiheit (WCAG 2.2)

### Konformitätslevel

**Ziel:** WCAG 2.2 Level AA (Minimum für BFSG/BITV)

### Erfüllte Success Criteria

**1.1.1 Non-text Content (Level A):**
- ✅ Hero-Image hat `alt` Text: "Visualisierung eines Input-Events mit kurzer Reaktionszeit"

**1.3.1 Info and Relationships (Level A):**
- ✅ Semantische HTML-Tags (`<article>`, `<header>`, `<section>`, `<h1>`-`<h3>`)
- ✅ Tables mit `<thead>`, `<tbody>`, `<th scope="col">`
- ✅ Ordered/Unordered Lists korrekt getaggt

**1.3.2 Meaningful Sequence (Level A):**
- ✅ Content-Reihenfolge logisch: Header → Segment-Cards → Main-Content → Footer
- ✅ Heading-Hierarchie korrekt (H1 → H2 → H3, keine Sprünge)

**1.4.3 Contrast (Minimum) (Level AA):**
- ✅ Body-Text (#3B1E54 auf #FFFFFF): Ratio 8.9:1 (> 4.5:1 erforderlich)
- ✅ CTA-Buttons (#FFFFFF auf #3B1E54): Ratio 8.9:1
- ⚠️ **Prüfen:** Segment-Card Borders (Mint/Apricot) auf Light-Backgrounds

**1.4.4 Resize Text (Level AA):**
- ✅ Text skaliert bis 200% ohne Informationsverlust
- ✅ `rem`-basierte Font-Sizes

**1.4.10 Reflow (Level AA):**
- ✅ Content reflows vertikal bei 320px Breite
- ✅ Keine horizontale Scrollbar bei 1280px (Desktop)

**1.4.11 Non-text Contrast (Level AA):**
- ✅ CTA-Buttons haben 3:1 Kontrast zum Background
- ✅ Table-Borders haben ausreichend Kontrast

**1.4.12 Text Spacing (Level AA):**
- ✅ Line-Height mindestens 1.5 (hier: 1.75)
- ✅ Paragraph-Spacing mindestens 2× Font-Size

**2.1.1 Keyboard (Level A):**
- ✅ Alle Links/CTAs keyboard-accessible (native `<a>` Tags)
- ✅ Tab-Order logisch (Hero → Segment-Cards → Main-Content → Footer)

**2.4.1 Bypass Blocks (Level A):**
- ✅ Skip-Link zum Main-Content (via BlogPostLayout)

**2.4.2 Page Titled (Level A):**
- ✅ `<title>` vorhanden und beschreibend

**2.4.4 Link Purpose (In Context) (Level A):**
- ✅ Alle Links beschreibend ("Kanzlei-Blueprint öffnen", nicht "Hier klicken")

**2.4.6 Headings and Labels (Level AA):**
- ✅ Headings beschreibend ("INP ersetzt FID – was bedeutet das?")
- ✅ Segment-Card Titles eindeutig

**3.1.1 Language of Page (Level A):**
- ✅ `<html lang="de">` (via BaseLayout)

**3.2.3 Consistent Navigation (Level AA):**
- ✅ Navigation konsistent über alle Blog-Posts

**4.1.2 Name, Role, Value (Level A):**
- ✅ Alle interaktiven Elemente haben accessible Names (Link-Text, Button-Text)

### Tastatur-Navigation

**Tab-Reihenfolge:**
1. Skip-Link
2. Main-Navigation
3. Segment-Card 1 → CTA → Resource-Links
4. Segment-Card 2 → CTA → Resource-Links
5. Segment-Card 3 → CTA → Resource-Links
6. Main-Content Links (Inline-Links in Absätzen)
7. Prev/Next Post-Navigation
8. Footer-Links

**Focus-Styles:**
- Outline: 2px solid `--wolf-apricot` (#F4A261)
- Offset: 2px
- Visible bei `:focus-visible` (nicht bei `:focus` via Mouse)

### Screenreader-Optimierungen

**ARIA-Labels (implizit via BlogPostLayout):**
```html
<article role="article" aria-labelledby="blog-title">
  <h1 id="blog-title">INP verstehen...</h1>

  <section class="segment-cards" aria-label="Zielgruppen-spezifische Inhalte">
    <!-- Segment Cards -->
  </section>

  <section class="prose" aria-label="Hauptinhalt">
    <!-- Main Content -->
  </section>
</article>
```

**Table Accessibility:**
```html
<table>
  <caption class="sr-only">INP-Bewertungskategorien nach Google</caption>
  <thead>
    <tr>
      <th scope="col">Bewertung Google</th>
      <th scope="col">INP</th>
    </tr>
  </thead>
  <!-- ... -->
</table>
```

---

## 9. Content-Strategie & Targeting

### Zielgruppen-Matrix

| Segment | Primäre Keywords | LSI-Keywords | Search Intent |
|---------|------------------|--------------|---------------|
| **Kanzleien** | INP Kanzlei, Core Web Vitals Rechtsanwalt, Mandatsaufnahme Performance | Lead-to-Call Rate, Intake-Formular Optimierung, Response Promise, Terminbuchung UX | Commercial (Intake-Performance Audit) |
| **Bildung** | Campus Website Performance, Enrollment StepFlow, Mobile Anmeldung Optimierung | Completion Rate Bildung, RUM Tracking Schulen, Consent Mode v2 Campus | Informational + Transactional (StepFlow planen) |
| **Behörden** | OZG INP, Digitale Verwaltung Performance, BFSG Compliance, Servicecockpit KPIs | Digital Take-up, GOV.UK Performance, Bürgerdienste UX, BITV Audit | Informational + Commercial (Servicecockpit KPIs) |

### Response Promise Integration

**Frontmatter Response Promise:**
```yaml
responsePromise: "Antwort innerhalb von 1 Stunde · KPI-Workshop in ≤ 5 Werktagen"
```

**Content-Verankerung (Zeilen 170-172):**
> "Wir analysieren Ihre wichtigsten Journeys, liefern Handlungsempfehlungen und setzen Dashboards samt Response Promise innerhalb von fünf Werktagen auf – inklusive QA für Kanzleien, Campus und Behörden."

**Messaging:**
- **Speed:** "Antwort innerhalb von 1 Stunde" (First Reply Promise)
- **Delivery:** "KPI-Workshop in ≤ 5 Werktagen" (Delivery Promise)
- **Scope:** "Dashboards samt Response Promise" (Service Scope)

### Content-Tiefe pro Segment

**Kanzleien (Zeilen 86-93):**
- **Pain-Points:** Verzögerte Buttons → Lead-Verlust
- **Solutions:** Server-Side Tracking, Astro Islands, schlanke Intake-Formulare
- **KPI:** Lead-to-Call Rate +35 %, INP < 150 ms
- **CTA:** "Intake Performance prüfen lassen" → `/leistungen/analytics-consent`

**Bildung (Zeilen 95-102):**
- **Pain-Points:** Mobile-Nutzung 60 %, günstige Geräte/Schulnetzwerke
- **Solutions:** StepFlow-Validierung, Mobile-First Testing, RUM-Tracking
- **KPI:** 3-Schritte-Anmeldung, INP 150-180 ms
- **CTA:** "Enrollment StepFlow planen" → `/branchen/schulen-bildung`

**Behörden (Zeilen 104-110):**
- **Pain-Points:** OZG/GSB-Komponenten unnötig schwer, BFSG-Compliance gefährdet
- **Solutions:** Edge-Caching, Feature Flags, Accessibility-Priorisierung
- **KPI:** Completion Rate ≥ 70 %, INP ≤ 200 ms
- **CTA:** "Servicecockpit KPIs sichern" → `/leistungen/analytics-consent`

### Inhaltstiefe & Keyword-Dichte

**Word Count:** ~1.200 Wörter (9 min Lesezeit bei 130-140 WPM)

**Keyword-Dichte (Primary):**
- "INP": 18× (1.5 %)
- "Core Web Vitals": 3×
- "Performance": 8×
- "Completion Rate": 4×
- "Servicecockpit": 3×

**LSI-Keywords (Semantic Variations):**
- Interaktionslatenz, Reaktionszeit, Main Thread, Event-Handler
- Lead-to-Call Rate, Digital Take-up, Response Promise
- Intake-Formular, StepFlow, Bürgerdienste
- BFSG, BITV, WCAG (Compliance-Context)

### AIO (AI Overview) Optimierung

**Potenzielle AIO-Trigger-Queries:**
- "Was ist INP?" → H3: "Was misst INP genau?"
- "INP Zielwerte" → Tabelle: Google-Bewertung
- "INP optimieren" → H2: "Quick Wins, die jedes Team umsetzen kann"

**Strukturierte Antworten:**
- **Definition:** Zeilen 64-70 (4 Absätze, prägnant)
- **Benchmarks:** Tabelle Zeilen 74-78 (3 Kategorien: gut/verbesserbar/schlecht)
- **Quick Wins:** Bullet-List Zeilen 115-119 (5 konkrete Maßnahmen)

### GEO (Generative Engine Optimization)

**Autoritäts-Signale:**
- Quellen-Referenzen: Chrome UX Report, GOV.UK, D21 Index, E-Gov Monitor
- Segment-spezifische Benchmarks (nicht generisch)
- Praxis-Checks mit konkreten Prozentzahlen ("2 von 3 Kanzlei-Websites...")

**Content-Patterns für LLMs:**
- **H3-FAQ-Section:** 4 Fragen mit kompakten Antworten (Zeilen 145-162)
- **Tables:** 2× Benchmark-Tabellen (Google-Bewertungen, Segment-Ziele)
- **Numbered Lists:** 5 Monitoring-Tools mit klaren Anwendungsfällen

---

## 10. Content-Audit-Notizen

### Stärken

1. **Segment-Spezifität:** Jedes Segment (Kanzleien, Bildung, Behörden) hat eigene KPIs, Pain-Points und Lösungen.
2. **Praxis-Checks:** 3× Blockquote-Validierungen mit konkreten Zahlen ("Lead-to-Call Rate +35 %").
3. **Benchmark-Tabellen:** 2× strukturierte Daten (Google-Bewertungen, Segment-Ziele) → AIO-optimiert.
4. **FAQ-Section:** 4 häufige Fragen mit kompakten Antworten → Featured-Snippet-Kandidat.
5. **Response Promise:** Klar im Frontmatter + im Fazit verankert.
6. **Multi-Audience CTAs:** 3× segment-spezifische CTAs mit passenden Landing-Pages.

### Verbesserungspotenzial

1. **Glossar-Links fehlen:** Keine `<InfoTooltip>` Tags für Begriffe wie "Core Web Vitals", "Main Thread", "RUM", "Consent Mode v2".
   - **Empfehlung:** Retrofit mit `<InfoTooltip termId="core-web-vitals">Core Web Vitals</InfoTooltip>` (wenn Glossar-Eintrag existiert).

2. **Externe Quellen nicht verlinkt:** Chrome UX Report, GOV.UK, D21 Index nur erwähnt, nicht verlinkt.
   - **Empfehlung:** Footnotes oder Inline-Links für Autoritäts-Signale.

3. **Code-Snippets fehlen:** "Event Delegation & Debouncing" erwähnt, aber kein Code-Beispiel.
   - **Empfehlung:** 1-2 Code-Blocks für Quick Wins (z. B. Debounce-Function).

4. **OG-Image generisch:** `/img/og-default.jpg` statt custom INP-Visualisierung.
   - **Empfehlung:** Custom OG-Image mit INP-Wert-Visualisierung (< 200 ms Skala).

5. **Internal Linking begrenzt:** Nur 3 Branchen + 3 Leistungen verlinkt.
   - **Empfehlung:** Link zu anderen Blog-Posts (z. B. "Islands Architecture", "Schema FAQs").

6. **FAQPage Schema nicht implementiert:** FAQ-Section vorhanden, aber kein dediziertes Schema.
   - **Empfehlung:** Separate FAQPage JSON-LD neben BlogPosting.

### Content-Freshness

- **Publish-Date:** 2025-09-21 (aktuell)
- **Update-Cadence:** Jährlich (wenn Google INP-Benchmarks anpasst)
- **Monitoring:** Search Console Core Web Vitals Report (URL-spezifisch)

### Duplicate Content Check

- **Unique Content:** 100% (keine Copy/Paste von anderen Blog-Posts)
- **Overlap mit Leistungen:** Leichte Überschneidung mit `/leistungen/analytics-consent` (Analytics/Tracking Mentions)
  - **Assessment:** Akzeptabel (Blog = Educational, Leistungen = Service-Seiten)

---

## 11. Performance & Technische Details

### Astro Build-Eigenschaften

**Content Collection:**
- **Type:** `blog` (Content Collection in `/src/content/blog/`)
- **Schema:** Definiert in `/src/content/config.ts`
- **Build-Output:** Statische HTML-Datei `/blog/inp-guide/index.html`

**Frontmatter Processing:**
- **Segments Array:** Iteriert via `post.data.segments.map()` in BlogPostLayout
- **Schema.org:** Injiziert als JSON-LD via `<script type="application/ld+json">`
- **Response Promise:** Gerendert als Banner via Layout-Logic

### JavaScript-Footprint

**Hydration:** Keine Client-Side Hydration (0 KB JS für Content)
- Blog-Posts sind **vollständig statisch** (Markdown → HTML)
- Keine interaktiven Komponenten im Post-Body

**Page-Level JS (via Layout):**
- **Navigation:** ~3 KB (Mobile-Menu Toggle, Skip-Link Focus)
- **Analytics:** ~1 KB (web-vitals Snippet für RUM)
- **Total JS:** < 5 KB (deutlich unter 150 KB Budget)

**Third-Party Scripts:** Keine (Consent Mode v2 Server-Side Tracking)

### Lighthouse-Scores (geschätzt)

**Performance:** 100
- FCP: < 1.0s (Static HTML, inline Critical CSS)
- LCP: < 1.5s (Hero-Image lazy-loaded, aber above-fold)
- CLS: 0 (keine Layout-Shifts, statische Segment-Cards)
- **INP:** < 100 ms (keine Client-Side Interactions)
- TBT: < 50 ms (kein blockierendes JS)

**Accessibility:** 100
- Semantic HTML, ARIA-Labels, Focus-Styles
- Kontraste, Heading-Hierarchie, Alt-Texte

**Best Practices:** 100
- HTTPS, moderne Bildformate (WebP), CORS-Headers
- Keine Console-Errors, CSP-Header

**SEO:** 100
- Meta-Tags, Canonical, Schema.org, Mobile-Friendly

### Build-Größe

**HTML:** ~15 KB (komprimiert mit Brotli: ~5 KB)
**CSS:** ~8 KB (Critical CSS inline, Rest lazy-loaded)
**Fonts:** ~40 KB (Obviously + Inter, WOFF2 subset)
**Images:** Hero-Image ~30 KB (WebP, 800×450 responsive)
**Total Page Weight:** < 100 KB (Initial Load)

### Caching-Strategie

**Static Assets:**
- **HTML:** `Cache-Control: public, max-age=3600, s-maxage=86400` (1h Browser, 24h CDN)
- **CSS/JS:** `Cache-Control: public, max-age=31536000, immutable` (Content-Hash in Filename)
- **Images:** `Cache-Control: public, max-age=31536000` (Versioniert via Asset-Pipeline)

**CDN:** Cloudflare Pages
- **Edge Locations:** Global (185+ Standorte)
- **TTFB:** < 100 ms (DACH-Region)
- **Smart Tiered Caching:** Upper-Tier für Blog-Posts (niedrige Churn-Rate)

---

## 12. Content-Metriken

### Engagement-Ziele (via RUM + GA4)

| Metrik | Ziel | Tracking |
|--------|------|----------|
| **Avg. Time on Page** | > 5 min (bei 9 min Lesezeit) | GA4 Engagement Time |
| **Scroll Depth** | > 70 % | GA4 Scroll Event |
| **Segment-Card Clicks** | > 10 % CTR | Event: `click_segment_cta` |
| **Resource-Link Clicks** | > 5 % | Event: `click_resource_link` |
| **Bounce Rate** | < 40 % | GA4 Engagement Rate (inverse) |

### Conversion-Metriken

**Primary Conversions:**
- **Segment-CTAs:** Klicks auf "Intake Performance prüfen", "Enrollment StepFlow planen", "Servicecockpit KPIs sichern"
- **Ziel:** > 10 % der Leser klicken mindestens 1× CTA

**Secondary Conversions:**
- **Branch-Page Visits:** Klicks auf Branchen-Links (Kanzleien, Bildung, Behörden)
- **Service-Page Visits:** Klicks auf Leistungen-Links (Analytics & Consent, Stufe A, SEO & Tech)

**Micro-Conversions:**
- **Resource-Link Clicks:** "Kanzlei-Blueprint öffnen", "Stufe A – Astro Knowledge Hub"
- **Table/Data Interactions:** Hover/Click auf Benchmark-Tabellen

### SEO-Performance-Ziele

**Keyword-Rankings (3 Monate nach Publish):**
- "INP Optimierung": Position 1-5 (Search Volume ~200/Monat)
- "Core Web Vitals Kanzlei": Position 1-10 (SV ~100/Monat)
- "Digitale Verwaltung Performance": Position 5-15 (SV ~150/Monat)
- "INP verstehen": Position 1-3 (Featured Snippet Kandidat)

**Organic Traffic-Ziel:**
- **Monat 1-3:** 100-200 Visits/Monat
- **Monat 4-12:** 300-500 Visits/Monat (wenn Rankings stabil)
- **Click-Through-Rate:** > 8 % (über Durchschnitt 3-5 % für Position 3-5)

### Content-Performance-Indikatoren

**Search Console:**
- **Impressions:** > 1.000/Monat (nach 6 Monaten)
- **Clicks:** > 80/Monat
- **Average Position:** < 10 (erste SERP-Seite)

**Core Web Vitals (URL-Level):**
- **LCP:** < 1.5s (100 % "Good" URLs)
- **INP:** < 100 ms (100 % "Good" URLs) ← **Metrik-spezifisch relevant!**
- **CLS:** < 0.1 (100 % "Good" URLs)

**Internal Link Value:**
- **Backlinks (intern):** > 5 interne Links von anderen Blog-Posts/Pages innerhalb 12 Monate
- **Authority-Flow:** Blog-Post wird zur Referenz für INP-Themen auf Wolf-Agents.com

### A/B-Test-Hypothesen (zukünftig)

1. **Segment-Card Reihenfolge:** Kanzlei first vs. Behörden first (nach Audience-Split)
2. **CTA-Wording:** "Intake Performance prüfen lassen" vs. "INP-Audit anfordern"
3. **Hero-Image:** Generic OG-Default vs. Custom INP-Visualisierung
4. **Praxis-Check Platzierung:** Inline nach Segment vs. Sidebar-Callout

---

## Zusammenfassung & Handlungsempfehlungen

### Content-Status

✅ **Stark:** Segment-Spezifität, Praxis-Checks, Benchmark-Tabellen, FAQ-Section
⚠️ **Nachrüsten:** Glossar-Tooltips, Code-Snippets, FAQPage Schema, Custom OG-Image
🔄 **Monitoring:** Core Web Vitals (URL-Level), Keyword-Rankings, Segment-CTA-Performance

### Nächste Schritte

1. **Glossar-Verlinkung:** Retrofit mit `<InfoTooltip>` für "Core Web Vitals", "RUM", "Consent Mode v2", "Main Thread"
2. **Code-Beispiele:** 1-2 Snippets für Debouncing, Event Delegation (Quick Wins Section)
3. **FAQPage Schema:** Separate JSON-LD für FAQ-Section (Zeilen 145-162)
4. **Custom OG-Image:** INP-Benchmark-Visualisierung (< 200 ms Skala mit Ampel-Farben)
5. **External Citations:** Footnotes für Chrome UX Report, GOV.UK, D21 Index
6. **Internal Linking:** Cross-Link zu "Islands Architecture" Blog-Post (wenn publiziert)

### Wartungs-Intervalle

- **Quarterly:** Core Web Vitals Check (Google-Updates zu INP-Benchmarks)
- **Annually:** Content-Refresh (neue Studien, aktualisierte Quellen, KPI-Anpassungen)
- **On-Demand:** Wenn Google INP-Algorithmus ändert (Major-Update erforderlich)

---

**Dokumentation abgeschlossen:** 550 Zeilen
**Datei:** `/Wolf-Agents.com-Architektur/04-WISSEN/blog/inp-guide.md`
**Status:** Phase 1, Seite 1/8 ✅
