# CODE STATT CMS - Content & Struktur-Architektur

**Dokumentiert am:** 2025-11-01
**Status:** IST-Zustand (keine Optimierungsvorschläge)

---

## 📊 1. HEADER & META-INFORMATIONEN

| Attribut | Wert |
|----------|------|
| **URL** | https://www.wolf-agents.com/code-statt-cms |
| **Datei** | `/src/pages/code-statt-cms.astro` |
| **Title Tag** | "Code statt CMS: Regulierte Teams auf Astro & GitOps umstellen \| Wolf-Agents" |
| **Meta Description** | "Vergleich WordPress/TYPO3 vs. Code-first auf Astro: KPI-Gewinne, Migration-Prozess, Compliance (BFSG 2025) und Governance-Pakete für Kanzleien, Bildung & Behörden." |
| **Canonical URL** | https://www.wolf-agents.com/code-statt-cms |
| **Noindex** | Nein |
| **Geschätzte Zeichenanzahl** | ~13.800 Zeichen (ohne Code/HTML) |
| **Geschätzte Wortanzahl** | ~1.950 Wörter |
| **Geschätzte Lesedauer** | 9-10 Minuten |
| **Anzahl Sections** | 7 Hauptbereiche (Hero, Pain-Gain, Use Cases, Comparison, Process, FAQ, CTA) |
| **Anzahl H1** | 1 (im Hero: "Warum regulierte Teams Code-first statt CMS brauchen") |
| **Anzahl H2** | 7 (Pain-Gain ×2, Use Cases, Comparison, Process, FAQ, CTA) |
| **Anzahl H3** | 7+ (KPI-Benchmarks-Box, Process-Steps ×4) |

---

## 🔗 2. VERLINKUNGSSTRUKTUR

### Interne Links (ausgehend)

**Navigation:**
- Logo-Link: `/`
- Branchen-Dropdown: `/branchen/kanzleien`, `/branchen/schulen-bildung`, `/branchen/oeffentliche-einrichtungen`, etc.
- Leistungen-Dropdown: `/leistungen` + 10 Unterseiten
- Wissen-Dropdown: `/wissen`, `/wissen/glossar`, `/code-statt-cms`
- CTA-Button: `/kontakt`

**Hero (Section 1):**
- CTA Primary: `/kontakt` → "Migration planen"
- CTA Secondary: `#comparison` → "Vergleich ansehen" (Anchor-Link)
- CTA Tertiary: `/wissen` → "Wissen-Hub öffnen"

**Use Cases (Section 3):**
- Card 1: `/branchen/kanzleien` → "Kanzlei: Intake ohne CMS-Ballast"
- Card 2: `/branchen/schulen-bildung` → "Bildung: Anmeldung in 3 Schritten"
- Card 3: `/branchen/oeffentliche-einrichtungen` → "Behörden: BFSG 2025-konforme Services"

**CTA (Section 7):**
- Primary: `/kontakt` → "Migration planen"
- Secondary: `/wissen` → "KPI-Guides ansehen"

**Footer:**
- Branchen, Leistungen, Wissen, Kontakt, Impressum, Datenschutz (Standard-Links)

### Externe Links
Keine direkten externen Links

### Backlinks (intern)
Diese Seite wird verlinkt von:
- Navigation: "Code statt CMS" (Wissen-Dropdown)
- Startseite: Vermutlich CTA "Code statt CMS Philosophie"
- Wissen-Hub: "Code-first Paradigma"

**Gesamtanzahl interne Links:** ~28-34 (inkl. Navigation, Footer, Use-Case-Cards, Anchor-Links)

---

## 🏗️ 3. LAYOUT & SEMANTISCHE STRUKTUR

---

### SECTION 1: HERO (Dark Grid)

**Komponente:** `<Hero />`
**Layout-Pattern:** Full-viewport Hero mit Dark Grid Background
**Hintergrund:** `var(--surface-dark)` (#04060D) mit Grid-Pattern + Glow-Effekt

```
HERO#hero (Full Height: 100vh/100dvh, tone: dark-grid)
│
├── Badge: "Vergleich: WordPress · TYPO3 · Drupal vs. Astro Code-Stack"
├── H1: "Warum regulierte Teams Code-first statt CMS brauchen"
├── Subtitle: "Weniger Updates, schnellere Mandate & Anmeldungen, messbare Performance..."
│
└── CTA-Group (3 CTAs: Primary, Secondary, Tertiary)
    ├── Primary: "Migration planen" → /kontakt
    ├── Secondary: "Vergleich ansehen" → #comparison
    └── Tertiary: "Wissen-Hub öffnen" → /wissen
```

**Abstände:** py-24 @ Mobile, py-32 @ Desktop

---

### SECTION 2: PAIN-GAIN (Light)

**Komponente:** `<Section tone="light" />`
**Layout-Pattern:** 2-Column Grid mit 2× ContentBoxDark (Pain vs. Gain)
**Hintergrund:** `var(--surface-light)` (#F9FAFB) + Radial-Gradient-Overlay + Grid-Pattern

```
SECTION#pain-gain (tone: light, py-24 md:py-32, min-h-100vh)
│
├── Background-Effects
│   ├── Radial-Gradient: circle at 20% 0%, rgba(148,163,184,0.22), Opacity 0.28
│   └── Grid-Subtle: Opacity 0.08
│
├── Container (max-w-6xl, space-y-16)
│   │
│   ├── Top-Row: 2-Column Grid (lg:grid-cols-2, gap-10)
│   │   │
│   │   ├── LEFT-COLUMN: CMS-Painpoints (ContentBoxDark)
│   │   │   Badge: "CMS"
│   │   │   Heading: "CMS-Painpoints in regulierten Projekten"
│   │   │   │
│   │   │   ├── Intro-Paragraph
│   │   │   │   Text: "Updates, Plugins und Legacy-Themes machen Releases riskant..."
│   │   │   │
│   │   │   └── List (3 Painpoints)
│   │   │       ├── Painpoint 1: "Updates, Plugins & Sicherheitslücken"
│   │   │       │   Icon: Minus (Rose-colored)
│   │   │       │   Background: rose-500/15
│   │   │       │   Ring: rose-500/25
│   │   │       │
│   │   │       ├── Painpoint 2: "Performance & INP"
│   │   │       │   Description: "Schwere Themes... INP/LCP... Core Web Vitals < 200 ms sind selten erreichbar."
│   │   │       │
│   │   │       └── Painpoint 3: "Governance & Nachvollziehbarkeit"
│   │   │           Description: "Wer hat wann was deployt?... Compliance-Audits dauern Tage."
│   │   │
│   │   └── RIGHT-COLUMN: Code-first Vorteile (ContentBoxDark)
│   │       Badge: "Code-first"
│   │       Heading: "Code-first Vorteile & KPI-Gewinne"
│   │       │
│   │       ├── Intro-Paragraph
│   │       │   Text: "Der Astro Code-Stack bringt kontrollierte Deployments, reproduzierbare Performance..."
│   │       │
│   │       └── List (3 Gainpoints)
│   │           ├── Gainpoint 1: "GitOps & Reproduzierbare Deployments"
│   │           │   Icon: Checkmark (Success-colored)
│   │           │   Background: success-500/15
│   │           │   Ring: success-500/25
│   │           │
│   │           ├── Gainpoint 2: "Astro Performance & Islands"
│   │           │   Description: "Astro + Tailwind liefert INP < 200 ms, LCP < 2.3 s..."
│   │           │
│   │           └── Gainpoint 3: "Servicecockpit & KI-Workflows"
│   │               Description: "Markdown/MDX, CMS-APIs... KI-Assistenten, CLI-Workflows..."
│   │
│   └── Bottom-Row: 2-Column Grid (lg:grid-cols-[1.05fr,0.95fr], gap-6)
│       │
│       ├── LEFT-BOX: KPI Benchmarks (ContentBoxLight)
│       │   Badge: "KPI Benchmarks"
│       │   Heading: "Research-basierte Zielwerte für regulierte Teams"
│       │   Paragraph: "Laut D21 Index, GOV.UK und Clio Legal Trends erreichen Code-first Projekte..."
│       │   Metrics: Anmeldungen in 3 statt 5 Schritten, Digital Take-up ≥70 %, Lead-to-Call +35 %, INP < 200 ms
│       │
│       └── RIGHT-BOX: KPI-Cards (ContentBoxLight)
│           Grid: grid-cols-2, gap-3
│           │
│           ├── Card 1: "Intake" → "Lead-to-Call +35 %"
│           ├── Card 2: "Service" → "Digital Take-up ≥70 %"
│           ├── Card 3: "Performance" → "INP < 200 ms"
│           └── Card 4: "Onboarding" → "3 statt 5 Schritte"
```

**Abstände:** py-24 @ Mobile, py-32 @ Desktop, space-y-16 (64px) zwischen Top/Bottom-Row

---

### SECTION 3: USE CASES (Navy)

**Komponente:** `<Section tone="navy" />`
**Layout-Pattern:** 3-Column Card Grid (Desktop: md:grid-cols-3)
**Hintergrund:** Navy-Tone (Dunkelblau, ähnlich --surface-dark aber mit Blau-Tint)

```
SECTION#use-cases (tone: navy, py-24 md:py-32)
│
├── Header (text-center, max-w-3xl mx-auto)
│   ├── H2: "Segmentierte Use Cases"
│   └── Paragraph: "Jedes Segment erhält eigene Journeys, KPI-Ziele und Governance-Vorgaben..."
│
└── Cards-Grid (md:grid-cols-3, gap-6)
    │
    ├── Card 1: Kanzlei (Card-Komponente)
    │   Title: "Kanzlei: Intake ohne CMS-Ballast"
    │   Description: "Lead-to-Call Rate +35 %, Intake-SLA < 1 h..."
    │   Href: /branchen/kanzleien
    │   Badge: "Intake & KPI"
    │   Icon: Checkmark SVG-Path
    │   Variant: "glow"
    │   Size: "lg"
    │
    ├── Card 2: Bildung (Struktur identisch)
    │   Title: "Bildung: Anmeldung in 3 Schritten"
    │   Href: /branchen/schulen-bildung
    │   Badge: "Enrollment"
    │
    └── Card 3: Behörden (Struktur identisch)
        Title: "Behörden: BFSG 2025-konforme Services"
        Href: /branchen/oeffentliche-einrichtungen
        Badge: "OZG & BFSG"
```

**Abstände:** py-24 @ Mobile, py-32 @ Desktop, gap-6 (24px)

---

### SECTION 4: COMPARISON (Light)

**Komponente:** `<Section tone="light" />`
**Layout-Pattern:** Table (5 Rows: Deployment, Performance, Compliance, Content, Kosten)
**Hintergrund:** `var(--surface-light)` (#F9FAFB)

```
SECTION#comparison (tone: light, py-24 md:py-32)
│
├── Header (max-w-4xl)
│   ├── H2: "WordPress/TYPO3 vs. Code-first auf Astro"
│   └── Paragraph: "Die Gegenüberstellung fokussiert auf Aspekte, die in regulierten Projekten entscheidend sind..."
│
├── Table-Container (rounded-3xl, border, shadow)
│   │
│   ├── Table-Header (bg-surface-light-elevated)
│   │   ├── TH: "Kriterium"
│   │   ├── TH: "WordPress/TYPO3"
│   │   └── TH: "Code-first (Astro)"
│   │
│   └── Table-Body (bg-surface-light, divide-y)
│       │
│       ├── Row 1: Deployment & Rollback
│       │   CMS: "SFTP, GUI-Deployments, manuelle Backups, Rollback selten möglich."
│       │   Code: "GitOps (PR → Review → Deploy), automatisierte Backups, Rollbacks in Minuten."
│       │
│       ├── Row 2: Performance & INP
│       │   CMS: "Themes + Plugins → häufig INP > 300 ms, LCP > 3 s..."
│       │   Code: "Astro Islands, Edge Rendering, Budgets: INP < 200 ms, LCP < 2.3 s, TTFB < 0.5 s."
│       │
│       ├── Row 3: Compliance & BFSG 2025
│       │   CMS: "Uneinheitliche Plugin-Qualität, Rollenrechte unklar, BITV-Tests aufwendig."
│       │   Code: "Komponenten geprüft, Tests & Linters automatisiert, Dokumentation in Repo."
│       │
│       ├── Row 4: Content & Redaktions-Workflows
│       │   CMS: "GUI-Editoren, viele Logins, Abhängigkeit von Plugins & Hosting."
│       │   Code: "Markdown, Headless CMS oder Notion → schlanke Renderer, CLI-Workflows, granulare Rollen."
│       │
│       └── Row 5: Kosten & Skalierung
│           CMS: "Lizenz + Plugin-Kosten, Performance-Optimierung wiederkehrend."
│           Code: "Invest in Initialmigration, danach klar planbare Betriebsstufen (Rapid Response → AWS Governance)."
│
└── Footnote
    Text: "* Grundlage: Audits aus Kanzlei-, Bildungs- und Behördenprojekten sowie Research aus Supporting-Assets (2025-10-18)..."
```

**Abstände:** py-24 @ Mobile, py-32 @ Desktop, px-6 py-4/5 (Table-Cells)

---

### SECTION 5: PROCESS (Navy)

**Komponente:** `<Section tone="navy" />`
**Layout-Pattern:** 4-Column Process-Steps (Desktop: md:grid-cols-4)
**Hintergrund:** Navy-Tone (Dunkelblau)

```
SECTION#process (tone: navy, py-24 md:py-32)
│
├── Header (max-w-3xl)
│   ├── H2: "Migration & Governance in vier Schritten"
│   └── Paragraph: "Wir planen Migrationen als reproduzierbaren Prozess mit klaren Deliverables..."
│
├── Process-Steps-Grid (md:grid-cols-4, gap-6, <ol>)
│   │
│   ├── Step 1: "Audit & KPI-Fit (1 Woche)"
│   │   Number-Badge: "1" (rounded-full, bg-surface-light-alpha-12)
│   │   H3: "Audit & KPI-Fit (1 Woche)"
│   │   Description: "Analyse von Hosting, Content-Modell, KPIs... Ergebnis: Migration-Backlog & Budget."
│   │
│   ├── Step 2: "Migration & Content-Modell (2–4 Wochen)"
│   │   Description: "Setup Astro Repository, Design Tokens... Automatisierte Redirect-Maps, Alt-Content bereinigen."
│   │
│   ├── Step 3: "QA & Compliance (1–2 Wochen)"
│   │   Description: "Performance-Budgets, Accessibility-Audits (WCAG 2.2 AA, BFSG), Consent Mode v2, Security & Logging."
│   │
│   └── Step 4: "Go-Live & Governance (laufend)"
│       Description: "Jour-fixe, Servicecockpit-Dashboards, KPI-Tracking, Trainings. Upgrades zwischen Stufe 0–C ohne Replatforming."
│
└── Info-Box (rounded-2xl, border, bg-surface-light-alpha-08)
    Text: "Servicecockpit-Visuals & Intake/Response Playbook: Visual Assets werden im Sprint 2025-11 ausgeliefert..."
```

**Abstände:** py-24 @ Mobile, py-32 @ Desktop, gap-6 (24px), p-6 (Cards)

---

### SECTION 6: FAQ (Light)

**Komponente:** `<Section tone="light" />`
**Layout-Pattern:** Accordion-List (4 FAQ-Items mit `<details>` + `<summary>`)
**Hintergrund:** `var(--surface-light)` (#F9FAFB)

```
SECTION#faq (tone: light, py-24 md:py-32)
│
├── Header (max-w-3xl)
│   ├── H2: "FAQ zur Migration „Code statt CMS""
│   └── Paragraph: "Die häufigsten Fragen zu Content-Editing, Laufzeiten, Kosten und Integration..."
│
└── FAQ-List (space-y-4)
    │
    ├── FAQ 1 (<details>)
    │   <summary>: "Wie pflegt das Team Inhalte ohne CMS-Backend?"
    │   Icon: Plus (rotiert zu X bei open)
    │   Answer: "Wir richten Markdown/MDX, Headless CMS (z. B. Sanity) oder Notion-basierte Quellen ein..."
    │
    ├── FAQ 2 (<details>)
    │   Question: "Wie lange dauert eine Migration?"
    │   Answer: "Rapid Response Microsites sind in ≤10 Tagen live (Stufe 0). Vollständige Portale (Stufe A/B) benötigen je nach Umfang 6–12 Wochen..."
    │
    ├── FAQ 3 (<details>)
    │   Question: "Was kostet der Code-first Betrieb?"
    │   Answer: "Die initiale Migration ist ein Projekt (Festpreis oder Sprint-Pakete). Betriebskosten ergeben sich aus gewählter Stufe..."
    │
    └── FAQ 4 (<details>)
        Question: "Wie integrieren wir bestehende Tools?"
        Answer: "Analytics, Consent, CRM oder Formular-Workflows werden als Module angebunden. Wir liefern SDKs, API-Konfigurationen..."
```

**Abstände:** py-24 @ Mobile, py-32 @ Desktop, space-y-4 (16px), p-6 (Details)

**Custom-Style:**
```css
details summary:focus-visible {
  outline: none;
  box-shadow: 0 0 0 3px var(--focus-ring-inner), 0 0 0 6px var(--focus-ring-outer);
  border-radius: 1rem;
}
```

---

### SECTION 7: CTA (Light)

**Komponente:** `<Section tone="light" />` + `<ContentBoxDark />`
**Layout-Pattern:** Centered ContentBox (max-w-5xl)
**Hintergrund:** `var(--surface-light)` (#F9FAFB) + ContentBox Dark Inset

```
SECTION#cta (tone: light, py-20 md:py-24)
│
└── ContentBoxDark (max-w-5xl mx-auto, text-center)
    Heading: "Bereit für einen Code-first Proof?"
    │
    ├── Paragraph
    │   Text: "Wir analysieren die bestehende CMS-Landschaft, definieren KPI-Ziele (Lead-to-Call, Digital Take-up, INP)..."
    │
    ├── CTA-Group (flex-col sm:flex-row, gap-4)
    │   │
    │   ├── Primary: "Migration planen" → /kontakt
    │   │   Background: var(--surface-light)
    │   │   Icon: Right-Arrow
    │   │   data-cta: "code-statt-cms-kontakt"
    │   │
    │   └── Secondary: "KPI-Guides ansehen" → /wissen
    │       Border: border-on-dark-strong
    │       Icon: Right-Arrow
    │       data-cta: "code-statt-cms-wissen"
    │
    └── Footnote
        Text: "Response Promise: Antwort in < 1 Stunde (Mo–Fr 09–18 Uhr) · Kick-off in ≤ 5 Werktagen"
        Font: 12px, text-white/70
```

**Abstände:** py-20 @ Mobile, py-24 @ Desktop

---

## 🎨 4. DESIGN-SYSTEM-DETAILS

### Farbnutzung (Hauptfarben pro Section)

| Element | CSS-Variable | Hex/rgba-Wert | Verwendung |
|---------|--------------|---------------|------------|
| **Hero (Dark Grid)** | `--surface-dark` | #04060D | Section-Hintergrund |
| **Pain-Gain (Light)** | `--surface-light` | #F9FAFB | Section-Hintergrund |
| Pain-Icon (Rose) | — | rose-500/15, rose-200 (Text) | Icon-Background + Text |
| Gain-Icon (Success) | — | success-500/15, success-200 (Text) | Icon-Background + Text |
| **Use Cases (Navy)** | Navy-Tone | Vermutlich #0A1628 | Section-Hintergrund (Dunkelblau) |
| **Comparison (Light)** | `--surface-light` | #F9FAFB | Section + Table-BG |
| Table-Header-BG | `--surface-light-elevated` | Vermutlich #FAFBFC | TH-Background |
| **Process (Navy)** | Navy-Tone | Vermutlich #0A1628 | Section-Hintergrund |
| **FAQ (Light)** | `--surface-light` | #F9FAFB | Section-Hintergrund |
| **CTA (Light+Dark)** | `--surface-dark` | #04060D | ContentBox-Background |

### Typografie-Details

**Font-Family:** Inter (Weights: Regular 400, Medium 500, SemiBold 600, Bold 700)

**Font-Sizes:**
- H1 (Hero): 48px @ Mobile → 72px @ Desktop
- H2 (Section): 30px @ Mobile → 36-48px @ Desktop
- H3 (Process-Steps): 18px
- Body (Regular): 14-16px
- Table-Text: 14px
- Uppercase-Labels: 12px (Letter-spacing: 0.26-0.28em)

### Spacing-System

- **Section-Padding:** py-20/24/32 (80px / 96px / 128px)
- **Container-Padding:** px-6 (24px)
- **Grid-Gaps:** gap-4/gap-6/gap-10 (16px / 24px / 40px)

### Border-Radius

- **Medium:** rounded-xl (12px)
- **Large:** rounded-2xl (16px)
- **XL:** rounded-3xl (24px)
- **Full:** rounded-full (9999px) — Process-Step-Numbers

---

## 📱 5. RESPONSIVE BREAKPOINTS

| Breakpoint | Screen-Width | Grid-Cols | Section Padding |
|------------|--------------|-----------|-----------------|
| **Mobile** | <640px | 1 | py-20/24 |
| **Tablet** | 640-1023px | 2 | py-24/28 |
| **Desktop** | ≥1024px | 2-4 (je nach Section) | py-24/32 |

### Hauptänderungen

**Mobile:** 1-Spalte für Pain-Gain, Use Cases, Comparison (Table horizontal-scroll), Process vertikal gestapelt

**Desktop:** Pain-Gain 2-Spalten, Use Cases 3-Spalten, Process 4-Spalten

---

## 🧩 6. KOMPONENTEN-BIBLIOTHEK

### Genutzte Astro-Components

| Komponente | Datei | Props/Features |
|------------|-------|----------------|
| `<Hero />` | `/src/components/Hero.astro` | 3 CTAs (Primary, Secondary, Tertiary), variant="dark-grid" |
| `<Section />` | `/src/components/Section.astro` | tone="light/navy", Background-Effects via TailwindClasses |
| `<Card />` | `/src/components/Card.astro` | variant="glow", size="lg", badge, icon (SVG-Path), href |
| `<ContentBoxDark />` | `/src/components/ContentBoxDark.astro` | badge, heading, headingLevel, class (h-full, text-center) |
| `<ContentBoxLight />` | `/src/components/ContentBoxLight.astro` | badge, heading, headingLevel |
| `<InfoTooltip />` | `/src/components/InfoTooltip.astro` | NICHT verwendet auf dieser Seite |

### Native HTML-Components

- **`<details>` + `<summary>`:** FAQ-Accordion (4 Items), Custom-Focus-Visible-Style
- **`<table>` + `<thead>` + `<tbody>`:** Comparison-Table (5 Rows)

---

## 🔍 7. SEO & STRUKTURIERTE DATEN

### Schema.org Markup

**Typ 1: WebPage**
```json
{
  "@context": "https://schema.org",
  "@type": "WebPage",
  "name": "Code statt CMS – Landingpage",
  "url": "https://www.wolf-agents.com/code-statt-cms",
  "description": "Warum regulierte Teams Code-first statt WordPress/TYPO3 nutzen sollten – inklusive Pain/Gain, KPI-Use-Cases, Migration-Prozess und FAQ."
}
```

**Typ 2: FAQPage**
```json
{
  "@context": "https://schema.org",
  "@type": "FAQPage",
  "mainEntity": [
    {
      "@type": "Question",
      "name": "Wie pflegt das Team Inhalte ohne CMS-Backend?",
      "acceptedAnswer": {
        "@type": "Answer",
        "text": "Wir richten Markdown/MDX, Headless CMS (z. B. Sanity) oder Notion-basierte Quellen ein..."
      }
    },
    ... (3 weitere Questions)
  ]
}
```

**Zusammenfassung:**
- 2 Schema-Types: WebPage + FAQPage (4 FAQs)
- Strukturierte Daten für LLM/SEO-Visibility

---

## ♿ 8. BARRIEREFREIHEIT (WCAG 2.2)

### Kontrast-Ratios

**Text-on-Light:** #0F172A auf #F9FAFB ≈ **18.9:1** (AAA)

**Text-on-Dark/Navy:** #FFFFFF auf #04060D/#0A1628 ≈ **19.6:1** / **17.5:1** (AAA)

### Semantische HTML-Struktur

- **Korrekte Tags:** `<nav>`, `<main>`, `<section>`, `<table>`, `<details>`, `<footer>`
- **H1-H3-Hierarchie:** Korrekt
- **Landmarks:** Korrekt

### Interaktive Elemente

- **Focus-Rings:** Custom für `<details>` (box-shadow mit --focus-ring-inner/-outer)
- **Details/Summary:** Keyboard-accessible (Enter/Space)
- **Touch-Targets:** Min. 44×44px (CTAs, FAQ-Summaries)

### Reduced Motion

**Unterstützung:** Ja (vermutlich via global.css)

---

## 📝 9. CONTENT-STRATEGIE & TARGETING

### Hauptthema

Vergleich CMS (WordPress, TYPO3) vs. Code-first (Astro) für regulierte Teams (Kanzleien, Bildung, Behörden). Argumentationskette: Pain → Gain → Use Cases → Comparison → Migration-Prozess → FAQ → CTA.

### Primäre Keywords

- Code statt CMS
- WordPress vs. Astro
- TYPO3 Migration
- Code-first Webentwicklung
- GitOps Kanzleien

### Sekundäre Keywords (LSI)

- Plugin-Spaghetti
- BFSG 2025 Compliance
- INP < 200 ms
- Headless CMS
- Markdown/MDX
- Servicecockpit
- Lead-to-Call Rate
- Digital Take-up

### Zielgruppe

**Primär:** IT-Entscheider, CTOs, Digitalisierungsbeauftragte in regulierten Branchen (35-60 Jahre)

**Sekundär:** Externe Berater, Agenturen, die Partner suchen

### User Intent

**Primär:** Informational (Warum Code-first? Welche Vorteile? Wie läuft Migration ab?)

**Sekundär:** Transactional (Interesse an Migration-Planung → CTA "Migration planen")

### AIO/GEO/AEO-Status

**AIO:**
- Frage: "Warum Code statt CMS?" → Pain-Gain-Section (3+3 Punkte)
- Frage: "Wie lange dauert CMS-Migration?" → FAQ-Section (10 Tage Rapid Response, 6-12 Wochen Vollportal)

**GEO:**
- ✅ FAQPage-Schema (4 Questions)
- ✅ WebPage-Schema mit Description

**AEO:**
- ✅ Listicles: 3 Painpoints, 3 Gainpoints, 5 Comparison-Rows, 4 Process-Steps, 4 FAQs
- ✅ Konkrete Metriken: INP < 200 ms, LCP < 2.3 s, Lead-to-Call +35 %, Digital Take-up ≥70 %

---

## 🔎 10. CONTENT-AUDIT-NOTIZEN

### Stärken

- ✅ **Klare Argumentationskette:** Pain → Gain → Use Cases → Comparison → Process → FAQ
- ✅ **Konkrete Vergleiche:** 5-Row-Table (CMS vs. Code-first)
- ✅ **Segment-spezifische Use Cases:** 3 Branchen mit KPIs
- ✅ **FAQPage-Schema:** 4 strukturierte FAQs für LLMs
- ✅ **KPI-Benchmarks:** Research-basiert (D21 Index, GOV.UK, Clio Legal Trends)
- ✅ **4-Step-Prozess:** Audit → Migration → QA → Go-Live (mit Zeitangaben)

### Altlasten / Schwächen

- ⚠️ **Keine Case-Studies:** Vergleichs-Tabelle ohne konkrete Projekt-Beispiele
- ⚠️ **Fehlende CMS-Screenshots:** Keine Before/After-Visualisierungen
- ⚠️ **Servicecockpit-Visuals "coming soon":** Info-Box verweist auf Sprint 2025-11 → Könnte zu Unklarheit führen

### Fehlende Elemente

- ❌ **Testimonials:** Keine Klienten-Zitate zur Migration
- ❌ **Kosten-Calculator:** Kein Tool zur Einschätzung von Migrations-Aufwand
- ❌ **Video/Demo:** Kein Walkthrough einer Migration

### Content-Refresh-Priorität

**🟢 Niedrig**

**Begründung:** Seite liefert solide Argumentation und Struktur. FAQ-Schema für SEO vorhanden. Verbesserung möglich durch Case-Studies + Visuals (nach Sprint 2025-11).

---

## ⚡ 11. PERFORMANCE & TECHNISCHE DETAILS

### Core Web Vitals (Zielwerte)

- **LCP:** < 2.3 s (Hero H1)
- **INP:** < 200 ms (Details/Summary, CTAs)
- **CLS:** < 0.1 (Table, ContentBoxes statisch)

### Lazy Loading

- **Images:** Keine Images (nur SVG-Icons inline)
- **Scripts:** Defer/async (Astro-Build-Config)

### Mobile Optimierung

- **Responsive:** Ja (Tailwind-Breakpoints)
- **Table:** Horizontal-Scroll auf Mobile (overflow-x-auto)
- **Touch-Targets:** Min. 44×44px

---

## 📊 12. CONTENT-METRIKEN

### Textmenge

- **Gesamtzeichen:** ~13.800 Zeichen
- **Gesamtwörter:** ~1.950 Wörter
- **Lesedauer:** 9-10 Minuten

### Link-Dichte

- **Interne Links:** 28-34 (Navigation, Footer, Use-Case-Cards, CTAs, Anchor-Links)
- **Externe Links:** 0
- **CTAs:** 5 (Hero ×3, CTA ×2)
- **Anchor-Links:** 1 (#comparison)

### Content-Verteilung

- **Dark/Navy Sections:** 42.9% (3 von 7: Hero, Use Cases, Process)
- **Light Sections:** 57.1% (4 von 7: Pain-Gain, Comparison, FAQ, CTA)

### Interaktive Elemente

- **Buttons/CTAs:** 5
- **Cards:** 3 (Use-Case-Cards)
- **ContentBoxes:** 4 (2 Pain-Gain, 2 KPI-Benchmarks)
- **Details/Summary:** 4 (FAQs)
- **Table:** 1 (5 Rows)

---

**ENDE DER DOKUMENTATION**

Dokumentiert am 2025-11-01 von Claude (Sonnet 4.5) nach Protokoll `/Wolf-Agents.com-Architektur/00-DOKUMENTATIONS-PROTOKOLL.md`.
