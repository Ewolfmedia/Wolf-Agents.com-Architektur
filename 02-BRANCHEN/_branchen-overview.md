# BRANCHEN-ÜBERSICHT - Content & Struktur-Architektur

**Dokumentiert am:** 2025-10-30
**Status:** IST-Zustand (keine Optimierungsvorschläge)

---

## 📊 META-INFORMATIONEN

| Attribut | Wert |
|----------|------|
| **URL** | https://www.wolf-agents.com/branchen/ |
| **Datei** | `/src/pages/branchen/index.astro` |
| **Title Tag** | "Branchenlösungen für regulierte & öffentliche Teams \| Wolf-Agents" |
| **Meta Description** | "Branchenspezifische Websites & WebApps für Kanzleien, Bildung, Behörden, Versicherungen, Industrie und Notariate. Intake-Flows, Servicecockpits und Compliance-Module inklusive." |
| **Canonical URL** | https://www.wolf-agents.com/branchen |
| **Noindex** | Nein |
| **Geschätzte Zeichenanzahl** | ~8.200 Zeichen (ohne Code/HTML) |
| **Geschätzte Wortanzahl** | ~1.150 Wörter |
| **Geschätzte Lesedauer** | 5-6 Minuten |
| **Anzahl Sections** | 6 Hauptbereiche (Hero, Segments, Modules, Glossary, CTA, Footer) |
| **Anzahl H1** | 1 |
| **Anzahl H2** | 5 |
| **Anzahl H3** | 12+ |

---

## 🔗 VERLINKUNGSSTRUKTUR

### Interne Links (ausgehend)
- Navigation: `/` (Startseite)
- Navigation: `/leistungen/` (Dropdown-Menü)
- Navigation: `/wissen/` (Dropdown-Menü)
- Hero CTA Primary: `/kontakt`
- Hero CTA Tertiary: `/leistungen`
- Segment Branch-Cards (9x):
  - `/branchen/kanzleien`
  - `/branchen/steuerberater`
  - `/branchen/wirtschaftspruefer`
  - `/branchen/notare`
  - `/branchen/versicherungen`
  - `/branchen/oeffentliche-einrichtungen`
  - `/branchen/schulen-bildung`
  - `/branchen/medizin`
  - `/branchen/industrie-b2b`
- Glossary Section: `/wissen/glossar`, `/wissen`, `/wissen#playbooks`
- CTA Section: `/kontakt`, `/capabilities`
- Footer: Diverse Links zu allen Seiten

**Gesamtanzahl interne Links:** ~45-50 (inkl. Navigation und Footer)

### Externe Links
Keine direkten externen Links (nur mailto in Navigation)

---

## 🏗️ LAYOUT & SEMANTISCHE STRUKTUR

---

### NAVIGATION (Sticky Header)

**Komponente:** `<Nav />`
**Datei:** `/src/components/Nav.astro`
**Hintergrund:** Transparent mit Blur-Effekt

*(Gleiche Struktur wie Startseite - siehe startseite.md)*

---

### SECTION 1: HERO (Fullscreen Dark Grid)

**Komponente:** `<Hero variant="dark-grid" />`
**Layout-Pattern:** Hero Dark Grid (100vh Fullscreen)
**Datei:** `/src/components/Hero.astro`

**Hintergrund:**
- Grundfarbe: `var(--brand-primary-900)` (#04060D - sehr dunkles Navy)
- Gitter-Pattern: `linear-gradient(rgba(255, 255, 255, 0.03) 1px, transparent 1px)` horizontal + vertikal, 50px × 50px Grid
- Background-size: 50px 50px

**Semantik & Content:**

```
SECTION (Hero, min-height: 100vh / 100dvh)
│
├── H1 (Hauptüberschrift)
│   Text: "Branchenlösungen für regulierte & öffentliche Teams"
│   Font: Inter ExtraBold, 4.5rem (72px) @ Desktop, 3rem (48px) @ Tablet, 2.25rem (36px) @ Mobile
│   Farbe: `var(--text-primary-on-dark)` (#F9FAFB)
│   Line-height: 1.15 (tight)
│   Letter-spacing: -0.02em
│   Max-width: 1200px
│
├── Paragraph (Hero-Subtitle)
│   Text: "Wir entwickeln Websites, WebApps und Servicecockpits, die Mandate, Einschreibungen und Bürgerdienste schneller zum Ziel führen – inklusive Compliance, Automationen und messbaren KPIs."
│   Font: Inter Regular, 1.25rem (20px) @ Desktop, 1.125rem (18px) @ Mobile
│   Farbe: `var(--text-secondary-on-dark)` (rgba(249, 250, 251, 0.72))
│   Line-height: 1.75 (loose)
│   Max-width: 720px
│   Margin-top: 1.5rem (24px)
│
└── CTA-Gruppe (Button-Cluster)
    Margin-top: 2.5rem (40px)
    │
    ├── Button Primary
    │   Label: "Kontakt aufnehmen"
    │   Href: /kontakt
    │   Variant: btn-primary-light
    │   Background: linear-gradient(135deg, #FFFFFF 0%, #E5E7EB 100%)
    │   Farbe: #0F172A (dark navy text)
    │   Font: Inter SemiBold, 16px
    │   Padding: px-6 py-3 (24px/12px)
    │   Border-radius: 12px (rounded-xl)
    │   Border: 2px solid #D1D5DB
    │   Shadow: 0 0 0 1px rgba(255,255,255,0.15), 0 8px 25px -8px rgba(0,0,0,0.12)
    │   Hover: translateY(-3px), background to lighter gradient, silver glow
    │
    └── Tertiary Button
        Label: "Leistungen entdecken"
        Href: /leistungen
        Font: Inter SemiBold, 15px
        Farbe: rgba(249,250,251,0.8)
        Text-decoration: underline
        Underline-offset: 4px
        Hover: color to white, text-glow
```

**Abstände & Layout:**
- Container: max-width 1280px, mx-auto, px-6 @ Mobile, px-12 @ Desktop
- Vertical Padding: py-20 (80px) @ Mobile, py-32 (128px) @ Desktop
- Min-Height: `min-height: 100vh; min-height: 100dvh;`
- Flexbox: flex-col, items-center, justify-center, text-center

---

### SECTION 2: SEGMENTS (Light Surface - Branchen-Karten)

**Komponente:** `<Section tone="light" id="segments" />`
**Layout-Pattern:** Header + Dark ContentBox + 3-Column Branch Grid
**Hintergrund:** `var(--surface-light)` (#F9FAFB)

**Semantik & Content:**

```
SECTION#segments (tone: light, padding: py-16 md:py-20)
│
├── Container (max-width: 1280px, mx-auto, px-6)
│   │
│   ├── Header-Bereich
│   │   Max-width: 768px
│   │   Margin-bottom: 48px (mb-12)
│   │   │
│   │   ├── Badge
│   │   │   Text: "Segment-Übersicht"
│   │   │   Klasse: chip-light caps-label-wide
│   │   │   Font: Inter SemiBold, 12px, uppercase, tracking: 0.26em
│   │   │   Farbe: `var(--text-on-light-primary)` (#0B101A)
│   │   │   Background: `bg-on-light-subtle` (rgba(226,232,240,0.5))
│   │   │   Padding: px-3 py-1, rounded-full
│   │   │
│   │   ├── H2
│   │   │   Text: "Lösungen für 3 Segmente – maßgeschneidert"
│   │   │   Font: Inter Bold, 1.875rem (30px) @ Mobile, 2.25rem (36px) @ Desktop
│   │   │   Farbe: `var(--text-on-light-primary)` (#0B101A)
│   │   │   Line-height: tight (1.25)
│   │   │   Margin-top: 16px (mt-4)
│   │   │   Note: "3 Segmente" wird dynamisch berechnet aus Collection
│   │   │
│   │   └── Paragraph
│   │       Text: "Jede Branchenlösung kombiniert Content, UX, Automationen und Governance-Bausteine. Wir adaptieren Module, Datenmodelle und Journeys auf Ihre Teams und Compliance-Anforderungen."
│   │       Font: Inter Regular, 16px @ Mobile, 18px @ Desktop
│   │       Farbe: `var(--text-on-light-secondary)` (#4B5563)
│   │       Line-height: relaxed (1.75)
│   │       Margin-top: 16px
│   │
│   ├── ContentBoxDark (Warum branchenspezifisch?)
│   │   Komponente: <ContentBoxDark>
│   │   Heading: "Warum branchenspezifisch?"
│   │   HeadingLevel: h3
│   │   Background: `var(--brand-primary-900)` (#04060D)
│   │   Border: 1px solid `var(--border-subtle-dark)` (rgba(148,163,184,0.18))
│   │   Border-radius: 24px (rounded-3xl)
│   │   Padding: px-8 py-8 @ Mobile, px-10 py-10 @ Desktop
│   │   Shadow: `var(--shadow-premium)` (3-layer shadow)
│   │   Margin-bottom: 48px (mb-12)
│   │   │
│   │   ├── H3
│   │   │   Text: "Warum branchenspezifisch?"
│   │   │   Font: Inter Bold, 1.25rem (20px)
│   │   │   Farbe: white (#FFFFFF)
│   │   │   Margin-bottom: 16px
│   │   │
│   │   └── UL (3 Checkmark Items)
│   │       Space-y: 16px (gap zwischen Items)
│   │       │
│   │       ├── LI 1
│   │       │   Layout: flex items-start gap-3
│   │       │   │
│   │       │   ├── Icon-Container
│   │       │   │   Size: 32px × 32px (h-8 w-8)
│   │       │   │   Background: `bg-white-alpha-12` (rgba(255,255,255,0.12))
│   │       │   │   Border-radius: 12px (rounded-xl)
│   │       │   │   Ring: 1px rgba(255,255,255,0.2)
│   │       │   │   │
│   │       │   │   └── SVG Checkmark
│   │       │   │       Size: 16px × 16px
│   │       │   │       Stroke: currentColor (slate-200)
│   │       │   │       Path: "M5 13l4 4L19 7"
│   │       │   │
│   │       │   └── Text
│   │       │       Font: Inter Regular, 14px
│   │       │       Farbe: rgba(226,232,240,0.9) - slate-200/90
│   │       │       Line-height: relaxed
│   │       │       │
│   │       │       ├── <strong> "Compliance by Design:"
│   │       │       │   Farbe: white
│   │       │       │
│   │       │       └── Plain Text: " DSGVO, BFSG, Barrierefreiheit und branchenspezifische Vorgaben bereits in Komponenten integriert"
│   │       │
│   │       ├── LI 2
│   │       │   [Gleiche Struktur]
│   │       │   Strong: "Voroptimierte User Journeys:"
│   │       │   Text: " Von Erstinformation über Intake bis Servicecockpit – basierend auf bewährten Prozessen Ihrer Branche"
│   │       │
│   │       └── LI 3
│   │           [Gleiche Struktur]
│   │           Strong: "Messbare KPIs:"
│   │           Text: " Completion Rates, Digital Take-up, Time-to-Resolution und weitere Metriken je nach Branchenziel"
│   │
│   └── Branch-Cards Grid
│       Display: grid
│       Grid-cols: 1 @ Mobile, 2 @ Tablet (md:), 3 @ Desktop (xl:)
│       Gap: 24px (gap-6)
│       │
│       ├── Card 1: Kanzleien
│       │   Component: <a> (Link-Card)
│       │   Href: /branchen/kanzleien
│       │   Background: white (#FFFFFF)
│       │   Border: 1px solid #D1D5DB (slate-300)
│       │   Border-radius: 16px (rounded-2xl)
│       │   Padding: 24px (p-6)
│       │   Shadow: `var(--shadow-sm)` (0 1px 2px rgba(0,0,0,0.05))
│       │   Hover: translateY(-1px), shadow-xl
│       │   Transition: all 300ms cubic-bezier(0.4,0,0.2,1)
│       │   │
│       │   ├── Label
│       │   │   Text: "Branche"
│       │   │   Font: Inter SemiBold, 12px, uppercase, tracking: 0.32em
│       │   │   Farbe: `var(--text-on-light-muted)` (#6B7280)
│       │   │
│       │   ├── H3
│       │   │   Text: "Kanzleien & Boutiquen"
│       │   │   Font: Inter SemiBold, 18px (1.125rem)
│       │   │   Farbe: `var(--text-on-light-primary)` (#0B101A)
│       │   │   Line-height: tight
│       │   │   Margin-top: 12px (mt-3)
│       │   │   Hover: color unchanged (group-hover)
│       │   │
│       │   ├── Description
│       │   │   Text: "Wir verbinden Geo-optimierte Inhalte, Intake-Flows und Governance, damit wirtschafts- und streitige Kanzleien schneller zu qualifizierten Mandaten kommen."
│       │   │   Font: Inter Regular, 14px
│       │   │   Farbe: `var(--text-on-light-secondary)` (#4B5563)
│       │   │   Line-height: relaxed
│       │   │   Margin-top: 8px (mt-2)
│       │   │
│       │   ├── KPI Badge Group
│       │   │   Display: inline-flex items-center gap-2
│       │   │   Margin-top: 16px (mt-4)
│       │   │   │
│       │   │   ├── Label
│       │   │   │   Text: "Lead-to-Call Rate"
│       │   │   │   Font: Inter SemiBold, 12px, uppercase, tracking: 0.2em
│       │   │   │   Farbe: `var(--text-on-light-primary)`
│       │   │   │
│       │   │   └── Value Badge
│       │   │       Text: "+35 %"
│       │   │       Background: `bg-white-alpha-10` (rgba(255,255,255,0.1))
│       │   │       Border: 1px solid `border-on-light-subtle`
│       │   │       Padding: px-2 py-0.5
│       │   │       Border-radius: 9999px (rounded-full)
│       │   │       Font: Inter SemiBold, 12px
│       │   │       Farbe: `var(--text-on-light-primary)`
│       │   │
│       │   └── Link-Text mit Icon
│       │       Text: "Zur Detailseite"
│       │       Font: Inter SemiBold, 14px
│       │       Farbe: `var(--text-on-light-primary)`
│       │       Display: inline-flex items-center gap-2
│       │       Margin-top: 16px (mt-4)
│       │       │
│       │       └── Arrow-Icon (SVG)
│       │           Size: 16px × 16px
│       │           Path: "M17 8l4 4m0 0l-4 4m4-4H7"
│       │           Transition: gap increases on hover (gap-3)
│       │
│       ├── Card 2: Steuerberater
│       │   [Gleiche Struktur wie Card 1]
│       │   Title: "Steuerberater & Lohnsteuerhilfe"
│       │   Deck: "Wir kombinieren GEO-Sichtbarkeit, Mandantenportale und Automationen, damit Steuerkanzleien Anfragen priorisieren und Backoffice-Zeit sparen."
│       │   KPI Label: "Telefonaufwand"
│       │   KPI Value: "−30 %"
│       │
│       ├── Card 3: Wirtschaftsprüfer
│       │   [Gleiche Struktur]
│       │
│       ├── Card 4: Notare
│       │   [Gleiche Struktur]
│       │
│       ├── Card 5: Versicherungen
│       │   [Gleiche Struktur]
│       │
│       ├── Card 6: Öffentliche Einrichtungen
│       │   [Gleiche Struktur]
│       │   Title: "Öffentliche Einrichtungen & Bildungsträger"
│       │   KPI Label: "Completion Rate"
│       │   KPI Value: "≥ 70 %"
│       │
│       ├── Card 7: Schulen & Bildung
│       │   [Gleiche Struktur]
│       │   KPI Label: "Anmeldeprozess"
│       │   KPI Value: "3 Schritte"
│       │
│       ├── Card 8: Medizin
│       │   [Gleiche Struktur]
│       │
│       └── Card 9: Industrie & B2B
│           [Gleiche Struktur]
```

**Abstände & Layout:**
- Section Padding: py-16 (64px) @ Mobile, py-20 (80px) @ Desktop
- Grid Gap: 24px (gap-6)
- Card Padding: 24px (p-6)
- Margin between Header/ContentBox/Grid: 48px (mb-12)

---

### SECTION 3: MODULES (Dark Navy - Drei Säulen)

**Komponente:** `<Section tone="dark" id="modules" />`
**Layout-Pattern:** Header + 3-Column Module Grid
**Hintergrund:** `var(--brand-primary-900)` (#04060D)

**Semantik & Content:**

```
SECTION#modules (tone: dark, padding: py-16 md:py-20, text: white)
│
├── Header-Bereich
│   Max-width: 768px
│   Margin-bottom: 48px (mb-12)
│   │
│   ├── H2
│   │   Text: "Drei Säulen, ein Setup"
│   │   Font: Inter Bold, 1.875rem (30px) @ Mobile, 2.25rem (36px) @ Desktop
│   │   Farbe: white (#FFFFFF)
│   │   Line-height: tight
│   │
│   └── Paragraph
│       Text: "Content + UX, Automationen + Integrationen sowie Governance + KPI-Monitoring bilden das Fundament jeder Branchenlösung."
│       Font: Inter Regular, 16px @ Mobile, 18px @ Desktop
│       Farbe: rgba(255,255,255,0.8)
│       Line-height: relaxed
│       Margin-top: 16px (mt-4)
│
└── Module-Grid
    Display: grid
    Grid-cols: 1 @ Mobile, 3 @ Desktop (md:grid-cols-3)
    Gap: 24px (gap-6)
    │
    ├── Article 1: Content & UX
    │   Background: `bg-white-alpha-08` (rgba(255,255,255,0.08))
    │   Border: 1px solid `var(--border-on-dark-subtle)` (rgba(148,163,184,0.18))
    │   Border-radius: 16px (rounded-2xl)
    │   Padding: 24px (p-6)
    │   Backdrop-filter: blur(2px)
    │   │
    │   ├── H3
    │   │   Text: "Content & UX"
    │   │   Font: Inter SemiBold, 18px (1.125rem)
    │   │   Farbe: white
    │   │
    │   └── UL (3 Checkmark Items)
    │       Margin-top: 16px (mt-4)
    │       Space-y: 12px
    │       │
    │       ├── LI 1
    │       │   Display: flex gap-2
    │       │   │
    │       │   ├── SVG Checkmark
    │       │   │   Size: 16px × 16px
    │       │   │   Margin-top: 4px (mt-1)
    │       │   │   Stroke: #85D4B2 (emerald-300)
    │       │   │   Stroke-width: 2px
    │       │   │
    │       │   └── Text
    │       │       Text: "Journey-orientierte Informationsarchitektur mit Plain Language"
    │       │       Font: Inter Regular, 14px
    │       │       Farbe: rgba(255,255,255,0.8)
    │       │       Line-height: relaxed
    │       │
    │       ├── LI 2
    │       │   [Gleiche Struktur]
    │       │   Text: "BFSG 2025 & WCAG 2.2 AA geprüfte Komponenten"
    │       │
    │       └── LI 3
    │           [Gleiche Struktur]
    │           Text: "GEO / AEO optimierter Content mit Schema.org & FAQ-Markup"
    │
    ├── Article 2: Automationen & Integrationen
    │   [Gleiche Card-Struktur]
    │   H3: "Automationen & Integrationen"
    │   UL Items:
    │   - "Intake-, Anmelde- und Service-Flows auf Workers + D1"
    │   - "CRM-, ERP-, PIM- und Fachverfahren-Integrationen"
    │   - "Trigger-basierte Nachfass-Strecken per E-Mail/SMS"
    │
    └── Article 3: Governance & KPIs
        [Gleiche Card-Struktur]
        H3: "Governance & KPIs"
        UL Items:
        - "GitOps Deployments mit Audit-Log & Rollback"
        - "Consent Mode v2 + Server-Side Tracking + RUM"
        - "Servicecockpits mit Completion, Digital Take-up & Zufriedenheit"
```

**Abstände & Layout:**
- Section Padding: py-16 (64px) @ Mobile, py-20 (80px) @ Desktop
- Grid Gap: 24px (gap-6)
- Card Padding: 24px (p-6)
- UL Space-y: 12px

---

### SECTION 4: GLOSSARY (Light Surface - Wissens-Promotion)

**Komponente:** `<Section tone="light" id="glossary" />`
**Layout-Pattern:** Header + 3 ContentBoxDark Cards mit Links
**Hintergrund:** `var(--surface-light)` (#F9FAFB)

**Semantik & Content:**

```
SECTION#glossary (tone: light, padding: py-16 md:py-20)
│
├── Header-Bereich
│   Max-width: 768px
│   Margin-bottom: 32px (mb-8)
│   │
│   ├── H2
│   │   Text: "Glossar, Guides & Playbooks für Stakeholder"
│   │   Font: Inter Bold, 1.875rem (30px) @ Mobile, 2.25rem (36px) @ Desktop
│   │   Farbe: `var(--text-on-light-primary)` (#0B101A)
│   │   Line-height: tight
│   │
│   └── Paragraph
│       Text: "Fachbegriffe und Patterns erklären wir in unserem Wissen-Bereich – inklusive Checklisten, Templates und Tooling."
│       Font: Inter Regular, 16px @ Mobile, 18px @ Desktop
│       Farbe: `var(--text-on-light-secondary)` (#4B5563)
│       Line-height: relaxed
│       Margin-top: 16px (mt-4)
│
└── Card-Grid
    Display: grid
    Grid-cols: 1 @ Mobile, 3 @ Desktop (md:grid-cols-3)
    Gap: 24px (gap-6)
    │
    ├── ContentBoxDark 1: Glossar & Tooltips
    │   Component: <ContentBoxDark>
    │   Background: `var(--brand-primary-900)` (#04060D)
    │   Border: 1px solid `var(--border-subtle-dark)`
    │   Border-radius: 24px (rounded-3xl)
    │   Padding: px-8 py-8
    │   Shadow: `var(--shadow-premium)`
    │   │
    │   ├── H3
    │   │   Text: "Glossar & Tooltips"
    │   │   Font: Inter Bold, 18px (1.125rem)
    │   │   Farbe: white
    │   │   Margin-bottom: 16px
    │   │
    │   ├── Paragraph
    │   │   Text: "Begriffe wie GEO, BFSG, Consent Mode v2 oder Auditierbare Deployments mit Kontext und Quellen."
    │   │   Font: Inter Regular, 14px @ Mobile, 16px @ Desktop
    │   │   Farbe: rgba(249,250,251,0.8)
    │   │   Line-height: relaxed
    │   │
    │   └── Link
    │       Text: "Glossar öffnen"
    │       Href: /wissen/glossar
    │       Display: inline-flex items-center gap-2
    │       Margin-top: 16px (mt-4)
    │       Font: Inter SemiBold, 16px
    │       Farbe: rgba(255,255,255,0.8)
    │       Hover: color white, text-shadow: 0 0 20px rgba(255,255,255,0.25)
    │       Transition: all 250ms cubic-bezier(0.16,1,0.3,1)
    │       │
    │       └── Arrow-Icon (SVG)
    │           Size: 20px × 20px
    │           Path: "M17 8l4 4m0 0l-4 4m4-4H7"
    │           Stroke: currentColor
    │
    ├── ContentBoxDark 2: Guides & Case Studies
    │   [Gleiche Card-Struktur]
    │   H3: "Guides & Case Studies"
    │   Text: "Vergleiche, Checklisten und Case Studies für Behörden, Bildung, Kanzleien und Industrie."
    │   Link-Text: "Wissen & Guides ansehen"
    │   Link-Href: /wissen
    │
    └── ContentBoxDark 3: Conversion Playbooks
        [Gleiche Card-Struktur]
        H3: "Conversion Playbooks"
        Text: "Microcopy, CTA-Strategien und KPI-Setups je Segment – vom Intake bis Servicecockpit."
        Link-Text: "Conversion-Playbook lesen"
        Link-Href: /wissen#playbooks
```

**Abstände & Layout:**
- Section Padding: py-16 (64px) @ Mobile, py-20 (80px) @ Desktop
- Grid Gap: 24px (gap-6)
- Card Padding: px-8 py-8 (32px)
- Margin between elements: 16px (mt-4)

---

### SECTION 5: CTA (Light Surface - Final Call-to-Action)

**Komponente:** `<Section tone="light" id="cta" />`
**Layout-Pattern:** ContentBoxDark mit 2-Column Layout (Text + Steps-Card)
**Hintergrund:** `var(--surface-light)` (#F9FAFB)

**Semantik & Content:**

```
SECTION#cta (tone: light, padding: py-20 md:py-24)
│
└── Container (max-width: 1152px, mx-auto)
    │
    └── ContentBoxDark
        Component: <ContentBoxDark>
        Heading: "Branchenlösung starten?"
        HeadingLevel: h2
        Background: `var(--brand-primary-900)` (#04060D)
        Border: 1px solid `var(--border-subtle-dark)`
        Border-radius: 24px (rounded-3xl)
        Padding: px-8 py-8 @ Mobile, px-10 py-10 @ Desktop
        Shadow: `var(--shadow-premium)`
        │
        ├── H2
        │   Text: "Branchenlösung starten?"
        │   Font: Inter Bold, 1.875rem (30px) @ Mobile, 2.25rem (36px) @ Desktop
        │   Farbe: white
        │   Margin-bottom: 24px
        │
        └── Grid-Layout (2-Spalten @ Large: 1.4fr + 1fr)
            Gap: 48px (gap-12)
            Items-align: start
            │
            ├── Haupt-Content (linke Spalte)
            │   │
            │   ├── Paragraph
            │   │   Text: "Wir führen Ihr Projekt von der KPI-Definition bis zur Live-Plattform: Strategie, Umsetzung, Monitoring und Hand-over – alles aus einer Hand."
            │   │   Font: Inter Regular, 16px @ Mobile, 18px @ Desktop
            │   │   Farbe: rgba(226,232,240,0.85) - slate-200/85
            │   │   Line-height: relaxed
            │   │
            │   └── Button-Gruppe
            │       Display: flex flex-wrap gap-4
            │       Margin-top: 32px (mt-8)
            │       │
            │       ├── Button Primary
            │       │   Label: "Strategie-Session buchen"
            │       │   Href: /kontakt
            │       │   Klasse: btn-primary-light
            │       │   Background: linear-gradient(135deg, #FFFFFF, #E5E7EB)
            │       │   Farbe: #0F172A
            │       │   Font: Inter SemiBold, 16px
            │       │   Padding: px-6 py-3
            │       │   Border-radius: 12px
            │       │   Border: 2px solid #D1D5DB
            │       │   Shadow: Premium multi-layer
            │       │   Display: inline-flex items-center gap-2
            │       │   Hover: lift + glow
            │       │
            │       └── Button Secondary
            │           Label: "Arbeitsweise ansehen"
            │           Href: /capabilities
            │           Background: transparent
            │           Farbe: white
            │           Font: Inter SemiBold, 16px
            │           Padding: px-6 py-3
            │           Border-radius: 12px
            │           Border: 2px solid `var(--border-on-dark-strong)` (rgba(255,255,255,0.6))
            │           Display: inline-flex items-center gap-2
            │           Hover: background rgba(255,255,255,0.12)
            │
            └── Steps-Card (rechte Spalte - ContentBoxLight)
                Component: <ContentBoxLight>
                Background: white (#FFFFFF)
                Border: 1px solid #E5E7EB (slate-200)
                Border-radius: 24px (rounded-3xl)
                Padding: 32px (p-8)
                Shadow: 0 10px 40px -15px rgba(0,0,0,0.2)
                Space-y: 16px (space-y-4)
                │
                ├── Label
                │   Text: "In 3 Schritten"
                │   Font: Inter SemiBold, 12px, uppercase, tracking: 0.22em
                │   Farbe: `var(--text-on-light-muted)` (#6B7280)
                │
                └── UL (3 Checkmark Items)
                    Space-y: 12px (space-y-3)
                    │
                    ├── LI 1
                    │   Display: flex gap-3
                    │   │
                    │   ├── SVG Checkmark
                    │   │   Size: 16px × 16px
                    │   │   Margin-top: 4px (mt-1)
                    │   │   Stroke: `var(--text-on-light-primary)` (#0B101A)
                    │   │   Stroke-width: 2px
                    │   │
                    │   └── Text
                    │       Text: "Discovery & KPI-Definition (Workshop + Research)"
                    │       Font: Inter Regular, 14px
                    │       Farbe: `var(--text-on-light-primary)`
                    │
                    ├── LI 2
                    │   [Gleiche Struktur]
                    │   Text: "UX/Content-Sprint + Komponentenaufbau (Astro + Workers)"
                    │
                    └── LI 3
                        [Gleiche Struktur]
                        Text: "Go-Live, Monitoring & Enablement Ihres Teams"
```

**Abstände & Layout:**
- Section Padding: py-20 (80px) @ Mobile, py-24 (96px) @ Desktop
- ContentBox Padding: px-8 py-8 @ Mobile, px-10 py-10 @ Desktop
- Grid Gap: 48px (gap-12)
- Inner Card Padding: 32px (p-8)
- Space between elements: 16px (space-y-4)

---

### FOOTER

**Komponente:** `<Footer />`
**Datei:** `/src/components/Footer.astro`
**Slot:** "footer" im Base-Layout

*(Gleiche Struktur wie Startseite - siehe startseite.md)*

---

## 🎨 DESIGN-SYSTEM-DETAILS

### Farbnutzung (Section-übergreifend)

| Element | CSS-Variable | Hex/rgba-Wert | Verwendung |
|---------|--------------|---------------|------------|
| Hero Background | `--brand-primary-900` | #04060D | Dark Grid Hero |
| Hero Grid Lines | - | rgba(255,255,255,0.03) | Grid Pattern (50px) |
| Hero Text Primary | `--text-primary-on-dark` | #F9FAFB | H1 Headline |
| Hero Text Secondary | `--text-secondary-on-dark` | rgba(249,250,251,0.72) | Subtitle/Paragraph |
| Light Section BG | `--surface-light` | #F9FAFB | Segments/Glossary/CTA |
| Dark Section BG | `--brand-primary-900` | #04060D | Modules Section |
| Card Background (Light) | - | #FFFFFF | Branch Cards |
| Card Border (Light) | - | #D1D5DB (slate-300) | Branch Card Borders |
| Card Background (Dark) | `--alpha-white-08` | rgba(255,255,255,0.08) | Module Cards |
| Card Border (Dark) | `--border-on-dark-subtle` | rgba(148,163,184,0.18) | Module Card Borders |
| Text on Light Primary | `--text-on-light-primary` | #0B101A | H2/H3 auf Light BG |
| Text on Light Secondary | `--text-on-light-secondary` | #4B5563 | Body-Text auf Light BG |
| Text on Light Muted | `--text-on-light-muted` | #6B7280 | Labels/Small Text |
| Checkmark Emerald | - | #85D4B2 (emerald-300) | Success Icons |
| Button Gradient Start | - | #FFFFFF | Primary Button Start |
| Button Gradient End | - | #E5E7EB | Primary Button End |
| Button Border | - | #D1D5DB (slate-300) | Button Border |

### Typografie-Details

| Element | Font-Family | Mobile Size | Desktop Size | Weight | Line-Height | Letter-Spacing |
|---------|-------------|-------------|--------------|---------|-------------|----------------|
| H1 (Hero) | Inter | 2.25rem (36px) | 4.5rem (72px) | ExtraBold (800) | 1.15 (tight) | -0.02em |
| H2 (Sections) | Inter | 1.875rem (30px) | 2.25rem (36px) | Bold (700) | 1.25 (tight) | 0 |
| H3 (Cards) | Inter | 1.125rem (18px) | 1.25rem (20px) | SemiBold (600) | 1.25 (tight) | 0 |
| Body (Hero) | Inter | 1.125rem (18px) | 1.25rem (20px) | Regular (400) | 1.75 (loose) | 0 |
| Body (Sections) | Inter | 1rem (16px) | 1.125rem (18px) | Regular (400) | 1.75 (relaxed) | 0 |
| Body Small | Inter | 0.875rem (14px) | 1rem (16px) | Regular (400) | 1.75 (relaxed) | 0 |
| Badge/Label | Inter | 0.75rem (12px) | 0.75rem (12px) | SemiBold (600) | 1.5 (normal) | 0.22-0.32em |
| Button Text | Inter | 0.9375rem (15px) | 1rem (16px) | SemiBold (600) | 1.5 (normal) | 0 |

### Spacing-System

| Element | Mobile | Tablet | Desktop |
|---------|--------|--------|---------|
| Section Padding Vertical | py-16 (64px) | py-20 (80px) | py-20 (80px) |
| Section Padding Horizontal | px-6 (24px) | px-8 (32px) | px-12 (48px) |
| Card Padding | p-6 (24px) | p-6 (24px) | p-6 (24px) |
| ContentBox Padding | px-8 py-8 (32px) | px-8 py-8 (32px) | px-10 py-10 (40px) |
| Grid Gap (Cards) | gap-6 (24px) | gap-6 (24px) | gap-6 (24px) |
| Button Gap (Icons) | gap-2 (8px) | gap-2 (8px) | gap-2 (8px) |
| Margin Header → Content | mb-8 (32px) | mb-10 (40px) | mb-12 (48px) |

### Shadow-System

| Name | Value | Verwendung |
|------|-------|------------|
| `--shadow-premium` | 0 0 0 1px rgba(255,255,255,0.05), 0 10px 30px -10px rgba(0,0,0,0.15), 0 30px 90px -60px rgba(107,114,128,0.25) | ContentBoxDark Cards |
| `--shadow-sm` | 0 1px 2px 0 rgba(0,0,0,0.05) | Branch Cards (Rest) |
| `shadow-xl` | 0 20px 25px -5px rgba(0,0,0,0.1), 0 8px 10px -6px rgba(0,0,0,0.1) | Branch Cards (Hover) |
| `--shadow-card-light` | 0 30px 70px -60px rgba(15,23,42,0.35) | Steps Card |

### Border-Radius

| Size | Tailwind Class | Pixel Value | Verwendung |
|------|----------------|-------------|------------|
| Medium | `rounded-xl` | 12px | Buttons |
| Large | `rounded-2xl` | 16px | Branch Cards, Module Cards |
| Extra Large | `rounded-3xl` | 24px | ContentBoxDark, ContentBoxLight |
| Full | `rounded-full` | 9999px | Badges, KPI Values |

---

## 📱 RESPONSIVE BREAKPOINTS

| Breakpoint | Screen-Width | Grid-Cols (Branch Cards) | Grid-Cols (Modules) | H1 Font-Size | Section Padding |
|------------|--------------|--------------------------|---------------------|--------------|-----------------|
| Mobile | <640px | 1 | 1 | 2.25rem (36px) | px-6 py-16 (24px/64px) |
| Tablet | 640-1023px | 2 (md:) | 1 | 3rem (48px) | px-8 py-20 (32px/80px) |
| Desktop | ≥1024px | 3 (xl:) | 3 (md:) | 4.5rem (72px) | px-12 py-20 (48px/80px) |

**Hauptänderungen:**
- **Hero:** H1 skaliert von 36px → 48px → 72px
- **Grid-Layout:** Branch Cards: 1-col → 2-col → 3-col; Module Cards: 1-col → 3-col
- **Padding:** Horizontal: 24px → 32px → 48px; Vertikal: 64px → 80px
- **Container Max-Width:** 1280px (max-w-7xl)
- **CTA Grid:** 1-col @ Mobile, 2-col (1.4fr + 1fr) @ Desktop (lg:)

---

## 🧩 KOMPONENTEN-BIBLIOTHEK

### Genutzte Astro-Components

| Komponente | Datei | Props (Key-Value-Paare) |
|------------|-------|-------------------------|
| `<Base>` | `/src/layouts/Base.astro` | title, description, canonical |
| `<Nav>` | `/src/components/Nav.astro` | slot="header" |
| `<Hero>` | `/src/components/Hero.astro` | title, subtitle, ctaText, ctaHref, showSecondaryCta={false}, tertiaryCtaText, tertiaryCtaHref, variant="dark-grid", minHeightStyle="min-height:100vh;min-height:100dvh;" |
| `<Section>` | `/src/components/Section.astro` | tone="light/dark", id="segments/modules/glossary/cta", class="py-16 md:py-20", aria-labelledby="..." |
| `<ContentBoxDark>` | `/src/components/ContentBoxDark.astro` | heading="...", headingLevel="h2/h3", class="mb-12" |
| `<ContentBoxLight>` | `/src/components/ContentBoxLight.astro` | class="bg-white border border-slate-200 rounded-3xl p-8 shadow-lg space-y-4" |
| `<Footer>` | `/src/components/Footer.astro` | slot="footer" |

### Dynamische Daten

**Collection Loading:**
```astro
const branches = await getCollection('branchen');
```

**Hero QuickLinks Mapping:**
```astro
const heroQuickLinks = branches.slice(0, 4).map((branch) => ({
  label: branch.data.title,
  description: branch.data.intro.deck,
  href: `/branchen/${branch.data.slug}`,
  badge: branch.data.intro.kpi.label,
  duration: branch.data.intro.kpi.value,
  icon: 'M17 8l4 4m0 0l-4 4m4-4H3',
}));
```

**Branch Cards Mapping:**
```astro
const branchCards = branches.map((branch) => ({
  title: branch.data.title,
  subtitle: branch.data.intro.headline,
  kpi: branch.data.intro.kpi,
  slug: branch.data.slug,
  deck: branch.data.intro.deck,
}));
```

**Segments Counting:**
```astro
const segments = new Map<string, number>();
branches.forEach((branch) => {
  segments.set(branch.data.segment, (segments.get(branch.data.segment) ?? 0) + 1);
});
// H2 zeigt: "Lösungen für {segments.size} Segmente – maßgeschneidert"
```

---

## 🔍 SEO & STRUKTURIERTE DATEN

### Schema.org Markup

**Typ:** Organization / CollectionPage (implizit)

**JSON-LD:** Kein explizites Schema.org Markup auf dieser Seite vorhanden. Dies ist eine Hub-Page ohne strukturierte Daten für einzelne Entities.

**Empfehlung:** CollectionPage Schema für Branchen-Übersicht könnte hinzugefügt werden mit `hasPart` Referenzen zu allen 9 Branch-Detailseiten.

### Open Graph / Twitter Card

**Metadaten im `<Base>`-Layout:**
- `og:title`: "Branchenlösungen für regulierte & öffentliche Teams | Wolf-Agents"
- `og:description`: "Branchenspezifische Websites & WebApps für Kanzleien, Bildung, Behörden, Versicherungen, Industrie und Notariate..."
- `og:url`: https://www.wolf-agents.com/branchen
- `og:type`: website
- `twitter:card`: summary_large_image

---

## ♿ BARRIEREFREIHEIT (WCAG 2.2)

### Kontrast-Ratios

| Text | Hintergrund | Ratio | Status |
|------|-------------|-------|--------|
| H1 Hero (#F9FAFB) | Dark BG (#04060D) | 19.2:1 | ✅ AAA |
| Hero Subtitle (rgba(249,250,251,0.72)) | Dark BG (#04060D) | 13.8:1 | ✅ AAA |
| Body Text on Light (#4B5563) | Light BG (#F9FAFB) | 8.1:1 | ✅ AAA |
| White Text | Dark Card BG (rgba(255,255,255,0.08)) | 18.5:1 | ✅ AAA |
| Button Text (#0F172A) | Button BG (#FFFFFF) | 16.1:1 | ✅ AAA |

### Semantische HTML-Struktur

**Tags:**
- ✅ `<nav>` (Navigation)
- ✅ `<main>` (implizit via Base-Layout)
- ✅ `<section>` mit ID und `aria-labelledby`
- ✅ `<article>` (Module-Cards)
- ✅ `<footer>`

**Heading-Hierarchie:**
- ✅ H1 → H2 → H3 korrekt verschachtelt
- ✅ Keine übersprungenen Levels
- ✅ Jede Section hat beschreibende Überschrift

### Interaktive Elemente

**Focus-Rings:**
- ✅ Buttons haben Custom Focus-States mit `focus-visible:outline-none focus-visible:ring-2`
- ✅ Links haben Underline + Color-Change auf Hover/Focus
- ✅ Branch-Cards haben Hover-States mit Transform + Shadow

**Button vs. Link:**
- ✅ Korrekt: `<a href="/branchen/kanzleien">` für Navigation
- ✅ Korrekt: `<button>` für Collapsibles (falls vorhanden)

**ARIA-Attribute:**
- ✅ `aria-labelledby` auf Sections verweist auf H2-ID
- ✅ `aria-hidden="true"` auf dekorativen SVG-Icons
- ✅ `role="navigation"` auf Nav-Element (implizit)

### Reduced Motion

**Support:**
- ✅ CSS beinhaltet `@media (prefers-reduced-motion: reduce)` für Transitions
- ✅ Hover-Animationen (translateY, scale) werden bei reduced-motion deaktiviert
- ✅ Fade-Ins und Slide-Animationen respektieren User-Preference

---

## 🎯 CONTENT-STRATEGIE & TARGETING

### Hauptthema der Seite

Diese Seite ist die zentrale Hub-Page für alle 9 Branchenlösungen. Sie zeigt, dass Wolf-Agents branchenspezifische Websites & WebApps für regulierte und öffentliche Teams entwickelt. Jede Branche hat eigene Compliance-Anforderungen, User Journeys und KPIs, die in maßgeschneiderte Module übersetzt werden.

### Primäre Keywords

- Branchenlösungen
- Websites für Kanzleien
- Websites für Behörden
- Websites für Schulen
- Websites für Steuerberater
- WebApps für regulierte Teams
- Branchenspezifische Webentwicklung

### Sekundäre Keywords (LSI)

- Intake-Flows
- Servicecockpits
- Compliance-Module
- BFSG 2025
- WCAG 2.2 AA
- GEO-Optimierung
- AEO-Content
- GitOps Deployments
- Mandatsreisen
- Einschreibungen
- Bürgerdienste
- Digital Take-up
- Completion Rate
- Content & UX
- Automationen & Integrationen
- Governance & KPIs

### Zielgruppe

**Primär:**
- Geschäftsführer und IT-Verantwortliche von Kanzleien, Steuerberatungen, Schulen, Hochschulen, Behörden und öffentlichen Einrichtungen
- Alter: 35-65 Jahre
- DACH-Region (Deutschland, Österreich, Schweiz)
- Suchen nach digitalen Lösungen für Intake, Anmeldungen, Bürgerservices
- Benötigen Compliance (DSGVO, BFSG), Barrierefreiheit (WCAG 2.2 AA)

**Sekundär:**
- Marketing-Verantwortliche in diesen Branchen
- IT-Dienstleister, die Lösungen für regulierte Branchen suchen

### User Intent

**Primär:** Informational (Recherche)
- User möchte verstehen, welche Branchenlösungen verfügbar sind
- Vergleich: Passt meine Branche zu Wolf-Agents?
- Welche Module/Features gibt es für meine Branche?

**Sekundär:** Navigational
- User klickt auf spezifische Branch-Card, um Detailseite zu besuchen
- Glossar-Links für Fachbegriffe (GEO, BFSG, GitOps, etc.)

**Tertiär:** Transactional (CTA)
- "Kontakt aufnehmen" / "Strategie-Session buchen"
- User ist bereit für Erstgespräch

### AIO/GEO/AEO-Status

**AIO (AI Overview Optimization):**
- ❓ **Noch nicht optimiert:** Keine expliziten FAQ-Strukturen auf der Overview-Page
- ✅ **Potenzial:** "Was sind Branchenlösungen?" als FAQ könnte AI Overviews ansprechen
- ⚠️ **Fehlend:** Kein FAQ-Markup auf dieser Seite (nur auf Detailseiten)

**GEO (Generative Engine Optimization):**
- ✅ **Strukturierte Daten vorhanden:** Indirekt via Branch-Detailseiten (LegalService, EducationalOrganization, GovernmentOrganization)
- ⚠️ **Verbesserungspotenzial:** CollectionPage Schema mit `hasPart` References zu Detailseiten
- ✅ **Interne Verlinkung:** Starke Hub-Struktur mit Links zu allen 9 Branchen

**AEO (Answer Engine Optimization):**
- ✅ **Konkrete Metriken:** "+35% Lead-to-Call Rate", "≥70% Completion Rate", "3 Schritte"
- ✅ **Klare Kategorisierung:** 3 Säulen (Content & UX, Automationen, Governance)
- ⚠️ **Fehlend:** Direkte Antworten auf "Wie lange dauert ein Projekt?", "Was kostet eine Branchenlösung?"

---

## 📝 CONTENT-AUDIT-NOTIZEN

### Stärken

- ✅ **Klare Hub-Struktur:** Alle 9 Branchen auf einen Blick mit KPI-Badges
- ✅ **Konsistente Branch-Cards:** Einheitliches Design, gleiche Informationsdichte (Title, Deck, KPI, CTA)
- ✅ **Dynamisches Content-Loading:** Collection API ermöglicht einfaches Hinzufügen neuer Branchen
- ✅ **"Drei Säulen"-Framework:** Content & UX, Automationen, Governance sind leicht verständlich
- ✅ **Glossar-Promotion:** Section verlinkt zu Wissen-Bereich, stärkt interne Link-Struktur
- ✅ **Premium Design:** Dark Grid Hero + ContentBoxDark-Pattern schafft hochwertige Anmutung
- ✅ **Barrierefreiheit:** Hohe Kontraste, semantisches HTML, ARIA-Labels
- ✅ **CTA-Clarity:** Klare nächste Schritte ("In 3 Schritten") in Steps-Card

### Altlasten / Schwächen

- ⚠️ **Keine Featured Branch:** Alle 9 Branchen gleichwertig präsentiert – keine Priorisierung für Haupt-Zielgruppen
- ⚠️ **Fehlende FAQ:** Wiederkehrende Fragen ("Wie lange dauert ein Projekt?", "Was kostet eine Branchenlösung?") werden nicht auf dieser Hub-Page beantwortet
- ⚠️ **Kein Schema.org:** Keine strukturierten Daten auf Overview-Page – GEO-Potenzial ungenutzt
- ⚠️ **"Warum branchenspezifisch?"-ContentBox:** Text ist informativ, aber könnte prägnanter sein (3 Bullet-Points wirken etwas generisch)
- ⚠️ **Segments-Zählung:** "Lösungen für 3 Segmente" – User versteht nicht, was "Segment" bedeutet (kanzlei, steuer, oeffentlich) – keine Erklärung
- ⚠️ **CTA-Text:** "Strategie-Session buchen" könnte spezifischer sein ("Kostenlose Erstberatung", "Branchenlösung besprechen")

### Fehlende Elemente

- ❌ **Testimonials / Social Proof:** Keine Kundenstimmen oder Logos von Referenzkunden
- ❌ **Case Studies:** Keine konkreten Projekt-Beispiele ("Kanzlei X hat Lead-to-Call Rate um 35% gesteigert")
- ❌ **FAQ-Section:** Häufige Fragen zu Projektlaufzeit, Kosten, Technologie-Stack fehlen
- ❌ **Vergleichstabelle:** "Welche Branche passt zu mir?" – Feature-Matrix (z.B. Intake-Flows: Ja/Nein, Servicecockpit: Ja/Nein)
- ❌ **Video/Demo:** Keine visuelle Präsentation der Lösungen (z.B. Loom-Video, Figma-Prototyp-Link)
- ❌ **Trust-Signale:** Keine Erwähnung von DSGVO-Compliance, ISO-Zertifikaten, BFSG-Audits auf Hub-Page

### Content-Refresh-Priorität

**Priorität:** 🔴 **HOCH**

**Begründung:**
1. **Zentrale Hub-Page:** Diese Seite ist das Gateway zu allen 9 Branchen-Detailseiten – hohe Bedeutung für Navigation & SEO
2. **Interne Link-Struktur:** Starke Backlinks von Startseite, Navigation, Footer
3. **SEO-Potenzial:** Ranking für "Branchenlösungen", "Websites für Kanzleien", "Websites für Behörden" möglich
4. **GEO-Opportunity:** CollectionPage Schema könnte AI Overviews und Google Discover ansprechen
5. **Conversion-Optimierung:** CTA-Section könnte mit FAQ/Testimonials deutlich gestärkt werden

**Empfohlene Maßnahmen (für externes LLM):**
- FAQ-Section hinzufügen (3-5 Fragen)
- Schema.org CollectionPage Markup einbauen
- "Warum branchenspezifisch?"-Text prägnanter formulieren
- Social Proof / Testimonials ergänzen
- Segment-Begriff erklären oder durch "Branchen" ersetzen

---

## 📈 PERFORMANCE & TECHNISCHE DETAILS (optional)

### Core Web Vitals (Zielwerte)

- **LCP (Largest Contentful Paint):** < 2.5s (Hero H1 ist LCP-Element)
- **INP (Interaction to Next Paint):** < 200ms (Hover-Animationen, Branch-Card-Klicks)
- **CLS (Cumulative Layout Shift):** < 0.1 (Keine Layout-Shifts erwartet, da statisches Grid)

### Lazy Loading

- **Images:** Keine Bilder auf dieser Seite (außer Logo in Nav)
- **Scripts:** Astro-Islands werden lazy geladen (falls vorhanden)
- **Branch-Data:** Collection wird zur Build-Time geladen (kein Client-Fetch)

### Mobile Optimierung

- ✅ **Responsive:** Vollständig responsive (Mobile-first Ansatz)
- ✅ **Touch-Targets:** Alle Buttons/Links ≥ 44px × 44px (WCAG 2.2 Guideline 2.5.8)
- ✅ **Viewport:** Meta-Tag `width=device-width, initial-scale=1`
- ✅ **Font-Sizes:** Minimum 14px auf Mobile (lesbar ohne Zoom)

---

## 📊 CONTENT-METRIKEN

### Textmenge

- **Gesamtzeichen:** ~8.200 (ohne Code/HTML)
- **Gesamtwörter:** ~1.150
- **Lesedauer:** 5-6 Minuten

### Link-Dichte

- **Interne Links:** ~45-50
  - Navigation: ~15 Links (Branchen, Leistungen, Wissen)
  - Branch-Cards: 9 Links
  - Glossary-Section: 3 Links
  - CTA-Section: 2 Links
  - Footer: ~20 Links
- **Externe Links:** 0 (nur mailto)
- **CTAs:** 4 (Hero Primary/Tertiary, CTA Primary/Secondary)

### Content-Verteilung

- **Dark Sections:** 40% (Hero 100vh, Modules Section)
- **Light Sections:** 60% (Segments, Glossary, CTA)

### Interaktive Elemente

- **Buttons:** 4 (Hero Primary/Tertiary, CTA Primary/Secondary)
- **Collapsibles:** 0 (keine Details/Summary auf dieser Seite)
- **Tooltips:** 0 (InfoTooltips sind auf Detailseiten)
- **Hover-Cards:** 9 (Branch Cards mit translateY + Shadow-Animation)
- **Link-Cards:** 9 (Branch Cards)
- **Module-Cards:** 3 (Content & UX, Automationen, Governance)
- **Glossary-Cards:** 3 (ContentBoxDark mit Links)

---

**ENDE DER DOKUMENTATION**

**Letzte Aktualisierung:** 2025-10-30
**Nächste Review:** Nach Content-Refresh oder Hinzufügen neuer Branchen
