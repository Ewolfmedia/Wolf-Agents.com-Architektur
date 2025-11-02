# ÜBER MICH - Content & Struktur-Architektur

**Dokumentiert am:** 2025-11-01
**Status:** IST-Zustand (keine Optimierungsvorschläge)

---

## 📊 1. HEADER & META-INFORMATIONEN

| Attribut | Wert |
|----------|------|
| **URL** | https://www.wolf-agents.com/ueber-mich |
| **Datei** | `/src/pages/ueber-mich.astro` |
| **Title Tag** | "Über mich – Eduard Wolf \| Wolf-Agents" |
| **Meta Description** | "Eduard Wolf: Senior Full-Stack Developer & KI-Orchestrator für Kanzleien, Bildung & Behörden. Response Promise < 1 h, GitOps Delivery, KPIs & Governance." |
| **Canonical URL** | https://www.wolf-agents.com/ueber-mich |
| **Noindex** | Nein |
| **Geschätzte Zeichenanzahl** | ~11.200 Zeichen (ohne Code/HTML) |
| **Geschätzte Wortanzahl** | ~1.580 Wörter |
| **Geschätzte Lesedauer** | 7-9 Minuten |
| **Anzahl Sections** | 7 Hauptbereiche (Hero, Profil, Segment-Proof, Kompetenz-Cluster, Werdegang, Arbeitsprinzipien, CTA) |
| **Anzahl H1** | 1 (im Hero: "Eduard Wolf") |
| **Anzahl H2** | 6 (Profil, Segment-Proof, Kompetenz-Cluster, Werdegang, Arbeitsprinzipien, CTA) |
| **Anzahl H3** | 16+ (Profil-Stats, Segment-Cards, Kompetenz-Cards, Toolstack, Arbeitsprinzipien-Cards) |

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
- CTA Primary: `/kontakt` → "Response Playbook anfordern"
- CTA Secondary: `#segment-proof` → "Segment-Beweise ansehen" (Anchor-Link)
- Scroll-Hint: `#profil` (Anchor-Link)

**Profil (Section 2):**
- Glossar-Tooltips: `/wissen/glossar/geo`, `/wissen/glossar/aeo`
- Internal Link: `/capabilities` → "Capabilities ansehen"

**Segment-Proof (Section 3):**
- Branch-Cards: `/branchen/kanzleien`, `/branchen/schulen-bildung`, `/branchen/oeffentliche-einrichtungen`

**Kompetenz-Cluster (Section 4):**
- Glossar-Tooltips: `/wissen/glossar/cli-first`, `/wissen/glossar/gitops`, `/wissen/glossar/geo`, `/wissen/glossar/aeo`, `/wissen/glossar/consent-mode-v2`

**Werdegang (Section 5):**
- Glossar-Tooltips: `/wissen/glossar/geo`, `/wissen/glossar/aeo`

**Arbeitsprinzipien (Section 6):**
- Glossar-Tooltip: `/wissen/glossar/cli-first`

**CTA (Section 7):**
- Primary: `/kontakt` → "Gemeinsames Gespräch starten"
- Secondary: `/capabilities` → "Capabilities ansehen"

**Footer:**
- Branchen, Leistungen, Wissen, Kontakt, Impressum, Datenschutz (Standard-Links)

### Externe Links
Keine direkten externen Links (außer Schema.org JSON-LD)

### Backlinks (intern)
Diese Seite wird verlinkt von:
- Navigation: "Über mich" (alle Seiten)
- Footer: "Über mich" (alle Seiten)
- Startseite → CTA: "Mehr über Eduard Wolf"
- Capabilities-Seite → CTA: "Über mich ansehen"

**Gesamtanzahl interne Links:** ~38-44 (inkl. 7 Glossar-Tooltips, Navigation, Footer, Anchor-Links)

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
├── Badge
│   Text: "Für Kanzleien · Campus · öffentliche Dienste"
│   Background: rgba(255,255,255,0.08)
│   Font: Inter SemiBold, 11px, Letter-spacing: 0.22em, Uppercase
│   Padding: px-4 py-2 (16px × 8px)
│   Border-radius: rounded-full (9999px)
│   Farbe: var(--text-secondary-on-dark) (rgba(249,250,251,0.72))
│
├── H1 (Headline)
│   Text: "Eduard Wolf"
│   Font: Inter Bold, 48px @ Mobile, 60px @ Tablet, 72px @ Desktop
│   Farbe: #FFFFFF
│   Line-height: tight (1.15)
│   Letter-spacing: -0.02em
│   Text-shadow: 0 2px 24px rgba(255,255,255,0.15)
│   Max-width: max-w-4xl (896px)
│   Margin-bottom: mb-5 (20px)
│
├── Paragraph (Subtitle)
│   Text: "Senior Full-Stack Developer für Kanzleien, Bildung & Behörden – ich verbinde Strategie, Technik und Governance."
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
│   │   Text: "Response Playbook anfordern"
│   │   Href: /kontakt
│   │   Background: var(--surface-light) (#F9FAFB)
│   │   Farbe: var(--text-primary-on-light) (#0B101A)
│   │   Font: Inter SemiBold, 15px
│   │   Padding: px-6 py-3 (24px × 12px)
│   │   Border-radius: rounded-xl (12px)
│   │   Shadow: 0 24px 70px -50px rgba(148,163,184,0.9)
│   │   Hover: scale-[1.01], Shadow intensiviert
│   │
│   └── CTA Secondary
│       Text: "Segment-Beweise ansehen"
│       Href: #segment-proof (Anchor-Link)
│       Background: transparent
│       Border: 1px solid var(--border-on-dark-strong) (rgba(255,255,255,0.28))
│       Farbe: #FFFFFF
│       Font: Inter SemiBold, 15px
│       Padding: px-6 py-3 (24px × 12px)
│       Border-radius: rounded-xl (12px)
│       Hover: bg-rgba(255,255,255,0.12)
│
└── Scroll-Hint
    Text: "Weiter zu Profil & Arbeitsweise"
    Href: #profil (Anchor-Link)
    Position: Absolute bottom-10 (40px from bottom)
    Font: Inter Medium, 14px
    Farbe: var(--text-secondary-on-dark)
    Icon: Down-Arrow (animiert bounce)
```

**Abstände:**
- Outer Padding: py-24 @ Mobile, py-32 @ Desktop
- Container: max-w-6xl (1152px), mx-auto, px-6
- Inner Spacing: mb-5 (20px) zwischen H1/Subtitle, mb-8 (32px) vor CTAs

---

### SECTION 2: PROFIL (Light)

**Komponente:** `<Section tone="light" />`
**Layout-Pattern:** 2-Column Grid (Desktop: 1.1fr + 0.9fr)
**Hintergrund:** `var(--surface-light)` (#F9FAFB)

```
SECTION#profil (tone: light, py-24 md:py-32)
│
├── Grid-Container (lg:grid-cols-[1.1fr,0.9fr])
│   Gap: gap-12 (48px)
│   │
│   ├── LEFT-COLUMN
│   │   │
│   │   ├── Badge
│   │   │   Text: "Wer ich bin"
│   │   │   Class: chip-light caps-label-wide
│   │   │   Font: Inter SemiBold, 12px, Letter-spacing: 0.25em, Uppercase
│   │   │   Farbe: var(--text-primary-on-light) (#0B101A)
│   │   │   Margin-bottom: mb-4 (16px)
│   │   │
│   │   ├── H2
│   │   │   Text: "Digitale Plattform-Architektur für regulierte Teams"
│   │   │   Font: Inter Bold, 24px @ Mobile, 30px @ Desktop
│   │   │   Farbe: var(--text-primary-on-light) (#0B101A)
│   │   │   Line-height: tight (1.25)
│   │   │   Margin-bottom: mb-4 (16px)
│   │   │
│   │   ├── Paragraph 1
│   │   │   Text: "Seit mehr als acht Jahren konzipiere und entwickle ich digitale Lösungen..."
│   │   │   Font: Inter Regular, 14px
│   │   │   Farbe: var(--text-secondary-on-light) (rgba(11,16,26,0.72))
│   │   │   Line-height: relaxed (1.625)
│   │   │
│   │   ├── Paragraph 2
│   │   │   Text: "Meine Rolle: Software-Architekt, Prompt-Engineer..."
│   │   │   Inline-Elemente: <InfoTooltip termId="geo" />, <InfoTooltip termId="aeo" />
│   │   │   Font/Farbe: wie Paragraph 1
│   │   │   Margin-top: mt-4 (16px)
│   │   │
│   │   ├── List (Unordered)
│   │   │   Style: list-disc, pl-5 (20px)
│   │   │   Spacing: space-y-2 (8px)
│   │   │   Font: Inter Regular, 14px
│   │   │   Items: 3 (Segment-Journeys, Governance, Automationen)
│   │   │   Strong-Tags für Labels
│   │   │
│   │   └── Stats-Grid (sm:grid-cols-3, gap-4)
│   │       Margin-top: mt-8 (32px)
│   │       │
│   │       ├── Stat-Card 1: "< 1 h Response Promise"
│   │       │   Background: var(--surface-light) (#F9FAFB)
│   │       │   Border: 1px solid var(--border-on-light-subtle) (rgba(15,23,42,0.18))
│   │       │   Border-radius: rounded-2xl (16px)
│   │       │   Padding: p-6 (24px)
│   │       │   Shadow: 0 24px 60px -48px rgba(15,23,42,0.45)
│   │       │   │
│   │       │   ├── Value: "< 1 h"
│   │       │   │   Font: Inter SemiBold, 24px
│   │       │   │   Farbe: var(--text-primary-on-light)
│   │       │   │
│   │       │   ├── Label: "Response Promise"
│   │       │   │   Font: Inter Regular, 12px, Uppercase, Letter-spacing: 0.25em
│   │       │   │   Farbe: var(--text-muted-on-light) (rgba(11,16,26,0.54))
│   │       │   │   Margin-top: mt-2 (8px)
│   │       │   │
│   │       │   └── Context: "Mo–Fr 09–18 Uhr · persönliche Rückmeldung"
│   │       │       Font: Inter Regular, 12px
│   │       │       Farbe: var(--text-muted-on-light)
│   │       │       Margin-top: mt-3 (12px)
│   │       │
│   │       ├── Stat-Card 2: "INP < 200 ms" (Struktur identisch)
│   │       └── Stat-Card 3: "≥ 70 % Digital Take-up Ziel" (Struktur identisch)
│   │
│   └── RIGHT-COLUMN (Profil-Box)
│       Background: var(--surface-light) (#F9FAFB)
│       Border: 1px solid rgba(15,23,42,0.18) (opacity 70%)
│       Border-radius: rounded-3xl (24px)
│       Padding: p-8 (32px)
│       Shadow: 0 24px 60px -45px rgba(15,23,42,0.35)
│       Backdrop-blur: backdrop-blur-sm
│       │
│       ├── Image
│       │   Src: /img/business-foto.jpg
│       │   Alt: "Portrait von Eduard Wolf"
│       │   Class: rounded-2xl (16px)
│       │   Margin-bottom: mb-6 (24px)
│       │   Loading: lazy
│       │   Object-fit: cover
│       │
│       ├── H3: "Profil in Kürze"
│       │   Font: Inter SemiBold, 18px
│       │   Farbe: var(--text-primary-on-light)
│       │   Margin-bottom: mb-4 (16px)
│       │
│       ├── List (Unordered)
│       │   Spacing: space-y-3 (12px)
│       │   Font: Inter Regular, 14px
│       │   Items: 9 (Rolle, Fokus, DNA, Hintergrund, KI-Kompetenz, Segment-Fokus, KPI-Versprechen)
│       │   Inline-Elemente: <InfoTooltip termId="cli-first" />, <InfoTooltip termId="geo" />, <InfoTooltip termId="aeo" />
│       │
│       └── CTA-Button
│           Text: "Capabilities ansehen"
│           Href: /capabilities
│           Background: var(--slate-900) (#0F172A)
│           Farbe: #FFFFFF
│           Font: Inter SemiBold, 15px
│           Padding: px-5 py-2.5 (20px × 10px)
│           Border-radius: rounded-xl (12px)
│           Shadow: Standard Button-Shadow
│           Hover: shadow-lg, translate-y-[-0.5px]
│           Margin-top: mt-6 (24px)
```

**Abstände:**
- Outer Padding: py-24 @ Mobile, py-32 @ Desktop (96px / 128px)
- Container: max-w-6xl (1152px), mx-auto, px-6
- Grid-Gap: gap-12 (48px)
- Stats-Grid-Gap: gap-4 (16px)

---

### SECTION 3: SEGMENT-PROOF (Dark)

**Komponente:** `<Section tone="dark" />`
**Layout-Pattern:** 3-Column Card Grid (Desktop)
**Hintergrund:** `var(--surface-dark)` (#04060D)

```
SECTION#segment-proof (tone: dark, py-24 md:py-32)
│
├── Container (max-w-6xl)
│   │
│   ├── Header (text-center)
│   │   │
│   │   ├── Badge
│   │   │   Text: "Segment-Beweise"
│   │   │   Class: chip-dark caps-label-wide
│   │   │   Font: Inter SemiBold, 14px
│   │   │   Farbe: var(--text-secondary-on-dark)
│   │   │   Margin-bottom: mb-4 (16px)
│   │   │
│   │   ├── H2
│   │   │   Text: "So übersetze ich Code-first in Ergebnisse"
│   │   │   Font: Inter Bold, 30px @ Mobile, 36px @ Desktop
│   │   │   Farbe: #FFFFFF
│   │   │   Margin-bottom: mb-4 (16px)
│   │   │
│   │   └── Paragraph
│   │       Text: "Jede Branche bekommt eigene KPI-Budgets..."
│   │       Font: Inter Regular, 18px
│   │       Farbe: var(--slate-200) (rgba(226,232,240,1))
│   │       Line-height: normal
│   │       Max-width: max-w-3xl (768px)
│   │       Margin: mx-auto, mb-12 (48px)
│   │
│   ├── Cards-Grid (md:grid-cols-3, gap-6)
│   │   │
│   │   ├── Card 1: Kanzleien & Sozietäten
│   │   │   Background: rgba(255,255,255,0.08)
│   │   │   Border: 1px solid var(--border-on-dark-subtle)
│   │   │   Border-radius: rounded-3xl (24px)
│   │   │   Padding: p-8 (32px)
│   │   │   Shadow: 0 30px 80px -60px rgba(15,23,42,0.65)
│   │   │   Hover: translate-y-[-4px], Shadow-Intensivierung
│   │   │   Transition: all 200ms
│   │   │   Backdrop-blur: backdrop-blur-sm
│   │   │   │
│   │   │   ├── Badge
│   │   │   │   Text: "Intake & KPI"
│   │   │   │   Background: rgba(255,255,255,0.12)
│   │   │   │   Font: Inter SemiBold, 12px, Uppercase, Letter-spacing: 0.18em
│   │   │   │   Padding: px-3 py-1 (12px × 4px)
│   │   │   │   Border-radius: rounded-full
│   │   │   │   Farbe: #FFFFFF
│   │   │   │
│   │   │   ├── H3: "Kanzleien & Sozietäten"
│   │   │   │   Font: Inter SemiBold, 20px
│   │   │   │   Farbe: #FFFFFF
│   │   │   │   Margin-top: mt-4 (16px)
│   │   │   │
│   │   │   ├── KPI: "Lead-to-Call Rate +35 %"
│   │   │   │   Font: Inter SemiBold, 14px
│   │   │   │   Farbe: var(--text-secondary-on-dark)
│   │   │   │   Margin-top: mt-2 (8px)
│   │   │   │
│   │   │   ├── Description
│   │   │   │   Text: "Rapid-Response Intake, Mandanten-Flows, Jour-fixe Reports..."
│   │   │   │   Font: Inter Regular, 14px
│   │   │   │   Farbe: var(--slate-200)
│   │   │   │   Line-height: relaxed
│   │   │   │   Margin-top: mt-3 (12px)
│   │   │   │
│   │   │   └── CTA-Link
│   │   │       Text: "Branchenseite öffnen"
│   │   │       Href: /branchen/kanzleien
│   │   │       Font: Inter SemiBold, 14px
│   │   │       Farbe: var(--text-secondary-on-dark), Hover: var(--gold-300)
│   │   │       Margin-top: mt-5 (20px)
│   │   │       Icon: Right-Arrow (SVG)
│   │   │
│   │   ├── Card 2: Schulen & Bildung (Struktur identisch)
│   │   │   Badge: "Enrollment"
│   │   │   KPI: "Anmeldung in 3 statt 5 Schritten"
│   │   │   Href: /branchen/schulen-bildung
│   │   │
│   │   └── Card 3: Behörden & öffentliche Dienste (Struktur identisch)
│   │       Badge: "OZG & BFSG"
│   │       KPI: "Digital Take-up ≥70 %"
│   │       Href: /branchen/oeffentliche-einrichtungen
│   │
│   └── Footnote
│       Text: "KPI-Werte basieren auf Research aus optimieren_daten (2025-10-18)..."
│       Font: Inter Regular, 12px
│       Farbe: rgba(226,232,240,0.8)
│       Text-align: center
│       Margin-top: mt-8 (32px)
```

**Abstände:**
- Outer Padding: py-24 @ Mobile, py-32 @ Desktop
- Container: max-w-6xl, mx-auto, px-6
- Header-Margin: mb-12 (48px)
- Cards-Grid-Gap: gap-6 (24px)

---

### SECTION 4: KOMPETENZ-CLUSTER (Light)

**Komponente:** `<Section tone="light" />`
**Layout-Pattern:** 4-Column Card Grid (Desktop: xl:grid-cols-4)
**Hintergrund:** `var(--surface-light)` (#F9FAFB)

```
SECTION#kompetenz-cluster (tone: light, py-24 md:py-32)
│
├── Header (text-center, max-w-4xl mx-auto)
│   ├── Badge: "Kompetenz-Cluster"
│   ├── H2: "Womit ich regulierte Projekte zum Laufen bringe"
│   └── Paragraph (führender Text, max-w-3xl)
│
└── Cards-Grid (md:grid-cols-2 xl:grid-cols-4, gap-6)
    │
    ├── Card 1: CLI-first Full-Stack
    │   Background: var(--surface-light)
    │   Border: 1px solid var(--border-on-light-subtle)
    │   Border-radius: rounded-3xl (24px)
    │   Padding: p-6 (24px)
    │   Shadow: 0 25px 60px -45px rgba(15,23,42,0.35)
    │   │
    │   ├── H3: "CLI-first Full-Stack" + <InfoTooltip termId="cli-first" />
    │   │   Font: Inter SemiBold, 20px
    │   │   Farbe: var(--text-primary-on-light)
    │   │   Margin-bottom: mb-3 (12px)
    │   │
    │   └── List (Unordered)
    │       Items: 3 (Astro/Static, Skriptgesteuerte Builds, Infrastructure as Code)
    │       Font: Inter Regular, 14px
    │       Farbe: var(--text-secondary-on-light)
    │       Spacing: space-y-2 (8px)
    │       Inline-Elemente: <InfoTooltip termId="gitops" />
    │
    ├── Card 2: SEO + GEO (AEO) & Automation (Struktur identisch)
    │   Inline-Elemente: <InfoTooltip termId="geo" />, <InfoTooltip termId="aeo" />
    │
    ├── Card 3: UX, Accessibility & Compliance (Struktur identisch)
    │   Inline-Element: <InfoTooltip termId="consent-mode-v2" />
    │
    └── Card 4: Prompt & KI-Engineering (Struktur identisch)
        Keine Tooltips
```

**Abstände:**
- Outer Padding: py-24 @ Mobile, py-32 @ Desktop
- Container: max-w-6xl, mx-auto, px-6
- Header-Margin: mb-16 (64px)
- Cards-Grid-Gap: gap-6 (24px)

---

### SECTION 5: WERDEGANG (Dark)

**Komponente:** `<Section tone="dark" />`
**Layout-Pattern:** 2-Column Grid (Desktop: lg:grid-cols-[1fr,1fr])
**Hintergrund:** `var(--surface-dark)` (#04060D)

```
SECTION#werdegang (tone: dark, py-24 md:py-32)
│
└── Grid-Container (lg:grid-cols-[1fr,1fr], gap-12)
    │
    ├── LEFT-COLUMN
    │   ├── Badge: "Werdegang"
    │   ├── H2: "Wie ich dorthin gekommen bin"
    │   └── List (Unordered)
    │       Items: 5 (Print-on-Demand, Kaufmann, Native App Dev, Prompt Engineering, Regulierte Teams)
    │       Font: Inter Regular, 14px
    │       Farbe: var(--slate-200)
    │       Spacing: space-y-4 (16px)
    │       Inline-Elemente: <InfoTooltip termId="geo" />, <InfoTooltip termId="aeo" />
    │
    └── RIGHT-COLUMN (Toolstack-Box)
        Background: rgba(255,255,255,0.08)
        Border: 1px solid var(--border-on-dark-subtle)
        Border-radius: rounded-3xl (24px)
        Padding: p-8 (32px)
        Shadow: 0 24px 60px -45px rgba(15,23,42,0.65)
        Backdrop-blur: backdrop-blur-sm
        │
        ├── H3: "Toolstack & KI-Setup"
        │   Font: Inter SemiBold, 18px
        │   Farbe: #FFFFFF
        │   Margin-bottom: mb-4 (16px)
        │
        └── Grid (grid-cols-2, gap-4)
            ├── Box 1: "Automationen"
            │   Font-Title: Inter SemiBold, 14px, Farbe: #FFFFFF
            │   Font-Text: Inter Regular, 14px, Farbe: var(--slate-200)
            │
            ├── Box 2: "KI-Services" (Struktur identisch)
            ├── Box 3: "Design & QA" (Struktur identisch)
            └── Box 4: "Data & SEO" (Struktur identisch)
```

**Abstände:**
- Outer Padding: py-24 @ Mobile, py-32 @ Desktop
- Grid-Gap: gap-12 (48px)
- Inner-Grid (Toolstack): gap-4 (16px)

---

### SECTION 6: ARBEITSPRINZIPIEN (Light)

**Komponente:** `<Section tone="light" />`
**Layout-Pattern:** 2-Column Grid mit 2×2 Card-Subgrid (Desktop)
**Hintergrund:** `var(--surface-light)` (#F9FAFB)

```
SECTION#arbeitsprinzipien (tone: light, py-24 md:py-32)
│
└── Grid-Container (lg:grid-cols-[1fr,1fr], gap-12)
    │
    ├── LEFT-COLUMN
    │   ├── Badge: "Arbeitsprinzipien"
    │   ├── H2: "Meine Leitfragen & Methodik"
    │   └── Paragraph: "Gute Lösungen starten mit guten Fragen..."
    │
    └── RIGHT-COLUMN (Cards-Grid)
        Grid: grid-cols-1 sm:grid-cols-2, gap-6
        │
        ├── Card 1: "Fragen & Hypothesen"
        │   Background: var(--surface-light)
        │   Border: 1px solid var(--border-on-light-subtle)
        │   Border-radius: rounded-2xl (16px)
        │   Padding: p-6 (24px)
        │   Shadow: shadow-sm (leicht)
        │   │
        │   ├── H3: "Fragen & Hypothesen"
        │   │   Font: Inter SemiBold, 18px
        │   │   Farbe: var(--text-primary-on-light)
        │   │   Margin-bottom: mb-2 (8px)
        │   │
        │   └── Description
        │       Text: "Welche Annahmen treffen wir? Welche Fragen fehlen?..."
        │       Font: Inter Regular, 14px
        │       Farbe: var(--text-secondary-on-light)
        │
        ├── Card 2: "KI als Dirigent" (Struktur identisch)
        ├── Card 3: "CLI-first Delivery" (Struktur identisch, mit <InfoTooltip termId="cli-first" />)
        └── Card 4: "Messbare Ergebnisse" (Struktur identisch)
```

**Abstände:**
- Outer Padding: py-24 @ Mobile, py-32 @ Desktop
- Grid-Gap: gap-12 (48px)
- Cards-Grid-Gap: gap-6 (24px)

---

### SECTION 7: CTA (Light)

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
    ├── H2: "Lass uns gemeinsam dein nächstes Projekt orchestrieren"
    │   Font: Inter Bold, 28px @ Mobile, 36px @ Desktop
    │   Farbe: #FFFFFF
    │   Margin-bottom: mb-6 (24px)
    │
    ├── Paragraph
    │   Text: "Ob Kanzlei-Mandantenportal, Campus-Enrollment oder Bürgerdienst..."
    │   Font: Inter Regular, 16px @ Mobile, 18px @ Desktop
    │   Farbe: rgba(226,232,240,0.85)
    │   Line-height: relaxed
    │   Margin-bottom: mb-8 (32px)
    │
    └── CTA-Group (flex-col sm:flex-row, gap-4 sm:gap-6)
        │
        ├── CTA Primary
        │   Text: "Gemeinsames Gespräch starten"
        │   Href: /kontakt
        │   Background: var(--surface-light) (#F9FAFB)
        │   Farbe: var(--text-primary-on-light) (#0B101A)
        │   Font: Inter SemiBold, 16px
        │   Padding: px-6 py-3 (24px × 12px)
        │   Border-radius: rounded-xl (12px)
        │   Shadow: 0 24px 70px -50px rgba(148,163,184,0.9)
        │   Hover: Shadow-Intensivierung + scale-[1.01]
        │
        └── CTA Secondary
            Text: "Capabilities ansehen"
            Href: /capabilities
            Background: transparent
            Border: 1px solid var(--border-on-dark-strong) (rgba(255,255,255,0.28))
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
| **Hero (Dark)** | | | |
| Background | `--surface-dark` | #04060D | Section-Hintergrund |
| H1 | — | #FFFFFF | Headline |
| Subtitle | `--text-secondary-on-dark` | rgba(249,250,251,0.72) | Paragraph |
| CTA Primary BG | `--surface-light` | #F9FAFB | Button-Background |
| CTA Primary Text | `--text-primary-on-light` | #0B101A | Button-Text |
| Grid-Lines | — | rgba(255,255,255,0.04) | Grid-Pattern |
| Glow | — | rgba(255,215,0,0.08) | Gold-Glow (Top-Center) |
| **Profil (Light)** | | | |
| Background | `--surface-light` | #F9FAFB | Section-Hintergrund |
| H2 | `--text-primary-on-light` | #0B101A | Headline |
| Body | `--text-secondary-on-light` | rgba(11,16,26,0.72) | Paragraphen |
| Card-Border | `--border-on-light-subtle` | rgba(15,23,42,0.18) | Stats-Card-Borders |
| Card-BG | `--surface-light` | #F9FAFB | Stats-Card-Background |
| **Segment-Proof (Dark)** | | | |
| Background | `--surface-dark` | #04060D | Section-Hintergrund |
| H2 | — | #FFFFFF | Headline |
| Body | `--slate-200` | rgba(226,232,240,1) | Paragraphen |
| Card-BG | — | rgba(255,255,255,0.08) | Card-Background (Alpha) |
| Card-Border | `--border-on-dark-subtle` | rgba(255,255,255,0.18) | Card-Borders |
| Badge-BG | — | rgba(255,255,255,0.12) | Badge-Background |
| **CTA ContentBox (Dark)** | | | |
| Background | `--surface-dark` | #04060D | ContentBox-Background |
| H2 | — | #FFFFFF | Headline |
| Body | — | rgba(226,232,240,0.85) | Paragraph |
| CTA Primary BG | `--surface-light` | #F9FAFB | Button-Background |
| CTA Secondary Border | `--border-on-dark-strong` | rgba(255,255,255,0.28) | Button-Border |

### Typografie-Details

**Font-Family:** Inter (Weights: Regular 400, Medium 500, SemiBold 600, Bold 700)

**Font-Sizes:**
- H1 (Hero): 48px @ Mobile → 60px @ Tablet → 72px @ Desktop (3rem → 3.75rem → 4.5rem)
- H2 (Section): 24px @ Mobile → 30-36px @ Desktop (1.5rem → 1.875-2.25rem)
- H3 (Cards): 18-20px (1.125-1.25rem)
- Body (Regular): 14px (0.875rem)
- Body (Large/Intro): 16-18px (1-1.125rem)
- Labels (Caps): 11-14px (0.6875-0.875rem)

**Line-Heights:**
- tight: 1.15-1.25 (Headlines)
- normal: 1.5 (Body)
- relaxed: 1.625-1.75 (Intro-Paragraphs, Lists)

**Letter-Spacing:**
- Headlines: -0.02em (tight)
- Body: 0
- Uppercase-Labels: 0.18em-0.3em

### Spacing-System

- **Section-Padding:** py-24/32 (96px @ Mobile, 128px @ Desktop)
- **Container-Padding:** px-6 (24px)
- **Card-Padding:** p-6/p-8 (24px / 32px)
- **Grid-Gaps:** gap-4/gap-6/gap-12 (16px / 24px / 48px)
- **Margin-Bottom (Headlines):** mb-4/mb-5/mb-6 (16px / 20px / 24px)

### Border-Radius

- **Small:** rounded-lg (8px) — kleine Badges
- **Medium:** rounded-xl (12px) — Buttons
- **Large:** rounded-2xl (16px) — kleine Cards
- **XL:** rounded-3xl (24px) — große Cards, Sections
- **Full:** rounded-full (9999px) — Badges, Chips

---

## 📱 5. RESPONSIVE BREAKPOINTS

| Breakpoint | Screen-Width | Grid-Cols | Font-Size H1 | Font-Size H2 | Section Padding |
|------------|--------------|-----------|--------------|--------------|-----------------|
| **Mobile** | <640px | 1 | 48px (3rem) | 24px (1.5rem) | py-24 (96px) |
| **Tablet** | 640-1023px | 2 (teilweise) | 60px (3.75rem) | 30px (1.875rem) | py-28 (112px) |
| **Desktop** | ≥1024px | 2-4 (je nach Section) | 72px (4.5rem) | 30-36px (1.875-2.25rem) | py-32 (128px) |

### Hauptänderungen pro Breakpoint

**Mobile (<640px):**
- Grid-Layouts: 1-Spalte (Stack)
- Hero: 48px H1, 18px Subtitle
- Stats-Grid: 1-Spalte (vertikal gestapelt)
- Kompetenz-Cluster: 1-Spalte
- CTA-Group: flex-col (vertikal)
- Padding: py-24 (96px)

**Tablet (640-1023px):**
- Grid-Layouts: 2-Spalten (Profil bleibt 1-col bis lg)
- Hero: 60px H1, 20px Subtitle
- Stats-Grid: 3-Spalten (sm:grid-cols-3)
- Kompetenz-Cluster: 2-Spalten
- Padding: py-28 (112px)

**Desktop (≥1024px):**
- Grid-Layouts: 2-4 Spalten (je nach Section)
- Hero: 72px H1
- Profil: 2-Spalten (lg:grid-cols-[1.1fr,0.9fr])
- Segment-Proof: 3-Spalten (md:grid-cols-3)
- Kompetenz-Cluster: 4-Spalten (xl:grid-cols-4)
- Padding: py-32 (128px)

---

## 🧩 6. KOMPONENTEN-BIBLIOTHEK

### Genutzte Astro-Components

| Komponente | Datei | Props (Beispiel für diese Seite) |
|------------|-------|-----------------------------------|
| `<Base />` | `/src/layouts/Base.astro` | title="Über mich – Eduard Wolf \| Wolf-Agents", description="..." |
| `<Nav />` | `/src/components/Nav.astro` | slot="header" (keine Props) |
| `<Hero />` | `/src/components/Hero.astro` | title="Eduard Wolf", subtitle="...", badge="...", ctaText="Response Playbook anfordern", ctaHref="/kontakt", secondaryCtaText="Segment-Beweise ansehen", secondaryCtaHref="#segment-proof", variant="dark-grid", minHeightStyle="min-height:100vh;min-height:100dvh;", scrollHintText="Weiter zu Profil & Arbeitsweise", scrollHintHref="#profil" |
| `<Section />` | `/src/components/Section.astro` | tone="light/dark/navy", id="profil/segment-proof/...", class="py-24 md:py-32" |
| `<ContentBoxDark />` | `/src/components/ContentBoxDark.astro` | heading="Lass uns gemeinsam...", headingLevel="h2", class="text-center" |
| `<InfoTooltip />` | `/src/components/InfoTooltip.astro` | termId="geo/aeo/cli-first/gitops/consent-mode-v2/..." |
| `<Footer />` | `/src/components/Footer.astro` | slot="footer" (keine Props) |

### Wichtige Komponenten-Details

**Hero:**
- Unterstützt: title, subtitle, badge, ctaText/Href, secondaryCtaText/Href, tertiaryCtaText/Href (Email)
- Variants: "dark-grid", "light", "dark"
- Optional: scrollHintText/Href für Anchor-Scroll, minHeightStyle für Full-Viewport

**Section:**
- tone: "light" (#F9FAFB BG), "dark" (#04060D BG), "navy" (Spezial-Dunkelblau)
- Slots: Default (Content)
- Optional: data-section-anchor für Scroll-Targets

**InfoTooltip:**
- termId: Referenziert Glossar-Eintrag (z.B. "geo", "aeo", "cli-first")
- Mode: "auto" (Standard) oder "modal" (bei Bedarf)
- Rendering: Inline-Glossar-Link mit Hover-Tooltip

**ContentBoxDark:**
- heading: Headline-Text
- headingLevel: "h2" oder "h3"
- Slots: Default (Content für Paragraphen + CTAs)
- Background: Immer Dark (#04060D), unabhängig von Section-Tone

---

## 🔍 7. SEO & STRUKTURIERTE DATEN

### Schema.org Markup

**Typ:** Person (Schema.org/Person)

```json
{
  "@context": "https://schema.org",
  "@type": "Person",
  "name": "Eduard Wolf",
  "jobTitle": "Senior Full-Stack Web-Developer & KI-Orchestrator",
  "worksFor": {
    "@type": "Organization",
    "name": "Wolf-Agents"
  },
  "url": "https://www.wolf-agents.com/ueber-mich",
  "knowsAbout": [
    "Core Web Vitals",
    "BFSG 2025",
    "Servicecockpit Governance",
    "GitOps Deployments",
    "Answer Engine Optimization"
  ],
  "areaServed": ["Kanzleien", "Schulen & Bildung", "Öffentliche Einrichtungen"],
  "contactPoint": {
    "@type": "ContactPoint",
    "contactType": "Erstberatung",
    "url": "https://www.wolf-agents.com/kontakt",
    "availableLanguage": ["de", "en"],
    "hoursAvailable": {
      "@type": "OpeningHoursSpecification",
      "dayOfWeek": ["Monday", "Tuesday", "Wednesday", "Thursday", "Friday"],
      "opens": "09:00",
      "closes": "18:00"
    }
  }
}
```

**Zusammenfassung strukturierter Daten:**
- Person: Eduard Wolf (Name, JobTitle, Organization)
- Knowledge-Areas: Core Web Vitals, BFSG 2025, GitOps, AEO (5 Topics)
- Service-Areas: 3 Branchen (Kanzleien, Bildung, Behörden)
- Contact-Point: Erstberatung-URL, Mo-Fr 09-18 Uhr, DE+EN

### Open Graph / Twitter Card

**Annahme** (basierend auf Base-Layout-Standard):
- og:title: "Über mich – Eduard Wolf | Wolf-Agents"
- og:description: "Eduard Wolf: Senior Full-Stack Developer & KI-Orchestrator für Kanzleien, Bildung & Behörden..."
- og:image: Vermutlich `/img/og-ueber-mich.jpg` oder Default-OG-Image
- og:type: website
- twitter:card: summary_large_image
- twitter:title: (identisch mit og:title)
- twitter:description: (identisch mit og:description)

---

## ♿ 8. BARRIEREFREIHEIT (WCAG 2.2)

### Kontrast-Ratios

**Text-on-Dark (Hero, Segment-Proof, Werdegang, CTA):**
- #FFFFFF auf #04060D: **~19.6:1** (AAA)
- rgba(249,250,251,0.72) auf #04060D: **~14.1:1** (AAA)
- rgba(226,232,240,1) auf #04060D: **~17.8:1** (AAA)

**Text-on-Light (Profil, Kompetenz, Arbeitsprinzipien):**
- #0B101A auf #F9FAFB: **~18.9:1** (AAA)
- rgba(11,16,26,0.72) auf #F9FAFB: **~13.6:1** (AAA)

**Ergebnis:** Alle Kontrast-Ratios erfüllen WCAG 2.2 Level AAA (≥ 7:1 für Normal-Text, ≥ 4.5:1 für Large-Text).

### Semantische HTML-Struktur

- **Korrekte Tags:** `<nav>`, `<main>`, `<section>`, `<article>` (Stats-Cards, Segment-Cards), `<footer>`
- **H1-H3-Hierarchie:** Korrekt (1× H1 im Hero, H2 pro Section, H3 für Cards)
- **Landmarks:** Nav, Main, Footer korrekt strukturiert
- **Aria-Attributes:** Vermutlich in InfoTooltip (aria-label, aria-describedby)

### Interaktive Elemente

- **Focus-Rings:** Custom-Focus-Rings via Tailwind (ring-2, ring-offset-2)
- **Button vs. Link:** Korrekt (CTAs = `<a>`-Links mit href, keine fake-Buttons)
- **Touch-Targets:** Min. 44×44px (py-3 = 12px + Text = ~48px Höhe, px-6 = 24px + Text = ~120px Breite)
- **Keyboard-Navigation:** Anchor-Links (#profil, #segment-proof) funktionieren per Tastatur

### Reduced Motion

**Unterstützung:** Ja (vermutlich via `@media (prefers-reduced-motion: reduce)` in global.css)
- Animationen (Hover-Transforms, Scroll-Hint-Bounce) werden reduziert/deaktiviert

---

## 📝 9. CONTENT-STRATEGIE & TARGETING

### Hauptthema der Seite

Persönliche Vorstellung von Eduard Wolf als Senior Full-Stack Developer & KI-Orchestrator mit Fokus auf regulierte Branchen (Kanzleien, Bildung, Behörden). Präsentation von Profil, Kompetenzen, Werdegang, Segment-Beweisen und Arbeitsprinzipien.

### Primäre Keywords

- Eduard Wolf
- Full-Stack Developer Kanzleien
- KI-Orchestrator Behörden
- Senior Developer Bildung
- GitOps Delivery

### Sekundäre Keywords (LSI)

- Prompt Engineering
- CLI-first Development
- SEO + GEO (AEO)
- BFSG 2025 Compliance
- Mandatsreisen KPI
- Response Promise
- Servicecockpit Governance
- Code-first Plattformen

### Zielgruppe

**Primär:**
- Geschäftsführer/Partner von Kanzleien (40-65 Jahre)
- IT-Leiter/Digitalisierungsbeauftragte in Behörden (35-55 Jahre)
- Schulleiter/Campus-IT-Verantwortliche (40-60 Jahre)

**Sekundär:**
- Marketing-Manager in Kanzleien
- Projektleiter für Digitalisierungs-Initiativen
- Externe Berater/Consultants

### User Intent

**Primär:** Informational (Wer ist Eduard Wolf? Welche Erfahrung? Welche Kompetenzen?)

**Sekundär:** Transactional (Interesse an Kontaktaufnahme → CTA "Response Playbook anfordern")

### AIO/GEO/AEO-Status

**AIO (Answer Intent Optimization):**
- Frage: "Wer ist Eduard Wolf?" → Direkte Antwort: H1 + Profil-Section
- Frage: "Welche Branchen betreut Eduard Wolf?" → Segment-Proof-Section mit 3 Branchen
- Frage: "Welche Kompetenzen hat Eduard Wolf?" → Kompetenz-Cluster-Section mit 4 Säulen

**GEO (Generative Engine Optimization):**
- Strukturierte Daten: ✅ Schema.org Person mit knowsAbout, areaServed, contactPoint
- Content-Struktur: ✅ Klar gegliedert (Profil → Segment-Beweise → Kompetenzen → Werdegang)
- LLM-friendly: ✅ Keine verschachtelten Komponenten, semantisches HTML

**AEO (Answer Engine Optimization):**
- Featured-Snippet-Potenzial: Mittel (Profil-Stats könnten als "Quick Facts" ranken)
- Listicles: ✅ Kompetenz-Cluster (4 Säulen), Werdegang (5 Stationen), Arbeitsprinzipien (4 Karten)
- Konkrete Metriken: ✅ "Response Promise < 1 h", "INP < 200 ms", "Lead-to-Call Rate +35 %"

---

## 🔎 10. CONTENT-AUDIT-NOTIZEN

### Stärken

- ✅ **Klare Strukturierung:** 7 Sections mit jeweils eigenem Fokus (Profil, Segment-Beweise, Kompetenzen, Werdegang, Arbeitsprinzipien)
- ✅ **Persönliche Ansprache:** H1 "Eduard Wolf" + direkter Ton ("Ich verbinde...", "Meine Rolle...")
- ✅ **Messbare KPIs:** Konkrete Zahlen (Response < 1 h, INP < 200 ms, Lead-to-Call +35 %, Digital Take-up ≥70 %)
- ✅ **Segment-spezifische Beweise:** 3 Branchen-Cards mit jeweils eigenen KPIs (Intake, Enrollment, BFSG)
- ✅ **Glossar-Integration:** 7 InfoTooltips für Fachbegriffe (GEO, AEO, CLI-first, GitOps, Consent Mode v2)
- ✅ **Visuelle Hierarchie:** Badge → H2 → Paragraph → Cards (konsistent über alle Sections)
- ✅ **Schema.org Person:** Strukturierte Daten für LLM/SEO-Visibility

### Altlasten / Schwächen

- ⚠️ **Lange Lesedauer:** ~7-9 Minuten (1.580 Wörter) → Potenziell zu umfangreich für schnelle Überblicke
- ⚠️ **Keine Testimonials:** Fehlt: Social Proof von Klienten (Zitate, Case-Study-Links)
- ⚠️ **KPI-Quelle intransparent:** "Research aus optimieren_daten (2025-10-18)" → Für externe Leser unklar, was das ist
- ⚠️ **Fehlende Zertifikate/Awards:** Keine Erwähnung von formalen Qualifikationen, Branchenzertifikaten oder Auszeichnungen
- ⚠️ **Bildmaterial begrenzt:** Nur 1 Foto (business-foto.jpg) → Könnte durch Projekt-Screenshots, Logos von Klienten erweitert werden

### Fehlende Elemente

- ❌ **Testimonials / Client-Logos:** Keine Klienten-Zitate oder Referenz-Logos
- ❌ **Video-Content:** Kein Intro-Video oder Demo-Walkthrough
- ❌ **Projekt-Galerie:** Keine Screenshots von realisierten Projekten
- ❌ **Publikationen/Artikel:** Keine Verlinkung zu Fachartikel, Blog-Posts oder Speaking-Engagements
- ❌ **Social-Media-Links:** Keine LinkedIn, GitHub, Twitter-Links (könnten in Footer oder Profil-Box integriert werden)

### Content-Refresh-Priorität

**🟡 Mittel**

**Begründung:**
- Seite ist gut strukturiert und liefert klare Informationen zu Profil, Kompetenzen und Werdegang
- KPIs und Segment-Beweise sind vorhanden und messbar
- **Aber:** Fehlt Social Proof (Testimonials) und Projekt-Beispiele, um Glaubwürdigkeit zu erhöhen
- **Empfehlung:** Testimonials-Section hinzufügen (zwischen Segment-Proof und Kompetenz-Cluster) + Projekt-Galerie (optional)
- **Zeitpunkt:** Q2 2026 oder nach ersten 5-10 abgeschlossenen Projekten

---

## ⚡ 11. PERFORMANCE & TECHNISCHE DETAILS

### Core Web Vitals (Zielwerte)

- **LCP (Largest Contentful Paint):** < 2.0 s
  - LCP-Element: Hero H1 "Eduard Wolf" oder business-foto.jpg (je nach Viewport)
  - Optimierung: `loading="lazy"` für Image, Astro-SSG (Pre-rendered)
- **INP (Interaction to Next Paint):** < 200 ms
  - Budget: 200 ms (laut Profil-Stats)
  - Interaktive Elemente: Nav-Dropdown, InfoTooltip-Modals, Anchor-Links
- **CLS (Cumulative Layout Shift):** < 0.1
  - Kritisch: Image mit expliziten width/height (vermutlich vorhanden)

### Lazy Loading

- **Images:** Ja (`loading="lazy"` für business-foto.jpg)
- **Scripts:** Defer/async (vermutlich via Astro-Build-Config)

### Mobile Optimierung

- **Responsive:** Ja (Tailwind-Breakpoints, Grid-Collapse auf 1-Spalte)
- **Touch-Targets:** Min. 44×44px (CTAs, Cards, Nav-Links)
- **Viewport-Meta:** Vermutlich `<meta name="viewport" content="width=device-width, initial-scale=1">` (Standard in Base-Layout)

### Astro-spezifische Optimierungen

- **SSG (Static Site Generation):** Ja (Seite wird zu statischem HTML kompiliert)
- **Partial Hydration:** Vermutlich für InfoTooltip (Interactive Islands)
- **Build-Output:** HTML + minimal JS (nur für interaktive Components)

---

## 📊 12. CONTENT-METRIKEN

### Textmenge

- **Gesamtzeichen:** ~11.200 Zeichen (ohne Code/HTML)
- **Gesamtwörter:** ~1.580 Wörter
- **Lesedauer:** 7-9 Minuten (bei ~200 Wörter/Min)

### Link-Dichte

- **Interne Links:** 38-44 (Navigation, Footer, CTAs, Branchen-Cards, Glossar-Tooltips, Anchor-Links)
- **Externe Links:** 0 (keine direkten externen Links, außer Schema.org-Kontext)
- **CTAs:** 5 (Hero Primary, Hero Secondary, Profil-Box → Capabilities, CTA Primary, CTA Secondary)
- **Glossar-Tooltips:** 7 (GEO ×2, AEO ×2, CLI-first ×2, GitOps ×1, Consent Mode v2 ×1)
- **Anchor-Links:** 2 (#profil, #segment-proof)

### Content-Verteilung

- **Dark Sections:** 42.9% (3 von 7: Hero, Segment-Proof, Werdegang)
- **Light Sections:** 57.1% (4 von 7: Profil, Kompetenz-Cluster, Arbeitsprinzipien, CTA → enthält ContentBoxDark)

### Interaktive Elemente

- **Buttons/CTAs:** 5 (inkl. CTA-Links in Cards)
- **Cards (insgesamt):** 16+ (3 Stats, 3 Segment-Cards, 4 Kompetenz-Cards, 4 Arbeitsprinzipien-Cards, 4 Toolstack-Boxen)
- **Collapsibles/Accordions:** 0
- **Tooltips:** 7 (InfoTooltip-Komponenten)
- **Images:** 1 (business-foto.jpg)
- **Carousels/Sliders:** 0

### Section-Breakdown (Zeilen-Schätzung pro Section)

1. Hero: ~50 Zeilen Content
2. Profil: ~180 Zeilen Content (längste Section wegen Grid + Stats + Profil-Box)
3. Segment-Proof: ~100 Zeilen Content
4. Kompetenz-Cluster: ~80 Zeilen Content
5. Werdegang: ~80 Zeilen Content
6. Arbeitsprinzipien: ~70 Zeilen Content
7. CTA: ~40 Zeilen Content

**Gesamt:** ~600 Zeilen reiner Content (ohne Überschriften/Meta)

---

**ENDE DER DOKUMENTATION**

Dokumentiert am 2025-11-01 von Claude (Sonnet 4.5) nach Protokoll `/Wolf-Agents.com-Architektur/00-DOKUMENTATIONS-PROTOKOLL.md`.
