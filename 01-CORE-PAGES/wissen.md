# WISSEN HUB - Content & Struktur-Architektur

**Dokumentiert am:** 2025-11-01
**Status:** IST-Zustand (keine Optimierungsvorschläge)

---

## 📊 1. HEADER & META-INFORMATIONEN

| Attribut | Wert |
|----------|------|
| **URL** | https://www.wolf-agents.com/wissen |
| **Datei** | `/src/pages/wissen.astro` |
| **Title Tag** | "Wissen Hub für Kanzleien, Bildung & Behörden \| Wolf-Agents" |
| **Meta Description** | "Guides, KPI-Playbooks, Glossar und Downloads für Kanzleien, Bildungseinrichtungen und Behörden – inklusive Response Promise, BFSG 2025 und Core Web Vitals." |
| **Canonical URL** | https://www.wolf-agents.com/wissen |
| **Noindex** | Nein |
| **Geschätzte Zeichenanzahl** | ~9.800 Zeichen (ohne Code/HTML) |
| **Geschätzte Wortanzahl** | ~1.380 Wörter |
| **Geschätzte Lesedauer** | 6-7 Minuten |
| **Anzahl Sections** | 6 Hauptbereiche (Hero, Overview, Segments, Guides, Glossar, Downloads) |
| **Anzahl H1** | 1 (im Hero: "Wissen Hub für Kanzleien, Campus & Behörden") |
| **Anzahl H2** | 5 (Overview-Text, Segments, Guides, Glossar, Downloads) |
| **Anzahl H3** | 15+ (Knowledge-Stats, Segment-Cards, Blog-Posts, Glossar-Kategorien, Download-Assets) |

---

## 🔗 2. VERLINKUNGSSTRUKTUR

### Interne Links (ausgehend)

**Navigation:**
- Logo-Link: `/`
- Branchen-Dropdown: `/branchen/kanzleien`, etc.
- Leistungen-Dropdown: `/leistungen` + Unterseiten
- Wissen-Dropdown: `/wissen`, `/wissen/glossar`, `/code-statt-cms`
- CTA-Button: `/kontakt`

**Hero (Section 1):**
- CTA Primary: `/kontakt` → "Kontakt aufnehmen"
- CTA Tertiary: `#downloads` → "Top-Task Downloads" (Anchor-Link)

**Segments (Section 3):**
- Card 1: `/branchen/kanzleien` → "Kanzleien & Sozietäten"
- Card 2: `/branchen/schulen-bildung` → "Schulen & Campus"
- Card 3: `/branchen/oeffentliche-einrichtungen` → "Behörden & öffentliche Dienste"

**Guides (Section 4):**
- CTA-Button: `/kontakt` → "Individuelles KPI-Briefing anfragen"
- Blog-Post-Links: `/wissen/{post.slug}` (dynamisch via getCollection('blog'))

**Glossar (Section 5):**
- CTA: `/wissen/glossar` → "Glossar öffnen"

**Downloads (Section 6):**
- Asset 1: `/code-statt-cms` → "Code statt CMS Landingpage"
- Asset 2: `/downloads/bfsg-bitv-checklist` → "BFSG/BITV Compliance Checklist"
- Asset 3: `/downloads/servicecockpit-intake-playbook` → "Servicecockpit Intake Playbook"

**Footer:**
- Branchen, Leistungen, Wissen, Kontakt, Impressum, Datenschutz (Standard-Links)

### Externe Links
Keine direkten externen Links

### Backlinks (intern)
Diese Seite wird verlinkt von:
- Navigation: "Wissen" (alle Seiten)
- Footer: "Wissen" (alle Seiten)
- Startseite: Vermutlich CTA "Wissen-Hub öffnen"
- code-statt-cms.md: CTA "KPI-Guides ansehen" → /wissen

**Gesamtanzahl interne Links:** ~35-45 (inkl. Navigation, Footer, Blog-Post-Links, Segment-Links, Download-Links, Anchor-Links)

---

## 🏗️ 3. LAYOUT & SEMANTISCHE STRUKTUR

---

### BACKGROUND-SYSTEM (Design-Dokumentation)

**Umfangreiches 3-Pattern-System** für skalierbare Dark-Mode-Backgrounds (dokumentiert im Kommentar Lines 14-77):

**PATTERN 1: CONTENT LIGHT** (Standard für Content-Sections)
- Background: `bg-gradient-to-b from-dark-100 via-dark-100 to-dark-100/98`
- Grid Opacity: 0.05
- Center Glow: rgba(255,255,255,0.05-0.06) – heller Bereich für Content
- Verwendung: Overview, Segments, Guides (Main Content-Sections)

**PATTERN 2: CONTENT MEDIUM** (Übergänge/Pre-Footer)
- Background: `bg-gradient-to-b from-dark-100 via-dark-100/95 to-dark-200`
- Grid Opacity: 0.04-0.05
- Center Glow: rgba(255,255,255,0.04) – subtiler als Pattern 1
- Verwendung: Glossar, Pre-Footer Sections, Transition-Bereiche

**PATTERN 3: CONTENT DARK** (Spezielle Sections)
- Background: `bg-gradient-to-br from-black via-[#060606] to-black`
- Grid Opacity: 0.03
- Orbs: Animated floating orbs mit blur-3xl
- Verwendung: Downloads, Assets, Footer-ähnliche Heavy Sections

---

### SECTION 1: HERO (Dark Grid)

**Komponente:** `<Hero />`
**Layout-Pattern:** Full-viewport Hero mit Dark Grid Background
**Hintergrund:** `var(--surface-dark)` (#04060D) mit Grid-Pattern + Glow-Effekt

```
HERO#hero (Full Height: 100vh/100dvh, tone: dark-grid)
│
├── Badge: "Segmentiert: Kanzlei · Bildung · öffentliche Dienste"
├── H1: "Wissen Hub für Kanzleien, Campus & Behörden"
├── Subtitle: "Guides, KPI-Playbooks und Tool-Erklärungen für regulierte Teams..."
│
└── CTA-Group (2 CTAs: Primary + Tertiary)
    ├── Primary: "Kontakt aufnehmen" → /kontakt (ctaVariant="sparkle")
    └── Tertiary: "Top-Task Downloads" → #downloads (Anchor-Link)
```

**Note:** `showSecondaryCta={false}` → Kein Secondary-CTA

---

### SECTION 2: OVERVIEW (Light)

**Komponente:** `<Section tone="light" />`
**Layout-Pattern:** Text-Center + 3-Column Stats-Grid
**Hintergrund:** `var(--surface-light)` (#F9FAFB)

```
SECTION#overview (tone: light, standard padding)
│
├── Intro-Text (max-w-5xl mx-auto, text-center)
│   ├── Paragraph 1: "Dieser Hub bündelt Research, KPI-Ziele und Umsetzungs-Workflows..."
│   │   Strong-Highlights: "Anmeldung in 3 Schritten", "Digital Take-up ≥70 %", "INP < 200 ms"
│   │   Quellen: E-Government Monitor 2023, GOV.UK Performance, D21 Mobile Index
│   │
│   └── Paragraph 2: "Nutzen Sie die Quicklinks, um Glossar-Einträge, Checklisten und segment-spezifische Guides..."
│
└── ContentBoxDark (mt-12)
    │
    └── Stats-Grid (sm:grid-cols-3, gap-6, max-w-5xl mx-auto)
        │
        ├── Stat-Card 1: "3 Schritte"
        │   Background: bg-white-alpha-08
        │   Border: border-on-dark-subtle
        │   Border-Radius: rounded-3xl (24px)
        │   Padding: px-6 py-8
        │   Shadow: 0 30px 80px -50px rgba(0,0,0,0.7)
        │   Hover: border-slate-400/40, translate-y-[-4px], shadow-intensiviert
        │   Min-Height: 200px
        │   │
        │   ├── Value: "3 Schritte"
        │   │   Font: Inter SemiBold, 32px @ Mobile, 36px @ Desktop
        │   │   Farbe: var(--slate-100)
        │   │
        │   ├── Label: "Digitale Anmeldung"
        │   │   Font: Inter SemiBold, 12px, Uppercase, Letter-spacing: 0.28em
        │   │   Farbe: var(--slate-400)
        │   │   Margin-top: mt-2 (8px)
        │   │
        │   └── Context: "Zielbild Bildung laut Enrollment-Blueprint"
        │       Font: Inter Regular, 14px
        │       Farbe: var(--slate-300)
        │       Margin-top: mt-4 (16px)
        │
        ├── Stat-Card 2: "≥70 %" (Struktur identisch)
        │   Label: "Digital Take-up"
        │   Context: "Behörden Services nach GOV.UK Benchmarks"
        │
        └── Stat-Card 3: "< 200 ms" (Struktur identisch)
            Label: "INP-Budget"
            Context: "Code-first Stack für alle Segmente"
```

**Abstände:** Standard py-24 md:py-32, mt-12 (48px) vor ContentBoxDark

---

### SEPARATOR (Glowing Line)

Zwischen jeder Section:
```
<div class="h-px bg-gradient-to-r from-transparent via-slate-300/20 to-transparent"></div>
```
(Opacity 0.2, via-color: slate-300 für Light-Separators, white/10 für Dark-Separators)

---

### SECTION 3: SEGMENTS (Dark)

**Komponente:** `<Section tone="dark" grid={true} />`
**Layout-Pattern:** 3-Column Card Grid (Desktop: md:grid-cols-3)
**Hintergrund:** `var(--surface-dark)` (#04060D) + Grid-Pattern (Pattern 1/2)

```
SECTION#segments (tone: dark, grid={true}, py-24 md:py-32)
│
├── Header (max-w-3xl mx-auto, text-center)
│   ├── H2: "Segment-Playbooks & KPIs"
│   └── Paragraph: "Jedes Segment erhält eigenständige KPI-Budgets..."
│
└── Cards-Grid (md:grid-cols-3, gap-6, max-w-6xl)
    │
    ├── Segment-Card 1: Kanzleien & Sozietäten
    │   Background: bg-white-alpha-08
    │   Border: border-on-dark-subtle
    │   Border-Radius: rounded-3xl (24px)
    │   Padding: p-10 (40px)
    │   Shadow: 0 20px 60px -30px rgba(0,0,0,0.3)
    │   Hover: border-slate-400/50, translate-y-[-6px], shadow-intensiviert + radial-glow (silver)
    │   Min-Height: 380px
    │   │
    │   ├── Icon + Badge-Row
    │   │   ├── Icon: Checkmark (SVG), w-12 h-12, bg-slate-700/30, border-slate-400/30, rounded-xl
    │   │   └── H3: "Kanzleien & Sozietäten"
    │   │       Font: Inter Bold, 20px @ Mobile, 24px @ Desktop
    │   │       Farbe: var(--slate-100)
    │   │       Badge: "Intake & KPIs" (bg-slate-600/20, text-slate-300)
    │   │
    │   ├── Description
    │   │   Text: "Lead-to-Call Rate +35 %, Intake-SLAs < 1 h..."
    │   │   Font: Inter Regular, 16px
    │   │   Farbe: var(--slate-300)
    │   │   Line-height: relaxed
    │   │
    │   └── Link: "Mehr erfahren" → /branchen/kanzleien
    │       Font: Inter SemiBold, 14px
    │       Farbe: var(--slate-400), Hover: underline-white
    │       Icon: Right-Arrow (SVG), transform-translateX on hover
    │
    ├── Segment-Card 2: Schulen & Campus (Struktur identisch)
    │   Badge: "Enrollment"
    │   Href: /branchen/schulen-bildung
    │
    └── Segment-Card 3: Behörden & öffentliche Dienste (Struktur identisch)
        Badge: "OZG & BFSG"
        Href: /branchen/oeffentliche-einrichtungen
```

**Unified Corporate Identity:** Alle Segment-Cards nutzen Silver/Navy-Farbschema (bg-slate-700/30, border-slate-400/30, text-slate-300)

---

### SECTION 4: GUIDES (Light)

**Komponente:** `<Section tone="light" />`
**Layout-Pattern:** Text + CTA-Button (oben) + Blog-Posts-Grid (unten, in ContentBoxDark)
**Hintergrund:** `var(--surface-light)` (#F9FAFB)

```
SECTION#guides (tone: light, py-24 md:py-32)
│
├── Header-Row (lg:flex-row, lg:items-center, lg:justify-between)
│   │
│   ├── LEFT: Text-Block (max-w-3xl)
│   │   ├── H2: "Guides, KPI-Pläne & Cases"
│   │   └── Paragraph: "Die neuesten Artikel kombinieren technische Schritte (Astro, Cloudflare, AWS) mit KPI-Ankern..."
│   │
│   └── RIGHT: CTA-Button (Button-Komponente)
│       Text: "Individuelles KPI-Briefing anfragen"
│       Href: /kontakt
│       Variant: "primary"
│       Size: "lg"
│       Icon: Right-Arrow, iconPosition: "right"
│       data-cta: "wissen-response-playbook"
│
└── ContentBoxDark (mt-12)
    │
    └── Blog-Posts-Grid (md:grid-cols-2 xl:grid-cols-3, gap-8 lg:gap-10)
        │
        ├── Blog-Post-Card (dynamisch via getCollection('blog'))
        │   Background: bg-white-alpha-08
        │   Border: border-on-dark-subtle
        │   Border-Radius: rounded-2xl (16px)
        │   Padding: p-8 (32px)
        │   Shadow: 0 20px 60px -30px rgba(0,0,0,0.3)
        │   Hover: border-slate-400/40, translate-y-[-6px], shadow + radial-glow (silver)
        │   Min-Height: 440px @ Mobile, 460px @ Desktop
        │   data-article-segment: {post.data.segment ?? 'kanzlei'}
        │   │
        │   ├── Header-Row
        │   │   ├── Badge: {post.data.category}
        │   │   │   Background: bg-slate-500/20 (unified silver scheme)
        │   │   │   Text: text-slate-300
        │   │   │   Font: Inter Medium, 12px
        │   │   │
        │   │   └── Read-Time: {post.data.readTime}
        │   │       Font: Inter Regular, 14px
        │   │       Farbe: var(--slate-400)
        │   │
        │   ├── H3: {post.data.title}
        │   │   Font: Inter SemiBold, 20px @ Mobile, 24px @ Desktop
        │   │   Farbe: var(--slate-400), Hover: var(--slate-300)
        │   │   Class: clamp-3 (max 3 lines)
        │   │
        │   ├── Description: {post.data.description}
        │   │   Font: Inter Regular, 16px
        │   │   Farbe: var(--slate-300)
        │   │   Class: clamp-3
        │   │   Margin: mb-6 (24px)
        │   │
        │   └── Footer-Row (flex, justify-between)
        │       ├── Time: {formatDate(post.data.publishedDate)}
        │       │   Font: Inter Regular, 14px
        │       │   Farbe: var(--slate-400)
        │       │   DateTime-Attribute: {post.data.publishedDate}
        │       │
        │       └── Link: "Artikel lesen" → /wissen/{post.slug}
        │           Font: Inter Medium, 14px
        │           Farbe: var(--slate-400), Hover: var(--slate-300)
        │           Icon: Right-Arrow (SVG)
        │
        ├── Blog-Post-Card 2 (Struktur identisch)
        ├── Blog-Post-Card 3 (Struktur identisch)
        └── ... (dynamisch, alle Posts via getCollection('blog'))
```

**Category-Based-Colors:** Alle Kategorien nutzen unified silver scheme (bg-slate-500/20, text-slate-300)

---

### SECTION 5: GLOSSAR (Dark)

**Komponente:** `<Section tone="dark" grid={true} />`
**Layout-Pattern:** Text-Center + CTA-Button + 4-Column Kategorie-Grid
**Hintergrund:** `var(--surface-dark)` (#04060D) + Grid-Pattern (Pattern 2)

```
SECTION#glossar (tone: dark, grid={true}, py-24 md:py-32)
│
├── Header (max-w-3xl mx-auto, text-center)
│   │
│   ├── H2: "Glossar & Kategorien"
│   ├── Paragraph: "Fachbegriffe wie BFSG, INP, Servicecockpit oder AEO sind mit Tooltips im gesamten Hub verlinkt..."
│   │
│   └── CTA-Button
│       Text: "Glossar öffnen"
│       Href: /wissen/glossar
│       Background: transparent
│       Border: 2px solid var(--border-on-dark-subtle)
│       Padding: px-6 py-3 (24px × 12px)
│       Border-Radius: rounded-full (9999px)
│       Hover: bg-white-alpha-12, border-[color:var(--border-strong-dark)]
│       Backdrop-blur: backdrop-blur-sm
│       Margin-top: mt-6 (24px)
│       data-cta: "wissen-glossar"
│
└── Kategorie-Grid (sm:grid-cols-2 lg:grid-cols-4, gap-6 lg:gap-8)
    │
    ├── Kategorie-Card 1: "Performance & Core Web Vitals"
    │   Background: bg-white-alpha-08
    │   Border: border-on-dark-subtle
    │   Border-Radius: rounded-2xl (16px)
    │   Padding: p-6 (24px)
    │   Shadow: 0 30px 80px -50px rgba(0,0,0,0.7)
    │   Hover: shadow-intensiviert, border-slate-400/30, translate-y-[-4px]
    │   Min-Height: 180px
    │   │
    │   ├── Icon: Lightning-Bolt (SVG), w-12 h-12, bg-gray-800/60, border-slate-400/30, rounded-xl
    │   ├── H3: "Performance & Core Web Vitals"
    │   │   Font: Inter SemiBold, 16px @ Mobile, 20px @ Desktop
    │   │   Farbe: var(--slate-100)
    │   │
    │   └── Description: "INP < 200 ms, LCP < 2.3 s, Budget-Tracking pro Segment."
    │       Font: Inter Regular, 14px
    │       Farbe: var(--slate-300)
    │       Line-height: snug
    │
    ├── Kategorie-Card 2: "SEO, GEO & AEO" (Struktur identisch)
    │   Icon: Search (SVG)
    │   Description: "Answer Engine Optimierung, Standort-Kennzahlen, Schema-Snippets."
    │
    ├── Kategorie-Card 3: "Barrierefreiheit & Compliance" (Struktur identisch)
    │   Icon: Target (SVG)
    │   Description: "BFSG 2025, WCAG 2.2 AA, Consent Mode v2 und Audit-Logs."
    │
    └── Kategorie-Card 4: "Servicecockpit & Governance" (Struktur identisch)
        Icon: Code (SVG)
        Description: "Jour-fixe Dashboards, Kosten pro Antrag, Rollout-Playbooks."
```

---

### SECTION 6: DOWNLOADS (Light)

**Komponente:** `<Section tone="light" />`
**Layout-Pattern:** Text + 3-Column Download-Assets-Grid (in ContentBoxDark)
**Hintergrund:** `var(--surface-light)` (#F9FAFB)

```
SECTION#downloads (tone: light, py-24 md:py-32)
│
├── Header (max-w-3xl)
│   ├── H2: "Downloads & Assets"
│   └── Paragraph: "Die folgenden Assets sind im Ausbau. „In Arbeit" bedeutet, dass der Content im laufenden Sprint erstellt wird..."
│
└── ContentBoxDark (mt-10)
    │
    └── Download-Assets-Grid (md:grid-cols-3, gap-6)
        │
        ├── Download-Asset-Card 1: "Code statt CMS Landingpage"
        │   Background: bg-white-alpha-08
        │   Border: border-on-dark-subtle
        │   Border-Radius: rounded-3xl (24px)
        │   Padding: p-6 (24px)
        │   Shadow: 0 30px 80px -50px rgba(0,0,0,0.7)
        │   Hover: shadow-intensiviert, border-slate-400/30, translate-y-[-4px]
        │   Min-Height: 320px
        │   data-status: "in-progress"
        │   │
        │   ├── Badge: "In Arbeit"
        │   │   Class: chip-dark (unified silver scheme)
        │   │   Padding: px-3 py-1
        │   │   Border-Radius: rounded-full
        │   │
        │   ├── H3: "Code statt CMS Landingpage"
        │   │   Font: Inter SemiBold, 20px
        │   │   Farbe: var(--slate-100)
        │   │   Margin-top: mt-4 (16px)
        │   │
        │   ├── Description: "Vergleicht WordPress/TYPO3 mit dem Astro Code-Stack und zeigt Migration & Governance Pfade."
        │   │   Font: Inter Regular, 14px
        │   │   Farbe: var(--slate-300)
        │   │   Margin-top: mt-3 (12px)
        │   │
        │   ├── Link: "Asset öffnen" → /code-statt-cms
        │   │   Font: Inter SemiBold, 14px
        │   │   Farbe: #FFFFFF, Hover: var(--slate-200)
        │   │   Icon: Right-Arrow (SVG)
        │   │   Margin-top: mt-4 (16px)
        │   │
        │   └── Statushinweis: "Integration Playbook & Servicecockpit Visuals ergänzen (siehe optimieren_daten/supporting-assets-plan-2025-10-18.md §3)."
        │       Font: Inter Regular, 12px
        │       Farbe: var(--slate-400)
        │       Margin-top: mt-4 (16px)
        │
        ├── Download-Asset-Card 2: "BFSG/BITV Compliance Checklist" (Struktur identisch)
        │   Badge: "Live"
        │   Href: /downloads/bfsg-bitv-checklist
        │   data-status: "live"
        │
        └── Download-Asset-Card 3: "Servicecockpit Intake Playbook" (Struktur identisch)
            Badge: "In Arbeit"
            Href: /downloads/servicecockpit-intake-playbook
            data-status: "in-progress"
```

**Unified Badge-Styling:** Alle 3 Status (In Arbeit, Geplant, Live) nutzen identisches Silver-Treatment (chip-dark)

---

## 🎨 4. DESIGN-SYSTEM-DETAILS

### Farbnutzung (Hauptfarben pro Section)

| Element | CSS-Variable | Hex/rgba-Wert | Verwendung |
|---------|--------------|---------------|------------|
| **Hero (Dark Grid)** | `--surface-dark` | #04060D | Section-Hintergrund |
| **Overview (Light)** | `--surface-light` | #F9FAFB | Section-Hintergrund |
| Stats-Card-BG (Dark) | — | rgba(255,255,255,0.08) | bg-white-alpha-08 |
| Stats-Card-Border | `--border-on-dark-subtle` | rgba(255,255,255,0.18) | border-on-dark-subtle |
| **Segments (Dark)** | `--surface-dark` | #04060D | Section-Hintergrund + Grid-Pattern |
| Segment-Card-Icon-BG | — | rgba(100,116,139,0.3) | bg-slate-700/30 (Silver-Scheme) |
| Segment-Card-Badge-BG | — | rgba(71,85,105,0.2) | bg-slate-600/20 |
| **Guides (Light)** | `--surface-light` | #F9FAFB | Section-Hintergrund |
| Blog-Post-Card-BG (Dark) | — | rgba(255,255,255,0.08) | bg-white-alpha-08 (in ContentBoxDark) |
| **Glossar (Dark)** | `--surface-dark` | #04060D | Section-Hintergrund + Grid-Pattern |
| Kategorie-Card-Icon-BG | — | rgba(31,41,55,0.6) | bg-gray-800/60 |
| **Downloads (Light)** | `--surface-light` | #F9FAFB | Section-Hintergrund |
| Download-Card-BG (Dark) | — | rgba(255,255,255,0.08) | bg-white-alpha-08 (in ContentBoxDark) |
| **Separator** | — | rgba(203,213,225,0.2) | via-slate-300/20 (Light), via-white/10 (Dark) |

### Typografie-Details

**Font-Family:** Inter (Weights: Regular 400, Medium 500, SemiBold 600, Bold 700)

**Font-Sizes:**
- H1 (Hero): 48px @ Mobile → 72px @ Desktop
- H2 (Section): 30px @ Mobile → 36-48px @ Desktop
- H3 (Cards): 16-24px (je nach Kontext)
- Body (Regular): 14-16px
- Stats-Values: 32-36px (2xl-4xl)
- Labels (Uppercase): 12-14px (Letter-spacing: 0.28em)

### Spacing-System

- **Section-Padding:** py-24 md:py-32 (96px / 128px) (Standard für alle Sections)
- **Container-Padding:** px-6 (24px)
- **Grid-Gaps:** gap-6/gap-8/gap-10 (24px / 32px / 40px)
- **Card-Padding:** p-6/p-8/p-10 (24px / 32px / 40px)

### Border-Radius

- **Medium:** rounded-xl (12px)
- **Large:** rounded-2xl (16px) — Glossar-Cards, Blog-Post-Cards
- **XL:** rounded-3xl (24px) — Segment-Cards, Download-Cards, Stats-Cards
- **Full:** rounded-full (9999px) — Badges, CTA-Buttons

---

## 📱 5. RESPONSIVE BREAKPOINTS

| Breakpoint | Screen-Width | Grid-Cols | Section-Padding |
|------------|--------------|-----------|-----------------|
| **Mobile** | <640px | 1 | py-24 (96px) |
| **Tablet** | 640-1023px | 2 (sm) | py-28 (112px) |
| **Desktop** | ≥1024px | 3-4 (je nach Section) | py-32 (128px) |

### Hauptänderungen

**Mobile:** Alle Grids 1-Spalte, Stats-Grid 1-Spalte, Segment-Grid 1-Spalte, Guides-Grid 1-Spalte, Glossar-Grid 1-Spalte, Downloads-Grid 1-Spalte

**Tablet (sm):** Stats-Grid 3-Spalten, Glossar-Grid 2-Spalten

**Desktop (lg/xl):** Segment-Grid 3-Spalten, Guides-Grid 3-Spalten (xl), Glossar-Grid 4-Spalten, Downloads-Grid 3-Spalten

---

## 🧩 6. KOMPONENTEN-BIBLIOTHEK

### Genutzte Astro-Components

| Komponente | Datei | Props/Features |
|------------|-------|----------------|
| `<Hero />` | `/src/components/Hero.astro` | 2 CTAs (Primary + Tertiary), ctaVariant="sparkle", showSecondaryCta={false} |
| `<Section />` | `/src/components/Section.astro` | tone="light/dark", grid={true/false}, id="overview/segments/..." |
| `<Card />` | `/src/components/Card.astro` | NICHT verwendet (Segment/Blog-Cards sind inline) |
| `<ContentBoxDark />` | `/src/components/ContentBoxDark.astro` | Wrappt Stats-Grid, Blog-Posts-Grid, Downloads-Grid |
| `<Button />` | `/src/components/Button.astro` | variant="primary", size="lg", href="/kontakt", icon, iconPosition="right", data-cta |

### Dynamische Content-Collections

- **Blog-Posts:** `getCollection('blog')` → sortiert nach publishedDate (absteigend)
- **Date-Formatter:** Intl.DateTimeFormat('de-DE') → formatDate-Funktion

---

## 🔍 7. SEO & STRUKTURIERTE DATEN

### Schema.org Markup

**Typ: Blog + Organization**
```json
{
  "@context": "https://schema.org",
  "@type": "Blog",
  "name": "Wolf-Agents Wissen Hub",
  "description": "Guides, KPI-Playbooks und Glossar für Kanzleien, Bildungseinrichtungen und Behörden zu Performance, Compliance und Servicecockpits.",
  "inLanguage": "de-DE",
  "url": "https://www.wolf-agents.com/wissen",
  "audience": [
    { "@type": "Audience", "audienceType": "Anwaltskanzleien & Notare" },
    { "@type": "Audience", "audienceType": "Schulen & Hochschulen" },
    { "@type": "Audience", "audienceType": "Öffentliche Einrichtungen" }
  ],
  "about": [
    { "@type": "Thing", "name": "Core Web Vitals" },
    { "@type": "Thing", "name": "BFSG 2025" },
    { "@type": "Thing", "name": "Digital Take-up" },
    { "@type": "Thing", "name": "Servicecockpit Governance" }
  ],
  "publisher": {
    "@type": "Organization",
    "name": "Eduard Wolf Grafik & Design"
  },
  "blogPost": [
    {
      "@type": "BlogPosting",
      "headline": "{post.data.title}",
      "url": "https://www.wolf-agents.com/wissen/{post.slug}",
      "datePublished": "{post.data.publishedDate}"
    },
    ... (dynamisch für alle Blog-Posts)
  ]
}
```

**Zusammenfassung:**
- Blog-Schema mit audience-Arrays (3 Branchen)
- about-Arrays (4 Topics: Core Web Vitals, BFSG 2025, Digital Take-up, Servicecockpit Governance)
- blogPost-Array (dynamisch via getCollection('blog'))

---

## ♿ 8. BARRIEREFREIHEIT (WCAG 2.2)

### Kontrast-Ratios

**Text-on-Light:** #0F172A auf #F9FAFB ≈ **18.9:1** (AAA)

**Text-on-Dark:** #FFFFFF auf #04060D ≈ **19.6:1** (AAA)

**Silver-Icons:** rgba(148,163,184,1) auf #04060D ≈ **12.5:1** (AAA)

### Semantische HTML-Struktur

- **Korrekte Tags:** `<nav>`, `<main>`, `<section>`, `<article>`, `<footer>`
- **H1-H3-Hierarchie:** Korrekt (1× H1 im Hero, H2 pro Section, H3 für Cards)
- **Landmarks:** Korrekt

### Interaktive Elemente

- **Focus-Rings:** Standard (vermutlich via global.css)
- **Touch-Targets:** Min. 44×44px (CTAs, Card-Links)
- **Keyboard-Navigation:** Card-Links via Tab, CTAs via Enter

### Reduced Motion

**Unterstützung:** Ja (vermutlich via global.css → `@media (prefers-reduced-motion: reduce)`)

---

## 📝 9. CONTENT-STRATEGIE & TARGETING

### Hauptthema

Wissen-Hub für Kanzleien, Bildungseinrichtungen und Behörden. Bündelt Guides, KPI-Playbooks, Glossar-Einträge und Download-Assets. Segment-spezifische Inhalte für regulierte Teams.

### Primäre Keywords

- Wissen Hub Wolf-Agents
- KPI-Playbooks Kanzleien
- Core Web Vitals Guides
- BFSG 2025 Compliance
- Servicecockpit Governance

### Sekundäre Keywords (LSI)

- Digital Take-up
- Enrollment-Blueprint
- Intake-SLAs
- Answer Engine Optimization (AEO)
- Jour-fixe Dashboards

### Zielgruppe

**Primär:** IT-Entscheider, CTOs, Digitalisierungsbeauftragte in Kanzleien, Bildungseinrichtungen, Behörden (35-65 Jahre)

**Sekundär:** Marketing-Manager, externe Berater, Agenturen

### User Intent

**Primär:** Informational (Guides lesen, Glossar durchsuchen, Downloads abrufen)

**Sekundär:** Transactional (Kontakt aufnehmen → CTA "Individuelles KPI-Briefing anfragen")

### AIO/GEO/AEO-Status

**AIO:**
- Frage: "Was ist INP < 200 ms?" → Glossar-Section (Kategorie "Performance & Core Web Vitals")
- Frage: "Wie erreiche ich Digital Take-up ≥70 %?" → Segments-Section (Behörden-Card) + Guides-Section (Blog-Posts)

**GEO:**
- ✅ Blog-Schema mit audience-Arrays (3 Branchen: Kanzleien, Schulen, Behörden)
- ✅ about-Arrays (4 Topics: Core Web Vitals, BFSG 2025, Digital Take-up, Servicecockpit)
- ✅ blogPost-Array (dynamisch, alle Blog-Posts mit datePublished)

**AEO:**
- ✅ Listicles: 3 Knowledge-Stats, 3 Segment-Playbooks, 4 Glossar-Kategorien, 3 Download-Assets
- ✅ Konkrete Metriken: "3 Schritte", "≥70 %", "< 200 ms", "Lead-to-Call Rate +35 %"
- ✅ Strukturierte Blog-Post-Liste mit Kategorien + Read-Time

---

## 🔎 10. CONTENT-AUDIT-NOTIZEN

### Stärken

- ✅ **Umfangreiches Background-System:** 3-Pattern-Dokumentation (Content Light/Medium/Dark) für skalierbare Dark-Mode-Backgrounds
- ✅ **Unified Corporate Identity:** Silver/Navy-Farbschema für alle Cards (Stats, Segments, Blog-Posts, Glossar, Downloads)
- ✅ **Glowing Separators:** Subtile Übergänge zwischen Sections (bg-gradient via-slate-300/20)
- ✅ **Dynamische Blog-Posts:** getCollection('blog') → sortiert nach publishedDate
- ✅ **Segment-spezifische Playbooks:** 3 Branchen mit KPI-Ankern (Lead-to-Call +35 %, Digital Take-up ≥70 %)
- ✅ **Download-Assets:** 3 Assets mit Status-Badges (In Arbeit, Live, Geplant)
- ✅ **Schema.org Blog:** audience-Arrays + about-Arrays + blogPost-Array (dynamisch)

### Altlasten / Schwächen

- ⚠️ **Download-Assets "In Arbeit":** 2 von 3 Assets sind noch nicht live → Könnte zu Enttäuschung führen
- ⚠️ **Keine Search-Funktion:** Hub-Seite hat keine Suchfunktion für Guides/Glossar-Einträge
- ⚠️ **Statische Segment-Playbooks:** Nur 3 Branchen verlinkt → Andere Branchen (Steuerberatung, WP, Notariat) fehlen

### Fehlende Elemente

- ❌ **Search-Bar:** Keine Suchfunktion für Guides/Glossar
- ❌ **Filter-System:** Keine Filter für Blog-Posts nach Kategorie/Segment
- ❌ **Newsletter-Signup:** Kein Newsletter-CTA für neue Guides
- ❌ **RSS-Feed:** Kein RSS-Feed für Blog-Posts

### Content-Refresh-Priorität

**🟡 Mittel**

**Begründung:** Hub ist gut strukturiert und liefert klare Segmentierung. Verbesserung möglich durch Search-Funktion + Filter-System (Q2 2026). Download-Assets sollten bis Q1 2026 fertiggestellt sein.

---

## ⚡ 11. PERFORMANCE & TECHNISCHE DETAILS

### Core Web Vitals (Zielwerte)

- **LCP:** < 2.3 s (Hero H1)
- **INP:** < 200 ms (Card-Hover, CTA-Buttons)
- **CLS:** < 0.1 (Alle Cards statisch, keine dynamischen Layouts)

### Lazy Loading

- **Images:** Keine Images (nur SVG-Icons inline)
- **Scripts:** Minimal (nur Schema.org JSON-LD)

### Mobile Optimierung

- **Responsive:** Ja (Tailwind-Breakpoints)
- **Touch-Targets:** Min. 44×44px (CTAs, Card-Links)
- **Viewport-Meta:** Standard in Base-Layout

### Astro-spezifische Features

- **getCollection('blog'):** Content-Collections-API für Blog-Posts
- **SSG (Static Site Generation):** Seite wird zu statischem HTML kompiliert
- **Partial Hydration:** Vermutlich für Button-Komponente

---

## 📊 12. CONTENT-METRIKEN

### Textmenge

- **Gesamtzeichen:** ~9.800 Zeichen
- **Gesamtwörter:** ~1.380 Wörter
- **Lesedauer:** 6-7 Minuten

### Link-Dichte

- **Interne Links:** 35-45 (Navigation, Footer, Segment-Links, Blog-Post-Links, Download-Links, Glossar-Link, Anchor-Links)
- **Externe Links:** 0
- **CTAs:** 4 (Hero ×2, Guides-Section ×1, Glossar-Section ×1)
- **Anchor-Links:** 1 (#downloads)

### Content-Verteilung

- **Dark Sections:** 50% (3 von 6: Hero, Segments, Glossar)
- **Light Sections:** 50% (3 von 6: Overview, Guides, Downloads)

### Interaktive Elemente

- **Buttons/CTAs:** 4
- **Cards (insgesamt):** 16+ (3 Stats, 3 Segments, N Blog-Posts, 4 Glossar-Kategorien, 3 Downloads)
- **ContentBoxes:** 3 (Overview-Stats, Guides-Posts, Downloads-Assets)
- **Separators:** 4 (Glowing Lines zwischen Sections)
- **Icons:** 12+ (Segment-Icons, Glossar-Icons, Download-Status-Badges)

### Dynamic-Content-Metriken

- **Blog-Posts:** Dynamisch (via getCollection('blog') → sortedPosts)
- **Categories:** 5 (Performance & KPIs, SEO · GEO (AEO), Technisches SEO & Governance, Architektur & Governance, Deployment & Governance)
- **Segments:** 3 (Kanzleien, Campus, Behörden)
- **Download-Assets:** 3 (Code statt CMS, BFSG/BITV, Servicecockpit Intake)

---

**ENDE DER DOKUMENTATION**

Dokumentiert am 2025-11-01 von Claude (Sonnet 4.5) nach Protokoll `/Wolf-Agents.com-Architektur/00-DOKUMENTATIONS-PROTOKOLL.md`.
