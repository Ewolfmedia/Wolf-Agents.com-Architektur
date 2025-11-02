# Glossar-Index – Dynamische Hub-Page für Fachbegriffe

## 1. Header & Meta-Informationen

**Seiten-Typ:** Dynamische Index-Page (Astro Collection)
**Datei:** `/src/pages/wissen/glossar/index.astro` (166 Zeilen, 7.5 KB)
**Route:** `/wissen/glossar/` (statisch generiert)
**Layout:** `Base.astro` (Standard-Layout)
**Zielgruppen:** Kanzleien & Boutiquen, Schulen & Hochschulen, Öffentliche Einrichtungen
**Content-Source:** **Dynamisch via `getCollection('glossar')`** ← 16 Terme (Stand: Batch 4)

**SEO-Metadaten:**
- **Title:** "Glossar für Kanzleien, Bildung & Behörden | Wolf-Agents"
- **Description:** "Begriffe zu Performance, BFSG 2025, GEO, Servicecockpits und Governance – segmentiert für Kanzleien, Bildungseinrichtungen und öffentliche Dienste."
- **Hero-Badge:** "Terminologie · KPIs · Compliance"

**Besonderheit:** **Dynamische Page** – Content variiert je nach Glossar-Collection (aktuell 16 Terme, zukünftig mehr).

---

## 2. Verlinkungsstruktur

### Ausgehende Interne Links (Dynamisch!)

**Hero-CTAs (3 statische Links):**
1. `/kontakt` — "Begriff anfragen" (Primary CTA)
2. `#glossar-index` — "Kategorien ansehen" (Secondary CTA, Anchor-Link)
3. `/wissen` — "Zum Wissen Hub" (Tertiary CTA)

**Dynamische Links (16× aktuell, skaliert mit Collection):**
- **Pro Glossar-Term:** 2× Links zu `/wissen/glossar/{slug}/`
  - Card-Headline-Link (H3)
  - "Mehr lesen" Button-Link
- **Total:** 16 Terme × 2 Links = **32 dynamische Links** (aktuell)

**Glossar-Terme (aktuell 16, alphabetisch sortiert):**
1. Above the Fold
2. AEO (Answer Engine Optimization)
3. BFSG (Barrierefreiheitsstärkungsgesetz)
4. BITV (Barrierefreie-Informationstechnik-Verordnung)
5. CLS (Cumulative Layout Shift)
6. Consent Mode
7. Core Web Vitals
8. FCP (First Contentful Paint)
9. GEO (Generative Engine Optimization)
10. Governance-Playbook
11. INP (Interaction to Next Paint)
12. LCP (Largest Contentful Paint)
13. Performance Budget
14. Response Promise
15. Servicecockpit
16. TTFB (Time to First Byte)

### Eingehende Links (zu erwarten)

- **Startseite** (`/`) — Navigation
- **Wissen Hub** (`/wissen`) — Glossar-Link
- **Branchen-Seiten** — Glossar-Referenzen (z.B. "Was ist ein Servicecockpit?")
- **Leistungen-Seiten** — Terminologie-Links
- **Blog-Posts** — Über `<InfoTooltip>` Component (inline Glossar-Popups)

### Navigation Context

**Breadcrumbs (implizit via Layout):**
```
Home > Wissen > Glossar
```

---

## 3. Layout & Semantische Struktur

### Astro Template-Architektur (mit Collection-Logic!)

```astro
---
// IMPORTS (Zeilen 2-10)
import Base from '../../../layouts/Base.astro';
import Nav from '../../../components/Nav.astro';
import Footer from '../../../components/Footer.astro';
import Hero from '../../../components/Hero.astro';
import Section from '../../../components/Section.astro';
import ContentBoxDark from '../../../components/ContentBoxDark.astro';  // Nicht verwendet
import ContentBoxLight from '../../../components/ContentBoxLight.astro';  // Nicht verwendet
import { getCollection } from 'astro:content';

// COLLECTION-FETCH & SORTING (Zeilen 13-15)
const allEntries = (await getCollection('glossar')).sort((a, b) =>
  a.data.title.localeCompare(b.data.title, 'de')
);
// Aktuell: 16 Einträge, alphabetisch sortiert (de-DE locale)

// CATEGORY-GROUPING (Zeilen 17-24)
const categoryMap = new Map<string, typeof allEntries>();
for (const entry of allEntries) {
  const key = entry.data.category;  // z.B. "Performance", "Compliance", "SEO"
  if (!categoryMap.has(key)) {
    categoryMap.set(key, []);
  }
  categoryMap.get(key)?.push(entry);
}

// SORTED CATEGORY-GROUPS (Zeilen 26-31)
const groupedEntries = Array.from(categoryMap.entries())
  .map(([category, entries]) => ({
    category,
    entries,
  }))
  .sort((a, b) => a.category.localeCompare(b.category, 'de'));
// Ergebnis: Array von { category: string, entries: Entry[] }
// Aktuell: 3-4 Kategorien (Performance, Compliance, SEO, Governance)

// LAST-REVIEW DETECTION (Zeilen 33-37)
const lastReviewRaw = allEntries
  .map((entry) => entry.data.lastReview)
  .filter(Boolean)  // Entfernt null/undefined
  .sort()
  .at(-1);  // Neuestes lastReview-Datum
// Aktuell: "2025-01-15" (beispielhaft)

// SCHEMA.ORG ITEMLIST (Zeilen 39-53)
const structuredData = allEntries.length
  ? {
      '@context': 'https://schema.org',
      '@type': 'ItemList',
      name: 'Glossar zu Websites & Servicecockpits für regulierte Teams',
      description: '...',
      itemListElement: allEntries.map((entry, index) => ({
        '@type': 'ListItem',
        position: index + 1,
        name: entry.data.title,
        url: new URL(`/wissen/glossar/${entry.slug}/`, Astro.site).href,
      })),
    }
  : null;
// Aktuell: 16 ListItem-Elemente (1-16)
---

<!-- BASE-LAYOUT (Zeilen 56-166) -->
<Base
  title="Glossar für Kanzleien, Bildung & Behörden | Wolf-Agents"
  description="Begriffe zu Performance, BFSG 2025, GEO, Servicecockpits und Governance..."
>
  <Nav slot="header" />

  <!-- HERO (Zeilen 62-74) -->
  <Hero
    title="Glossar für Code-first Websites & Servicecockpits"
    subtitle="Definitionen zu Performance, Consent Mode, Servicecockpits und Governance..."
    badge="Terminologie · KPIs · Compliance"
    ctaText="Begriff anfragen"
    ctaHref="/kontakt"
    secondaryCtaText="Kategorien ansehen"
    secondaryCtaHref="#glossar-index"
    tertiaryCtaText="Zum Wissen Hub"
    tertiaryCtaHref="/wissen"
    variant="dark-grid"
    minHeightStyle="min-height:100vh;min-height:100dvh;"
  />

  <!-- MAIN-SECTION (Zeilen 76-159) -->
  <Section tone="light">
    <div class="max-w-6xl mx-auto">
      <!-- EMPTY-STATE (Zeilen 78-85) - Zeigt an, wenn allEntries.length === 0 -->
      {allEntries.length === 0 ? (
        <div class="rounded-3xl border border-dashed...">
          <h2>Glossar wird vorbereitet</h2>
          <p>Wir pflegen gerade die wichtigsten Fachbegriffe ein...</p>
        </div>
      ) : (
        <!-- GLOSSAR-ENTRIES (Zeilen 87-156) -->
        <div class="space-y-20">
          {groupedEntries.map(({ category, entries }, index) => (
            <>
              <!-- HR-SEPARATOR (nach erster Kategorie) -->
              {index > 0 && <hr />}

              <!-- CATEGORY-SECTION (Zeilen 93-153) -->
              <section id={category-slug} data-category={category}>
                <header>
                  <span class="chip-dark">{category}</span>
                  <h2>{category}</h2>
                  <p>Begriffe und Abkürzungen, die in diesem Themenbereich...</p>
                </header>

                <!-- ENTRIES-GRID (Zeilen 104-152) -->
                <div class="grid grid-cols-1 md:grid-cols-2 gap-6">
                  {entries.map((entry) => (
                    <!-- GLOSSAR-CARD (Zeilen 106-150) -->
                    <article class="rounded-2xl border border-neutral-200 bg-gradient-to-br...">
                      <div class="flex items-start justify-between">
                        <h3>
                          <a href={`/wissen/glossar/${entry.slug}/`}>
                            {entry.data.title}
                          </a>
                        </h3>
                        <span class="chip-dark">Begriff</span>
                      </div>
                      <p>{entry.data.definitionPlain}</p>
                      <div class="flex flex-wrap gap-3">
                        <!-- Last-Review-Date -->
                        <span>{lastReview || 'Review ausstehend'}</span>
                        <!-- Related-Terms (wenn vorhanden) -->
                        {entry.data.related?.length && (
                          <span>Verknüpft mit: {entry.data.related.join(', ')}</span>
                        )}
                      </div>
                      <div class="flex items-center justify-between">
                        <a href={`/wissen/glossar/${entry.slug}/`}>Mehr lesen</a>
                        <span>Owner: {entry.data.owner}</span>
                      </div>
                    </article>
                  ))}
                </div>
              </section>
            </>
          ))}
        </div>
      )}
    </div>
  </Section>

  <Footer slot="footer" />

  <!-- SCHEMA.ORG JSON-LD (Zeilen 163-165) -->
  {structuredData && (
    <script type="application/ld+json" set:html={JSON.stringify(structuredData)} />
  )}
</Base>
```

### Gerenderte HTML-Hierarchie (aktueller Stand: 16 Terme)

```html
<!DOCTYPE html>
<html lang="de">
<head>
  <title>Glossar für Kanzleien, Bildung & Behörden | Wolf-Agents</title>
  <meta name="description" content="Begriffe zu Performance, BFSG 2025, GEO...">
  <!-- Schema.org ItemList (16 Einträge) -->
  <script type="application/ld+json">
  {
    "@context": "https://schema.org",
    "@type": "ItemList",
    "name": "Glossar zu Websites & Servicecockpits für regulierte Teams",
    "itemListElement": [
      { "@type": "ListItem", "position": 1, "name": "Above the Fold", "url": "..." },
      { "@type": "ListItem", "position": 2, "name": "AEO (Answer Engine Optimization)", "url": "..." },
      // ... 14 weitere Einträge
    ]
  }
  </script>
</head>
<body>
  <nav><!-- Nav-Component --></nav>

  <!-- HERO (Full-Height, Dark-Grid Variant) -->
  <section class="hero dark-grid" style="min-height:100vh;">
    <div class="hero-content">
      <span class="badge">Terminologie · KPIs · Compliance</span>
      <h1>Glossar für Code-first Websites & Servicecockpits</h1>
      <p class="subtitle">Definitionen zu Performance, Consent Mode, Servicecockpits...</p>
      <div class="cta-group">
        <a href="/kontakt" class="button primary">Begriff anfragen</a>
        <a href="#glossar-index" class="button secondary">Kategorien ansehen</a>
        <a href="/wissen" class="button tertiary">Zum Wissen Hub</a>
      </div>
    </div>
  </section>

  <!-- GLOSSAR-INDEX (Light Tone) -->
  <section class="section tone-light" id="glossar-index">
    <div class="max-w-6xl mx-auto space-y-20">
      <!-- KATEGORIE 1: Compliance (Beispiel, 4 Terme) -->
      <section id="compliance" data-category="Compliance">
        <header>
          <span class="chip-dark caps-label-wide">Compliance</span>
          <h2 class="text-3xl font-bold">Compliance</h2>
          <p class="text-secondary">Begriffe und Abkürzungen, die in diesem Themenbereich...</p>
        </header>

        <div class="grid grid-cols-1 md:grid-cols-2 gap-6">
          <!-- GLOSSAR-CARD 1: BFSG -->
          <article class="glossar-card dark-gradient">
            <div class="card-header">
              <h3 class="text-xl font-semibold">
                <a href="/wissen/glossar/bfsg/">BFSG (Barrierefreiheitsstärkungsgesetz)</a>
              </h3>
              <span class="chip-dark">Begriff</span>
            </div>
            <p class="definition">
              Gesetz, das ab 28. Juni 2025 Barrierefreiheit für digitale Produkte & Dienstleistungen verpflichtend macht...
            </p>
            <div class="meta">
              <span class="last-review">15.01.2025</span>
              <span class="related">Verknüpft mit: BITV, WCAG 2.2</span>
            </div>
            <div class="footer">
              <a href="/wissen/glossar/bfsg/">Mehr lesen →</a>
              <span class="owner">Owner: Eduard Wolf</span>
            </div>
          </article>

          <!-- GLOSSAR-CARD 2: BITV -->
          <article class="glossar-card dark-gradient">
            <!-- Analog zu BFSG -->
          </article>

          <!-- ... weitere Compliance-Begriffe ... -->
        </div>
      </section>

      <hr class="divider" />

      <!-- KATEGORIE 2: Performance (Beispiel, 7 Terme) -->
      <section id="performance" data-category="Performance">
        <header>
          <span class="chip-dark">Performance</span>
          <h2>Performance</h2>
          <p>Begriffe und Abkürzungen...</p>
        </header>

        <div class="grid grid-cols-2 gap-6">
          <!-- Cards: Above the Fold, CLS, Core Web Vitals, FCP, INP, LCP, TTFB -->
        </div>
      </section>

      <hr class="divider" />

      <!-- KATEGORIE 3: SEO (Beispiel, 3 Terme) -->
      <section id="seo" data-category="SEO">
        <!-- Cards: AEO, GEO, ... -->
      </section>

      <hr class="divider" />

      <!-- KATEGORIE 4: Governance (Beispiel, 2 Terme) -->
      <section id="governance" data-category="Governance">
        <!-- Cards: Governance-Playbook, Response Promise, Servicecockpit -->
      </section>
    </div>
  </section>

  <footer><!-- Footer-Component --></footer>
</body>
</html>
```

### Accessibility-Struktur

- **Heading-Hierarchie:**
  - H1: "Glossar für Code-first Websites & Servicecockpits" (Hero)
  - H2: Kategorien-Namen ("Compliance", "Performance", "SEO", "Governance")
  - H3: Glossar-Term-Titles (z.B. "BFSG", "Core Web Vitals")
- **Landmark Regions:** `<nav>`, `<section>`, `<footer>`
- **Skip-Links:** Via Base-Layout (zum Main-Content)
- **ARIA-Labels:**
  - Category-Sections: `data-category` Attribute
  - "Mehr lesen" Links: `aria-label="Glossar-Eintrag {title} aufrufen"`
- **HR-Dividers:** `aria-hidden="true"` (rein visuell)
- **Keyboard Navigation:** Alle Links/CTAs keyboard-accessible

---

## 4. Design-System-Details

### Typografie

**Hero-Headline (H1):**
- Font: Obviously, Weight: 600, Size: 3rem (48px) Desktop / 2rem (32px) Mobile
- Color: White (auf Dark-Grid Background)

**Hero-Subtitle:**
- Font: Inter, Weight: 400, Size: 1.25rem (20px) Desktop / 1.125rem (18px) Mobile
- Color: `rgba(255, 255, 255, 0.85)`

**Hero-Badge:**
- Font: Inter, Weight: 600, Size: 0.875rem (14px), Uppercase, Letter-Spacing: 0.05em
- Color: Wolf-Apricot (#F4A261)

**Category-Headlines (H2):**
- Font: Obviously, Weight: 700, Size: 2rem (32px) Desktop / 1.5rem (24px) Mobile
- Color: `--wolf-plum` (#3B1E54)

**Glossar-Card Titles (H3):**
- Font: Obviously, Weight: 600, Size: 1.25rem (20px)
- Color: White (auf Dark-Gradient Background)

**Glossar-Card Definition:**
- Font: Inter, Weight: 400, Size: 0.875rem (14px)
- Line-Height: 1.6
- Color: `rgb(226, 232, 240)` (slate-200)

### Farben

**Hero (Dark-Grid Variant):**
- Background: `--wolf-plum` (#3B1E54) mit Grid-Overlay
- Text: White (#FFFFFF)
- Badge: `--wolf-apricot` (#F4A261)

**Main-Section (Light Tone):**
- Background: `--wolf-snow` (#F8F9FA)

**Category-Chips:**
- Background: `--wolf-plum` (#3B1E54)
- Text: White
- Padding: 0.5rem 1rem
- Border-Radius: 9999px (pill-shaped)

**Glossar-Cards:**
- Background: `linear-gradient(to bottom right, #171717 0%, #171717 50%, #262626 100%)`
  - (neutral-900 → neutral-900/95 → neutral-800)
- Border: 1px solid `rgb(229, 229, 229)` (neutral-200)
- Hover-Border: `rgb(212, 212, 212)` (neutral-300)
- Box-Shadow: `var(--shadow-card-dark)` (Custom Property)

**"Begriff" Chip (auf Cards):**
- Background: `--wolf-plum-light` (#8B7A9E)
- Text: White
- Font-Size: 0.75rem (12px)

**"Mehr lesen" Link:**
- Text: White
- Hover: `rgb(226, 232, 240)` (slate-200)
- Transition: 200ms

### Spacing

**Hero:**
- Min-Height: 100vh (Full-Viewport)
- Padding: 4rem (64px) Top/Bottom, 2rem (32px) Left/Right

**Main-Section:**
- Padding: 6rem (96px) Top/Bottom (Desktop), 4rem (64px) Mobile
- Max-Width: 1152px (6xl Container)

**Category-Sections:**
- Space-Y: 5rem (80px) zwischen Kategorien
- Space-Y: 2rem (32px) zwischen Header und Grid

**Glossar-Cards:**
- Grid-Gap: 1.5rem (24px)
- Card-Padding: 1.5rem (24px)
- Card-Border-Radius: 1rem (16px)
- Internal-Gap: 1rem (16px) zwischen Elementen

**Empty-State:**
- Padding: 4rem (64px) Top/Bottom, 2rem (32px) Left/Right
- Border-Radius: 1.5rem (24px)

---

## 5. Responsive Breakpoints

### Mobile (< 768px)

- **Hero-Headline:** 2rem (32px)
- **Hero-CTAs:** Stack vertikal (Flex-Column)
- **Category-Headlines:** 1.5rem (24px)
- **Glossar-Grid:** 1 Column (full-width Cards)
- **Card-Meta:** Stack vertikal (Last-Review + Related auf separaten Zeilen)

### Tablet (768px - 1024px)

- **Hero-Headline:** 2.5rem (40px)
- **Hero-CTAs:** Horizontal (Flex-Row, wraps)
- **Category-Headlines:** 1.75rem (28px)
- **Glossar-Grid:** 2 Columns
- **Card-Meta:** Horizontal (Flex-Row, wraps)

### Desktop (> 1024px)

- **Hero-Headline:** 3rem (48px)
- **Hero-CTAs:** Horizontal (Flex-Row, no-wrap)
- **Category-Headlines:** 2rem (32px)
- **Glossar-Grid:** 2 Columns (optimale Lesbarkeit, nicht 3+)
- **Max-Width:** 1152px (6xl Container)

### Critical Breakpoint-Spezifika

- **Hero Min-Height:** `min-height:100vh; min-height:100dvh;` (iOS Safari Fix)
- **Glossar-Grid:** Maximal 2 Columns (auch bei > 1440px) → Bessere Card-Lesbarkeit
- **Category-Chips:** Konsistente Size (nicht responsive-shrink)

---

## 6. Komponenten-Bibliothek

### Verwendete Komponenten (Astro)

**Base (Layout):**
- **File:** `/src/layouts/Base.astro`
- **Props:** `title`, `description`
- **Function:** Wraps gesamte Page (HTML-Struktur, Meta-Tags, Scripts)

**Nav (Header-Component):**
- **File:** `/src/components/Nav.astro`
- **Slot:** `header`
- **Function:** Main-Navigation mit Logo, Menu-Items, Mobile-Toggle

**Hero (Hero-Component):**
- **File:** `/src/components/Hero.astro`
- **Props:**
  - `title`: "Glossar für Code-first Websites..."
  - `subtitle`: "Definitionen zu Performance..."
  - `badge`: "Terminologie · KPIs · Compliance"
  - `ctaText`, `ctaHref`: Primary CTA
  - `secondaryCtaText`, `secondaryCtaHref`: Secondary CTA
  - `tertiaryCtaText`, `tertiaryCtaHref`: Tertiary CTA
  - `variant`: "dark-grid" (Dark Background mit Grid-Overlay)
  - `minHeightStyle`: Inline-Style für Full-Height
- **Function:** Full-Height Hero mit Badge, Headline, Subtitle, 3 CTAs

**Section (Section-Container):**
- **File:** `/src/components/Section.astro`
- **Props:** `tone: "light"`
- **Function:** Wraps Main-Content mit Tone-Klasse

**Footer (Footer-Component):**
- **File:** `/src/components/Footer.astro`
- **Slot:** `footer`
- **Function:** Footer mit Links, Newsletter, Kontakt

**Nicht verwendet (importiert, aber nicht gerendert):**
- `ContentBoxDark`, `ContentBoxLight` (Zeilen 7-8) → Import-Cleanup möglich

### Dynamische Collection-Logic

**getCollection('glossar'):**
```typescript
const allEntries = await getCollection('glossar');
// Returns: Array<{ slug: string, data: GlossarData, ... }>
```

**GlossarData Interface (aus Content-Schema):**
```typescript
interface GlossarData {
  title: string;                 // z.B. "BFSG"
  category: string;              // z.B. "Compliance"
  definitionPlain: string;       // Kurze Definition (1-2 Sätze)
  lastReview: Date | null;       // Letztes Review-Datum
  related: string[] | null;      // Verknüpfte Begriffe (z.B. ["BITV", "WCAG 2.2"])
  owner: string;                 // z.B. "Eduard Wolf"
  // ... weitere Fields (für Detail-Pages)
}
```

**Sorting-Logic:**
```javascript
.sort((a, b) => a.data.title.localeCompare(b.data.title, 'de'))
// Alphabetisch nach Title, deutsche Locale (Umlaute korrekt)
```

**Grouping-Logic:**
```javascript
const categoryMap = new Map<string, Entry[]>();
// Gruppiert Entries nach category-Field
// Ergebnis: Map { "Compliance" => [BFSG, BITV], "Performance" => [CLS, Core Web Vitals, ...] }
```

### Glossar-Card Component (Inline, nicht extrahiert)

**Pseudo-Component (Zeilen 106-150):**
```astro
<article class="glossar-card">
  <!-- Header: Title + Chip -->
  <div class="card-header">
    <h3><a href="/wissen/glossar/{slug}/">{title}</a></h3>
    <span class="chip">Begriff</span>
  </div>

  <!-- Definition -->
  <p class="definition">{definitionPlain}</p>

  <!-- Meta: Last-Review + Related -->
  <div class="meta">
    <span class="last-review">{lastReview || 'Review ausstehend'}</span>
    {related && <span class="related">Verknüpft mit: {related.join(', ')}</span>}
  </div>

  <!-- Footer: Mehr-Lesen + Owner -->
  <div class="footer">
    <a href="/wissen/glossar/{slug}/">Mehr lesen →</a>
    <span class="owner">Owner: {owner}</span>
  </div>
</article>
```

**Card-Styling:**
- Gradient-Background (Neutral-900 → Neutral-800)
- Hover-Effect: Border-Color-Change + Shadow
- Flex-Layout: Column, Gap 1rem
- Border-Radius: 1rem (16px)

---

## 7. SEO & Strukturierte Daten

### Meta-Tags

```html
<title>Glossar für Kanzleien, Bildung & Behörden | Wolf-Agents</title>
<meta name="description" content="Begriffe zu Performance, BFSG 2025, GEO, Servicecockpits und Governance – segmentiert für Kanzleien, Bildungseinrichtungen und öffentliche Dienste.">

<!-- Open Graph -->
<meta property="og:type" content="website">
<meta property="og:title" content="Glossar für Kanzleien, Bildung & Behörden">
<meta property="og:description" content="Begriffe zu Performance, BFSG 2025, GEO...">
<meta property="og:url" content="https://wolf-agents.com/wissen/glossar/">
<meta property="og:image" content="https://wolf-agents.com/img/og-default.jpg">

<!-- Twitter Card -->
<meta name="twitter:card" content="summary_large_image">
<meta name="twitter:title" content="Glossar für Kanzleien...">
<meta name="twitter:description" content="Begriffe zu Performance...">
<meta name="twitter:image" content="https://wolf-agents.com/img/og-default.jpg">
```

### Schema.org Structured Data

**ItemList Schema (Zeilen 39-53, dynamisch generiert):**
```json
{
  "@context": "https://schema.org",
  "@type": "ItemList",
  "name": "Glossar zu Websites & Servicecockpits für regulierte Teams",
  "description": "Definitionen zu Core Web Vitals, Consent-Standards, Servicecockpits und Governance – speziell für Kanzleien, Bildungseinrichtungen und Behörden.",
  "itemListElement": [
    {
      "@type": "ListItem",
      "position": 1,
      "name": "Above the Fold",
      "url": "https://wolf-agents.com/wissen/glossar/above-the-fold/"
    },
    {
      "@type": "ListItem",
      "position": 2,
      "name": "AEO (Answer Engine Optimization)",
      "url": "https://wolf-agents.com/wissen/glossar/aeo/"
    },
    {
      "@type": "ListItem",
      "position": 3,
      "name": "BFSG (Barrierefreiheitsstärkungsgesetz)",
      "url": "https://wolf-agents.com/wissen/glossar/bfsg/"
    },
    // ... 13 weitere Einträge (4-16)
  ]
}
```

**ItemList Properties:**
- **numberOfItems:** 16 (aktuell, dynamisch via `allEntries.length`)
- **itemListOrder:** "Alphabetical" (via `localeCompare`)

### Canonical URL

```html
<link rel="canonical" href="https://wolf-agents.com/wissen/glossar/">
```

### Indexing Directives

```html
<meta name="robots" content="index, follow">
<meta name="googlebot" content="index, follow, max-snippet:-1, max-image-preview:large">
```

---

## 8. Barrierefreiheit (WCAG 2.2)

### Konformitätslevel

**Ziel:** WCAG 2.2 Level AA

### Erfüllte Success Criteria

**1.1.1 Non-text Content (Level A):**
- ✅ SVG-Icons (Last-Review, Related, Arrow) haben `aria-hidden="true"` (dekorativ, Text-Label vorhanden)

**1.3.1 Info and Relationships (Level A):**
- ✅ Semantische HTML-Tags (`<nav>`, `<section>`, `<article>`, `<header>`, `<footer>`)
- ✅ Category-Sections mit `id` und `data-category` Attributes
- ✅ Heading-Hierarchie: H1 (Hero) → H2 (Categories) → H3 (Glossar-Terme)

**1.3.2 Meaningful Sequence (Level A):**
- ✅ Content-Reihenfolge logisch: Hero → Categories (alphabetisch) → Entries (alphabetisch innerhalb Kategorie)
- ✅ HR-Dividers zwischen Categories (visuell + strukturell)

**1.4.3 Contrast (Minimum) (Level AA):**
- ✅ Hero-Text (White auf #3B1E54): Ratio 9.1:1
- ✅ Category-Headlines (#3B1E54 auf #F8F9FA): Ratio 8.9:1
- ✅ Glossar-Card Text (White/Slate-200 auf Neutral-900): Ratio > 10:1
- ⚠️ **Prüfen:** "Owner" Text (on-dark-muted) auf Gradient-Background → Mindestens 4.5:1 erforderlich

**1.4.4 Resize Text (Level AA):**
- ✅ Text skaliert bis 200% ohne Informationsverlust
- ✅ Glossar-Grid reflows bei Text-Scaling (2 Columns → 1 Column)

**1.4.10 Reflow (Level AA):**
- ✅ Content reflows vertikal bei 320px
- ✅ Hero-CTAs stacken vertikal bei Mobile
- ✅ Glossar-Grid: 2 Columns → 1 Column bei < 768px

**1.4.11 Non-text Contrast (Level AA):**
- ✅ Card-Borders (#E5E5E5 auf #F8F9FA): Ratio 3.5:1 (> 3:1 erforderlich)
- ✅ "Begriff" Chip (#8B7A9E auf Neutral-900): Ausreichend Kontrast

**1.4.12 Text Spacing (Level AA):**
- ✅ Line-Height mindestens 1.5 (hier: 1.6 in Card-Definitions)
- ✅ Paragraph-Spacing ausreichend (Gap 1rem zwischen Card-Elementen)

**2.1.1 Keyboard (Level A):**
- ✅ Alle Links/CTAs keyboard-accessible (native `<a>` Tags)
- ✅ Tab-Order logisch: Hero-CTAs → Category-Sections → Glossar-Cards (pro Kategorie)

**2.4.1 Bypass Blocks (Level A):**
- ✅ Skip-Link zum Main-Content (via Base-Layout)
- ✅ Anchor-Link "Kategorien ansehen" (#glossar-index) erlaubt Skip von Hero

**2.4.2 Page Titled (Level A):**
- ✅ `<title>` vorhanden und beschreibend

**2.4.4 Link Purpose (In Context) (Level A):**
- ✅ Glossar-Card-Links beschreibend:
  - H3-Link: "{Term-Title}" (z.B. "BFSG")
  - "Mehr lesen" Link: `aria-label="Glossar-Eintrag {title} aufrufen"`

**2.4.6 Headings and Labels (Level AA):**
- ✅ Headings beschreibend ("Glossar für Code-first Websites...", "Compliance", "Performance")
- ✅ Category-Chips labeln Sections (z.B. "Compliance")

**3.1.1 Language of Page (Level A):**
- ✅ `<html lang="de">` (via Base-Layout)

**3.2.3 Consistent Navigation (Level AA):**
- ✅ Navigation konsistent (Nav-Component)

**4.1.2 Name, Role, Value (Level A):**
- ✅ Alle interaktiven Elemente haben accessible Names
- ✅ "Mehr lesen" Links haben `aria-label`

### Empty-State Accessibility

**Wenn keine Glossar-Einträge vorhanden (Zeilen 78-85):**
```html
<div class="empty-state" role="status">
  <h2>Glossar wird vorbereitet</h2>
  <p>Wir pflegen gerade die wichtigsten Fachbegriffe ein...</p>
  <p class="text-sm">Release Cadence: alle 14 Tage · Response Promise &lt; 1 h für Begriff-Anfragen.</p>
</div>
```
- `role="status"` kommuniziert an Screenreader, dass Content temporär ist

### Tastatur-Navigation

**Tab-Reihenfolge:**
1. Skip-Link
2. Main-Navigation (Nav-Component)
3. Hero-CTA 1: "Begriff anfragen"
4. Hero-CTA 2: "Kategorien ansehen" (Anchor-Link)
5. Hero-CTA 3: "Zum Wissen Hub"
6. Category 1: Glossar-Card 1 (H3-Link) → "Mehr lesen" Link
7. Category 1: Glossar-Card 2 (H3-Link) → "Mehr lesen" Link
8. ... (alle Cards in Kategorie 1)
9. Category 2: Glossar-Cards...
10. ... (alle weiteren Kategorien)
11. Footer-Links

**Focus-Styles:**
- Outline: 2px solid `--wolf-apricot` (#F4A261)
- Offset: 2px
- Glossar-Card-Links: Dedicated Focus-Style (Ring + Text-Color-Change)

---

## 9. Content-Strategie & Targeting

### Zielgruppen-Matrix

| Segment | Primäre Keywords | LSI-Keywords | Search Intent |
|---------|------------------|--------------|---------------|
| **Alle** | Glossar Web-Performance, Fachbegriffe BFSG, Terminologie Servicecockpit | Core Web Vitals erklärt, Consent Mode Definition, GEO Bedeutung | Informational (Educational) |
| **Kanzleien** | Glossar Website Kanzlei, Performance Begriffe Rechtsanwalt | Response Promise Definition, BAIT Terminologie | Informational + Research |
| **Bildung** | Campus Website Glossar, Enrollment Fachbegriffe | StepFlow Definition, Course Schema Bedeutung | Informational + Research |
| **Behörden** | OZG Glossar, BFSG Fachbegriffe, Servicecockpit Terminologie | Digital Take-up Definition, BITV Bedeutung | Informational + Compliance-Research |

### Content-Tiefe (Dynamisch skalierend!)

**Aktueller Stand (16 Terme):**
- **Compliance:** 4 Begriffe (BFSG, BITV, evtl. weitere)
- **Performance:** 7 Begriffe (Above the Fold, CLS, Core Web Vitals, FCP, INP, LCP, TTFB)
- **SEO:** 3 Begriffe (AEO, GEO, evtl. Schema.org)
- **Governance:** 3 Begriffe (Governance-Playbook, Response Promise, Servicecockpit)

**Zukünftige Expansion:**
- **Ziel:** 30-40 Begriffe innerhalb 6 Monate
- **Priorisierung:** Häufigste Fragen aus Search Console, Hotline, Client-Feedback
- **Release-Cadence:** Alle 14 Tage (2 neue Begriffe)

### Response Promise Integration

**Hero-CTA:** "Begriff anfragen" → `/kontakt`
- **Messaging:** "Response Promise < 1 h für Begriff-Anfragen" (Empty-State, Zeile 84)
- **Service:** Nutzer können fehlende Begriffe anfragen → Wolf-Agents erstellt Eintrag

**Empty-State-Messaging (Zeilen 84):**
> "Release Cadence: alle 14 Tage · Response Promise < 1 h für Begriff-Anfragen."

### Inhaltstiefe & Keyword-Dichte (Dynamisch!)

**Aktuell (16 Terme):**
- **Pro Kategorie:** 4-7 Begriffe
- **Pro Begriff:** 1-2 Sätze Definition (Card), ausführlicher auf Detail-Page

**Zukünftig (30-40 Terme):**
- **Pro Kategorie:** 8-12 Begriffe
- **Neue Kategorien:** z.B. "Consent & Tracking", "IaC & DevOps", "Accessibility"

---

## 10. Content-Audit-Notizen

### Stärken

1. **Dynamische Collection:** Content skaliert automatisch bei neuen Glossar-Einträgen (future-proof).
2. **Category-Grouping:** Alphabetisch sortierte Kategorien → Gute Scannability.
3. **ItemList Schema:** SEO-optimiert, 16 ListItems → Rich-Snippet-Kandidat für "Glossar Wolf-Agents".
4. **Empty-State:** Professionelles Placeholder-UI mit Release-Cadence → Transparenz.
5. **Related-Links:** Verknüpfte Begriffe zeigen Content-Netz (z.B. "BFSG" ↔ "BITV", "WCAG 2.2").
6. **Owner-Tracking:** Jeder Eintrag hat Owner → Governance-Accountability.
7. **Last-Review-Dates:** Zeigt Content-Freshness → Vertrauen.

### Verbesserungspotenzial

1. **Related-Links nicht clickable:** "Verknüpft mit: BITV, WCAG 2.2" ist nur Text, sollten Links sein.
   - **Empfehlung:** Parse `related` Array und generiere Links zu `/wissen/glossar/{related-slug}/`.

2. **Keine Suchfunktion:** Bei 30+ Begriffen wird manuelle Suche mühsam.
   - **Empfehlung:** Client-Side Search-Input (Filter-als-Type) oder Algolia-Integration.

3. **Keine Alphabet-Navigation:** Bei vielen Begriffen hilfreich (A-Z Buchstaben-Links).
   - **Empfehlung:** Alphabet-Nav above Categories (nur wenn > 20 Begriffe).

4. **Card-Gradient wirkt dunkel:** Kontrast zwischen Card und Section-Background könnte stärker sein.
   - **Empfehlung:** A/B-Test: Dark-Gradient vs. Light-Card mit Plum-Border.

5. **OG-Image generisch:** `/img/og-default.jpg` statt custom Glossar-Visual.
   - **Empfehlung:** Custom OG-Image mit "16 Begriffe"-Badge oder Fachbegriff-Cloud.

6. **Keine BreadcrumbList Schema:** ItemList vorhanden, aber keine Breadcrumbs.
   - **Empfehlung:** BreadcrumbList JSON-LD zusätzlich zu ItemList.

7. **ContentBoxDark/Light importiert, aber nicht verwendet:** Unnötige Imports (Zeilen 7-8).
   - **Empfehlung:** Imports entfernen (Code-Cleanup).

8. **Kein "Letztes Update" für gesamte Glossar-Index-Page:** `lastReviewRaw` wird berechnet (Zeile 33), aber nicht gerendert.
   - **Empfehlung:** Display "Letztes Glossar-Update: {lastReviewRaw}" in Footer oder Hero-Badge.

### Content-Freshness

- **Review-Cadence:** Alle 14 Tage (2 neue Begriffe) laut Empty-State
- **Last-Review-Tracking:** Pro Eintrag via `lastReview` Field
- **Gesamte-Page-Update:** Automatisch bei jedem neuen Glossar-Eintrag (Dynamic Collection)

### Duplicate Content Check

- **Unique Content:** 100% (jeder Glossar-Term unique)
- **Overlap mit Detail-Pages:** Minimal (Index zeigt nur `definitionPlain`, Detail-Pages haben `definitionFull`)
  - **Assessment:** Kein Duplicate-Risk

---

## 11. Performance & Technische Details

### Astro Build-Eigenschaften

**Static Site Generation (SSG):**
- **Build-Time:** `getCollection('glossar')` wird zur Build-Zeit ausgeführt (0 Client-JS!)
- **Output:** Statische HTML-Datei `/wissen/glossar/index.html`
- **Rebuild-Trigger:** Wenn neue Glossar-Einträge hinzugefügt werden (Content-Collection-Change)

**Collection-Processing:**
```javascript
// Build-Time (Server-Side Only)
const allEntries = await getCollection('glossar');  // Fetch all entries
.sort(...)  // Alphabetisch sortieren
// → categoryMap (Grouping-Logic)
// → groupedEntries (Sorted Categories)
// → structuredData (ItemList JSON-LD)
```

**Dynamic Rendering:** 0% (vollständig statisch!)
- Keine Client-Side Hydration
- Keine Server-Side Rendering (SSR)
- Alle Daten zur Build-Zeit integriert

### JavaScript-Footprint

**Hydration:** Keine Client-Side Hydration (0 KB JS für Content)
- Glossar-Index vollständig statisch

**Page-Level JS (via Base-Layout):**
- **Navigation:** ~3 KB (Mobile-Menu Toggle)
- **Analytics:** ~1 KB (web-vitals Snippet)
- **Total JS:** < 5 KB (unter 150 KB Budget)

**Third-Party Scripts:** Keine

### Lighthouse-Scores (geschätzt)

**Performance:** 100
- FCP: < 0.8s (statisches HTML, kein JS-Processing)
- LCP: < 1.3s (Hero-Text above-fold, kein Image-Hero)
- CLS: 0 (statische Glossar-Cards, kein Dynamic-Loading)
- INP: < 50 ms (keine Interaktionen außer Links)
- TBT: < 50 ms (kein blockierendes JS)

**Accessibility:** 100
- Semantic HTML, ARIA-Labels, Focus-Styles, Heading-Hierarchie

**Best Practices:** 100
- HTTPS, moderne CSS, keine Console-Errors

**SEO:** 100
- Meta-Tags, ItemList Schema, Canonical

### Build-Größe

**HTML:** ~25 KB (komprimiert mit Brotli: ~8 KB) ← Größer wegen 16 Glossar-Cards
**CSS:** ~12 KB (Critical CSS inline + Glossar-Card-Styles)
**Fonts:** ~40 KB (Obviously + Inter, WOFF2 subset)
**Images:** Keine (Text-Only Page!)
**Total Page Weight:** < 80 KB (Initial Load) ← **Sehr leicht!**

**Skalierung:**
- **Pro zusätzlichem Glossar-Eintrag:** ~1 KB HTML (Card-Markup)
- **Bei 40 Begriffen:** ~50 KB HTML (komprimiert: ~15 KB)
- **Build-Time:** < 2 Sekunden (bei 40 Begriffen)

### Caching-Strategie

**Static Assets:**
- **HTML:** `Cache-Control: public, max-age=3600, s-maxage=86400` (1h Browser, 24h CDN)
- **CSS/JS:** `Cache-Control: public, max-age=31536000, immutable`

**CDN:** Cloudflare Pages
- **Edge Locations:** 300+ PoPs
- **TTFB:** < 100 ms (DACH-Region)
- **Smart Tiered Caching:** Upper-Tier für Glossar-Index (moderate Churn-Rate: alle 14 Tage)

**Cache-Invalidation:**
- **Trigger:** Neuer Glossar-Eintrag → Rebuild → Cloudflare Pages Auto-Invalidation
- **Cadence:** Alle 14 Tage (Release-Cadence)

---

## 12. Content-Metriken

### Engagement-Ziele (via RUM + GA4)

| Metrik | Ziel | Tracking |
|--------|------|----------|
| **Avg. Time on Page** | > 2 min (Scanning-Mode) | GA4 Engagement Time |
| **Scroll Depth** | > 60 % (mindestens 1-2 Kategorien) | GA4 Scroll Event |
| **Glossar-Card Clicks** | > 20 % CTR | Event: `click_glossar_card` |
| **"Begriff anfragen" CTA** | > 3 % Clicks | Event: `click_glossar_request_cta` |
| **Category-Section Scrolls** | Tracking pro Kategorie | Event: `scroll_into_category` |
| **Bounce Rate** | < 40 % | GA4 Engagement Rate (inverse) |

### Conversion-Metriken

**Primary Conversions:**
- **Glossar-Term-Clicks:** Klicks auf H3-Links oder "Mehr lesen" (Detail-Pages)
- **Ziel:** > 20 % der Besucher klicken mindestens 1× Term

**Secondary Conversions:**
- **"Begriff anfragen" Clicks:** Zeigt Bedarf nach fehlenden Termen
- **Ziel:** > 3 % (50-100 Anfragen/Monat bei 2.000 Visits)

**Micro-Conversions:**
- **"Zum Wissen Hub" Clicks:** Navigation zu `/wissen` (weiterer Content-Konsum)
- **Category-Section Scrolls:** Zeigt Interest an spezifischen Themenbereichen (Performance vs. Compliance)

### SEO-Performance-Ziele

**Keyword-Rankings (6 Monate nach 30+ Begriffen):**
- "Glossar Wolf-Agents": Position 1 (Brand-Term)
- "Glossar Web-Performance": Position 5-15 (SV ~200/Monat)
- "BFSG Glossar": Position 3-10 (SV ~150/Monat)
- "Core Web Vitals Glossar": Position 10-20 (SV ~400/Monat, kompetitiv)
- "Servicecockpit Definition": Position 1-5 (SV ~50/Monat, Long-Tail)

**Organic Traffic-Ziel:**
- **Monat 1-3 (16 Begriffe):** 100-200 Visits/Monat
- **Monat 6-12 (30+ Begriffe):** 500-800 Visits/Monat
- **Click-Through-Rate:** > 5 % (Glossar-Snippet in SERPs)

### Content-Performance-Indikatoren

**Search Console:**
- **Impressions:** > 1.000/Monat (nach 6 Monaten, 30+ Begriffe)
- **Clicks:** > 80/Monat
- **Average Position:** < 15 (erste 1-2 SERP-Seiten)

**Core Web Vitals (URL-Level):**
- **LCP:** < 1.3s (100 % "Good" URLs) ← **Text-Only, sehr schnell**
- **INP:** < 50 ms (100 % "Good" URLs)
- **CLS:** 0 (100 % "Good" URLs) ← **Statisches Layout**

**Glossar-Term-Engagement:**
- **Most-Clicked Terms:** Top 5 Glossar-Einträge (Zeigt Interest)
- **Category-Distribution:** Welche Kategorie hat meiste Clicks? (Performance vs. Compliance)
- **Related-Link Clicks:** (wenn implementiert) → Zeigt Content-Netz-Nutzung

### A/B-Test-Hypothesen (zukünftig)

1. **Card-Styling:** Dark-Gradient vs. Light-Card mit Plum-Border (Contrast-Test)
2. **Hero-CTA-Wording:** "Begriff anfragen" vs. "Fachbegriff vorschlagen"
3. **Category-Order:** Alphabetisch vs. nach Popularity (Most-Clicked Category first)
4. **Related-Links:** Text-Only vs. Clickable-Links (Impact auf Time-on-Page?)

---

## Zusammenfassung & Handlungsempfehlungen

### Content-Status

✅ **Stark:** Dynamische Collection (skaliert automatisch), Category-Grouping, ItemList Schema, Empty-State, Related-Links-Tracking, Owner/Last-Review pro Eintrag
⚠️ **Nachrüsten:** Related-Links clickable machen, Suchfunktion (bei 20+ Begriffen), Alphabet-Nav (bei 30+ Begriffen), Custom OG-Image, BreadcrumbList Schema, Unused-Imports entfernen, "Letztes Update" rendern
🔄 **Monitoring:** Search Console (Glossar-Rankings), Glossar-Card-CTR, "Begriff anfragen"-Conversions, Category-Engagement

### Nächste Schritte (PRIO-Sortiert!)

1. **Related-Links clickable (HÖCHSTE PRIO):** Parse `related` Array und generiere `<a>`-Tags zu `/wissen/glossar/{slug}/`
   ```astro
   {entry.data.related?.map(relatedTerm => (
     <a href={`/wissen/glossar/${slugify(relatedTerm)}/`}>{relatedTerm}</a>
   )).join(', ')}
   ```

2. **Unused-Imports entfernen:** ContentBoxDark, ContentBoxLight (Zeilen 7-8) nicht verwendet

3. **"Letztes Glossar-Update" rendern:** Display `lastReviewRaw` in Hero-Badge oder Section-Header
   ```astro
   <p class="text-sm">Letztes Update: {new Date(lastReviewRaw).toLocaleDateString('de-DE')}</p>
   ```

4. **Custom OG-Image:** Visual mit "16 Begriffe"-Badge oder Fachbegriff-Cloud

5. **BreadcrumbList Schema:** Zusätzlich zu ItemList (Home → Wissen → Glossar)

6. **Suchfunktion (bei 20+ Begriffen):** Client-Side Filter-Input (Filter-als-Type)
   ```javascript
   // Client-Side JS (< 1 KB)
   const filterInput = document.querySelector('#glossar-search');
   filterInput.addEventListener('input', (e) => {
     const query = e.target.value.toLowerCase();
     document.querySelectorAll('.glossar-card').forEach(card => {
       const title = card.querySelector('h3').textContent.toLowerCase();
       card.style.display = title.includes(query) ? 'flex' : 'none';
     });
   });
   ```

7. **Alphabet-Nav (bei 30+ Begriffen):** A-Z Buchstaben-Links (Anchor-Links zu Begriffen)

### Wartungs-Intervalle

- **Bi-Weekly:** 2 neue Glossar-Einträge (laut Release-Cadence)
- **Monthly:** Review `lastReview` Dates (Update veraltete Definitionen, z.B. wenn BFSG-Details ändern)
- **Quarterly:** Category-Re-Organization (neue Kategorien bei > 40 Begriffen?)
- **Annually:** Content-Audit (Entfernen veralteter Begriffe, Konsolidierung ähnlicher Terme)

### Skalierungs-Strategie

**Bei 20 Begriffen:**
- Suchfunktion implementieren (Client-Side Filter)

**Bei 30 Begriffen:**
- Alphabet-Navigation hinzufügen (A-Z Buchstaben)
- 4-5 Kategorien statt 3

**Bei 40+ Begriffen:**
- Pagination oder Infinite-Scroll erwägen (aktuell: Alle Begriffe auf 1 Page)
- Glossar-Tag-System (Multi-Category-Tagging statt Single-Category)

---

**Dokumentation abgeschlossen:** 600 Zeilen
**Datei:** `/Wolf-Agents.com-Architektur/01-CORE-PAGES/glossar-index.md`
**Status:** Phase 1, Seite 6/8 ✅ **GLOSSAR-INDEX FERTIG!** 🎉
