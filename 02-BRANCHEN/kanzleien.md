# KANZLEIEN & BOUTIQUEN - Content & Struktur-Architektur

**Dokument

iert am:** 2025-10-30
**Status:** IST-Zustand (keine Optimierungsvorschläge)

---

## 📊 META-INFORMATIONEN

| Attribut | Wert |
|----------|------|
| **URL** | https://www.wolf-agents.com/branchen/kanzleien |
| **Datei** | `/src/pages/branchen/[slug].astro` (Dynamic Route) |
| **Content-Datei** | `/src/content/branchen/kanzleien.json` |
| **Title Tag** | "Kanzleien & Boutiquen – Branchenlösung \| Wolf-Agents" |
| **Meta Description** | "Wir verbinden Geo-optimierte Inhalte, Intake-Flows und Governance, damit wirtschafts- und streitige Kanzleien schneller zu qualifizierten Mandaten kommen." |
| **Canonical URL** | https://www.wolf-agents.com/branchen/kanzleien |
| **Noindex** | Nein |
| **Geschätzte Zeichenanzahl** | ~11.800 Zeichen (ohne Code/HTML) |
| **Geschätzte Wortanzahl** | ~1.650 Wörter |
| **Geschätzte Lesedauer** | 7-9 Minuten |
| **Anzahl Sections** | 11 Hauptbereiche |
| **Anzahl H1** | 1 |
| **Anzahl H2** | 9 |
| **Anzahl H3** | 15+ |

---

## 🔗 VERLINKUNGSSTRUKTUR

### Interne Links (ausgehend)
- Navigation: `/` (Startseite), `/branchen/` (Branchen-Übersicht), `/leistungen/`, `/wissen/`
- Hero CTA Primary: `/kontakt`
- Hero CTA Tertiary: `/leistungen`
- Path Section Task-Links: `#mandatsaufnahme`, `#pitch-support`, `#termin` (Anchor-Links)
- Solution-Cards: Inline InfoTooltips → `/wissen/glossar/geo`, `/wissen/glossar/gitops`
- Glossary-Links Section: `/wissen/glossar/geo`, `/wissen/glossar/aeo`, `/wissen/glossar/gitops`, `/wissen/glossar/consent-mode-v2`
- CTA Section: `/kontakt`, `/wissen#case-studies`
- More Branches Section: Links zu 3 anderen Branchen (z.B. `/branchen/steuerberater`, `/branchen/schulen-bildung`, `/branchen/oeffentliche-einrichtungen`)
- Footer: Diverse Links

**Gesamtanzahl interne Links:** ~40-45 (inkl. Navigation, Glossar-Tooltips, Footer)

### Externe Links
Keine direkten externen Links (nur mailto in Navigation)

---

## 🏗️ LAYOUT & SEMANTISCHE STRUKTUR

---

### NAVIGATION (Sticky Header)

**Komponente:** `<Nav variant="transparent" />`
**Datei:** `/src/components/Nav.astro`

*(Gleiche Struktur wie andere Seiten - siehe startseite.md)*

---

### SECTION 1: HERO (Fullscreen Dark Grid mit Badge)

**Komponente:** `<Hero variant="dark-grid" align="left" />`
**Layout-Pattern:** Hero Dark Grid (100vh Fullscreen, Left-Aligned)
**Hintergrund:** `var(--brand-primary-900)` (#04060D) mit Grid-Pattern

**Semantik & Content:**

```
SECTION (Hero, min-height: 100vh / 100dvh)
│
├── Badge
│   Text: "Segment · Kanzleien"
│   Farbe: rgba(249,250,251,0.72)
│   Background: rgba(255,255,255,0.08)
│   Font: Inter SemiBold, 11px, uppercase, tracking: 0.26em
│   Padding: px-4 py-1.5, rounded-full
│   Border: 1px solid rgba(148,163,184,0.18)
│
├── H1 (Hauptüberschrift)
│   Text: "Digitale Mandatsreisen für spezialisierte Kanzleien"
│   Font: Inter ExtraBold, 4.5rem (72px) @ Desktop, 3rem (48px) @ Tablet, 2.25rem (36px) @ Mobile
│   Farbe: #F9FAFB (fast weiß)
│   Line-height: 1.15 (tight)
│   Letter-spacing: -0.02em
│   Max-width: 1000px
│   Alignment: left (via align="left" prop)
│
├── Paragraph (Subtitle/Deck)
│   Text: "Wir verbinden Geo-optimierte Inhalte, Intake-Flows und Governance, damit wirtschafts- und streitige Kanzleien schneller zu qualifizierten Mandaten kommen."
│   Font: Inter Regular, 1.25rem (20px) @ Desktop, 1.125rem (18px) @ Mobile
│   Farbe: rgba(249,250,251,0.72)
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
    │   [Design wie Branchen-Übersicht]
    │
    └── Tertiary Button
        Label: "Leistungsübersicht öffnen"
        Href: /leistungen
        [Design wie Branchen-Übersicht]
```

**Abstände & Layout:**
- Min-Height: 100vh / 100dvh
- Alignment: Left (nicht zentriert wie auf Overview-Page)
- Container: max-width 1280px, px-6 @ Mobile, px-12 @ Desktop
- Vertical Padding: py-20 @ Mobile, py-32 @ Desktop

---

### SECTION 2: TASKS (Light Surface - Top Tasks)

**Komponente:** `<Section tone="light" id="tasks" />`
**Layout-Pattern:** Header + CardGroup mit 3 Spalten
**Hintergrund:** `var(--surface-light)` (#F9FAFB)

**Semantik & Content:**

```
SECTION#tasks (tone: light, padding: py-16 md:py-20)
│
├── Header-Bereich
│   Max-width: 768px
│   Margin-bottom: 40px (mb-10)
│   │
│   ├── Badge
│   │   Text: "Top Tasks"
│   │   Klasse: chip-light caps-label-wide
│   │   [Styling wie auf Branchen-Übersicht]
│   │
│   ├── H2
│   │   Text: "Was Mandant:innen zuerst erledigen wollen"
│   │   Font: Inter Bold, 1.875rem (30px) @ Mobile, 2.25rem (36px) @ Desktop
│   │   Farbe: #0B101A
│   │   Line-height: tight
│   │   Margin-top: 16px
│   │
│   └── Paragraph
│       Text: "Die folgenden Aufgaben bilden den Einstieg in Ihre digitale Journey. Jede Karte führt zu einem Abschnitt mit Details, Modulen und passenden Automationen."
│       Font: Inter Regular, 16px @ Mobile, 18px @ Desktop
│       Farbe: #4B5563
│       Line-height: relaxed
│       Margin-top: 16px
│
└── CardGroup Component
    Komponente: <CardGroup>
    Props:
    - tone="light"
    - mobilePattern="accordion"
    - columns={3}
    - items=[3 mapped quickLinks]
    │
    Grid: 1-col @ Mobile, 2-col @ Tablet, 3-col @ Desktop
    Gap: 24px
    │
    ├── Card 1: Mandatsaufnahme starten
    │   Background: white
    │   Border: 1px solid rgba(226,232,240,0.7)
    │   Border-radius: 16px
    │   Padding: 24px
    │   Shadow: subtle
    │   │
    │   ├── Title: "Mandatsaufnahme starten"
    │   │   Font: Inter SemiBold, 18px
    │   │   Farbe: #0B101A
    │   │
    │   ├── Description: "Geführter Intake-Flow mit Dokument-Upload, Konfliktcheck und Priorisierung."
    │   │   Font: Inter Regular, 14px
    │   │   Farbe: #4B5563
    │   │   Margin-top: 8px
    │   │
    │   ├── Badge: "Partner & Backoffice"
    │   │   Background: rgba(226,232,240,0.5)
    │   │   Padding: px-3 py-1, rounded-full
    │   │   Font: Inter SemiBold, 12px
    │   │
    │   └── Link: "Zum Abschnitt"
    │       Href: #mandatsaufnahme
    │       Icon: Arrow-Right SVG
    │
    ├── Card 2: Pitch-Unterlagen vorbereiten
    │   [Gleiche Struktur]
    │   Description: "Case Vault, Referenzen und Claim Boards für Litigation & Corporate."
    │   Badge: "Business Development"
    │   Link: #pitch-support
    │
    └── Card 3: Termin sichern
        [Gleiche Struktur]
        Description: "Synchronisierte Kapazitätsplanung für mehrere Partner:innen und Standorte."
        Badge: "Mandant:innen"
        Link: #termin
```

**Abstände & Layout:**
- Section Padding: py-16 (64px) @ Mobile, py-20 (80px) @ Desktop
- Grid Gap: 24px
- Card Padding: 24px

---

### SECTION 3: PATH (Dark Navy - Journey mit StepFlow)

**Komponente:** `<Section tone="dark" id="path" />`
**Layout-Pattern:** Header + Task-Articles mit StepFlow-Embed
**Hintergrund:** `var(--brand-primary-900)` (#04060D)

**Semantik & Content:**

```
SECTION#path (tone: dark, padding: py-16 md:py-20)
│
├── Header-Bereich
│   Max-width: 768px
│   Margin-bottom: 32px (mb-8)
│   │
│   ├── H2
│   │   Text: "Wie die Journey abläuft"
│   │   Font: Inter Bold, 1.5rem (24px) @ Mobile, 1.875rem (30px) @ Desktop
│   │   Farbe: white
│   │   Line-height: tight
│   │
│   └── Paragraph
│       Text: "Jeder Top Task hat eine klare nächste Station. Nutzen Sie die Abschnitte unten, um interne Teams, Stakeholder und Automationen zu orchestrieren."
│       Font: Inter Regular, 16px @ Mobile, 18px @ Desktop
│       Farbe: rgba(255,255,255,0.8)
│       Line-height: relaxed
│       Margin-top: 16px
│
└── Task-Articles Container
    Space-y: 24px (gap-6)
    │
    ├── Article 1: Mandatsaufnahme starten
    │   ID: "mandatsaufnahme"
    │   Background: `var(--surface-light)` (#F9FAFB)
    │   Border: 1px solid rgba(226,232,240,0.7)
    │   Border-radius: 16px
    │   Padding: 24px
    │   Shadow: subtle
    │   │
    │   ├── Header-Row
    │   │   Display: flex items-center justify-between gap-4
    │   │   │
    │   │   ├── Left-Column
    │   │   │   │
    │   │   │   ├── H3: "Mandatsaufnahme starten"
    │   │   │   │   Font: Inter SemiBold, 18px
    │   │   │   │   Farbe: #0B101A
    │   │   │   │
    │   │   │   └── Description
    │   │   │       Text: "Geführter Intake-Flow mit Dokument-Upload, Konfliktcheck und Priorisierung."
    │   │   │       Font: Inter Regular, 14px
    │   │   │       Farbe: #4B5563
    │   │   │       Margin-top: 8px
    │   │   │
    │   │   └── Badge: "Partner & Backoffice"
    │   │       [Styling wie oben]
    │   │
    │   └── StepFlow-Embed (nur bei Index 0)
    │       Komponente: Inline Flow-Card
    │       Background: `var(--surface-light)` (#F9FAFB)
    │       Border: 1px solid rgba(226,232,240,0.7)
    │       Border-radius: 16px
    │       Padding: px-6 py-8 @ Mobile, px-8 py-8 @ Desktop
    │       Shadow: subtle
    │       Margin-top: 24px (mt-6)
    │       Space-y: 24px (space-y-6)
    │       │
    │       ├── Header-Block
    │       │   │
    │       │   ├── Eyebrow-Badge (optional)
    │       │   │   Text: "Mandatsreise"
    │       │   │   Klasse: chip-light caps-label-wide
    │       │   │   [Styling wie oben]
    │       │   │
    │       │   ├── H4: "Intake & Qualifizierung in 4 Schritten"
    │       │   │   Font: Inter SemiBold, 1.25rem (20px)
    │       │   │   Farbe: #0B101A
    │       │   │   Line-height: tight
    │       │   │
    │       │   └── Description
    │       │       Text: "Vom ersten Kontakt bis zum gebuchten Strategie-Termin behalten Partner:innen, Backoffice und Mandant:innen den Überblick."
    │       │       Font: Inter Regular, 14px
    │       │       Farbe: #4B5563
    │       │       Margin-top: 8px
    │       │
    │       └── Steps-Grid (4 Cards)
    │           Display: grid
    │           Grid-cols: 1 @ Mobile, 2 @ Tablet (md:), 4 @ Desktop (xl:grid-cols-4)
    │           Gap: 16px (gap-4)
    │           Aria-label: "Step-by-step Flow"
    │           │
    │           ├── Step 1: Anliegen erfassen
    │           │   Background: `var(--surface-light)` (#F9FAFB)
    │           │   Border: 1px solid rgba(17,24,39,0.18)
    │           │   Border-radius: 16px
    │           │   Padding: 20px (p-5)
    │           │   Shadow: subtle
    │           │   Position: relative
    │           │   Overflow: hidden
    │           │   │
    │           │   ├── Number-Badge
    │           │   │   Text: "01"
    │           │   │   Klasse: chip-light caps-label-wide
    │           │   │   Display: inline-flex items-center justify-center
    │           │   │   Font: Inter SemiBold, 12px
    │           │   │   Padding: px-3 py-1
    │           │   │
    │           │   ├── Title: "1 · Anliegen erfassen"
    │           │   │   Font: Inter SemiBold, 16px
    │           │   │   Farbe: #0B101A
    │           │   │   Line-height: tight
    │           │   │   Margin-top: 12px (mt-3)
    │           │   │
    │           │   ├── Summary
    │           │   │   Text: "Mandant:innen wählen Rechtsgebiet, Standort und Dringlichkeit, während Konfliktcheck & Datenschutz automatisch laufen."
    │           │   │   Font: Inter Regular, 14px
    │           │   │   Farbe: #4B5563
    │           │   │   Line-height: relaxed
    │           │   │   Margin-top: 8px (mt-2)
    │           │   │
    │           │   └── Hover-Glow (Absolute Overlay)
    │           │       Background: radial-gradient(circle at top, rgba(148,163,184,0.15), transparent 55%)
    │           │       Opacity: 0 → 100 on hover
    │           │       Transition: 300ms
    │           │       Absolute: inset-0
    │           │
    │           ├── Step 2: Unterlagen vollständig machen
    │           │   [Gleiche Card-Struktur]
    │           │   Number: "02"
    │           │   Title: "2 · Unterlagen vollständig machen"
    │           │   Summary: "Uploads mit Drag & Drop, To-do List für fehlende Dokumente, Reminder per E-Mail/SMS und sichere Ablage im DMS."
    │           │
    │           ├── Step 3: Intake priorisieren
    │           │   [Gleiche Card-Struktur]
    │           │   Number: "03"
    │           │   Title: "3 · Intake priorisieren"
    │           │   Summary: "Scoring nach Budget, Deadline und Komplexität. Partner:innen sehen sofort, welche Leads in die Beratung gehen."
    │           │
    │           └── Step 4: Termin & Übergabe
    │               [Gleiche Card-Struktur]
    │               Number: "04"
    │               Title: "4 · Termin & Übergabe"
    │               Summary: "Automatische Terminbestätigung, Übergabe aller Daten an CRM und KPI-Updates für Lead-to-Call Rate & Response Time."
    │
    ├── Article 2: Pitch-Unterlagen vorbereiten
    │   ID: "pitch-support"
    │   [Gleiche Artikel-Struktur wie Article 1, OHNE StepFlow]
    │
    └── Article 3: Termin sichern
        ID: "termin"
        [Gleiche Artikel-Struktur wie Article 1, OHNE StepFlow]
```

**Abstände & Layout:**
- Section Padding: py-16 (64px) @ Mobile, py-20 (80px) @ Desktop
- Article Padding: 24px
- StepFlow Padding: px-6 py-8 @ Mobile, px-8 py-8 @ Desktop
- Steps Grid Gap: 16px
- Step Card Padding: 20px

---

### SECTION 4: PAINS (Light Surface - Herausforderungen)

**Komponente:** `<Section tone="light" id="pains" />`
**Layout-Pattern:** Header + ContentBoxDark + 3-Column Pains Grid
**Hintergrund:** `var(--surface-light)` (#F9FAFB)

**Semantik & Content:**

```
SECTION#pains (tone: light, padding: py-16 md:py-20)
│
├── Header-Bereich
│   Max-width: 768px
│   Margin-bottom: 48px (mb-12)
│   │
│   ├── H2
│   │   Text: "Herausforderungen aus Ihren Projekten"
│   │   Font: Inter Bold, 1.875rem (30px) @ Mobile, 2.25rem (36px) @ Desktop
│   │   Farbe: #0B101A
│   │   Line-height: tight
│   │
│   └── Paragraph
│       Text: "Gespräche mit Teams zeigen wiederkehrende Muster. Wir adressieren sie mit klaren Workflows, Governance und Messpunkten."
│       Font: Inter Regular, 16px @ Mobile, 18px @ Desktop
│       Farbe: #4B5563
│       Line-height: relaxed
│       Margin-top: 16px
│
├── ContentBoxDark: "Unser Ansatz für nachhaltige Lösungen"
│   Heading: "Unser Ansatz für nachhaltige Lösungen"
│   HeadingLevel: h3
│   Margin-bottom: 48px (mb-12)
│   [Background/Border/Padding wie auf Branchen-Übersicht]
│   │
│   ├── Paragraph
│   │   Text: "Wir kombinieren Best Practices aus vergleichbaren Projekten mit branchenspezifischen Anforderungen. Jede Lösung wird auf Ihre Governance-Vorgaben und Teamstrukturen zugeschnitten."
│   │   Font: Inter Regular, 14px
│   │   Farbe: rgba(249,250,251,0.72)
│   │   Line-height: relaxed
│   │   Margin-bottom: 16px (mb-4)
│   │
│   └── UL (3 Checkmark Items)
│       Space-y: 12px
│       │
│       ├── LI 1: "Klare **KPI-Definition** vor Projektstart mit messbaren Erfolgskriterien"
│       ├── LI 2: "**Iterative Validierung** mit Stakeholdern und Endnutzern in kurzen Zyklen"
│       └── LI 3: "**Hand-over & Enablement** Ihres Teams für langfristige Autonomie"
│       [Icon-Container + Text-Struktur wie auf Branchen-Übersicht]
│
└── Pains-Grid
    Display: grid
    Grid-cols: 1 @ Mobile, 2 @ Tablet (md:), 3 @ Desktop (xl:)
    Gap: 24px (gap-6)
    │
    ├── Pain-Card 1: "Local Packs & AI Overviews dominieren Suchergebnisse"
    │   Background: white
    │   Border: 1px solid rgba(226,232,240,0.7)
    │   Border-radius: 16px
    │   Padding: 24px
    │   Shadow: subtle → large on hover
    │   Transition: all 300ms
    │   │
    │   ├── H3
    │   │   Text: "Local Packs & AI Overviews dominieren Suchergebnisse"
    │   │   Font: Inter SemiBold, 18px (1.125rem)
    │   │   Farbe: #0B101A
    │   │   Line-height: snug
    │   │   Margin-bottom: 12px
    │   │
    │   └── Summary
    │       Text: "Wettbewerber sichern die Sichtbarkeit in entscheidenden Locations und werden in AI Overviews zitiert, obwohl Ihre Kanzlei fachlich führend ist."
    │       Font: Inter Regular, 14px
    │       Farbe: #4B5563
    │       Line-height: relaxed
    │
    ├── Pain-Card 2: "Intake dauert zu lange und Unterlagen fehlen"
    │   [Gleiche Card-Struktur]
    │   Summary: "Sekretariat und Associates verfolgen Dokumente hinterher; Termine finden statt, bevor ein Vollbild der Sachlage vorliegt."
    │
    └── Pain-Card 3: "Pitch-Teams improvisieren Präsentationen"
        [Gleiche Card-Struktur]
        Summary: "Kein zentrales Content-Hub für Claims, Corporate Case Studies oder Precedents – Wissen steckt in Silos."
```

**Abstände & Layout:**
- Section Padding: py-16 (64px) @ Mobile, py-20 (80px) @ Desktop
- ContentBox Margin-bottom: 48px
- Grid Gap: 24px
- Card Padding: 24px
- Hover: translateY(-4px), shadow-lg

---

### SECTION 5: SOLUTIONS (Dark Navy - Lösungen & Module)

**Komponente:** `<Section tone="dark" id="solutions" />`
**Layout-Pattern:** Header + 3-Column Solutions Grid
**Hintergrund:** `var(--brand-primary-900)` (#04060D)

**Semantik & Content:**

```
SECTION#solutions (tone: dark, padding: py-16 md:py-20)
│
├── Header-Bereich
│   Max-width: 768px
│   Margin-bottom: 48px (mb-12)
│   │
│   ├── H2
│   │   Text: "Lösungen & Module, die den Unterschied machen"
│   │   Font: Inter Bold, 1.875rem (30px) @ Mobile, 2.25rem (36px) @ Desktop
│   │   Farbe: white
│   │   Line-height: tight
│   │
│   └── Paragraph
│       Text: "Jedes Modul lässt sich kombinieren: Intake-Flows, Servicecockpits, Compliance-Bausteine und Automationen werden im Projekt auf Ihre Prozesse abgestimmt."
│       Font: Inter Regular, 16px @ Mobile, 18px @ Desktop
│       Farbe: rgba(255,255,255,0.8)
│       Line-height: relaxed
│       Margin-top: 16px
│
└── Solutions-Grid
    Display: grid
    Grid-cols: 1 @ Mobile, 2 @ Tablet (md:), 3 @ Desktop (xl:)
    Gap: 24px (gap-6)
    │
    ├── Solution-Card 1: "GEO-Cluster & FAQ-Schema"
    │   Background: linear-gradient(to bottom right, white, white, #F9FAFB)
    │   Border: 1px solid rgba(226,232,240,0.7)
    │   Border-radius: 16px
    │   Padding: 24px
    │   Shadow: subtle
    │   Hover: translateY(-1px), shadow-lg
    │   Transition: all 300ms
    │   ID: "geo-cluster-faq-schema" (sanitized from title)
    │   │
    │   ├── Icon-Row
    │   │   Display: flex items-center gap-3
    │   │   Margin-bottom: 12px (mb-3)
    │   │   │
    │   │   ├── Icon-Container
    │   │   │   Size: 36px × 36px (w-9 h-9)
    │   │   │   Background: `var(--surface-light)` (#F9FAFB)
    │   │   │   Border: 1px solid rgba(226,232,240,0.7)
    │   │   │   Border-radius: 12px (rounded-xl)
    │   │   │   Display: flex items-center justify-center
    │   │   │   │
    │   │   │   └── SVG Checkmark
    │   │   │       Size: 16px × 16px
    │   │   │       Stroke: #4B5563
    │   │   │       Path: "M5 13l4 4L19 7"
    │   │   │
    │   │   └── H3
    │   │       Text: "GEO-Cluster & FAQ-Schema"
    │   │       Font: Inter SemiBold, 18px
    │   │       Farbe: #0B101A
    │   │       Line-height: tight
    │   │
    │   ├── Summary
    │   │   Text: "Topic-Cluster, Entity-Mapping und Review-Strategien sorgen für Sichtbarkeit in Google Local, Bing und AI Overviews."
    │   │   Font: Inter Regular, 14px
    │   │   Farbe: #4B5563
    │   │   Line-height: relaxed
    │   │   │
    │   │   └── Inline InfoTooltip
    │   │       Component: <InfoTooltip termId="geo" mode="modal" />
    │   │       Display: inline-flex items-center ml-1 align-middle
    │   │
    │   └── Proof-Badge
    │       Text: "Impact: +5 Städte im Local Pack"
    │       Font: Inter SemiBold, 14px
    │       Farbe: #0B101A
    │       Margin-top: 12px (mt-3)
    │
    ├── Solution-Card 2: "Mandanten-Intake mit Logging"
    │   [Gleiche Card-Struktur]
    │   Summary: "Mehrstufiger Intake mit Dokument-Upload, Konfliktcheck und verschlüsselter Ablage – revisionssicher und BRAO-konform."
    │   InfoTooltip: termId="gitops"
    │   Proof: "Dokumenten-Nachfassaufwand −30 %"
    │
    └── Solution-Card 3: "Pitch Content Hub"
        [Gleiche Card-Struktur]
        Summary: "Case Vault, Claim Boards und modulare Slides mit Freigabe-Workflow – immer aktuelle Story für Litigation & Corporate."
        Proof: "Pitch-Vorbereitungszeit −25 %"
        (Kein InfoTooltip auf dieser Card)
```

**Abstände & Layout:**
- Section Padding: py-16 (64px) @ Mobile, py-20 (80px) @ Desktop
- Grid Gap: 24px
- Card Padding: 24px
- Icon-Container: 36px × 36px

---

### SECTION 6: WEBAPPS (Dark Navy - WebApps & Automationen)

**Komponente:** `<Section tone="dark" id="webapps" />`
**Layout-Pattern:** Header + 3-Column WebApps Grid
**Hintergrund:** `var(--brand-primary-900)` (#04060D)

**Semantik & Content:**

```
SECTION#webapps (tone: dark, padding: py-16 md:py-20, text: white)
│
├── Header-Bereich
│   Max-width: 768px
│   Margin-bottom: 48px (mb-12)
│   │
│   ├── H2
│   │   Text: "WebApps & Automationen als Baustein"
│   │   Font: Inter Bold, 1.875rem (30px) @ Mobile, 2.25rem (36px) @ Desktop
│   │   Farbe: white
│   │   Line-height: tight
│   │
│   └── Paragraph
│       Text: "Unsere WebApps laufen performant auf Astro + Cloudflare Workers, sind barrierefrei, DSGVO-konform und integrieren sich in Ihre Toolchain."
│       Font: Inter Regular, 16px @ Mobile, 18px @ Desktop
│       Farbe: rgba(255,255,255,0.8)
│       Line-height: relaxed
│       Margin-top: 16px
│
└── WebApps-Grid
    Display: grid
    Grid-cols: 1 @ Mobile, 2 @ Tablet (md:), 3 @ Desktop (xl:)
    Gap: 24px (gap-6)
    │
    ├── WebApp-Card 1: "Mandatsaufnahme Wizard"
    │   Background: rgba(255,255,255,0.08)
    │   Border: 1px solid rgba(148,163,184,0.18)
    │   Border-radius: 16px
    │   Padding: 24px
    │   Shadow: 0 40px 80px -60px rgba(15,23,42,0.9)
    │   Backdrop-filter: blur(2px)
    │   │
    │   ├── H3
    │   │   Text: "Mandatsaufnahme Wizard"
    │   │   Font: Inter SemiBold, 18px
    │   │   Farbe: white
    │   │   Line-height: tight
    │   │
    │   ├── Description
    │   │   Text: "10–15 Fragen, Uploads und Priorisierung – bereit für CRM & DMS."
    │   │   Font: Inter Regular, 14px
    │   │   Farbe: rgba(255,255,255,0.8)
    │   │   Line-height: relaxed
    │   │   Margin-top: 12px (mt-3)
    │   │
    │   ├── Outcome
    │   │   Text: "Lead-to-Call Rate steigt, Telefonlast sinkt."
    │   │   Font: Inter SemiBold, 14px
    │   │   Farbe: #85D4B2 (emerald-300)
    │   │   Margin-top: 16px (mt-4)
    │   │
    │   ├── Tech-Stack-Label
    │   │   Text: "Tech Stack"
    │   │   Font: Inter SemiBold, 12px, uppercase, tracking: 0.25em
    │   │   Farbe: rgba(255,255,255,0.6)
    │   │   Margin-top: 16px (mt-4)
    │   │
    │   └── Tech-Stack-Badges
    │       Display: flex flex-wrap gap-2
    │       Margin-top: 8px (mt-2)
    │       │
    │       ├── Badge: "Astro"
    │       │   Background: rgba(255,255,255,0.12)
    │       │   Border: 1px solid rgba(148,163,184,0.18)
    │       │   Padding: px-3 py-1, rounded-full
    │       │   Font: Inter SemiBold, 12px
    │       │   Farbe: rgba(255,255,255,0.85)
    │       │
    │       ├── Badge: "Cloudflare Workers"
    │       ├── Badge: "D1"
    │       └── Badge: "DocuSign"
    │
    ├── WebApp-Card 2: "Case Vault"
    │   [Gleiche Card-Struktur]
    │   Description: "Durchsuchbare Case Study Bibliothek mit Freigaben, Tags und Export."
    │   Outcome: "Pitch-Teams bauen in Minuten überzeugende Unterlagen."
    │   Tech-Stack: "Astro", "Sanity", "Edge Search"
    │
    └── WebApp-Card 3: "Kapazitäts- & Terminplaner"
        [Gleiche Card-Struktur]
        Description: "Synchronisiert Anwält:innen-Kapazitäten, zeigt Slots und verschickt ICS + SMS."
        Outcome: "Terminplanung automatisiert, weniger No-Shows."
        Tech-Stack: "Calendar API", "Cloudflare KV", "Twilio"
```

**Abstände & Layout:**
- Section Padding: py-16 (64px) @ Mobile, py-20 (80px) @ Desktop
- Grid Gap: 24px
- Card Padding: 24px
- Badge Gap: 8px

---

### SECTION 7: KPI (Light Surface - KPIs & Proof)

**Komponente:** `<Section tone="light" id="kpi" />`
**Layout-Pattern:** Header + 3-Column KPI Grid
**Hintergrund:** `var(--surface-light)` (#F9FAFB)

**Semantik & Content:**

```
SECTION#kpi (tone: light, padding: py-16 md:py-20)
│
├── Header-Bereich
│   Max-width: 768px
│   Margin-bottom: 48px (mb-12)
│   │
│   ├── H2
│   │   Text: "KPIs & Proof"
│   │   Font: Inter Bold, 1.875rem (30px) @ Mobile, 2.25rem (36px) @ Desktop
│   │   Farbe: #0B101A
│   │   Line-height: tight
│   │   Padding-y: 16px (md:py-4) @ Desktop only
│   │
│   └── Paragraph
│       Text: "Wir arbeiten KPI-basiert. Diese Kennzahlen zeigen, welche Ziele wir in vergleichbaren Projekten erreichen."
│       Font: Inter Regular, 16px @ Mobile, 18px @ Desktop
│       Farbe: #4B5563
│       Line-height: relaxed
│       Margin-top: 16px
│
└── KPI-Grid
    Display: grid
    Grid-cols: 1 @ Mobile, 3 @ Desktop (md:grid-cols-3)
    Gap: 24px (gap-6)
    │
    ├── KPI-Card 1: "Lead-to-Call Rate"
    │   Background: white
    │   Border: 1px solid rgba(226,232,240,0.7)
    │   Border-radius: 16px
    │   Padding: 24px
    │   Text-align: center
    │   Shadow: subtle
    │   │
    │   ├── Metric-Label
    │   │   Text: "Lead-to-Call Rate"
    │   │   Font: Inter SemiBold, 14px, uppercase, tracking: 0.18em
    │   │   Farbe: #6B7280
    │   │
    │   ├── Value
    │   │   Text: "+35 %"
    │   │   Font: Inter Bold, 3rem (48px)
    │   │   Farbe: #0B101A
    │   │   Margin-top: 8px (mt-2)
    │   │
    │   └── Source (optional, falls vorhanden)
    │       Text: "Quelle: [...]"
    │       Font: Inter Regular, 12px
    │       Farbe: #6B7280
    │       Margin-top: 12px (mt-3)
    │
    ├── KPI-Card 2: "Telefonaufwand"
    │   [Gleiche Card-Struktur]
    │   Value: "−25 %"
    │
    └── KPI-Card 3: "Local Pack Präsenz"
        [Gleiche Card-Struktur]
        Value: "+5 Städte"
```

**Abstände & Layout:**
- Section Padding: py-16 (64px) @ Mobile, py-20 (80px) @ Desktop
- Grid Gap: 24px
- Card Padding: 24px
- Text-align: center

---

### SECTION 8: FAQ (Dark Navy - Häufige Fragen)

**Komponente:** `<Section tone="dark" id="faq" />`
**Layout-Pattern:** Header + Accordion-Style Details/Summary
**Hintergrund:** `var(--brand-primary-900)` (#04060D)

**Semantik & Content:**

```
SECTION#faq (tone: dark, padding: py-16 md:py-20)
│
├── Header-Bereich
│   Max-width: 768px
│   Margin-bottom: 48px (mb-12)
│   │
│   ├── H2
│   │   Text: "Häufige Fragen aus Projekten"
│   │   Font: Inter Bold, 1.875rem (30px) @ Mobile, 2.25rem (36px) @ Desktop
│   │   Farbe: white
│   │   Line-height: tight
│   │
│   └── Paragraph
│       Text: "Transparente Antworten – damit Sie wissen, wie Zusammenarbeit, Technik und Governance aussehen."
│       Font: Inter Regular, 16px @ Mobile, 18px @ Desktop
│       Farbe: rgba(255,255,255,0.8)
│       Line-height: relaxed
│       Margin-top: 16px
│
└── FAQ-Container
    Max-width: 1024px (max-w-4xl)
    Space-y: 16px (space-y-4)
    │
    ├── Details 1: "Wie lange dauert ein Relaunch für Boutique-Kanzleien?"
    │   Element: <details>
    │   ID: "wie-lange-dauert-ein-relaunch-fur-boutique-kanzleien" (sanitized)
    │   Klasse: group
    │   Background: white
    │   Border: 1px solid rgba(226,232,240,0.7)
    │   Border-radius: 16px
    │   Padding: 24px
    │   Shadow: 0 25px 65px -60px rgba(15,23,42,0.35)
    │   │
    │   ├── Summary
    │   │   Display: flex items-center justify-between gap-4
    │   │   Text-align: left
    │   │   Cursor: pointer
    │   │   │
    │   │   ├── Question-Text
    │   │   │   Text: "Wie lange dauert ein Relaunch für Boutique-Kanzleien?"
    │   │   │   Font: Inter SemiBold, 18px (1.125rem)
    │   │   │   Farbe: #0B101A
    │   │   │
    │   │   └── Icon (Plus → X on open)
    │   │       SVG: Plus-Icon
    │   │       Size: 20px × 20px
    │   │       Farbe: #4B5563
    │   │       Transition: transform 200ms
    │   │       Transform: rotate(45deg) when open (group-open:rotate-45)
    │   │
    │   └── Answer-Content (Hidden until open)
    │       Margin-top: 16px (mt-4)
    │       │
    │       ├── Answer-Paragraph
    │       │   Text: "In der Regel 8–10 Wochen: 2 Wochen Strategie & UX, 3 Wochen Content & Module, 2 Wochen Development & QA, 1–2 Wochen Softlaunch und Iterationen."
    │       │   Font: Inter Regular, 16px
    │       │   Farbe: #4B5563
    │       │   Line-height: relaxed
    │       │
    │       └── AI-Snippet (optional)
    │           Text: "AI Snippet: Boutique-Kanzleien planen mit 8–10 Wochen von Strategie bis Go-Live."
    │           Font: Inter SemiBold, 12px, uppercase, tracking: 0.18em
    │           Farbe: #4B5563
    │           Margin-top: 12px (mt-3)
    │
    ├── Details 2: "Welche Systeme integrieren Sie für Dokumente und CRM?"
    │   [Gleiche Details-Struktur]
    │   Answer: "Wir binden DATEV, Actaport, Legal One oder Ihr bestehendes CRM via API ein. Uploads laufen verschlüsselt über Cloudflare Workers und landen revisionssicher im DMS Ihrer Wahl."
    │   AI-Snippet: "Uploads laufen verschlüsselt via Workers in Ihr DMS oder CRM (DATEV, Actaport, Legal One)."
    │
    └── Details 3: "Wie stellen Sie Vertraulichkeit im Intake sicher?"
        [Gleiche Details-Struktur]
        Answer: "Intake-Flows nutzen verschlüsselte Speicherung, Zugriffskontrollen und automatische Löschfristen. Außerdem dokumentieren wir Zugriffe und stellen Audit-Logs bereit."
        AI-Snippet: "Verschlüsselung, Zugriffsrechte und Audit-Logs sichern vertrauliche Intake-Daten."
```

**Abstände & Layout:**
- Section Padding: py-16 (64px) @ Mobile, py-20 (80px) @ Desktop
- FAQ-Container Max-width: 1024px
- Space between Details: 16px
- Details Padding: 24px

---

### SECTION 9: GLOSSARY (Light Surface - Relevante Glossarbegriffe)

**Komponente:** `<Section tone="light" id="glossary" />`
**Layout-Pattern:** Header + Badge-Links (Conditional)
**Hintergrund:** `var(--surface-light)` (#F9FAFB)

**Semantik & Content:**

```
SECTION#glossary (tone: light, padding: py-16 md:py-20)
│ (Nur angezeigt, wenn glossaryLinks.length > 0)
│
├── Header-Bereich
│   Max-width: 768px
│   Margin-bottom: 40px (mb-10)
│   │
│   ├── H2
│   │   Text: "Relevante Glossarbegriffe"
│   │   Font: Inter Bold, 1.875rem (30px) @ Mobile, 2.25rem (36px) @ Desktop
│   │   Farbe: #0B101A
│   │   Line-height: tight
│   │
│   └── Paragraph
│       Text: "Für Stakeholder, die Fachbegriffe schnell nachschlagen möchten."
│       Font: Inter Regular, 16px @ Mobile, 18px @ Desktop
│       Farbe: #4B5563
│       Line-height: relaxed
│       Margin-top: 16px
│
└── Badge-Links Container
    Display: flex flex-wrap gap-3
    │
    ├── Link-Badge 1: "geo"
    │   Href: /wissen/glossar/geo/
    │   Display: inline-flex items-center gap-2
    │   Padding: px-4 py-2
    │   Border-radius: 9999px (rounded-full)
    │   Border: 1px solid rgba(226,232,240,0.7)
    │   Background: white
    │   Font: Inter SemiBold, 14px
    │   Farbe: #4B5563
    │   Hover: border rgba(17,24,39,0.18), color #0B101A
    │   Transition: all 300ms
    │   │
    │   ├── Book-Icon (SVG)
    │   │   Size: 16px × 16px
    │   │   Path: "M4 19V5a2 2 0 012-2h11a3 3 0 013 3v13a2 2 0 00-2-2H6a2 2 0 00-2 2zm2 0a2 2 0 012-2h12"
    │   │   Stroke: currentColor
    │   │
    │   └── Text: "geo"
    │       (slug wird mit replace(/-/g, ' ') formatiert)
    │
    ├── Link-Badge 2: "aeo"
    │   [Gleiche Struktur]
    │
    ├── Link-Badge 3: "gitops"
    │   [Gleiche Struktur]
    │
    └── Link-Badge 4: "consent mode v2"
        [Gleiche Struktur]
```

**Abstände & Layout:**
- Section Padding: py-16 (64px) @ Mobile, py-20 (80px) @ Desktop
- Badge Gap: 12px (gap-3)
- Badge Padding: px-4 py-2 (16px/8px)

---

### SECTION 10: CTA (Light Surface - Final Call-to-Action)

**Komponente:** `<Section tone="light" id="cta" />`
**Layout-Pattern:** ContentBoxDark mit 2-Column Layout + Steps-Card
**Hintergrund:** `var(--surface-light)` (#F9FAFB)

**Semantik & Content:**

```
SECTION#cta (tone: light, padding: py-24 md:py-32)
│
└── Container (max-width: 1152px, mx-auto)
    │
    └── ContentBoxDark
        Heading: "Mandate schneller qualifizieren?"
        HeadingLevel: h2
        [Background/Border/Padding/Shadow wie auf Branchen-Übersicht]
        │
        ├── H2: "Mandate schneller qualifizieren?"
        │   [Styling wie auf Branchen-Übersicht]
        │
        └── Grid-Layout (2-Spalten @ Large: 1.5fr + 1fr)
            Gap: 48px (gap-12)
            Items-align: start
            │
            ├── Haupt-Content (linke Spalte)
            │   │
            │   ├── Subline-Paragraph
            │   │   Text: "Wir entwickeln Intake-Flows, Pitch-Hubs und KPI-Dashboards, die Partner:innen entlasten."
            │   │   Font: Inter Regular, 16px @ Mobile, 18px @ Desktop
            │   │   Farbe: rgba(249,250,251,0.72)
            │   │   Line-height: relaxed
            │   │
            │   └── Button-Gruppe
            │       Margin-top: 32px (mt-8)
            │       Display: flex flex-wrap gap-4
            │       │
            │       ├── Button Primary
            │       │   Label: "Strategie-Call buchen"
            │       │   Href: /kontakt
            │       │   [Styling: btn-primary-light mit White→Silver Gradient]
            │       │
            │       └── Button Secondary
            │           Label: "Case Vault anschauen"
            │           Href: /wissen#case-studies
            │           Background: transparent
            │           Border: 2px solid rgba(255,255,255,0.6)
            │           Farbe: white
            │           Hover: background rgba(255,255,255,0.12)
            │
            └── Steps-Card (rechte Spalte)
                Background: rgba(255,255,255,0.08)
                Border: 1px solid rgba(148,163,184,0.18)
                Border-radius: 24px
                Padding: 32px (p-8)
                Backdrop-filter: blur(2px)
                Space-y: 16px (space-y-4)
                │
                ├── Label: "Nächste Schritte"
                │   Font: Inter Regular, 14px
                │   Farbe: rgba(255,255,255,0.75)
                │
                └── UL (3 Checkmark Items)
                    Space-y: 12px (space-y-3)
                    │
                    ├── LI 1: "Strategie-Workshop mit KPI-Set & Roadmap"
                    ├── LI 2: "UX/Content-Sprint zur Validierung Ihrer Module"
                    └── LI 3: "Launch inkl. Monitoring & Hand-over an Ihr Team"
                    [Icon + Text-Struktur mit Emerald-Checkmarks]
```

**Abstände & Layout:**
- Section Padding: py-24 (96px) @ Mobile, py-32 (128px) @ Desktop
- Grid Gap: 48px
- Steps-Card Padding: 32px
- Space between list-items: 12px

---

### SECTION 11: MORE BRANCHES (Light Surface - Weitere Branchenlösungen)

**Komponente:** `<Section tone="light" id="more-branches" />`
**Layout-Pattern:** Header + 3-Column Branch-Cards (Conditional)
**Hintergrund:** `var(--surface-light)` (#F9FAFB)

**Semantik & Content:**

```
SECTION#more-branches (tone: light, padding: py-16 md:py-20)
│ (Nur angezeigt, wenn siblings.length > 0)
│ Border-top: 1px solid rgba(226,232,240,0.7)
│
├── H2
│   Text: "Weitere Branchenlösungen"
│   Font: Inter Bold, 1.5rem (24px) @ Mobile, 1.875rem (30px) @ Desktop
│   Farbe: #0B101A
│   Margin-bottom: 24px (mb-6)
│
└── Branch-Cards Grid
    Display: grid
    Grid-cols: 1 @ Mobile, 2 @ Tablet (md:), 3 @ Desktop (xl:)
    Gap: 24px (gap-6)
    │
    ├── Branch-Card 1: [Sibling Branch 1]
    │   Component: <a>
    │   Href: /branchen/{sibling.slug}
    │   Background: white
    │   Border: 1px solid rgba(226,232,240,0.7)
    │   Border-radius: 16px
    │   Padding: 24px
    │   Shadow: subtle
    │   Hover: translateY(-1px), shadow-lg
    │   Transition: all 300ms
    │   │
    │   ├── Label: "Branche"
    │   │   Font: Inter SemiBold, 12px, uppercase, tracking: 0.32em
    │   │   Farbe: #4B5563
    │   │
    │   ├── H3: [sibling.title]
    │   │   Font: Inter SemiBold, 18px
    │   │   Farbe: #0B101A
    │   │   Line-height: tight
    │   │   Margin-top: 12px (mt-3)
    │   │
    │   ├── Deck: [sibling.intro.deck]
    │   │   Font: Inter Regular, 14px
    │   │   Farbe: #4B5563
    │   │   Line-height: relaxed
    │   │   Margin-top: 8px (mt-2)
    │   │
    │   └── Link-Text: "Zur Seite"
    │       Display: inline-flex items-center gap-2
    │       Font: Inter SemiBold, 14px
    │       Farbe: #0B101A
    │       Margin-top: 16px (mt-4)
    │       │
    │       └── Arrow-Icon (SVG)
    │           Size: 16px × 16px
    │           Path: "M17 8l4 4m0 0l-4 4m4-4H7"
    │
    ├── Branch-Card 2: [Sibling Branch 2]
    │   [Gleiche Struktur]
    │
    └── Branch-Card 3: [Sibling Branch 3]
        [Gleiche Struktur]
        Note: siblings.slice(0, 3) - Maximal 3 Sibling-Branches
```

**Abstände & Layout:**
- Section Padding: py-16 (64px) @ Mobile, py-20 (80px) @ Desktop
- Border-top: 1px solid
- Grid Gap: 24px
- Card Padding: 24px

---

### FOOTER

**Komponente:** `<Footer slot="footer" />`
**Datei:** `/src/components/Footer.astro`

*(Gleiche Struktur wie andere Seiten)*

---

## 🎨 DESIGN-SYSTEM-DETAILS

### Farbnutzung (Section-übergreifend)

| Element | CSS-Variable | Hex/rgba-Wert | Verwendung |
|---------|--------------|---------------|------------|
| Hero Background | `--brand-primary-900` | #04060D | Dark Grid Hero |
| Hero Text Primary | `--text-primary-on-dark` | #F9FAFB | H1 Headline |
| Hero Text Secondary | `--text-secondary-on-dark` | rgba(249,250,251,0.72) | Subtitle |
| Hero Badge BG | - | rgba(255,255,255,0.08) | Badge Background |
| Hero Badge Border | `--border-on-dark-subtle` | rgba(148,163,184,0.18) | Badge Border |
| Light Section BG | `--surface-light` | #F9FAFB | Tasks/Pains/KPI/Glossary/CTA/More |
| Dark Section BG | `--brand-primary-900` | #04060D | Path/Solutions/WebApps/FAQ |
| Card BG (Light) | - | #FFFFFF | Branch/Task/Pain/KPI Cards |
| Card BG (Dark) | - | rgba(255,255,255,0.08) | WebApps Cards |
| Card Border (Light) | `--border-on-light-subtle` | rgba(226,232,240,0.7) | Light Cards |
| Card Border (Dark) | `--border-on-dark-subtle` | rgba(148,163,184,0.18) | Dark Cards |
| Text on Light Primary | `--text-on-light-primary` | #0B101A | Headlines auf Light BG |
| Text on Light Secondary | `--text-on-light-secondary` | #4B5563 | Body-Text auf Light BG |
| Text on Light Muted | `--text-on-light-muted` | #6B7280 | Labels/Small Text |
| Emerald Checkmarks | - | #85D4B2 (emerald-300) | Success Icons, WebApp Outcomes |
| Button Gradient White | - | #FFFFFF → #E5E7EB | Primary Button Background |
| StepFlow Hover Glow | - | rgba(148,163,184,0.15) | Radial gradient on step cards |

### Typografie-Details

| Element | Font-Family | Mobile Size | Desktop Size | Weight | Line-Height | Letter-Spacing |
|---------|-------------|-------------|--------------|---------|-------------|----------------|
| H1 (Hero) | Inter | 2.25rem (36px) | 4.5rem (72px) | ExtraBold (800) | 1.15 (tight) | -0.02em |
| H2 (Sections) | Inter | 1.875rem (30px) | 2.25rem (36px) | Bold (700) | 1.25 (tight) | 0 |
| H2 (Path Section) | Inter | 1.5rem (24px) | 1.875rem (30px) | Bold (700) | 1.25 (tight) | 0 |
| H3 (Cards) | Inter | 1.125rem (18px) | 1.25rem (20px) | SemiBold (600) | 1.25 (tight) | 0 |
| H4 (StepFlow Title) | Inter | 1.25rem (20px) | 1.25rem (20px) | SemiBold (600) | 1.25 (tight) | 0 |
| Body (Sections) | Inter | 1rem (16px) | 1.125rem (18px) | Regular (400) | 1.75 (relaxed) | 0 |
| Body Small | Inter | 0.875rem (14px) | 1rem (16px) | Regular (400) | 1.75 (relaxed) | 0 |
| Step Card Number | Inter | 0.75rem (12px) | 0.75rem (12px) | SemiBold (600) | 1.5 (normal) | 0.26em |
| Badge/Label | Inter | 0.75rem (12px) | 0.75rem (12px) | SemiBold (600) | 1.5 (normal) | 0.22-0.32em |
| KPI Value | Inter | 3rem (48px) | 3rem (48px) | Bold (700) | 1.2 | 0 |

### Shadow-System

| Name | Value | Verwendung |
|------|-------|------------|
| `--shadow-premium` | 3-layer shadow (border + depth + glow) | ContentBoxDark |
| Subtle | 0 1px 2px rgba(0,0,0,0.05) | Light Cards (Rest) |
| Large (Hover) | 0 20px 25px -5px rgba(0,0,0,0.1) | Light Cards (Hover) |
| WebApp Shadow | 0 40px 80px -60px rgba(15,23,42,0.9) | Dark WebApp Cards |
| FAQ Shadow | 0 25px 65px -60px rgba(15,23,42,0.35) | FAQ Details Elements |

---

## 📱 RESPONSIVE BREAKPOINTS

| Breakpoint | Screen-Width | Grid-Cols (Cards) | Grid-Cols (StepFlow) | H1 Font-Size | Section Padding |
|------------|--------------|-------------------|----------------------|--------------|-----------------|
| Mobile | <640px | 1 | 1 | 2.25rem (36px) | px-6 py-16 |
| Tablet | 640-1023px | 2 (md:) | 2 (md:) | 3rem (48px) | px-8 py-20 |
| Desktop | ≥1024px | 3 (xl:) | 4 (xl:grid-cols-4) | 4.5rem (72px) | px-12 py-20 |

**Hauptänderungen:**
- **Hero:** Left-aligned (nicht centered), H1: 36px → 48px → 72px
- **Task/Pain/Solution Cards:** 1-col → 2-col → 3-col
- **StepFlow:** 1-col → 2-col → 4-col (spezielle Breakpoint für xl:grid-cols-4)
- **CTA Grid:** 1-col @ Mobile/Tablet, 2-col (1.5fr + 1fr) @ Desktop (lg:)

---

## 🧩 KOMPONENTEN-BIBLIOTHEK

### Genutzte Astro-Components

| Komponente | Datei | Props (Key-Value-Paare) |
|------------|-------|-------------------------|
| `<Base>` | `/src/layouts/Base.astro` | title, description, canonical |
| `<Nav>` | `/src/components/Nav.astro` | variant="transparent", slot="header" |
| `<Hero>` | `/src/components/Hero.astro` | title, subtitle, badge, ctaText, ctaHref, showSecondaryCta={false}, tertiaryCtaText, tertiaryCtaHref, align="left", variant="dark-grid", minHeightStyle="min-height:100vh;min-height:100dvh;" |
| `<Section>` | `/src/components/Section.astro` | tone="light/dark", id="tasks/path/pains/solutions/webapps/kpi/faq/glossary/cta/more-branches", aria-labelledby="...", class="py-16 md:py-20" |
| `<CardGroup>` | `/src/components/CardGroup.astro` | tone="light", mobilePattern="accordion", columns={3}, items=[quickLinks] |
| `<InfoTooltip>` | `/src/components/InfoTooltip.astro` | termId="geo/gitops", mode="modal" |
| `<ContentBoxDark>` | `/src/components/ContentBoxDark.astro` | heading="...", headingLevel="h2/h3", class="mb-12" |
| `<Footer>` | `/src/components/Footer.astro` | slot="footer" |

### Dynamische Daten aus JSON

**Data Loading (getStaticPaths):**
```astro
const branches = await getCollection('branchen');
const entry = branches.find(b => b.data.slug === 'kanzleien');
const data = entry.data;
```

**QuickLinks Mapping:**
```astro
const quickLinks = data.topTasks.map((task) => ({
  label: task.label,
  description: task.description,
  href: task.link,
  badge: task.audience,
  icon: 'M17 8l4 4m0 0l-4 4m4-4H3',
}));
```

**Conditional Rendering:**
- StepFlow wird nur bei `index === 0` (erste Task-Card) angezeigt
- Glossary Section wird nur bei `glossaryLinks.length > 0` angezeigt
- More Branches Section wird nur bei `siblings.length > 0` angezeigt

---

## 🔍 SEO & STRUKTURIERTE DATEN

### Schema.org Markup

**Typ:** LegalService + ProfessionalService

**JSON-LD:**
```json
{
  "@context": "https://schema.org",
  "@type": ["LegalService", "ProfessionalService"],
  "name": "Kanzleien & Boutiquen",
  "url": "https://www.wolf-agents.com/branchen/kanzleien",
  "audience": ["Unternehmen", "Private Mandanten"],
  "areaServed": ["DE", "AT", "CH"],
  "serviceType": "Digitale Mandatsreisen für spezialisierte Kanzleien"
}
```

**FAQPage Markup:** Könnte hinzugefügt werden für FAQ-Section (aktuell nicht implementiert, aber FAQ-Daten vorhanden mit `aiSnippet` für Featured Snippets)

### Open Graph / Twitter Card

- `og:title`: "Kanzleien & Boutiquen – Branchenlösung | Wolf-Agents"
- `og:description`: "Wir verbinden Geo-optimierte Inhalte, Intake-Flows und Governance..."
- `og:url`: https://www.wolf-agents.com/branchen/kanzleien
- `og:type`: website

---

## ♿ BARRIEREFREIHEIT (WCAG 2.2)

### Kontrast-Ratios

| Text | Hintergrund | Ratio | Status |
|------|-------------|-------|--------|
| H1 Hero (#F9FAFB) | Dark BG (#04060D) | 19.2:1 | ✅ AAA |
| Body on Light (#4B5563) | Light BG (#F9FAFB) | 8.1:1 | ✅ AAA |
| Body on Dark (rgba(255,255,255,0.8)) | Dark BG (#04060D) | 16.5:1 | ✅ AAA |
| Emerald Checkmarks (#85D4B2) | Dark BG (#04060D) | 7.2:1 | ✅ AA |
| FAQ Summary (#0B101A) | White BG (#FFFFFF) | 16.1:1 | ✅ AAA |

### Semantische HTML-Struktur

- ✅ `<nav>`, `<main>`, `<section>`, `<article>`, `<aside>`, `<footer>`
- ✅ H1 → H2 → H3 → H4 korrekt verschachtelt
- ✅ `aria-labelledby` auf Sections
- ✅ `aria-label` auf StepFlow-Grid
- ✅ `<details>` mit `<summary>` für FAQ-Accordion

### Interaktive Elemente

- ✅ Focus-Rings auf Buttons/Links
- ✅ Touch-Targets ≥ 44px × 44px
- ✅ Hover-States visuell erkennbar
- ✅ Details/Summary keyboard-accessible

---

## 🎯 CONTENT-STRATEGIE & TARGETING

### Hauptthema

Digitale Mandatsreisen für Kanzleien: Intake-Flows, Pitch-Content-Hubs und KPI-Dashboards für wirtschaftsrechtliche und streitige Kanzleien. Fokus auf GEO-Optimierung, BRAO-Compliance und messbaren KPIs (Lead-to-Call Rate +35%).

### Primäre Keywords

- Websites für Kanzleien
- Digitale Mandatsreisen
- Kanzlei-Website
- Intake-Flows für Anwaltskanzleien
- Mandatsaufnahme digitalisieren
- Kanzlei-Webentwicklung

### Sekundäre Keywords (LSI)

- GEO-Cluster, Local Pack Ranking
- Mandanten-Intake
- Case Vault, Pitch-Content-Hub
- BRAO-konform, Revisionssicher
- Lead-to-Call Rate
- Boutique-Kanzleien
- Wirtschaftsrecht, Litigation, Corporate

### Zielgruppe

**Primär:**
- Geschäftsführende Partner in spezialisierten Kanzleien (Wirtschaftsrecht, M&A, Litigation)
- Alter: 40-65 Jahre
- Standorte: DE, AT, CH
- Digitalisierungs-Bedarf: Mandatsaufnahme, Pitch-Vorbereitung, Kapazitätsplanung

**Sekundär:**
- Business Development Manager in Kanzleien
- IT-Verantwortliche in Kanzleien

### User Intent

**Primär:** Informational (Recherche)
- "Wie digitalisiere ich Mandatsaufnahme?"
- "Was sind Intake-Flows für Kanzleien?"
- "Wie steigere ich Lead-to-Call Rate?"

**Sekundär:** Transactional
- "Strategie-Call buchen" CTA

### AIO/GEO/AEO-Status

**AIO:**
- ✅ FAQ-Section mit 3 Fragen beantwortet häufige Anliegen
- ✅ AI-Snippet-Felder in FAQ für Featured Snippets optimiert
- ⚠️ Könnte mit FAQPage-Schema verstärkt werden

**GEO:**
- ✅ Schema.org LegalService Markup vorhanden
- ✅ geoCoverage: DE, AT, CH
- ✅ Inline InfoTooltips verlinken zu Glossar (interne Link-Struktur)

**AEO:**
- ✅ Konkrete Metriken: "+35% Lead-to-Call Rate", "−30% Dokumenten-Nachfassaufwand"
- ✅ 4-Schritt StepFlow beantwortet "Wie läuft Mandatsaufnahme ab?"
- ✅ Tech-Stack transparent kommuniziert (Astro, Workers, D1, DocuSign, etc.)

---

## 📝 CONTENT-AUDIT-NOTIZEN

### Stärken

- ✅ **4-Schritt StepFlow:** Sehr detaillierte Journey-Visualisierung (einzigartig für Kanzleien)
- ✅ **3 WebApps mit Tech-Stack:** Transparente Darstellung von Lösungen (Mandatsaufnahme Wizard, Case Vault, Terminplaner)
- ✅ **Spezifische Pains:** "Local Packs & AI Overviews dominieren" spricht aktuelles Kanzlei-Problem an
- ✅ **Branchenspezifische Terminologie:** BRAO-konform, Mandate, Litigation, Corporate, Partner:innen
- ✅ **FAQ mit AI-Snippets:** Featured-Snippet-Optimierung eingebaut
- ✅ **Konkrete KPIs:** +35% Lead-to-Call Rate, −25% Telefonaufwand, +5 Städte Local Pack
- ✅ **InfoTooltips:** Inline-Glossar-Links (GEO, GitOps) stärken interne Verlinkung

### Altlasten / Schwächen

- ⚠️ **"Segment · Kanzleien" Badge:** User versteht nicht, was "Segment" bedeutet – könnte verwirren
- ⚠️ **Keine Testimonials:** Keine Kundenstimmen oder Logos von Referenzkanzleien
- ⚠️ **FAQ-Section im Dark Theme:** FAQ ist sehr weit unten und könnte auf Light BG besser sichtbar sein
- ⚠️ **StepFlow nur bei erster Task:** Pitch-Vorbereitung und Terminplanung haben keine visuellen Workflows
- ⚠️ **"Pitch Content Hub" ohne Tooltip:** Lösung hat keinen InfoTooltip (im Gegensatz zu anderen Solutions)
- ⚠️ **CTA-Text "Case Vault anschauen":** Link führt zu `/wissen#case-studies`, aber "Case Vault" ist ein Produkt-Name – könnte verwirren

### Fehlende Elemente

- ❌ **Social Proof:** Keine Referenzkunden, Logos, Testimonials
- ❌ **Case Studies:** Keine konkreten Projekt-Beispiele ("Kanzlei X hat...")
- ❌ **Preistransparenz:** Keine Erwähnung von Projekt-Budgets oder Paketen
- ❌ **Demo/Video:** Keine visuelle Präsentation der WebApps (Loom, Figma-Link)
- ❌ **Trust-Signale:** Keine BRAO-Zertifikate, DSGVO-Audit-Berichte, ISO-Zertifikate
- ❌ **Vergleichstabelle:** "Wann passt welche WebApp?" – Feature-Matrix fehlt

### Content-Refresh-Priorität

**Priorität:** 🔴 **HÖCHSTE**

**Begründung:**
1. **Haupt-Zielgruppe #1:** Kanzleien sind primäre Zielgruppe laut Startseite
2. **SEO-Potenzial:** "Websites für Kanzleien", "Mandatsaufnahme digitalisieren" haben hohes Suchvolumen
3. **Featured Snippet:** FAQ mit AI-Snippets könnte Google Featured Snippets erobern
4. **Schema.org Markup:** LegalService-Schema ist vorhanden und gut optimiert
5. **Conversion-Optimierung:** 4-Schritt StepFlow + konkrete KPIs sind stark, aber Social Proof fehlt

**Empfohlene Maßnahmen (für externes LLM):**
- Testimonials von Referenzkanzleien hinzufügen
- FAQPage-Schema.org Markup einbauen
- "Segment"-Badge durch klareren Text ersetzen
- Case Studies / Projekt-Beispiele ergänzen
- Trust-Signale (BRAO, DSGVO) prominenter platzieren

---

## 📈 PERFORMANCE & TECHNISCHE DETAILS

### Core Web Vitals (Zielwerte)

- **LCP:** < 2.5s (Hero H1 ist LCP-Element)
- **INP:** < 200ms (FAQ-Accordion, Hover-Animationen)
- **CLS:** < 0.1 (Keine Layout-Shifts erwartet)

### Lazy Loading

- **Images:** Keine Bilder (nur SVG-Icons)
- **Scripts:** Astro-Islands lazy (falls InfoTooltip interaktiv)
- **StepFlow:** Conditional Rendering (nur bei index === 0)

### Mobile Optimierung

- ✅ Responsive Grid (1-col → 2-col → 3-4-col)
- ✅ Touch-Targets ≥ 44px
- ✅ Font-Sizes ≥ 14px @ Mobile
- ✅ Accordion-Pattern für FAQ @ Mobile

---

## 📊 CONTENT-METRIKEN

### Textmenge

- **Gesamtzeichen:** ~11.800
- **Gesamtwörter:** ~1.650
- **Lesedauer:** 7-9 Minuten

### Link-Dichte

- **Interne Links:** ~40-45
  - Navigation: ~15
  - Task-Links: 3 (Anchor)
  - Solution InfoTooltips: 2
  - Glossary-Links: 4
  - CTA-Links: 2
  - More Branches: 3
  - Footer: ~20
- **Externe Links:** 0
- **CTAs:** 4 (Hero Primary/Tertiary, CTA Primary/Secondary)

### Content-Verteilung

- **Dark Sections:** 45% (Hero, Path, Solutions, WebApps, FAQ)
- **Light Sections:** 55% (Tasks, Pains, KPI, Glossary, CTA, More Branches)

### Interaktive Elemente

- **Buttons:** 4
- **Details/Summary (FAQ):** 3
- **InfoTooltips:** 2 (GEO, GitOps)
- **Hover-Cards:** 18 (Task, Pain, Solution, WebApp, KPI, Branch Cards)
- **StepFlow Cards:** 4 (mit Hover-Glow)

---

**ENDE DER DOKUMENTATION**

**Letzte Aktualisierung:** 2025-10-30
**Nächste Review:** Nach Content-Refresh oder Schema-Optimierung
