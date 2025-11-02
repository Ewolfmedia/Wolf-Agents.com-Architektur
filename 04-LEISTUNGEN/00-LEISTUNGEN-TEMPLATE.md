# LEISTUNGEN-SEITEN - Master-Referenz & Template

**Dokumentiert am:** 2025-10-30
**Status:** IST-Zustand (Master-Template für alle 11 Leistungen-Seiten)
**Version:** 1.0

---

## 🎯 ZWECK DIESES DOKUMENTS

Dieses Dokument dient als **Master-Referenz** für ALLE Leistungen-Seiten auf Wolf-Agents.com. Es dokumentiert die **gemeinsame Struktur**, Components, Props und Design-Patterns, die auf allen 11 Leistungen-Seiten identisch sind.

**Für Individual-Dokumentationen:**
- Verweise auf dieses Template
- Dokumentiere nur die **Unterschiede** (Badge-Texte, KPIs, Segment-Cases, etc.)
- Nutze **KOMPAKT-STIL** (~800-1.200 Wörter pro Seite)

---

## 📂 ALLE LEISTUNGEN-SEITEN (11 Total)

### Leistungen-Index (Hub-Seite)
- **Datei:** `/src/pages/leistungen/index.astro`
- **URL:** `/leistungen`
- **Funktion:** Übersicht über 4 Betriebsstufen + 6 Fach-Module + 3 Engagement-Modelle

### Betriebsstufen (4 Seiten)
1. **Stufe 0 – Rapid Response** → `/leistungen/stufe-0-ftp-classic`
2. **Stufe A – Astro Hub** → `/leistungen/stufe-a-astro-ftp`
3. **Stufe B – Cloudflare Pages** → `/leistungen/stufe-b-cloudflare-pages`
4. **Stufe C – AWS CloudFront** → `/leistungen/stufe-c-aws-cloudfront`

### Fach-Module (6 Seiten)
1. **Analytics & Consent** → `/leistungen/analytics-consent`
2. **SEO, GEO & Performance** → `/leistungen/seo-tech`
3. **GEO & Location Clusters** → `/leistungen/geo`
4. **Barrierefreiheit & BFSG** → `/leistungen/barrierefreiheit`
5. **Redesign & UX Sprints** → `/leistungen/redesign`
6. **Migration & Redirect Ops** → `/leistungen/migration-redirects`

---

## 🏗️ GEMEINSAME STRUKTUR (Alle Leistungen)

**Layout-Hierarchie (typisch):**

```
Base Layout
│
├── Nav (Sticky Header)
│
├── Hero (Dark Grid Fullscreen)
│   ├── Badge (z.B. "Kick-off in 5 Werktagen", "Cluster-Launch in 3 Sprints")
│   ├── H1 (Title)
│   ├── Paragraph (Subtitle)
│   ├── Primary CTA → /kontakt
│   └── Secondary CTA → /leistungen#module oder /leistungen#stufen
│
├── Section (Light) - TL;DR + Stats
│   ├── Grid: 1.35fr + 0.65fr @ Desktop
│   │   ├── Article (TL;DR Box)
│   │   │   ├── Badge: "TL;DR"
│   │   │   ├── H2
│   │   │   ├── Intro Paragraph
│   │   │   └── UL (3 Checkmark Items)
│   │   │
│   │   └── Stats-Cards Grid (3 Cards)
│   │       ├── Card 1: Dauer/Scope
│   │       ├── Card 2: Tools/Scope
│   │       └── Card 3: Deliverables/KPIs
│   │
│   ├── ContentBoxDark (optional)
│   │   └── Segment-Szenarien Intro
│   │
│   ├── H2: "Segment-Cluster & [Thema] Outcomes"
│   ├── Segment-Cards Grid (3 Cards)
│   │   ├── Card: Kanzleien & Sozietäten
│   │   ├── Card: Schulen & Bildung
│   │   └── Card: Behörden & öffentliche Dienste
│   │
│   ├── H2: "Segment Use Cases"
│   ├── Segment Use Cases Grid (3 Cards) - Wiederholung mit mehr Detail
│   │   ├── Card: Kanzleien (mit KPI-Badge)
│   │   ├── Card: Schulen (mit KPI-Badge)
│   │   └── Card: Behörden (mit KPI-Badge)
│   │
│   ├── Grid: 2-Spalten @ Desktop
│   │   ├── Article: Deliverables & Daten
│   │   │   ├── H2
│   │   │   └── UL (4 Checkmark Items)
│   │   │
│   │   └── Article: Projektablauf
│   │       ├── H2
│   │       └── UL (4 Checkmark Items - Sprints/Phasen)
│   │
│   └── ContentBoxDark (Final CTA)
│       ├── Heading (H2): "[Service] Sprint starten?"
│       ├── Description Paragraph
│       └── Button-Gruppe
│           ├── Primary CTA → /kontakt
│           └── Secondary CTA → /leistungen
│
└── Footer
```

**Sections-Anzahl:** 3-5 (viel weniger als Branchen: 11)

---

## 🧩 KOMPONENTEN-BIBLIOTHEK

**Alle Leistungen-Seiten nutzen diese Components:**

| Komponente | Datei | Verwendung |
|------------|-------|------------|
| `<Base />` | `/src/layouts/Base.astro` | Layout Wrapper (Title, Description, Meta) |
| `<Nav />` | `/src/components/Nav.astro` | Sticky Header Navigation |
| `<Hero />` | `/src/components/Hero.astro` | Fullscreen Dark Grid Hero |
| `<Section />` | `/src/components/Section.astro` | Content Container (tone="light/dark/navy") |
| `<ContentBoxDark />` | `/src/components/ContentBoxDark.astro` | Dark Card für CTAs/Highlights |
| `<ContentBoxLight />` | `/src/components/ContentBoxLight.astro` | Light Card (selten genutzt) |
| `<InfoTooltip />` | `/src/components/InfoTooltip.astro` | Glossar-Tooltip (selten: 0-1 pro Seite) |
| `<Footer />` | `/src/components/Footer.astro` | Footer Component |

**KEINE Leistungen-spezifischen Components!** Alle nutzen die generischen Basis-Components.

---

## 🎨 HERO-COMPONENT (Leistungen-Spezifisch)

**Komponente:** `<Hero variant="dark-grid" minHeightStyle="min-height:100vh;min-height:100dvh;" />`

### Props (Leistungen vs. Branchen)

**Leistungen-Hero Props:**
```astro
<Hero
  title="[Leistungsname]"
  subtitle="[Beschreibung der Leistung, 1-2 Sätze]"
  badge="[Badge-Text, z.B. 'Kick-off in 5 Werktagen']"
  ctaText="[Primary CTA, z.B. 'GEO-Sprint starten']"
  ctaHref="/kontakt"
  secondaryCtaText="[Secondary CTA, z.B. 'Stufen vergleichen']"  ← NEU!
  secondaryCtaHref="/leistungen#module"  ← NEU!
  variant="dark-grid"
  minHeightStyle="min-height:100vh;min-height:100dvh;"
/>
```

**UNTERSCHIED ZU BRANCHEN:**
- **Leistungen:** `secondaryCtaText` + `secondaryCtaHref` (2 CTAs)
- **Branchen:** `tertiaryCtaText` + `tertiaryCtaHref` (3 CTAs möglich)
- **Leistungen:** Zentriertes Alignment (kein `align="left"`)
- **Branchen:** `align="left"` (linksbündiges Hero)

### Hero-Hintergrund

**Hintergrund:** `var(--brand-primary-900)` (#04060D)
**Gitter-Pattern:** Ja, subtiles Gitter mit `rgba(255,255,255,0.02)`
**Min-Height:** 100vh / 100dvh (Fullscreen)

### Hero-Badge

**Styling:**
- Farbe: rgba(249,250,251,0.72)
- Background: rgba(255,255,255,0.08)
- Font: Inter SemiBold, 11px, uppercase, tracking: 0.26em
- Padding: px-4 py-1.5, rounded-full
- Border: 1px solid rgba(148,163,184,0.18)

### Hero-Headlines

**H1 (Title):**
- Font: Inter ExtraBold, 4.5rem (72px) @ Desktop, 3rem (48px) @ Tablet, 2.25rem (36px) @ Mobile
- Farbe: #F9FAFB (fast weiß)
- Line-height: 1.15 (tight)
- Letter-spacing: -0.02em
- Max-width: 1000px (zentriert, da kein align="left")

**Paragraph (Subtitle):**
- Font: Inter Regular, 1.25rem (20px) @ Desktop, 1.125rem (18px) @ Mobile
- Farbe: rgba(249,250,251,0.72)
- Line-height: 1.75 (loose)
- Max-width: 720px

---

## 📊 TL;DR + STATS SECTION

**Layout:** Grid mit 1.35fr + 0.65fr @ Desktop (Links: TL;DR-Box, Rechts: 3 Stats-Cards)

### TL;DR-Box (Article)

**Styling:**
- Background: `surface-light` (var(--surface-light))
- Border: 1px solid var(--border-on-light-subtle)
- Border-radius: 24px (rounded-3xl)
- Padding: p-8 md:p-10
- Shadow: `box-shadow: var(--shadow-premium)` oder `0_30px_80px_-60px_rgba(15,23,42,0.45)`

**Content:**
```
Badge: "TL;DR"
  Chip-Style: chip-light caps-label-wide
  Font: Inter SemiBold, 12px, uppercase, tracking: 0.24em
  Farbe: text-on-light-primary

H2: "[Service] Mastery" oder "[Thema] in 3 Sprints"
  Font: Inter Bold, 2xl md:3xl (24-30px → 36px)
  Farbe: text-on-light-primary

Paragraph (Intro):
  Font: Inter Regular, base md:lg (16px → 18px)
  Farbe: text-on-light-secondary
  Line-height: leading-relaxed (1.75)

UL (3 Checkmark Items):
  Checkmark Icon: SVG, w-5 h-5, text-on-light-primary
  Font: text-sm md:text-base
  Farbe: text-on-light-primary
  Spacing: space-y-3
  Gap: gap-3 (zwischen Icon und Text)
```

### Stats-Cards (3 Cards)

**Grid:** grid gap-4 (3 Rows @ Mobile, 3 Cols @ Desktop)

**Card-Styling:**
- Background: `surface-light-muted` (var(--surface-light-muted))
- Border: 1px solid var(--border-on-light-subtle)
- Border-radius: 16px (rounded-2xl)
- Padding: p-6

**Card-Content:**
```
Label (Uppercase):
  Font: Inter SemiBold, xs (11-12px), uppercase, tracking: 0.24em
  Farbe: text-on-light-muted

Value (Big Number):
  Font: Inter Bold, 3xl (30px)
  Farbe: text-on-light-primary
  Beispiele: "3 Sprints", "50+ Städte", "+35 %", "10-15 Tage"

Context (Description):
  Font: Inter Regular, sm (14px)
  Farbe: text-on-light-secondary
  Line-height: leading-relaxed
```

**Variations:**
- **Card 1:** Rollout Sprints / Dauer / Setup-Zeit
- **Card 2:** Location Kits / Tools / Scope
- **Card 3:** KPI Ziele / Deliverables / Ergebnisse

---

## 👥 SEGMENT USE CASES (3 Branchen-Cards)

**WICHTIG:** Jede Leistung hat 3 Segment-Cards, die auf die 3 Haupt-Branchen verlinken:
1. **Kanzleien & Sozietäten** → `/branchen/kanzleien`
2. **Schulen & Bildung** → `/branchen/schulen-bildung`
3. **Behörden & öffentliche Dienste** → `/branchen/oeffentliche-einrichtungen`

### Content-Struktur (Hardcoded Array)

**TypeScript-Interface:**
```typescript
interface SegmentCase {
  title: string;           // "Kanzleien & Sozietäten"
  kpi: string;             // "Local Pack Visibility +40 %"
  description: string;     // Segment-spezifische Beschreibung
  link: string;            // "/branchen/kanzleien"
  linkLabel: string;       // "Kanzlei-Local SEO ansehen"
  badge?: string;          // "CMS → Astro Migration" (optional)
}
```

**Beispiel-Array (geo.astro):**
```javascript
const segmentCases = [
  {
    title: 'Kanzleien & Sozietäten',
    kpi: 'Local Pack Visibility +40 %',
    description: 'Entity-Maps für Fachbereiche, Standort-Cluster, Review-Playbooks...',
    link: '/branchen/kanzleien',
    linkLabel: 'Kanzlei-Local SEO ansehen'
  },
  {
    title: 'Schulen & Bildung',
    kpi: 'Anfragen +30 % · Mobile RUM > 70 %',
    description: 'Campus-/Standortseiten mit Step-by-Step Informationen...',
    link: '/branchen/schulen-bildung',
    linkLabel: 'Enrollment-Guides öffnen'
  },
  {
    title: 'Behörden & öffentliche Dienste',
    kpi: 'Completion Rate ≥ 70 % · Review Score ≥ 4,5',
    description: 'GovernmentService Schema, Top-Task Navigation...',
    link: '/branchen/oeffentliche-einrichtungen',
    linkLabel: 'Behörden-Top Tasks prüfen'
  }
];
```

### Segment-Cards Layout

**Grid:** grid grid-cols-1 md:grid-cols-3 gap-6

**Card-Styling:**
- Background: `surface-light-muted` (var(--surface-light-muted))
- Border: 1px solid var(--border-on-light-subtle)
- Border-radius: 16px (rounded-2xl)
- Padding: p-6
- Shadow: shadow-sm (leicht)
- Hover: hover:-translate-y-1 hover:shadow-md transition

**Card-Content:**
```
Badge (KPI):
  Text: [segment.kpi]
  Styling: inline-flex items-center px-3 py-1 rounded-full
  Background: surface-light-alpha-08
  Farbe: text-on-dark-secondary
  Border: 1px solid var(--border-on-dark-subtle)
  Font: Inter SemiBold, xs (11-12px), uppercase, tracking: 0.18em

H3 (Title):
  Text: [segment.title]
  Font: Inter SemiBold, lg (18px)
  Farbe: text-on-light-primary

Description:
  Text: [segment.description]
  Font: Inter Regular, sm (14px)
  Farbe: text-on-light-secondary
  Line-height: leading-relaxed

CTA-Link:
  Text: [segment.linkLabel]
  Href: [segment.link]
  Icon: Arrow Right (SVG, w-4 h-4)
  Font: Inter SemiBold, sm (14px)
  Farbe: text-on-light-primary
  Hover: hover:text-on-light-primary
```

**VARIATIONS:**
- KPI-Texte variieren je Leistung (z.B. "Lead-to-Call Rate +35 %" vs. "Completion Rate ≥ 70 %")
- Descriptions sind leistungsspezifisch
- Link-Labels variieren leicht

---

## 📋 DELIVERABLES + PROJEKTABLAUF (2-Spalten-Grid)

**Layout:** grid gap-8 lg:grid-cols-2 (2 Articles nebeneinander @ Desktop)

### Deliverables-Article (Links)

**Styling:**
- Background: `surface-light` (var(--surface-light))
- Border: 1px solid var(--border-on-light-subtle)
- Border-radius: 24px (rounded-3xl)
- Padding: p-8
- Shadow: `0_25px_70px_-55px_rgba(15,23,42,0.35)`

**Content:**
```
H2: "Deliverables & Daten"
  Font: Inter SemiBold, xl (20px)
  Farbe: text-on-light-primary

UL (4 Checkmark Items):
  Checkmark Icon: SVG, w-5 h-5, text-on-light-primary
  Font: Inter Regular, sm (14px)
  Farbe: text-on-light-secondary
  Spacing: space-y-3
  Gap: gap-3
  Line-height: leading-relaxed
```

**Variations:**
- 4 Deliverable-Items pro Leistung (leistungsspezifisch)
- Beispiele: "Keyword & Entity Maps", "Templates für Location Pages", "Citation & Review Playbooks", "KPI-Dashboard"

### Projektablauf-Article (Rechts)

**Styling:** Identisch zu Deliverables-Article

**Content:**
```
H2: "Projektablauf"
  Font: Inter SemiBold, xl (20px)
  Farbe: text-on-light-primary

UL (4 Checkmark Items):
  [Gleiche Struktur wie Deliverables]
```

**Variations:**
- 4 Projekt-Phasen/Sprints (leistungsspezifisch)
- Beispiele: "Sprint 0: Audit, KPI Alignment...", "Sprint 1: Keyword/Entity Research...", "Sprint 2: Umsetzung...", "Sprint 3 (optional): Monitoring..."

---

## 🎯 FINAL CTA (ContentBoxDark)

**Komponente:** `<ContentBoxDark heading="[Service] Sprint starten?" headingLevel="h2" class="text-center" />`

**Styling:**
- Background: `var(--surface-dark)` (#04060D) oder `var(--brand-primary-900)`
- Border: 1px solid var(--border-on-dark-subtle)
- Border-radius: 24px (rounded-3xl)
- Padding: p-8 md:p-10
- Shadow: premium-shadow
- Text-Align: center

**Content:**
```
Heading (H2):
  Text: "[Service] Sprint starten?" oder "Projekt einordnen lassen?"
  Font: Inter Bold, 2xl md:3xl
  Farbe: text-white oder text-on-dark-primary
  Margin-bottom: mb-6

Description Paragraph:
  Font: Inter Regular, sm md:base (14px → 16px)
  Farbe: text-slate-200/85 oder rgba(249,250,251,0.85)
  Max-width: max-w-2xl mx-auto
  Margin-bottom: mb-8
  Line-height: leading-relaxed

Button-Gruppe (Flex):
  Display: flex flex-col sm:flex-row gap-4 justify-center

  Primary CTA:
    Text: "Kick-off anfragen" oder "Erstgespräch sichern"
    Href: /kontakt
    Styling: inline-flex items-center justify-center px-6 py-3 rounded-xl
    Background: surface-light (white)
    Farbe: text-on-light-primary (dunkel/schwarz)
    Font: Inter SemiBold
    Shadow: shadow-lg hover:shadow-xl
    Transition: transition-all duration-200

  Secondary CTA:
    Text: "Weitere Pakete ansehen" oder "Wissen & Playbooks ansehen"
    Href: /leistungen oder /wissen
    Styling: [Gleich wie Primary]
    Background: transparent
    Border: 1px solid var(--border-on-dark-strong)
    Farbe: text-white
    Hover: hover:surface-light-alpha-12 (leichter Hintergrund)
```

**VARIATIONS:**
- Heading-Texte variieren (z.B. "GEO/AEO Sprint starten?" vs. "Projekt einordnen lassen?")
- Description variiert je Leistung
- CTA-Labels variieren leicht ("Kick-off anfragen" vs. "Erstgespräch sichern")

---

## 🎨 DESIGN-SYSTEM (Farben & Typografie)

### Farb-Palette (Leistungen-Seiten)

**Hauptfarben:**

| Element | CSS-Variable | Hex/rgba-Wert | Verwendung |
|---------|--------------|---------------|------------|
| Hero Background | `--brand-primary-900` | #04060D | Hero Dark Grid |
| Section Light BG | `--surface-light` | #FFFFFF | TL;DR-Box, Stats-Cards, Deliverables |
| Section Light Muted | `--surface-light-muted` | #F9FAFB | Stats-Cards, Segment-Cards |
| Section Dark BG | `--surface-dark` | #04060D | ContentBoxDark, Final CTA |
| Section Navy BG | `--brand-primary-900` | #04060D | Engagement-Modelle (nur Index) |
| Text on Light Primary | `--text-primary-on-light` | #0F172A | Headlines auf Light |
| Text on Light Secondary | `--text-secondary-on-light` | rgba(15,23,42,0.72) | Body-Text auf Light |
| Text on Dark Primary | `--text-primary-on-dark` | #F9FAFB | Headlines auf Dark |
| Text on Dark Secondary | `--text-secondary-on-dark` | rgba(249,250,251,0.72) | Body-Text auf Dark |
| Border on Light Subtle | `--border-on-light-subtle` | rgba(15,23,42,0.12) | Card-Borders auf Light |
| Border on Dark Subtle | `--border-on-dark-subtle` | rgba(255,255,255,0.18) | Card-Borders auf Dark |

### Typografie

**Font-Family:** Inter (Weights: Regular, Medium, SemiBold, Bold, ExtraBold)

**Font-Sizes (Responsive):**

| Element | Mobile | Tablet | Desktop |
|---------|--------|--------|---------|
| Hero H1 | 2.25rem (36px) | 3rem (48px) | 4.5rem (72px) |
| Hero Subtitle | 1.125rem (18px) | 1.25rem (20px) | 1.25rem (20px) |
| Section H2 | 1.5rem (24px) | 1.875rem (30px) | 2.25rem (36px) |
| Card H3 | 1.125rem (18px) | 1.125rem (18px) | 1.125rem (18px) |
| Body Text | 1rem (16px) | 1rem (16px) | 1.125rem (18px) |
| Small Text | 0.875rem (14px) | 0.875rem (14px) | 0.875rem (14px) |
| Stats Value | 1.875rem (30px) | 1.875rem (30px) | 1.875rem (30px) |
| Badge/Label | 0.75rem (12px) | 0.75rem (12px) | 0.75rem (12px) |

**Line-Heights:**
- tight: 1.15 (Hero H1)
- snug: 1.25 (Section H2)
- normal: 1.5 (Body)
- relaxed: 1.75 (Descriptions)

**Letter-Spacing:**
- Headlines: -0.02em (Hero H1, Section H2)
- Body: 0 (normal)
- Uppercase Labels: 0.18em - 0.3em (Badges, Stats-Labels)

### Spacing-System

**Section-Padding:**
- py-20 @ Mobile (80px)
- py-28 @ Tablet (112px)
- py-32 @ Desktop (128px)

**Container-Padding:**
- px-6 @ Mobile (24px)
- px-8 @ Tablet (32px)
- px-12 @ Desktop (48px)

**Gaps (Grid/Flex):**
- gap-4: 16px (Stats-Cards)
- gap-6: 24px (Segment-Cards, Deliverables-Grid)
- gap-8: 32px (Deliverables-Grid lg)

### Border-Radius

- Small: 8px (rounded-lg)
- Medium: 12px (rounded-xl)
- Large: 16px (rounded-2xl) - Stats-Cards, Segment-Cards
- XL: 24px (rounded-3xl) - TL;DR-Box, Deliverables, Final CTA
- Full: 9999px (rounded-full) - Badges

### Shadows

**Shadows (Light Sections):**
- Card-Shadow: `shadow-sm` (leicht)
- Premium-Shadow: `0_30px_80px_-60px_rgba(15,23,42,0.45)` (TL;DR-Box)
- Deliverables-Shadow: `0_25px_70px_-55px_rgba(15,23,42,0.35)`
- Hover-Shadow: `shadow-md` → `shadow-lg` (Segment-Cards)

**Shadows (Dark Sections):**
- ContentBox-Shadow: `0_30px_80px_-60px_rgba(15,23,42,0.55)`

---

## 📐 RESPONSIVE BREAKPOINTS

**Tailwind Breakpoints:**

| Breakpoint | Screen-Width | Grid-Cols (Segment) | Grid-Cols (TL;DR+Stats) | Padding |
|------------|--------------|---------------------|-------------------------|---------|
| Mobile | <640px | 1 | 1 (Stack) | px-6 py-20 |
| Tablet (sm) | 640-1023px | 2 | 1 (Stack) | px-8 py-28 |
| Desktop (lg) | ≥1024px | 3 | 1.35fr + 0.65fr (Side-by-Side) | px-12 py-32 |

**Hauptänderungen:**
- **TL;DR + Stats:** Stack @ Mobile/Tablet → Side-by-Side @ Desktop (lg:grid-cols-[1.35fr,0.65fr])
- **Segment-Cards:** 1-col → 2-col @ Tablet (md) → 3-col @ Desktop (md)
- **Deliverables-Grid:** Stack @ Mobile → 2-col @ Desktop (lg:grid-cols-2)
- **Font-Sizes:** Hero H1 skaliert stark (36px → 72px), andere Elemente moderat

---

## ⚙️ SEO & METADATA (Leistungen)

### Title-Tag-Pattern

**Format:** `"[Thema] & [Keywords] | Wolf-Agents"`

**Beispiele:**
- "GEO, AEO & Local Search Architecture | Wolf-Agents"
- "BFSG, BITV & Accessibility Sprints | Wolf-Agents"
- "Analytics, Consent & Servicecockpit KPIs | Wolf-Agents"

**Länge:** ~50-60 Zeichen

### Meta-Description-Pattern

**Format:** `"[Service-Details] – zugeschnitten auf Kanzleien, Bildung und öffentliche Dienste mit [KPIs/Deliverables]."`

**Beispiel:**
```
"Entity-Mapping, Local Packs, AEO-Snippets und Location-Cluster für Kanzleien, Bildung und Behörden – inklusive Content-Kits, Review-Playbooks und KPI-Dashboards."
```

**Länge:** ~140-160 Zeichen

### Canonical URL

**Pattern:** `https://www.wolf-agents.com/leistungen/[slug]`

**Beispiele:**
- `https://www.wolf-agents.com/leistungen/geo`
- `https://www.wolf-agents.com/leistungen/barrierefreiheit`

### Schema.org Markup

**STATUS:** ⚠️ **NICHT VORHANDEN** auf allen gelesenen Leistungen-Seiten!

**Empfohlene Schema-Typen (nicht implementiert):**
- `Service` oder `ProfessionalService`
- `Offer` (für Engagement-Modelle)
- `FAQPage` (falls FAQ-Section hinzugefügt wird)

**Unterschied zu Branchen:**
- **Branchen:** Haben Schema.org-Markup (LegalService, InsuranceAgency, etc.)
- **Leistungen:** ⚠️ Kein Schema.org-Markup gefunden

### Hreflang/Multilingual

**STATUS:** ⚠️ **NICHT VORHANDEN**

Alle Leistungen-Seiten sind **nur auf Deutsch** (DACH-Markt).

---

## ♿ BARRIEREFREIHEIT

### Semantische Struktur

**HTML-Tags:**
- `<nav>` - Navigation
- `<main>` - Main Content
- `<section>` - Sections (Hero, TL;DR, Segment-Cases, Deliverables, Final CTA)
- `<article>` - TL;DR-Box, Stats-Cards, Segment-Cards, Deliverables-Articles
- `<footer>` - Footer

**H1-H3-Hierarchie:**
- ✅ H1: Hero-Headline (1× pro Seite)
- ✅ H2: Section-Headlines (TL;DR, Segment-Cluster, Deliverables, Projektablauf, Final CTA)
- ✅ H3: Card-Titles (Segment-Cards, Stats-Cards optional)

### Kontrast-Ratios

**Text-on-Light:**
- Primary (#0F172A) auf Light (#FFFFFF) = **~19:1 (AAA)**
- Secondary (rgba(15,23,42,0.72)) auf Light (#FFFFFF) = **~12:1 (AAA)**

**Text-on-Dark:**
- Primary (#F9FAFB) auf Dark (#04060D) = **~19:1 (AAA)**
- Secondary (rgba(249,250,251,0.72)) auf Dark (#04060D) = **~14:1 (AAA)**

**Alle Kontraste erfüllen WCAG 2.2 AAA!**

### Interaktive Elemente

**Focus-Rings:**
- ✅ Vorhanden (Browser-Default oder Custom via Tailwind `focus:ring-2`)

**Button vs. Link:**
- ✅ `<a href="/kontakt">` für Navigation (korrekt)
- ✅ `<button>` für Interaktionen (falls vorhanden)

**ARIA-Attribute:**
- Minimal (nur wo semantisches HTML nicht ausreicht)
- `aria-label` für Icon-Only-Buttons (z.B. Arrow-Icons)

### Reduced Motion

**STATUS:** ✅ **VORHANDEN**

- `@media (prefers-reduced-motion: reduce)` unterstützt
- Animationen (Hover-Transitions, -translate-y) werden bei reduced-motion deaktiviert

---

## 🔄 UNTERSCHIEDE ZU BRANCHEN-SEITEN

**Wichtige Unterschiede (Leistungen vs. Branchen):**

| Feature | Branchen | Leistungen |
|---------|----------|------------|
| **Content-Quelle** | JSON-Files (`/src/content/branchen/*.json`) | Hardcoded in .astro-Dateien |
| **Dynamic Routes** | Ja (`/src/pages/branchen/[slug].astro`) | Nein (statische Seiten) |
| **Hero-Alignment** | Left (`align="left"`) | Center (kein align-Prop) |
| **Hero-CTAs** | 3 CTAs (Primary, Secondary, Tertiary) | 2 CTAs (Primary, Secondary) |
| **StepFlow** | Ja (4-Schritt-Journey bei Index 0) | ❌ Nein |
| **Segment-Cards** | ❌ Nein | ✅ Ja (3 Branchen-Cards pro Leistung) |
| **FAQ-Section** | Ja (Accordion mit Details/Summary) | ❌ Nein |
| **Glossary-Links Section** | Ja (Badge-Links zu Glossar) | ❌ Nein |
| **InfoTooltips** | Häufig (2-3 pro Seite) | Selten (0-1 pro Seite) |
| **More-Siblings Section** | Ja (3 Sibling-Branch-Cards) | ❌ Nein |
| **Schema.org Markup** | Ja (LegalService, InsuranceAgency, etc.) | ⚠️ Nein (nicht gefunden) |
| **Sections-Anzahl** | 11 Sections | 3-5 Sections |
| **Geschätzte Wortanzahl** | ~1.650 Wörter (Kanzleien) | ~900-1.500 Wörter |

**Fazit:** Leistungen-Seiten sind **strukturell einfacher** und **kompakter** als Branchen-Seiten!

---

## 🔧 VARIATIONS-PUNKTE (Was variiert zwischen Leistungen?)

**Für jede Individual-Doku dokumentieren:**

### 1. Meta-Informationen
- **URL:** `/leistungen/[slug]`
- **Datei:** `/src/pages/leistungen/[slug].astro`
- **Title Tag:** [Variiert]
- **Meta Description:** [Variiert]
- **Geschätzte Wortanzahl:** [Variiert: ~900-1.500]

### 2. Hero-Texte
- **Badge:** [Variiert, z.B. "Kick-off in 5 Werktagen", "Cluster-Launch in 3 Sprints"]
- **H1 (Title):** [Variiert pro Leistung]
- **Subtitle:** [Variiert pro Leistung]
- **Primary CTA Text:** [Variiert, meist "Kick-off anfragen" oder "[Service]-Sprint starten"]
- **Secondary CTA Text:** [Variiert, meist "Stufen vergleichen" oder "Weitere Pakete ansehen"]
- **Secondary CTA Href:** [Variiert: /leistungen#module oder /leistungen#stufen]

### 3. TL;DR-Box
- **H2:** [Variiert, z.B. "Location & Entity Mastery", "Consent & KPI Tracking"]
- **Intro Paragraph:** [Variiert pro Leistung]
- **3 Checkmark Items:** [Variiert pro Leistung]

### 4. Stats-Cards (3)
- **Card 1 (Dauer/Scope):**
  - Label: [Variiert, z.B. "Rollout Sprints", "Setup"]
  - Value: [Variiert, z.B. "3 Sprints", "10-15 Tage"]
  - Context: [Variiert]
- **Card 2 (Tools/Scope):**
  - Label: [Variiert, z.B. "Location Kits", "Tools"]
  - Value: [Variiert, z.B. "50+ Städte", "GA4 + BigQuery"]
  - Context: [Variiert]
- **Card 3 (KPIs/Deliverables):**
  - Label: [Variiert, z.B. "KPI Ziele", "Deliverables"]
  - Value: [Variiert, z.B. "+35 %", "4 Kits"]
  - Context: [Variiert]

### 5. Segment Use Cases (segmentCases-Array)
- **3 Segment-Cards:** Struktur identisch, aber:
  - **KPI-Badges:** [Variieren pro Leistung und Segment]
  - **Descriptions:** [Variieren pro Leistung und Segment]
  - **Link-Labels:** [Variieren leicht]

### 6. Deliverables & Projektablauf
- **Deliverables (4 Items):** [Komplett unterschiedlich pro Leistung]
- **Projektablauf (4 Phasen/Sprints):** [Komplett unterschiedlich pro Leistung]

### 7. Final CTA
- **Heading:** [Variiert, z.B. "GEO/AEO Sprint starten?", "Projekt einordnen lassen?"]
- **Description:** [Variiert pro Leistung]
- **Primary CTA Text:** [Variiert, meist "Kick-off anfragen" oder "Erstgespräch sichern"]
- **Secondary CTA Text:** [Variiert, meist "Weitere Pakete ansehen" oder "Wissen ansehen"]
- **Secondary CTA Href:** [Variiert: /leistungen oder /wissen]

### 8. Besonderheiten
- **InfoTooltip-Usage:** [Dokumentiere falls vorhanden, meist 0-1 pro Seite]
- **ContentBoxDark-Platzierung:** [Optional: nach TL;DR-Box oder nur als Final CTA]
- **Zusätzliche Sections:** [Falls eine Leistung Abweichungen hat]

---

## 📝 KOMPAKT-DOKU-FORMAT (Individual-Seiten)

**Verwende dieses Format für jede Leistungen-Seite:**

```markdown
# [LEISTUNGSNAME]

**Verweis:** Siehe `/04-LEISTUNGEN/00-LEISTUNGEN-TEMPLATE.md` für gemeinsame Struktur

## 📊 META-INFORMATIONEN

| Attribut | Wert |
|----------|------|
| **URL** | https://www.wolf-agents.com/leistungen/[slug] |
| **Datei** | `/src/pages/leistungen/[slug].astro` |
| **Title Tag** | "[Title]" |
| **Meta Description** | "[Description]" |
| **Geschätzte Wortanzahl** | ~[X] Wörter |
| **Geschätzte Lesedauer** | [X-Y] Minuten |

---

## 🏗️ HERO-BEREICH

**Badge:** "[Badge-Text]"
**H1 (Title):** "[Headline]"
**Subtitle:** "[Subtitle-Text]"
**Primary CTA:** "[CTA-Text]" → `/kontakt`
**Secondary CTA:** "[Secondary-CTA-Text]" → `[Href]`

---

## 📊 TL;DR + STATS

### TL;DR-Box

**H2:** "[Headline]"
**Intro:** "[Intro-Text]"

**3 Checkmark Items:**
1. [Item 1]
2. [Item 2]
3. [Item 3]

### Stats-Cards (3)

**Card 1: [Label]**
- Value: [Value]
- Context: [Context]

**Card 2: [Label]**
- Value: [Value]
- Context: [Context]

**Card 3: [Label]**
- Value: [Value]
- Context: [Context]

---

## 👥 SEGMENT USE CASES

**H2:** "Segment-Cluster & [Thema] Outcomes" oder "Segment Use Cases"

### Segment-Cards (3)

**1. Kanzleien & Sozietäten**
- **KPI:** [KPI-Badge-Text]
- **Description:** [Description]
- **Link-Label:** [Label]

**2. Schulen & Bildung**
- **KPI:** [KPI-Badge-Text]
- **Description:** [Description]
- **Link-Label:** [Label]

**3. Behörden & öffentliche Dienste**
- **KPI:** [KPI-Badge-Text]
- **Description:** [Description]
- **Link-Label:** [Label]

---

## 📋 DELIVERABLES & PROJEKTABLAUF

### Deliverables (4)

1. [Deliverable 1]
2. [Deliverable 2]
3. [Deliverable 3]
4. [Deliverable 4]

### Projektablauf (4)

1. [Phase 1]
2. [Phase 2]
3. [Phase 3]
4. [Phase 4]

---

## 🎯 FINAL CTA

**Heading (H2):** "[Heading-Text]"
**Description:** "[Description-Text]"

**CTAs:**
- Primary: "[CTA-Text]" → `/kontakt`
- Secondary: "[CTA-Text]" → `[Href]`

---

## 🔍 BESONDERHEITEN

- **InfoTooltip-Usage:** [Falls vorhanden: termId + Position dokumentieren, z.B. "1× `<InfoTooltip termId="bfsg-2025" />` in TL;DR-Paragraph"]
- **ContentBoxDark-Platzierung:** [Falls zusätzlich zu Final CTA: Position + Content]
- **Abweichungen von Template:** [Falls vorhanden: Unique Sections, Components, etc.]

---

## 📊 CONTENT-AUDIT

### ✅ Stärken
- [Stärke 1]
- [Stärke 2]
- [Stärke 3]

### ⚠️ Schwächen
- [Schwäche 1]
- [Schwäche 2]

### ❌ Fehlende Elemente
- ❌ **Schema.org-Markup:** Kein Service/Offer-Schema (wie alle Leistungen-Seiten)
- ❌ **FAQ-Section:** Keine FAQs (wie alle Leistungen-Seiten)
- ❌ **Glossary-Links Section:** Keine Querverweise zu Glossar (wie alle Leistungen-Seiten)
- [Weitere fehlende Elemente...]

### 🔴 PRIORITÄT

**Content-Refresh-Priorität:** [Hoch / Mittel / Niedrig]

**Begründung:** [Warum ist diese Seite wichtig/unwichtig?]

**Empfohlene Maßnahmen:**
1. [Maßnahme 1] - Timeline: [X Wochen]
2. [Maßnahme 2] - Timeline: [X Wochen]
3. [Maßnahme 3] - Timeline: [X Wochen]

---

## 🎯 CONTENT-STRATEGIE

**Primäre Keywords:**
- [Keyword 1]
- [Keyword 2]
- [Keyword 3]

**Sekundäre Keywords (LSI):**
- [LSI-Keyword 1]
- [LSI-Keyword 2]

**Zielgruppe:** [Beschreibung]

**User Intent:** [Informational / Transactional / Commercial Investigation]

**AIO/GEO/AEO-Status:**
- **AIO:** [Welche Frage beantwortet diese Seite?]
- **GEO:** ⚠️ Kein Schema.org-Markup (alle Leistungen)
- **AEO:** [Featured-Snippet-Potenzial?]
```

**Umfang pro Doku:** ~800-1.200 Wörter

---

## 📚 REFERENZ-DATEIEN

**Für Individual-Dokumentationen lesen:**
1. **Dieses Template:** `/04-LEISTUNGEN/00-LEISTUNGEN-TEMPLATE.md` (Master-Referenz)
2. **Astro-Datei:** `/src/pages/leistungen/[slug].astro` (spezifische Seite)
3. **Protokoll:** `/00-DOKUMENTATIONS-PROTOKOLL.md` (Standards)
4. **Kanzleien:** `/02-BRANCHEN/kanzleien.md` (Vergleichs-Referenz)

---

## ✅ QUALITÄTS-CHECKLISTE (Individual-Dokus)

Vor Abschluss jeder Leistungen-Doku prüfen:

- [ ] Verweis auf Template-Datei vorhanden
- [ ] Alle Variations-Punkte dokumentiert (Hero, TL;DR, Stats, Segment-Cases, Deliverables, Ablauf, Final CTA)
- [ ] segmentCases-Array vollständig (3 Segments mit KPIs, Descriptions, Links)
- [ ] Content-Audit mit ✅ Stärken, ⚠️ Schwächen, ❌ Fehlendem, 🔴 Priorität
- [ ] InfoTooltip-Usage dokumentiert (falls vorhanden)
- [ ] Besonderheiten/Abweichungen vom Template dokumentiert
- [ ] Content-Strategie (Keywords, User Intent, AIO/GEO) dokumentiert
- [ ] Kompakt-Format eingehalten (~800-1.200 Wörter)

---

**ENDE DES MASTER-TEMPLATES**

**Version:** 1.0
**Erstellt am:** 2025-10-30
**Gilt für:** Alle 11 Leistungen-Seiten (4 Betriebsstufen + 6 Fach-Module + 1 Index)

Dieses Template dient als **Master-Referenz** für alle Individual-Dokumentationen. Nutze den **KOMPAKT-STIL** und verweise auf dieses Template, statt alles zu wiederholen!
