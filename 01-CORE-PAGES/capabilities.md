# CAPABILITIES - Content & Struktur-Architektur

**Dokumentiert am:** 2025-11-01
**Status:** IST-Zustand (keine Optimierungsvorschläge)

---

## 📊 1. HEADER & META-INFORMATIONEN

| Attribut | Wert |
|----------|------|
| **URL** | https://www.wolf-agents.com/capabilities |
| **Datei** | `/src/pages/capabilities.astro` |
| **Title Tag** | "Arbeitsweise & Delivery - Wolf-Agents" |
| **Meta Description** | "Code-first Delivery für Kanzleien, Bildung & öffentliche Dienste: CLI-first Engineering, KPI-getriebene Automationen, SEO + GEO (AEO) und Compliance. Überblick über Fähigkeiten und typische Projekt-Szenarien." |
| **Canonical URL** | https://www.wolf-agents.com/capabilities |
| **Noindex** | Nein |
| **Geschätzte Zeichenanzahl** | ~8.900 Zeichen (ohne Code/HTML) |
| **Geschätzte Wortanzahl** | ~1.260 Wörter |
| **Geschätzte Lesedauer** | 6-7 Minuten |
| **Anzahl Sections** | 6 Hauptbereiche (Hero, Capabilities, Einsatzfelder, Arbeitsweise, Benchmarks, CTA) |
| **Anzahl H1** | 1 (im Hero: "Arbeitsweise & Delivery für regulierte Teams") |
| **Anzahl H2** | 5 (Capabilities, Einsatzfelder, Arbeitsweise, Benchmarks, CTA) |
| **Anzahl H3** | 15+ (4 Capability-Cards, 3 Einsatzfelder-Cards, 4 Benchmark-Cards, Toolstack-Boxen) |

---

## 🔗 2. VERLINKUNGSSTRUKTUR

### Interne Links (ausgehend)

**Navigation:**
- Logo-Link: `/`
- Branchen-Dropdown: `/branchen/kanzleien`, `/branchen/schulen-bildung`, `/branchen/oeffentliche-einrichtungen`, `/branchen/steuerberatung`, `/branchen/wirtschaftspruefung`, `/branchen/notariat`, `/branchen/versicherungen`, `/branchen/medizin`, `/branchen/industrie-b2b`
- Leistungen-Dropdown: `/leistungen` + 10 Unterseiten
- Wissen-Dropdown: `/wissen`, `/wissen/glossar`, `/code-statt-cms`
- CTA-Button: `/kontakt`

**Hero (Section 1):**
- CTA Primary: `/kontakt` → "Kontakt aufnehmen"
- CTA Tertiary: `/wissen#playbooks` → "Guides & Playbooks öffnen"

**Capabilities (Section 2):**
- Glossar-Tooltips: `/wissen/glossar/cli-first`, `/wissen/glossar/gitops`, `/wissen/glossar/geo`, `/wissen/glossar/aeo`, `/wissen/glossar/consent-mode-v2`, `/wissen/glossar/wcag-22`

**CTA (Section 6):**
- Primary: `/kontakt` → "Capability Call sichern"
- Secondary: `/leistungen` → "Leistungsstufen vergleichen"

**Footer:**
- Branchen, Leistungen, Wissen, Kontakt, Impressum, Datenschutz (Standard-Links)

### Externe Links
Keine direkten externen Links (außer Schema.org-Kontext, falls vorhanden)

### Backlinks (intern)
Diese Seite wird verlinkt von:
- ueber-mich.md: "Capabilities ansehen" (CTA in Profil-Box + CTA-Section)
- Startseite: Vermutlich "Arbeitsweise & Methoden ansehen" (CTA)
- Footer: "Capabilities" (falls verlinkt)

**Gesamtanzahl interne Links:** ~32-38 (inkl. 6 Glossar-Tooltips, Navigation, Footer)

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
├── Background-Layer
│   Grid-Pattern: 1px weiße Lines, Opacity 0.04, Grid-Size: 48px
│   Glow: Radial-Gradient am Top-Center (Gold #FFD700, Opacity ~0.08)
│
├── H1 (Headline)
│   Text: "Arbeitsweise & Delivery für regulierte Teams"
│   Font: Inter Bold, 48px @ Mobile, 60px @ Tablet, 72px @ Desktop
│   Farbe: #FFFFFF
│   Line-height: tight (1.15)
│   Letter-spacing: -0.02em
│   Text-shadow: 0 2px 24px rgba(255,255,255,0.15)
│   Max-width: max-w-4xl (896px)
│   Margin-bottom: mb-5 (20px)
│
├── Paragraph (Subtitle)
│   Text: "Wir orchestrieren Mandatsreisen, Campus-Services und Bürgerportale mit auditierbaren Deployments, StepFlow-Komponenten und KPI-Cockpits – von Rapid Launches bis Enterprise-Governance."
│   Font: Inter Regular, 18px @ Mobile, 20px @ Desktop
│   Farbe: var(--text-secondary-on-dark) (rgba(249,250,251,0.72))
│   Line-height: relaxed (1.625)
│   Max-width: max-w-3xl (768px)
│   Margin-bottom: mb-8 (32px)
│
├── CTA-Group (Flex-Row @ Desktop, Flex-Col @ Mobile)
│   Gap: gap-4 (16px)
│   │
│   ├── CTA Primary
│   │   Text: "Kontakt aufnehmen"
│   │   Href: /kontakt
│   │   Background: var(--surface-light) (#F9FAFB)
│   │   Farbe: var(--text-primary-on-light) (#0B101A)
│   │   Font: Inter SemiBold, 15px
│   │   Padding: px-6 py-3 (24px × 12px)
│   │   Border-radius: rounded-xl (12px)
│   │   Shadow: 0 24px 70px -50px rgba(148,163,184,0.9)
│   │   Hover: scale-[1.01], Shadow intensiviert
│   │
│   └── CTA Tertiary
│       Text: "Guides & Playbooks öffnen"
│       Href: /wissen#playbooks (Anchor-Link)
│       Background: transparent
│       Border: 1px solid var(--border-on-dark-strong) (rgba(255,255,255,0.28))
│       Farbe: #FFFFFF
│       Font: Inter SemiBold, 15px
│       Padding: px-6 py-3 (24px × 12px)
│       Border-radius: rounded-xl (12px)
│       Hover: bg-rgba(255,255,255,0.12)
│
└── Note: showSecondaryCta={false} → Kein Secondary-CTA
```

**Abstände:**
- Outer Padding: py-24 @ Mobile, py-32 @ Desktop
- Container: max-w-6xl (1152px), mx-auto, px-6
- Inner Spacing: mb-5 (20px) zwischen H1/Subtitle, mb-8 (32px) vor CTAs

---

### SECTION 2: CAPABILITIES (Light)

**Komponente:** `<Section tone="light" />`
**Layout-Pattern:** 4-Column Card Grid (Desktop: xl:grid-cols-4)
**Hintergrund:** `var(--surface-light)` (#F9FAFB)

```
SECTION#capabilities (tone: light, py-24 md:py-32)
│
├── Header (text-center, max-w-5xl mx-auto)
│   │
│   ├── Badge
│   │   Text: "Was Sie von mir erwarten"
│   │   Class: chip-light caps-label-wide
│   │   Font: Inter SemiBold, 14px, Letter-spacing: 0.25em, Uppercase
│   │   Farbe: var(--text-primary-on-light) (#0B101A)
│   │   Margin-bottom: mb-4 (16px)
│   │
│   ├── H2
│   │   Text: "Vier Kompetenzsäulen für regulierte & öffentliche Projekte"
│   │   Font: Inter Bold, 30px @ Mobile, 36px @ Tablet, 48px @ Desktop
│   │   Farbe: var(--slate-900) (#0F172A)
│   │   Line-height: tight (1.25)
│   │   Margin-bottom: mb-6 (24px)
│   │
│   └── Paragraph
│       Text: "Ich agiere als Software-Architekt, Prompt-Engineer und Orchestrator verschiedener KI-Agenten..."
│       Font: Inter Regular, 18px @ Mobile, 20px @ Desktop
│       Farbe: var(--slate-600) (rgba(71,85,105,1))
│       Line-height: relaxed (1.625)
│       Max-width: max-w-3xl (768px)
│       Margin: mx-auto, mb-16 (64px)
│
└── Cards-Grid (md:grid-cols-2 xl:grid-cols-4, gap-6)
    │
    ├── Card 1: KI & Prompt Engineering
    │   Background: var(--surface-light) (#F9FAFB)
    │   Border: 1px solid var(--border-on-light-subtle) (rgba(15,23,42,0.18))
    │   Border-radius: rounded-3xl (24px)
    │   Padding: p-6 (24px)
    │   Shadow: 0 25px 60px -45px rgba(15,23,42,0.35)
    │   │
    │   ├── H3: "KI & Prompt Engineering"
    │   │   Font: Inter SemiBold, 20px
    │   │   Farbe: var(--slate-900) (#0F172A)
    │   │   Margin-bottom: mb-3 (12px)
    │   │
    │   └── List (Unordered)
    │       Items: 3 (Chain-of-Thought, Agent-Orchestrierung, Generative KI seit 2019)
    │       Font: Inter Regular, 14px
    │       Farbe: var(--slate-600) (rgba(71,85,105,1))
    │       Line-height: relaxed
    │       Spacing: space-y-2 (8px)
    │
    ├── Card 2: CLI-first Engineering
    │   Struktur identisch zu Card 1
    │   H3: "CLI-first Engineering" + <InfoTooltip termId="cli-first" />
    │   List-Items: 3 (Astro Islands, Skriptgesteuerte Builds, Infrastructure as Code)
    │   Inline-Element: <InfoTooltip termId="gitops" />
    │
    ├── Card 3: SEO + GEO (AEO) & Automation
    │   Struktur identisch zu Card 1
    │   List-Items: 3 (Technisches SEO, Python-/API-Automationen, Core Web Vitals 95+)
    │   Inline-Elemente: <InfoTooltip termId="geo" />, <InfoTooltip termId="aeo" />
    │
    └── Card 4: Compliance & Governance
        Struktur identisch zu Card 1
        List-Items: 3 (DSGVO/BRAO/StBerG, Consent Mode v2, Barrierefreiheit WCAG 2.2)
        Inline-Elemente: <InfoTooltip termId="consent-mode-v2" />, <InfoTooltip termId="wcag-22" />
```

**Abstände:**
- Outer Padding: py-24 @ Mobile, py-32 @ Desktop
- Container: max-w-6xl, mx-auto, px-6
- Header-Margin: mb-16 (64px)
- Cards-Grid-Gap: gap-6 (24px)

---

### SECTION 3: EINSATZFELDER (Dark)

**Komponente:** `<Section tone="dark" />`
**Layout-Pattern:** 3-Column Card Grid (Desktop: lg:grid-cols-3)
**Hintergrund:** `var(--surface-dark)` (#04060D)

```
SECTION#einsatzfelder (tone: dark, py-24 md:py-32)
│
├── Header (text-center, max-w-4xl mx-auto)
│   │
│   ├── Badge: "Typische Einsatzfelder"
│   │   Class: chip-dark caps-label-wide
│   │   Font: Inter SemiBold, 14px
│   │   Farbe: var(--text-secondary-on-dark)
│   │
│   ├── H2: "Wo meine Capabilities Wirkung entfalten"
│   │   Font: Inter Bold, 30px @ Mobile, 36px @ Desktop
│   │   Farbe: #FFFFFF
│   │   Margin-bottom: mb-6 (24px)
│   │
│   └── Paragraph
│       Text: "Ich baue Systeme, die sich schnell launchen lassen und anschließend kontrolliert wachsen..."
│       Font: Inter Regular, 18px
│       Farbe: rgba(226,232,240,0.85)
│       Line-height: relaxed
│       Margin-bottom: mb-16 (64px)
│
└── Cards-Grid (lg:grid-cols-3, gap-6)
    │
    ├── Card 1: Mandatsreisen & Intake-Pipelines
    │   Background: rgba(255,255,255,0.08)
    │   Border: 1px solid var(--border-on-dark-subtle)
    │   Border-radius: rounded-3xl (24px)
    │   Padding: p-8 (32px)
    │   Shadow: 0 30px 70px -55px rgba(15,23,42,0.65)
    │   Backdrop-blur: backdrop-blur-sm
    │   │
    │   ├── H3: "Mandatsreisen & Intake-Pipelines"
    │   │   Font: Inter SemiBold, 20px
    │   │   Farbe: #FFFFFF
    │   │   Margin-bottom: mb-3 (12px)
    │   │
    │   └── List (Unordered)
    │       Items: 3 (Intake-Flows, Response-Promise, Pitch-Hubs)
    │       Font: Inter Regular, 14px
    │       Farbe: var(--slate-200)
    │       Spacing: space-y-2 (8px)
    │
    ├── Card 2: Digitale Einschreibungen & Campus-Services
    │   Struktur identisch zu Card 1
    │   List-Items: 3 (StepFlow-Komponenten, Mobile-first, Integration Schulsoftware)
    │
    └── Card 3: Bürgerdienste & Servicecockpits
        Struktur identisch zu Card 1
        List-Items: 3 (BFSG 2025, Vier-Augen-Governance, KPIs Completion Rate)
```

**Abstände:**
- Outer Padding: py-24 @ Mobile, py-32 @ Desktop
- Container: max-w-6xl, mx-auto, px-6
- Header-Margin: mb-16 (64px)
- Cards-Grid-Gap: gap-6 (24px)

---

### SECTION 4: ARBEITSWEISE (Light)

**Komponente:** `<Section tone="light" />`
**Layout-Pattern:** 2-Column Grid (Desktop: lg:grid-cols-[1.1fr,0.9fr])
**Hintergrund:** `var(--surface-light)` (#F9FAFB)

```
SECTION#arbeitsweise (tone: light, py-24 md:py-32)
│
└── Grid-Container (lg:grid-cols-[1.1fr,0.9fr], gap-12)
    │
    ├── LEFT-COLUMN
    │   │
    │   ├── Badge
    │   │   Text: "Arbeitsweise"
    │   │   Class: chip-light caps-label-wide
    │   │   Font: Inter SemiBold, 12px
    │   │   Farbe: var(--text-secondary-on-light)
    │   │
    │   ├── H2: "How I build – Fragen, Meta-Reflexion und KI-Orchestrierung"
    │   │   Font: Inter Bold, 24px @ Mobile, 30px @ Desktop
    │   │   Farbe: var(--slate-900)
    │   │   Margin-bottom: mb-4 (16px)
    │   │
    │   ├── Paragraph
    │   │   Text: "Jedes Projekt startet mit den Fragen: Welche Annahmen treffe ich?..."
    │   │   Font: Inter Regular, 14px
    │   │   Farbe: var(--slate-600)
    │   │   Line-height: relaxed
    │   │   Margin-bottom: mb-5 (20px)
    │   │
    │   └── List (Unordered)
    │       Items: 4 (Chain-of-Thought, Questions-first, CLI-Pipelines, Rapid Prototyping)
    │       Font: Inter Regular, 14px
    │       Farbe: var(--slate-600)
    │       Spacing: space-y-3 (12px)
    │       Strong-Tags für Labels
    │
    └── RIGHT-COLUMN (Toolstack-Box)
        Background: var(--surface-light) (#F9FAFB)
        Border: 1px solid var(--border-on-light-subtle)
        Border-radius: rounded-3xl (24px)
        Padding: p-8 (32px)
        Shadow: 0 24px 60px -45px rgba(15,23,42,0.35)
        Backdrop-blur: backdrop-blur-sm
        │
        ├── H3: "Toolstack & Assets"
        │   Font: Inter SemiBold, 18px
        │   Farbe: var(--slate-900)
        │   Margin-bottom: mb-4 (16px)
        │
        └── Grid (grid-cols-2, gap-4)
            ├── Box 1: "Dev & Ops"
            │   Font-Title: Inter SemiBold, 14px, Farbe: var(--slate-900)
            │   Font-Text: Inter Regular, 14px, Farbe: var(--slate-600)
            │   Text: "Astro, Tailwind, Workers, SwiftUI, Kotlin, Terraform, GitHub Actions"
            │
            ├── Box 2: "KI & Automationen" (Struktur identisch)
            │   Text: "OpenAI API, Claude, eigene CLI-Agenten, LangChain, Automation via HTTP/Workers"
            │
            ├── Box 3: "SEO & Analytics" (Struktur identisch)
            │   Text: "Search Console, GA4, Matomo, Screaming Frog, Looker Studio, BigQuery, RUM"
            │
            └── Box 4: "Design & QA" (Struktur identisch)
                Text: "Figma, Storybook, Lighthouse CI, axe, Pa11y, WAVE, Chrome DevTools Recorder"
```

**Abstände:**
- Outer Padding: py-24 @ Mobile, py-32 @ Desktop
- Grid-Gap: gap-12 (48px)
- Inner-Grid (Toolstack): gap-4 (16px)

---

### SECTION 5: BENCHMARKS (Navy)

**Komponente:** `<Section tone="navy" />`
**Layout-Pattern:** 2-Column Grid mit 2×2 Benchmark-Cards (Desktop)
**Hintergrund:** Navy-Tone (Spezial-Dunkelblau, vermutlich ähnlich zu --surface-dark aber mit Blau-Tint)

```
SECTION#benchmarks (tone: navy, py-24 md:py-32)
│
└── Grid-Container (lg:grid-cols-[1fr,1fr], gap-12)
    │
    ├── LEFT-COLUMN
    │   │
    │   ├── Badge: "Messbare Kennzahlen"
    │   │   Class: chip-dark caps-label-wide
    │   │   Font: Inter SemiBold, 14px
    │   │   Farbe: var(--text-secondary-on-dark)
    │   │
    │   ├── H2: "Benchmarks & Proof-of-Delivery"
    │   │   Font: Inter Bold, 30px @ Mobile, 36px @ Desktop
    │   │   Farbe: #FFFFFF
    │   │   Margin-bottom: mb-6 (24px)
    │   │
    │   └── Paragraph
    │       Text: "Auch ohne öffentlich gelistete Fallstudien liegen harte Fakten vor..."
    │       Font: Inter Regular, 18px
    │       Farbe: rgba(226,232,240,0.85)
    │       Line-height: relaxed
    │
    └── RIGHT-COLUMN (Benchmark-Cards-Grid)
        Grid: grid-cols-1 sm:grid-cols-2, gap-6
        │
        ├── Card 1: "Kick-off ≤ 5 Werktage"
        │   Background: rgba(255,255,255,0.08)
        │   Border: 1px solid var(--border-on-dark-subtle)
        │   Border-radius: rounded-2xl (16px)
        │   Padding: p-6 (24px)
        │   │
        │   ├── Metric: "Kick-off ≤ 5 Werktage"
        │   │   Font: Inter Bold, 24px @ Mobile, 30px @ Desktop
        │   │   Farbe: #FFFFFF
        │   │   Line-height: tight
        │   │   Word-break: break-words
        │   │
        │   └── Description
        │       Text: "Rapid Launch für Microsites, Intake- oder Bürgerdienst-Prototypen in 7 Tagen..."
        │       Font: Inter Regular, 14px
        │       Farbe: var(--slate-200)
        │       Margin-top: mt-2 (8px)
        │
        ├── Card 2: "INP < 200 ms · LCP < 2.3 s" (Struktur identisch)
        ├── Card 3: "Lead-to-Call Rate +35 %" (Struktur identisch)
        └── Card 4: "Completion Rate ≥ 70 %" (Struktur identisch)
```

**Abstände:**
- Outer Padding: py-24 @ Mobile, py-32 @ Desktop
- Grid-Gap: gap-12 (48px)
- Cards-Grid-Gap: gap-6 (24px)

---

### SECTION 6: CTA (Light)

**Komponente:** `<Section tone="light" />` + `<ContentBoxDark />`
**Layout-Pattern:** Centered ContentBox (max-w-4xl)
**Hintergrund:** `var(--surface-light)` (#F9FAFB) + ContentBox Dark Inset

```
SECTION#cta (tone: light, py-24 md:py-32)
│
└── ContentBoxDark (max-w-4xl mx-auto, text-center)
    Background: var(--surface-dark) (#04060D)
    Border-radius: rounded-3xl (24px)
    Padding: p-10 md:p-12 (40px / 48px)
    Shadow: 0 30px 80px -55px rgba(15,23,42,0.7)
    │
    ├── H2: "Bereit für ein Capability-Upgrade?"
    │   Font: Inter Bold, 28px @ Mobile, 36px @ Desktop
    │   Farbe: #FFFFFF
    │   Margin-bottom: mb-6 (24px)
    │
    ├── Paragraph
    │   Text: "Lassen Sie uns über Launch-Fenster, Automationen und KPI-Strukturen sprechen..."
    │   Font: Inter Regular, 16px @ Mobile, 18px @ Desktop
    │   Farbe: rgba(226,232,240,0.85)
    │   Line-height: relaxed
    │   Margin-bottom: mb-8 (32px)
    │
    └── CTA-Group (flex-col sm:flex-row, gap-4 sm:gap-6)
        │
        ├── CTA Primary
        │   Text: "Capability Call sichern"
        │   Href: /kontakt
        │   Background: var(--surface-light) (#F9FAFB)
        │   Farbe: var(--slate-900) (#0F172A)
        │   Font: Inter SemiBold, 16px
        │   Padding: px-6 py-3 (24px × 12px)
        │   Border-radius: rounded-xl (12px)
        │   Shadow: 0 20px 60px -45px rgba(148,163,184,0.65)
        │   Hover: Shadow-Intensivierung + scale-[1.01]
        │
        └── CTA Secondary
            Text: "Leistungsstufen vergleichen"
            Href: /leistungen
            Background: transparent
            Border: 1px solid var(--border-on-dark-subtle) (rgba(255,255,255,0.18))
            Farbe: #FFFFFF
            Font: Inter SemiBold, 16px
            Padding: px-6 py-3 (24px × 12px)
            Border-radius: rounded-xl (12px)
            Hover: bg-rgba(255,255,255,0.12)
```

**Abstände:**
- Outer Padding: py-24 @ Mobile, py-32 @ Desktop
- Container: max-w-4xl, mx-auto
- ContentBox-Padding: p-10 @ Mobile, p-12 @ Desktop
- CTA-Group-Gap: gap-4 @ Mobile, gap-6 @ Desktop

---

## 🎨 4. DESIGN-SYSTEM-DETAILS

### Farbnutzung (Hauptfarben pro Section)

| Element | CSS-Variable | Hex/rgba-Wert | Verwendung |
|---------|--------------|---------------|------------|
| **Hero (Dark Grid)** | | | |
| Background | `--surface-dark` | #04060D | Section-Hintergrund |
| H1 | — | #FFFFFF | Headline |
| Subtitle | `--text-secondary-on-dark` | rgba(249,250,251,0.72) | Paragraph |
| CTA Primary BG | `--surface-light` | #F9FAFB | Button-Background |
| Grid-Lines | — | rgba(255,255,255,0.04) | Grid-Pattern |
| **Capabilities (Light)** | | | |
| Background | `--surface-light` | #F9FAFB | Section-Hintergrund |
| H2 | `--slate-900` | #0F172A | Headline |
| Body | `--slate-600` | rgba(71,85,105,1) | Paragraphen |
| Card-Border | `--border-on-light-subtle` | rgba(15,23,42,0.18) | Card-Borders |
| **Einsatzfelder (Dark)** | | | |
| Background | `--surface-dark` | #04060D | Section-Hintergrund |
| H2 | — | #FFFFFF | Headline |
| Body | — | rgba(226,232,240,0.85) | Paragraphen |
| Card-BG | — | rgba(255,255,255,0.08) | Card-Background (Alpha) |
| Card-Border | `--border-on-dark-subtle` | rgba(255,255,255,0.18) | Card-Borders |
| **Benchmarks (Navy)** | | | |
| Background | Navy-Tone | Vermutlich #0A1628 oder ähnlich | Section-Hintergrund (Dunkelblau) |
| H2 | — | #FFFFFF | Headline |
| Body | — | rgba(226,232,240,0.85) | Paragraphen |
| Card-BG | — | rgba(255,255,255,0.08) | Card-Background |
| **CTA ContentBox (Dark)** | | | |
| Background | `--surface-dark` | #04060D | ContentBox-Background |
| H2 | — | #FFFFFF | Headline |
| Body | — | rgba(226,232,240,0.85) | Paragraph |

### Typografie-Details

**Font-Family:** Inter (Weights: Regular 400, Medium 500, SemiBold 600, Bold 700)

**Font-Sizes:**
- H1 (Hero): 48px @ Mobile → 60px @ Tablet → 72px @ Desktop (3rem → 3.75rem → 4.5rem)
- H2 (Section): 30px @ Mobile → 36-48px @ Desktop (1.875rem → 2.25-3rem)
- H3 (Cards): 20px (1.25rem)
- Body (Regular): 14px (0.875rem)
- Body (Large/Intro): 18-20px (1.125-1.25rem)
- Benchmark-Metrics: 24px @ Mobile → 30px @ Desktop (1.5rem → 1.875rem)

**Line-Heights:**
- tight: 1.15-1.25 (Headlines, Metrics)
- normal: 1.5 (Body)
- relaxed: 1.625-1.75 (Intro-Paragraphs, Lists)

**Letter-Spacing:**
- Headlines: -0.02em (tight)
- Body: 0
- Uppercase-Labels: 0.25em

### Spacing-System

- **Section-Padding:** py-24/32 (96px @ Mobile, 128px @ Desktop)
- **Container-Padding:** px-6 (24px)
- **Card-Padding:** p-6/p-8 (24px / 32px)
- **Grid-Gaps:** gap-4/gap-6/gap-12 (16px / 24px / 48px)
- **Margin-Bottom (Headlines):** mb-4/mb-5/mb-6 (16px / 20px / 24px)

### Border-Radius

- **Medium:** rounded-xl (12px) — Buttons
- **Large:** rounded-2xl (16px) — Benchmark-Cards
- **XL:** rounded-3xl (24px) — Cards, ContentBox

---

## 📱 5. RESPONSIVE BREAKPOINTS

| Breakpoint | Screen-Width | Grid-Cols | Font-Size H1 | Font-Size H2 | Section Padding |
|------------|--------------|-----------|--------------|--------------|-----------------|
| **Mobile** | <640px | 1 | 48px (3rem) | 30px (1.875rem) | py-24 (96px) |
| **Tablet** | 640-1023px | 2 (teilweise) | 60px (3.75rem) | 36px (2.25rem) | py-28 (112px) |
| **Desktop** | ≥1024px | 2-4 (je nach Section) | 72px (4.5rem) | 36-48px (2.25-3rem) | py-32 (128px) |

### Hauptänderungen pro Breakpoint

**Mobile (<640px):**
- Grid-Layouts: 1-Spalte (Stack)
- Hero: 48px H1, 18px Subtitle
- Capabilities: 1-Spalte
- Einsatzfelder: 1-Spalte
- Arbeitsweise: 1-Spalte
- Benchmarks-Grid: 1-Spalte
- CTA-Group: flex-col (vertikal)

**Tablet (640-1023px):**
- Capabilities: 2-Spalten (md:grid-cols-2)
- Einsatzfelder: 2-3 Spalten (lg:grid-cols-3 ab 1024px)
- Arbeitsweise: bleibt 1-Spalte bis lg
- Benchmarks-Grid: 2-Spalten (sm:grid-cols-2)

**Desktop (≥1024px):**
- Capabilities: 4-Spalten (xl:grid-cols-4)
- Einsatzfelder: 3-Spalten (lg:grid-cols-3)
- Arbeitsweise: 2-Spalten (lg:grid-cols-[1.1fr,0.9fr])
- Benchmarks: 2-Spalten (lg:grid-cols-[1fr,1fr])

---

## 🧩 6. KOMPONENTEN-BIBLIOTHEK

### Genutzte Astro-Components

| Komponente | Datei | Props (Beispiel für diese Seite) |
|------------|-------|-----------------------------------|
| `<Base />` | `/src/layouts/Base.astro` | title="Arbeitsweise & Delivery - Wolf-Agents", description="..." |
| `<Nav />` | `/src/components/Nav.astro` | slot="header" (keine Props) |
| `<Hero />` | `/src/components/Hero.astro` | title="Arbeitsweise & Delivery für regulierte Teams", subtitle="...", ctaText="Kontakt aufnehmen", ctaHref="/kontakt", showSecondaryCta={false}, tertiaryCtaText="Guides & Playbooks öffnen", tertiaryCtaHref="/wissen#playbooks", variant="dark-grid", minHeightStyle="min-height:100vh;min-height:100dvh;" |
| `<Section />` | `/src/components/Section.astro` | tone="light/dark/navy", id="capabilities/einsatzfelder/...", class="py-24 md:py-32" |
| `<ContentBoxDark />` | `/src/components/ContentBoxDark.astro` | class="text-center", heading="Bereit für ein Capability-Upgrade?", headingLevel="h2" |
| `<InfoTooltip />` | `/src/components/InfoTooltip.astro` | termId="cli-first/gitops/geo/aeo/consent-mode-v2/wcag-22" |
| `<Footer />` | `/src/components/Footer.astro` | slot="footer" (keine Props) |

### Wichtige Komponenten-Details

**Hero:**
- Besonderheit: `showSecondaryCta={false}` → Kein Secondary-CTA, nur Primary + Tertiary
- tertiaryCtaText/Href für zusätzlichen CTA (z.B. Wissen/Playbooks)

**Section:**
- tone="navy": Spezial-Tone (Dunkelblau-Background, ähnlich Dark aber mit Blau-Tint)
- Genutzt in Benchmarks-Section für visuelle Variation

**InfoTooltip:**
- 6 termId-Varianten: cli-first, gitops, geo, aeo, consent-mode-v2, wcag-22
- Inline-Rendering in Listen und Paragraphen

---

## 🔍 7. SEO & STRUKTURIERTE DATEN

### Schema.org Markup

**Annahme:** Keine spezifischen strukturierten Daten auf dieser Seite (keine FAQ, kein Article-Schema). Möglicherweise Organization-Schema im Base-Layout (global).

**Falls vorhanden:**
- Typ: WebPage oder AboutPage
- Verknüpfung zu Person-Schema (Eduard Wolf) via mainEntity

### Open Graph / Twitter Card

**Annahme** (basierend auf Base-Layout-Standard):
- og:title: "Arbeitsweise & Delivery - Wolf-Agents"
- og:description: "Code-first Delivery für Kanzleien, Bildung & öffentliche Dienste..."
- og:image: Vermutlich `/img/og-capabilities.jpg` oder Default-OG-Image
- og:type: website
- twitter:card: summary_large_image

---

## ♿ 8. BARRIEREFREIHEIT (WCAG 2.2)

### Kontrast-Ratios

**Text-on-Dark (Hero, Einsatzfelder, Benchmarks, CTA):**
- #FFFFFF auf #04060D: **~19.6:1** (AAA)
- rgba(249,250,251,0.72) auf #04060D: **~14.1:1** (AAA)
- rgba(226,232,240,0.85) auf #04060D: **~16.8:1** (AAA)

**Text-on-Light (Capabilities, Arbeitsweise):**
- #0F172A auf #F9FAFB: **~18.9:1** (AAA)
- rgba(71,85,105,1) auf #F9FAFB: **~8.2:1** (AAA)

**Text-on-Navy (Benchmarks):**
- Annahme Navy-BG #0A1628: #FFFFFF auf #0A1628 ≈ **~17.5:1** (AAA)

**Ergebnis:** Alle Kontrast-Ratios erfüllen WCAG 2.2 Level AAA.

### Semantische HTML-Struktur

- **Korrekte Tags:** `<nav>`, `<main>`, `<section>`, `<article>` (Cards), `<footer>`
- **H1-H3-Hierarchie:** Korrekt (1× H1 im Hero, H2 pro Section, H3 für Cards)
- **Landmarks:** Nav, Main, Footer korrekt strukturiert

### Interaktive Elemente

- **Focus-Rings:** Custom-Focus-Rings via Tailwind
- **Button vs. Link:** Korrekt (CTAs = `<a>`-Links mit href)
- **Touch-Targets:** Min. 44×44px (py-3 = ~48px Höhe)
- **Keyboard-Navigation:** Anchor-Links (#playbooks) funktionieren

### Reduced Motion

**Unterstützung:** Ja (vermutlich via `@media (prefers-reduced-motion: reduce)`)

---

## 📝 9. CONTENT-STRATEGIE & TARGETING

### Hauptthema der Seite

Präsentation der Arbeitsweise, Fähigkeiten (Capabilities) und Delivery-Methodik von Wolf-Agents/Eduard Wolf. Fokus auf 4 Kompetenzsäulen (KI, CLI-first, SEO+GEO, Compliance), typische Einsatzfelder (Mandatsreisen, Campus, Bürgerdienste) und messbare Benchmarks.

### Primäre Keywords

- Arbeitsweise Webentwicklung
- Code-first Delivery
- CLI-first Engineering
- KI-Orchestrierung Kanzleien
- Capabilities Behörden-Digitalisierung

### Sekundäre Keywords (LSI)

- Prompt Engineering
- GitOps Deployment
- SEO + GEO (AEO)
- BFSG 2025
- WCAG 2.2
- Consent Mode v2
- Mandatsreisen
- Servicecockpit
- Core Web Vitals
- Rapid Launch

### Zielgruppe

**Primär:**
- IT-Entscheider in Kanzleien, Behörden, Bildungseinrichtungen (35-60 Jahre)
- Digitalisierungs-Verantwortliche (CTOs, CIOs, Projektleiter)
- Externe Berater/Consultants, die Partner für Umsetzung suchen

**Sekundär:**
- Marketing-Manager in Kanzleien
- Campus-IT-Leiter
- Startup-Gründer (regulierte Branchen)

### User Intent

**Primär:** Informational (Wie arbeitet Wolf-Agents? Welche Methoden? Welche Tools?)

**Sekundär:** Transactional (Interesse an Kontaktaufnahme → CTA "Capability Call sichern")

### AIO/GEO/AEO-Status

**AIO (Answer Intent Optimization):**
- Frage: "Wie arbeitet Wolf-Agents?" → Arbeitsweise-Section (Chain-of-Thought, CLI-Pipelines, Rapid Prototyping)
- Frage: "Welche Kompetenzen hat Wolf-Agents?" → 4 Capability-Cards (KI, CLI-first, SEO+GEO, Compliance)
- Frage: "Wo werden Wolf-Agents Capabilities eingesetzt?" → 3 Einsatzfelder-Cards (Mandatsreisen, Campus, Bürgerdienste)

**GEO (Generative Engine Optimization):**
- Content-Struktur: ✅ Klar gegliedert (Capabilities → Einsatzfelder → Arbeitsweise → Benchmarks)
- LLM-friendly: ✅ Listen-basiert, konkrete Metriken, keine verschachtelten Komponenten
- Strukturierte Daten: ⚠️ Vermutlich keine spezifischen (könnte ergänzt werden: FAQPage für "How I build")

**AEO (Answer Engine Optimization):**
- Featured-Snippet-Potenzial: Hoch (Listicles: 4 Capabilities, 3 Einsatzfelder, 4 Benchmarks)
- Konkrete Metriken: ✅ "Kick-off ≤ 5 Werktage", "INP < 200 ms", "Lead-to-Call Rate +35 %", "Completion Rate ≥ 70 %"
- Toolstack-Liste: ✅ Nützlich für LLMs (Astro, Tailwind, OpenAI, Claude, GA4, Lighthouse, etc.)

---

## 🔎 10. CONTENT-AUDIT-NOTIZEN

### Stärken

- ✅ **Klare 4-Säulen-Struktur:** Capabilities als zentrale Section mit 4 gleichwertigen Cards (KI, CLI-first, SEO, Compliance)
- ✅ **Messbare Benchmarks:** 4 konkrete Metriken (Kick-off ≤ 5 Tage, INP/LCP, Lead-to-Call +35 %, Completion ≥70 %)
- ✅ **Segment-spezifische Einsatzfelder:** 3 Use-Cases (Mandatsreisen, Campus, Bürgerdienste) mit konkreten Beispielen
- ✅ **Transparenter Toolstack:** 4 Boxen (Dev/Ops, KI, SEO, Design/QA) mit spezifischen Tool-Namen
- ✅ **Meta-Reflexion:** "How I build" erklärt Arbeitsmethodik (Chain-of-Thought, Questions-first, CLI-Pipelines)
- ✅ **Glossar-Integration:** 6 InfoTooltips für Fachbegriffe

### Altlasten / Schwächen

- ⚠️ **Keine Case-Studies:** Benchmarks ohne konkrete Projekt-Beispiele (z.B. "Kanzlei X: Lead-to-Call +35 %")
- ⚠️ **Fehlende Differenzierung:** Capabilities-Cards sehr kompakt → Könnte detaillierter sein (z.B. Sub-Kategorien)
- ⚠️ **Navy-Tone unklar:** Section "Benchmarks" nutzt tone="navy" → Design-Differenzierung zu Dark nicht dokumentiert
- ⚠️ **Keine Timeline:** Werdegang/Projekt-Historie fehlt (im Gegensatz zu ueber-mich.md)

### Fehlende Elemente

- ❌ **Case-Study-Links:** Keine Verlinkung zu konkreten Projekten oder Referenzen
- ❌ **FAQ-Section:** Keine häufig gestellten Fragen zu Arbeitsweise/Capabilities
- ❌ **Video/Demo:** Kein Walkthrough-Video der Toolstack oder Methodik
- ❌ **Client-Logos:** Keine Referenz-Logos (falls vorhanden)
- ❌ **Zertifikate:** Keine Erwähnung von Zertifikaten (z.B. AWS, Cloudflare, Accessibility)

### Content-Refresh-Priorität

**🟡 Mittel**

**Begründung:**
- Seite liefert solide Überblick über Capabilities und Arbeitsweise
- Benchmarks sind messbar und glaubwürdig
- **Aber:** Fehlt Case-Study-Substanz → Benchmarks ohne konkrete Projekt-Beispiele
- **Empfehlung:** Case-Study-Section hinzufügen (zwischen Benchmarks und CTA) mit 2-3 anonymisierten Projekt-Beispielen
- **Zeitpunkt:** Q3 2026 oder nach 10+ abgeschlossenen Projekten

---

## ⚡ 11. PERFORMANCE & TECHNISCHE DETAILS

### Core Web Vitals (Zielwerte)

- **LCP (Largest Contentful Paint):** < 2.3 s
  - LCP-Element: Hero H1 "Arbeitsweise & Delivery für regulierte Teams"
  - Optimierung: Astro-SSG (Pre-rendered), keine großen Images
- **INP (Interaction to Next Paint):** < 200 ms
  - Budget: 200 ms (laut Benchmarks-Section: "INP < 200 ms")
  - Interaktive Elemente: Nav-Dropdown, InfoTooltip-Modals, Anchor-Links
- **CLS (Cumulative Layout Shift):** < 0.1
  - Kritisch: Keine dynamischen Layouts, alle Cards statisch

### Lazy Loading

- **Images:** Keine Images auf dieser Seite (außer evtl. Icons, inline-SVGs)
- **Scripts:** Defer/async (vermutlich via Astro-Build-Config)

### Mobile Optimierung

- **Responsive:** Ja (Tailwind-Breakpoints, Grid-Collapse auf 1-Spalte)
- **Touch-Targets:** Min. 44×44px (CTAs, Cards)
- **Viewport-Meta:** Standard in Base-Layout

### Astro-spezifische Optimierungen

- **SSG (Static Site Generation):** Ja
- **Partial Hydration:** Vermutlich für InfoTooltip
- **Build-Output:** HTML + minimal JS

---

## 📊 12. CONTENT-METRIKEN

### Textmenge

- **Gesamtzeichen:** ~8.900 Zeichen (ohne Code/HTML)
- **Gesamtwörter:** ~1.260 Wörter
- **Lesedauer:** 6-7 Minuten (bei ~200 Wörter/Min)

### Link-Dichte

- **Interne Links:** 32-38 (Navigation, Footer, CTAs, Glossar-Tooltips, Anchor-Links)
- **Externe Links:** 0
- **CTAs:** 3 (Hero Primary, Hero Tertiary, CTA Primary, CTA Secondary)
- **Glossar-Tooltips:** 6 (cli-first, gitops, geo, aeo, consent-mode-v2, wcag-22)
- **Anchor-Links:** 1 (#playbooks)

### Content-Verteilung

- **Dark/Navy Sections:** 50% (3 von 6: Hero, Einsatzfelder, Benchmarks)
- **Light Sections:** 50% (3 von 6: Capabilities, Arbeitsweise, CTA → enthält ContentBoxDark)

### Interaktive Elemente

- **Buttons/CTAs:** 3
- **Cards (insgesamt):** 15 (4 Capabilities, 3 Einsatzfelder, 4 Benchmarks, 4 Toolstack-Boxen)
- **Collapsibles/Accordions:** 0
- **Tooltips:** 6 (InfoTooltip-Komponenten)
- **Images:** 0 (nur SVG-Icons inline)
- **Carousels/Sliders:** 0

### Section-Breakdown (Zeilen-Schätzung pro Section)

1. Hero: ~40 Zeilen Content
2. Capabilities: ~120 Zeilen Content (4 Cards + Header)
3. Einsatzfelder: ~80 Zeilen Content (3 Cards + Header)
4. Arbeitsweise: ~100 Zeilen Content (Text + Toolstack)
5. Benchmarks: ~80 Zeilen Content (4 Cards + Header)
6. CTA: ~40 Zeilen Content

**Gesamt:** ~460 Zeilen reiner Content (ohne Überschriften/Meta)

---

**ENDE DER DOKUMENTATION**

Dokumentiert am 2025-11-01 von Claude (Sonnet 4.5) nach Protokoll `/Wolf-Agents.com-Architektur/00-DOKUMENTATIONS-PROTOKOLL.md`.
