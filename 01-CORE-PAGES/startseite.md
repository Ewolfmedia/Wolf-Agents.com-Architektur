# STARTSEITE - Content & Struktur-Architektur

**Dokumentiert am:** 2025-11-01
**Status:** IST-Zustand (keine Optimierungsvorschläge)

---

## 📊 1. HEADER & META-INFORMATIONEN

| Attribut | Wert |
|----------|------|
| **URL** | https://www.wolf-agents.com/ |
| **Datei** | `/src/pages/index.astro` |
| **Title Tag** | "Websites & WebApps für Kanzleien, Bildung & Behörden \| Wolf-Agents" |
| **Meta Description** | "SEO + GEO optimierte, barrierefreie Webplattformen für Kanzleien, Schulen & Behörden in DACH. Automatisierte Intake-, Anmelde- und Bürger-Services, auditierbare Deployments, persönliche Betreuung." |
| **Canonical URL** | https://www.wolf-agents.com/ |
| **Noindex** | Nein |
| **Geschätzte Zeichenanzahl** | ~15.400 Zeichen (ohne Code/HTML) |
| **Geschätzte Wortanzahl** | ~2.150 Wörter |
| **Geschätzte Lesedauer** | 9-11 Minuten |
| **Anzahl Sections** | 8 Hauptbereiche (Hero, TLDR, Segments, Painpoints, Trust, Tech Stack, CTA, FAQ) |
| **Anzahl H1** | 1 (im Hero) |
| **Anzahl H2** | 8 (pro Section) |
| **Anzahl H3** | 9+ (Cards, FAQ-Items, Trust-Features) |

---

## 🔗 2. VERLINKUNGSSTRUKTUR

### Interne Links (ausgehend)

**Navigation:**
- Logo-Link: `/`
- Branchen-Dropdown: `/branchen/kanzleien`, `/branchen/schulen-bildung`, `/branchen/oeffentliche-einrichtungen`, `/branchen/steuerberatung`, `/branchen/wirtschaftspruefung`, `/branchen/notariat`, `/branchen/versicherungen`, `/branchen/medizin`, `/branchen/industrie-b2b`
- Leistungen-Dropdown: `/leistungen`, `/leistungen/stufe-0-ftp-classic`, `/leistungen/stufe-a-astro-ftp`, `/leistungen/stufe-b-cloudflare-pages`, `/leistungen/stufe-c-aws-cloudfront`, `/leistungen/analytics-consent`, `/leistungen/seo-tech`, `/leistungen/geo`, `/leistungen/barrierefreiheit`, `/leistungen/redesign`, `/leistungen/migration-redirects`
- Wissen-Dropdown: `/wissen`, `/wissen/glossar`, `/code-statt-cms`
- CTA-Button: `/kontakt`

**Hero (Section 1):**
- CTA Primary: `/kontakt` → "Kontakt aufnehmen"
- CTA Tertiary: `mailto:info@wolf-agents.com` → "Oder direkt an info@wolf-agents.com schreiben"

**TLDR (Section 2):**
- Glossar-Tooltips: `/wissen/glossar/geo`, `/wissen/glossar/core-web-vitals`, `/wissen/glossar/bfsg-2025`, `/wissen/glossar/gitops`
- Code statt CMS Link: `/code-statt-cms`

**Segments (Section 3):**
- Branch-Cards: `/branchen/kanzleien`, `/branchen/schulen-bildung`, `/branchen/oeffentliche-einrichtungen`
- "Alle ansehen" Link: `/branchen`

**Painpoints (Section 4):**
- CardGroup-Links: `/branchen/kanzleien`, `/branchen/schulen-bildung`, `/branchen/oeffentliche-einrichtungen`

**Trust (Section 5):**
- Glossar-Tooltips: `/wissen/glossar/rum`, `/wissen/glossar/ttfb`

**CTA (Section 7):**
- Primary: `/kontakt` → "Kostenfreie Strategie-Session sichern"
- Secondary: `/capabilities` → "Arbeitsweise & Methoden ansehen"

**Footer:**
- Branchen, Leistungen, Wissen, Kontakt, Impressum (`/impressum`), Datenschutz (`/datenschutz`)

### Externe Links
- `mailto:info@wolf-agents.com` (1× im Hero)

### Backlinks (intern)
Diese Seite wird verlinkt von:
- Navigation (alle Seiten → Logo-Link)
- Branchen-Seiten (CTA-Sections → "Zur Startseite")
- Leistungen-Seiten (CTA-Sections → "Zur Startseite")
- Footer (alle Seiten → Logo-Link)

**Gesamtanzahl interne Links:** ~42-48 (inkl. 6 Glossar-Tooltips, Navigation, Footer)

---

## 🏗️ 3. LAYOUT & SEMANTISCHE STRUKTUR

---

### NAVIGATION (Sticky Header)

**Komponente:** `<Nav />`
**Datei:** `/src/components/Nav.astro`
**Position:** Slot "header" im Base-Layout
**Hintergrund:** Transparent mit Blur-Effekt (scrollt mit)

```
NAV (role: navigation, sticky top-0, z-50)
├── Container (max-width: 1280px, mx-auto, px-6)
│   ├── Logo-Link → /
│   │   Font: Inter SemiBold, 18px
│   │   Farbe: var(--text-primary-on-light) (#0B101A)
│   │
│   ├── Hauptmenü (Desktop: flex, Mobile: Burger-Menü)
│   │   ├── Branchen-Dropdown (3 Cluster)
│   │   │   ├── "Kanzlei & Audit Teams" (5 Links)
│   │   │   ├── "Finance & Growth Ops" (2 Links)
│   │   │   └── "Public · Health · Education" (3 Links)
│   │   │
│   │   ├── Leistungen-Dropdown
│   │   │   ├── Betriebsstufen (4 Links: Stufe 0-C)
│   │   │   └── Fach-Module (6 Links)
│   │   │
│   │   └── Wissen-Dropdown
│   │       ├── Glossar → /wissen/glossar
│   │       ├── Blog → /wissen
│   │       └── Code statt CMS → /code-statt-cms
│   │
│   └── CTA-Button: "Kontakt"
│       Href: /kontakt
│       Background: btn-gradient (Navy → Slate Gradient)
│       Farbe: #FFFFFF
│       Border-radius: 12px (rounded-xl)
│       Shadow: var(--shadow-premium)
```

**Farben:**
- Background: rgba(255, 255, 255, 0.95) + backdrop-filter: blur(10px)
- Border (unten): var(--border-subtle-light) (rgba(226, 232, 240, 0.7))
- Text: var(--text-primary-on-light) (#0B101A)
- Hover: var(--text-primary-on-light) mit Opacity 0.8

---

### SECTION 1: HERO (Fullscreen Dark Grid)

**Komponente:** `<Hero variant="dark-grid" />`
**Layout-Pattern:** Hero Dark Grid (100vh Fullscreen)
**Hintergrund:** var(--brand-primary-900) (#04060D) + Gitter + Glow

```
SECTION.hero (min-height: 100vh / 100dvh, position: relative)
│ Background: var(--brand-primary-900) (#04060D)
│ Grid-Pattern: 40px × 40px, rgba(148, 163, 184, 0.05)
│ Glow: radial-gradient(circle 900px at 50% 50%, rgba(156, 163, 184, 0.35), transparent)
│ Glow-Opacity: 0.08
│
├── Container (max-width: 1280px, mx-auto, px-6 md:px-12)
│   Padding: py-20 md:py-32
│   Display: flex, flex-col, items-center, justify-center, text-center
│   │
│   ├── Badge (oben)
│   │   Text: "Für Kanzleien, Bildung & öffentliche Dienste"
│   │   Background: bg-white-alpha-08 (rgba(255, 255, 255, 0.08))
│   │   Border: 1px border-on-dark-subtle (rgba(255, 255, 255, 0.18))
│   │   Text-Farbe: var(--text-on-dark-secondary) (rgba(249, 250, 251, 0.72))
│   │   Font: Inter SemiBold, 11px (0.6875rem), uppercase
│   │   Letter-spacing: 0.26em
│   │   Padding: px-4 py-1.5 (16px × 6px)
│   │   Border-radius: 9999px (rounded-full)
│   │
│   ├── H1 (Hauptüberschrift)
│   │   Text: "Code‑First Websites & Web‑Apps für Kanzleien, Bildung & öffentliche Dienste."
│   │   Font: Inter ExtraBold, 900
│   │   Font-Size: 2.25rem (36px) @ Mobile
│   │              3rem (48px) @ Tablet (md)
│   │              4.5rem (72px) @ Desktop (lg)
│   │   Farbe: var(--text-primary-on-dark) (#F9FAFB)
│   │   Line-height: 1.15 (tight)
│   │   Letter-spacing: -0.02em
│   │   Text-shadow: 0 2px 4px rgba(0, 0, 0, 0.25)
│   │   Max-width: 1200px
│   │   Margin-bottom: 1.5rem (24px)
│   │
│   ├── Paragraph (Subheadline)
│   │   Text: "Kanzleien digitalisieren Mandatsreisen effizient."
│   │   Font: Inter Regular, 400
│   │   Font-Size: 1.125rem (18px) @ Mobile
│   │              1.25rem (20px) @ Desktop
│   │   Farbe: var(--text-secondary-on-dark) (rgba(249, 250, 251, 0.72))
│   │   Line-height: 1.75 (relaxed)
│   │   Max-width: 600px
│   │   Margin-top: 1.5rem (24px)
│   │
│   ├── CTA-Gruppe (Flex-Row @ Desktop, Flex-Col @ Mobile)
│   │   Gap: 16px (gap-4)
│   │   Margin-top: 2.5rem (40px)
│   │   │
│   │   ├── Button Primary
│   │   │   Label: "Kontakt aufnehmen"
│   │   │   Href: /kontakt
│   │   │   Class: btn-gradient
│   │   │   Background: linear-gradient Navy → Slate
│   │   │   Farbe: #FFFFFF
│   │   │   Font: Inter SemiBold, 16px (1rem)
│   │   │   Padding: px-6 py-3 (24px × 12px)
│   │   │   Border-radius: 12px (rounded-xl)
│   │   │   Shadow: var(--shadow-premium) (0 12px 30px -18px rgba(4, 6, 13, 0.65))
│   │   │   Hover: translateY(-2px), Shadow verstärkt
│   │   │   Icon: SVG Pfeil rechts (20px × 20px)
│   │   │
│   │   └── Tertiary Link
│   │       Text: "Oder direkt an info@wolf-agents.com schreiben"
│   │       Href: mailto:info@wolf-agents.com
│   │       Font: Inter Medium, 14px
│   │       Farbe: var(--text-secondary-on-dark)
│   │       Text-decoration: underline, thickness 1px, offset 4px
│   │       Hover: Farbe → var(--text-primary-on-dark)
│   │
│   └── Founder-Card (Position: absolute, bottom-right @ Desktop, relative @ Mobile)
│       Background: bg-white-alpha-08 (rgba(255, 255, 255, 0.08))
│       Border: 1px border-on-dark-subtle
│       Border-radius: 20px (rounded-[20px])
│       Padding: p-6 (24px)
│       Backdrop-filter: blur(8px)
│       Shadow: 0 8px 32px -8px rgba(0, 0, 0, 0.25)
│       │
│       ├── Avatar (float left, mr-4)
│       │   Image: /img/business-foto.jpg
│       │   Alt: "Portrait von Eduard Wolf"
│       │   Size: 64px × 64px @ Desktop, 56px × 56px @ Mobile
│       │   Border-radius: 50% (rounded-full)
│       │   Border: 2px solid rgba(255, 255, 255, 0.18)
│       │   Shadow: 0 4px 12px rgba(0, 0, 0, 0.3)
│       │
│       └── Text-Block
│           ├── Name: "Eduard Wolf"
│           │   Font: Inter SemiBold, 16px
│           │   Farbe: var(--text-primary-on-dark) (#F9FAFB)
│           │
│           ├── Role: "Inhaber & Software-Architekt"
│           │   Font: Inter Regular, 13px
│           │   Farbe: var(--text-secondary-on-dark)
│           │   Margin-top: 2px
│           │
│           └── Quote
│               Text: "Sie sprechen direkt mit mir – vom Kanzlei-Intake bis zum Bürgerportal, das Anträge sortiert."
│               Font: Inter Regular, 14px
│               Font-style: italic
│               Farbe: rgba(249, 250, 251, 0.85)
│               Line-height: 1.6
│               Margin-top: 12px
```

---

### SECTION 2: TLDR/OVERVIEW (Light Surface)

**Komponente:** `<Section tone="light" />`
**Layout-Pattern:** Single Premium Card (Centered)
**Hintergrund:** var(--surface-light) (#F9FAFB)

```
SECTION#tldr (tone: light, padding: py-20 md:py-28 lg:py-32)
│ Background: var(--surface-light) (#F9FAFB)
│
└── Container (max-width: 1024px, mx-auto, px-6)
    │
    └── Premium-Card
        Background: var(--surface-light) (#F9FAFB)
        Border: 1px border-on-light-subtle (rgba(226, 232, 240, 0.7))
        Border-radius: 24px (rounded-3xl)
        Shadow: var(--shadow-premium) (0 12px 30px -18px rgba(4, 6, 13, 0.65))
        Padding: px-6 py-10 @ Mobile, px-12 py-14 @ Desktop
        Backdrop-filter: blur(10px)
        │
        ├── Badge: "Kurz zusammengefasst"
        │   Class: chip-light caps-label-wide
        │   Background: rgba(226, 232, 240, 0.5)
        │   Font: Inter SemiBold, 12px, uppercase, tracking: 0.26em
        │   Farbe: var(--text-on-light-primary) (#0B101A)
        │   Padding: px-3 py-1, rounded-full
        │   Margin-bottom: 20px
        │
        ├── H2
        │   Text: "Was regulierte & öffentliche Teams mit Wolf-Agents erreichen"
        │   Font: Inter Bold, 700
        │   Font-Size: 1.875rem (30px) @ Mobile, 2.25rem (36px) @ Desktop
        │   Farbe: var(--text-on-light-primary) (#0B101A)
        │   Line-height: 1.25
        │   Margin-bottom: 16px
        │
        └── Grid-Layout (lg:grid-cols-[1.15fr,0.85fr])
            Gap: 32px (gap-8)
            │
            ├── Linke Spalte (Haupt-Content)
            │   │
            │   ├── Paragraph 1
            │   │   Text: "Kanzleiteams verbinden SEO- und GEO (AEO) Inhalte mit Intake-Flows, die Mandate in < 4 Minuten qualifizieren – inklusive Dashboards für Response Time und Lead-to-Call Rate."
            │   │   Font: Inter Regular, 16px (1rem)
            │   │   Farbe: var(--text-on-light-secondary) (rgba(55, 65, 81, 0.9))
            │   │   Line-height: 1.75
            │   │   Inline-Element: <InfoTooltip termId="geo" mode="auto" />
            │   │   Strong-Tag: "< 4 Minuten"
            │   │
            │   ├── Details-Element (Collapsible)
            │   │   Summary: "Mehr lesen"
            │   │   Icon: Plus-Icon (rotiert zu X bei open)
            │   │   Font: Inter SemiBold, 14px
            │   │   Farbe: var(--text-on-light-secondary)
            │   │   Hover: var(--text-on-light-primary)
            │   │   │
            │   │   └── Hidden-Content (bei open)
            │   │       ├── Paragraph 2
            │   │       │   Text: "Schulen und Hochschulen ersetzen Papier- und PDF-Strecken durch geführte Online-Anmeldungen mit Dokument-Upload, Status-Mails und Core Web Vitals im grünen Bereich – optimiert für > 60 % mobile Nutzung."
            │   │       │   Inline: <InfoTooltip termId="core-web-vitals" mode="auto" />
            │   │       │
            │   │       └── Paragraph 3
            │   │           Text: "Öffentliche Einrichtungen liefern barrierefreie Service-Flows mit BFSG 2025 Checks, GitOps Deployments und Servicecockpits, die Completion Rate, Digital Take-up und Zufriedenheit sichtbar machen."
            │   │           Inline: <InfoTooltip termId="bfsg-2025" mode="modal" />, <InfoTooltip termId="gitops" mode="modal" />
            │   │
            │   ├── KPI-Cards-Grid (sm:grid-cols-2, gap-4)
            │   │   │
            │   │   ├── Card 1: Kanzleien
            │   │   │   Background: linear-gradient(to-br, var(--surface-light), white, var(--surface-light-muted))
            │   │   │   Border: 1px border-on-light-subtle
            │   │   │   Border-radius: 20px (rounded-[20px])
            │   │   │   Shadow: var(--shadow-card-light) (0 4px 16px rgba(15, 23, 42, 0.08))
            │   │   │   Padding: px-5 py-4 (20px × 16px)
            │   │   │   │
            │   │   │   ├── Label: "KANZLEIEN"
            │   │   │   │   Font: Inter SemiBold, 12px, uppercase, tracking: 0.22em
            │   │   │   │   Farbe: var(--text-on-light-secondary)
            │   │   │   │   Border-bottom: 1px border-on-light-subtle, pb-1, inline-block
            │   │   │   │
            │   │   │   ├── Metric-Value: "Lead-to-Call Rate +35 %"
            │   │   │   │   Font: Inter Bold, 18px (1.125rem)
            │   │   │   │   Farbe: var(--text-on-light-primary)
            │   │   │   │   Margin-top: 8px
            │   │   │   │
            │   │   │   └── Description
            │   │   │       Text: "Intake-Flows priorisieren Mandate, reduzieren Rückfragen und liefern strukturierte Daten."
            │   │   │       Font: Inter Regular, 14px
            │   │   │       Farbe: var(--text-on-light-secondary)
            │   │   │       Margin-top: 8px
            │   │   │
            │   │   └── Card 2: Behörden & Bildung
            │   │       [Gleiche Struktur]
            │   │       Label: "BEHÖRDEN & BILDUNG"
            │   │       Metric: "Completion Rate ≥ 70 %"
            │   │       Description: "Guided Forms, Status-Updates und Monitoring senken Abbruchquoten nachhaltig."
            │   │
            │   └── Footer-Paragraph (Disclaimer)
            │       Text: "Jedes Projekt bleibt refaktorierbar: Code statt Baukasten, versionierte Backups, dokumentierte KPIs und Reaktionszeiten < 1 Stunde im Kick-off."
            │       Font: Inter Regular, 14px
            │       Farbe: var(--text-on-light-muted) (rgba(107, 114, 128, 0.8))
            │       Margin-top: 20px
            │
            └── Rechte Spalte (Dark Aside: "Code statt CMS")
                Background: var(--surface-navy) (#0F172A)
                Border: 1px border-on-dark-subtle (rgba(255, 255, 255, 0.18))
                Border-radius: 20px
                Shadow: var(--shadow-card-dark) (0 8px 32px -8px rgba(0, 0, 0, 0.25))
                Padding: p-7 @ Mobile, p-10 @ Desktop
                Glow-Overlay (absolute, inset-0): radial-gradient(circle at 50% 50%, rgba(156, 163, 184, 0.35), transparent 70%), opacity: 0.08
                │
                ├── Badge: "CODE STATT CMS"
                │   Background: bg-white-alpha-08
                │   Font: Inter SemiBold, 12px, uppercase, tracking: 0.3em
                │   Farbe: var(--text-on-dark-secondary)
                │   Padding: px-4 py-1.5, rounded-full
                │
                ├── H3: "Warum ein Code-first Setup?"
                │   Font: Inter SemiBold, 1.25rem (20px) @ Mobile, 1.5rem (24px) @ Desktop
                │   Farbe: var(--text-on-dark-primary) (#F9FAFB)
                │   Line-height: 1.375 (snug)
                │   Margin-top: 20px
                │
                ├── Intro-Paragraph
                │   Text: "Keine Plugin-Ketten, keine Redaktions-Limits: Wir shippen modulare Komponenten, die Sie anpassen, versionieren und auditieren können."
                │   Font: Inter Regular, 14px
                │   Farbe: var(--text-on-dark-secondary)
                │   Margin-top: 20px
                │
                ├── Checklist (3 Items, space-y-4)
                │   │
                │   ├── Item 1
                │   │   Icon-Container: 32px × 32px, bg-white-alpha-12, rounded-xl, ring-1 ring-white/20
                │   │   Icon: Checkmark SVG (16px × 16px), Farbe: var(--text-on-dark-secondary)
                │   │   Text: "Astro Islands & Edge Rendering halten INP < 200 ms und LCP < 2.3 s als Budget."
                │   │   Strong: "INP < 200 ms", "LCP < 2.3 s"
                │   │   Font: Inter Regular, 14px
                │   │   Farbe: var(--text-on-dark-primary)
                │   │
                │   ├── Item 2
                │   │   Text: "Servicecockpits zeigen Completion Rate, Response Time & Digital Take-up – ideal für Intake-Teams."
                │   │   Strong: "Servicecockpits"
                │   │
                │   └── Item 3
                │       Text: "GitOps Deployments mit Audit-Log, Feature Flags und Rollbacks sichern Governance ab."
                │       Strong: "GitOps Deployments"
                │
                └── Link (pt-4)
                    Text: "/code-statt-cms – Landingpage öffnen"
                    Href: /code-statt-cms
                    Font: Inter SemiBold, 14px
                    Farbe: var(--text-on-dark-secondary)
                    Hover: var(--text-primary-on-dark)
                    Icon: Pfeil rechts (16px)
                    Data-Attribute: data-cta="homepage-code-vs-cms"
```

---

### SECTION 3: SEGMENTS/BRANCHES (Dark Grid + Glow)

**Komponente:** `<Section tone="dark" glow="center" />`
**Layout-Pattern:** 3-Column Card Grid
**Hintergrund:** var(--surface-dark) (#04060D) + Gitter + Center-Glow

```
SECTION#segments (tone: dark, glow: center, padding: py-20 md:py-28 lg:py-32)
│ Background: var(--surface-dark) (#04060D)
│ Grid-Pattern: 40px × 40px, rgba(148, 163, 184, 0.05)
│ Glow: radial-gradient(circle 900px at 50% 50%, rgba(156, 163, 184, 0.35), transparent), opacity: 0.06
│
├── Header-Block (max-width: 768px, mb-12)
│   │
│   ├── Badge: "Branchenauswahl"
│   │   Background: bg-white-alpha-08, Border: 1px border-on-dark-subtle
│   │   Font: Inter SemiBold, 12px, uppercase, tracking: 0.26em
│   │   Farbe: var(--text-on-dark-secondary)
│   │   Padding: px-4 py-1.5, rounded-full
│   │
│   ├── H2: "Branchen, die wir aktiv begleiten"
│   │   Font: Inter Bold, 1.875rem (30px) @ Mobile, 2.25rem (36px) @ Desktop
│   │   Farbe: #FFFFFF
│   │   Text-shadow: 0 1px 2px rgba(0, 0, 0, 0.15) (drop-shadow-sm)
│   │   Line-height: 1.25 (tight)
│   │
│   └── Intro-Paragraph
│       Text: "Wir bauen wiederverwendbare Module, die in Kanzleien, Bildungsorganisationen und Verwaltungen bestehen – inklusive KPIs, Governance und Servicecockpits."
│       Font: Inter Regular, 1rem (16px) @ Mobile, 1.125rem (18px) @ Desktop
│       Farbe: rgba(226, 232, 240, 0.9) (slate-200/90)
│       Line-height: 1.75
│
└── Grid-Layout (lg:grid-cols-3, gap-6)
    │
    ├── Branch-Card 1: Kanzleien
    │   Link: /branchen/kanzleien
    │   Background: bg-white-alpha-08 (rgba(255, 255, 255, 0.08))
    │   Border: 1px border-on-dark-subtle (rgba(255, 255, 255, 0.18))
    │   Border-radius: 20px (rounded-[20px])
    │   Padding: p-7 (28px)
    │   Backdrop-filter: blur(8px)
    │   Shadow (default): 0 0 0 1px rgba(255, 255, 255, 0.05), 0 10px 30px -10px rgba(0, 0, 0, 0.2), 0 30px 90px -60px rgba(107, 114, 128, 0.3)
    │   Hover: translateY(-8px) scale(1.02), Shadow verstärkt
    │   Transition: all 350ms cubic-bezier(0.4, 0, 0.2, 1) → all 250ms cubic-bezier(0.16, 1, 0.3, 1) (hover)
    │   │
    │   ├── Header-Row (flex justify-between)
    │   │   ├── Segment-Label: "KANZLEIEN"
    │   │   │   Font: Inter SemiBold, 12px, uppercase, tracking: 0.3em
    │   │   │   Farbe: var(--text-on-dark-secondary)
    │   │   │
    │   │   └── Badge-Number: "01"
    │   │       Size: 40px × 40px, rounded-xl
    │   │       Background: bg-white-alpha-08
    │   │       Ring: 1px rgba(209, 213, 219, 0.28)
    │   │       Font: Inter Bold, 16px
    │   │       Farbe: #FFFFFF
    │   │       Shadow: inset 0 1px 2px rgba(255, 255, 255, 0.1), 0 0 12px rgba(148, 163, 184, 0.2)
    │   │
    │   ├── H3 (Branch-Headline)
    │   │   Text: [Dynamisch aus Content-Collection] (Beispiel: "Mandatsreisen digital, ohne Nachtelefonieren")
    │   │   Font: Inter SemiBold, 1.25rem (20px)
    │   │   Farbe: #FFFFFF
    │   │   Line-height: 1.375 (snug)
    │   │   Margin-top: 16px
    │   │
    │   ├── Description-Paragraph
    │   │   Text: [Dynamisch aus Content-Collection] (Beispiel: "Intake-Flows, die Mandate qualifizieren, bevor sie anrufen – mit Dashboard für Response Time.")
    │   │   Font: Inter Regular, 14px
    │   │   Farbe: rgba(226, 232, 240, 0.85)
    │   │   Line-height: 1.75
    │   │   Margin-top: 16px
    │   │
    │   └── CTA-Link (mt-auto)
    │       Text: "Zur Branchenseite"
    │       Icon: Pfeil rechts (16px), translateX(4px) @ hover
    │       Font: Inter SemiBold, 14px
    │       Farbe: rgba(203, 213, 225, 1) (slate-300) → #FFFFFF (hover)
    │       Transition: all 300ms
    │       Gap: 8px → 12px (hover)
    │
    ├── Branch-Card 2: Schulen & Bildung
    │   [Gleiche Struktur]
    │   Badge-Number: "02"
    │   Link: /branchen/schulen-bildung
    │
    └── Branch-Card 3: Öffentliche Einrichtungen
        [Gleiche Struktur]
        Badge-Number: "03"
        Link: /branchen/oeffentliche-einrichtungen

└── "Alle ansehen"-Link (mt-12, flex flex-wrap gap-4)
    Text: "Alle Segmente & KPI-Blaupausen ansehen"
    Href: /branchen
    Background: bg-white-alpha-08, Hover: bg-white-alpha-12
    Border-radius: rounded-full
    Padding: px-5 py-2.5
    Font: Inter SemiBold, 14px
    Farbe: #FFFFFF
    Icon: Pfeil rechts (16px), gap-3
```

---

### SECTION 4: PAINPOINTS/USE CASES (Dark Grid + Top Glow)

**Komponente:** `<Section tone="dark" glow="top" />` + `<CardGroup mobilePattern="accordion" columns={3} />`
**Layout-Pattern:** CardGroup mit Accordion @ Mobile
**Hintergrund:** var(--surface-dark) + Gitter + Top-Glow

```
SECTION#painpoints (tone: dark, glow: top, padding: py-20 md:py-28 lg:py-32)
│ Background: var(--surface-dark) (#04060D)
│ Glow: radial-gradient(circle 900px at 50% 0%, rgba(156, 163, 184, 0.35), transparent), opacity: 0.06
│
├── Header-Block (max-width: 768px, mx-auto, text-center, mb-20 md:mb-24)
│   │
│   ├── Badge: "Einsatzfelder"
│   │   Background: bg-white-alpha-08, Border: 1px border-on-dark-subtle
│   │   Font: Inter SemiBold, 12px, uppercase, tracking: 0.18em
│   │
│   ├── H2: "Drei regulierte Segmente – eine Plattform"
│   │   Font: Inter Bold, 2.25rem (36px) @ Mobile, 3rem (48px) @ Tablet, 3.75rem (60px) @ Desktop
│   │   Farbe: #FFFFFF
│   │   Text-shadow: 0 1px 2px rgba(0, 0, 0, 0.15)
│   │   Line-height: 1.25 (tight)
│   │
│   └── Intro-Paragraph
│       Text: "Mandatsaufnahme, Einschreibungen oder Bürgerdienste: Wir liefern vorkonfigurierte Module mit Compliance, Analytics und Governance."
│       Font: Inter Regular, 1.125rem (18px) @ Mobile, 1.25rem (20px) @ Desktop
│       Farbe: rgba(226, 232, 240, 0.9)
│       Line-height: 1.75
│
└── CardGroup-Komponente
    Props: title="Was wir in regulierten Teams standardisieren"
           intro="Module für Intake, Anmeldungen und digitale Services – inklusive Monitoring, Rollenrechten und auditierbaren Deployments."
           mobilePattern="accordion"
           columns={3}
           items=[...] (siehe unten)
    │
    ├── Card 1: Kanzleien
    │   Title: "Mandatsreisen ohne Nachtelefonieren"
    │   Badge: "Kanzleien"
    │   Description: "Mandant:innen beantworten Intake-Fragen, laden Dokumente hoch und wissen, was als Nächstes passiert – bevor sie anrufen."
    │   Bullets:
    │   - "Geo- & FAQ-Cluster sichern Sichtbarkeit bei High-Stake-Verfahren"
    │   - "Intake-Strecken mit Dokument-Upload, Signatur & BRAO-konformem Logging"
    │   - "Dashboards für Response-Time, Lead-to-Call Rate & Intake-Status"
    │   Metrics:
    │   - label: "Reaktionszeit", value: "< 1 Stunde"
    │   - label: "Lead-to-Call Rate", value: "+35 % Ziel"
    │   Link: /branchen/kanzleien, label: "Digitale Mandatsreise ansehen"
    │
    ├── Card 2: Bildung
    │   Title: "Digitale Anmeldungen ohne CMS-Limits"
    │   Badge: "Bildung"
    │   Description: "Schulen und Hochschulen entlasten das Sekretariat mit geführten Online-Flows, Status-E-Mails und mobilen Oberflächen."
    │   Bullets:
    │   - "Aufnahme-Assistent inkl. Dokument-Upload & Status-Updates in 3 Schritten"
    │   - "Modulare Content-Layouts für Fachbereiche, Stundenpläne & Alumni-Portale"
    │   - "Performance-Budgets & Monitoring für hohe mobile Nutzung"
    │   Metrics:
    │   - label: "Anmeldeprozess", value: "3 Schritte"
    │   - label: "Mobile Nutzung", value: "> 60 % Fokus"
    │   Link: /branchen/schulen-bildung, label: "Campus-Flow entdecken"
    │
    └── Card 3: Behörden
        Title: "Bürgerdienste mit Completion Rate im Blick"
        Badge: "Behörden"
        Description: "Progressive Formulare, Servicecockpit und Governance-Workflows sorgen dafür, dass Anträge abgeschlossen werden – compliant & auditierbar."
        Bullets:
        - "BFSG 2025 & WCAG 2.2 Checks inklusive Audit-Dokumentation"
        - "Vier-Augen-Freigaben, Rollen & Rechte für Fachbereiche, Audit-Trails via GitOps"
        - "Servicecockpit mit Completion Rate, Digital Take-up & Zufriedenheit"
        Metrics:
        - label: "Completion Rate", value: "≥ 70 % Ziel"
        - label: "Audit-Protokoll", value: "100 % nachvollziehbar"
        Link: /branchen/oeffentliche-einrichtungen, label: "Bürgerportal modernisieren"
```

**Hinweis:** CardGroup rendert @ Mobile als Accordion (Details/Summary), @ Desktop als Grid (3 Spalten).

---

### SECTION 5: TRUST & PROOF (Light Surface + Grid)

**Komponente:** `<Section tone="light" grid={true} />`
**Layout-Pattern:** 4-Column Feature Grid + Performance Metrics
**Hintergrund:** var(--surface-light) (#F9FAFB) + Gitter-Pattern

```
SECTION#trust (tone: light, grid: true, padding: py-20 md:py-28 lg:py-32)
│ Background: var(--surface-light) (#F9FAFB)
│ Grid-Pattern: 40px × 40px, rgba(148, 163, 184, 0.05)
│
├── Header-Block (max-width: 768px, mx-auto, text-center, mb-16)
│   │
│   ├── Badge: "Warum Wolf-Agents"
│   │   Class: chip-light caps-label-wide
│   │   Font: Inter SemiBold, 14px
│   │   Farbe: var(--text-on-light-primary)
│   │
│   ├── H2: "Inhabergeführt, direkt, transparent"
│   │   Font: Inter Bold, 1.875rem (30px) @ Mobile, 2.25rem (36px) @ Desktop
│   │   Farbe: var(--text-on-light-primary)
│   │   Margin-bottom: 16px
│   │
│   └── Intro-Paragraph
│       Text: "Als junges Unternehmen setzen wir auf modernste Technologien und persönlichen Service."
│       Font: Inter Regular, 1.125rem (18px)
│       Farbe: var(--text-on-light-secondary)
│
├── Feature-Grid (md:grid-cols-2 lg:grid-cols-4, gap-8, mb-16)
│   │
│   ├── Feature-Card 1: "Inhabergeführt"
│   │   Background: var(--surface-light), Border: 1px border-on-light-subtle
│   │   Border-radius: 20px (rounded-[20px])
│   │   Padding: p-8 (32px)
│   │   Shadow (default): 0 0 0 1px rgba(255, 255, 255, 0.05), 0 10px 30px -10px rgba(15, 23, 42, 0.2), 0 30px 90px -60px rgba(107, 114, 128, 0.3)
│   │   Hover: translateY(-6px), Shadow verstärkt
│   │   Transition: all 350ms cubic-bezier(0.4, 0, 0.2, 1)
│   │   │
│   │   ├── Icon-Container
│   │   │   Size: 56px × 56px (w-14 h-14)
│   │   │   Background: var(--surface-light), Border: 1px border-on-light-subtle
│   │   │   Border-radius: 12px (rounded-xl)
│   │   │   Shadow (inset): inset 0 1px 2px rgba(0, 0, 0, 0.05)
│   │   │   Icon: SVG User (28px × 28px), Farbe: var(--text-on-light-secondary)
│   │   │   Margin-bottom: 16px
│   │   │
│   │   ├── H3: "Inhabergeführt"
│   │   │   Font: Inter Bold, 1.25rem (20px)
│   │   │   Farbe: var(--text-on-light-primary)
│   │   │   Margin-bottom: 12px
│   │   │
│   │   └── Description
│   │       Text: "Direkter Kontakt zum Entwickler - keine Umwege, keine Missverständnisse."
│   │       Font: Inter Regular, 14px
│   │       Farbe: var(--text-on-light-secondary)
│   │
│   ├── Feature-Card 2: "Faire Preise"
│   │   [Gleiche Struktur]
│   │   Icon: SVG Dollar/Currency (28px)
│   │   Text: "Transparente Kalkulation ohne versteckte Kosten. Flexibel an Ihr Budget angepasst."
│   │
│   ├── Feature-Card 3: "Begleitete Startphase"
│   │   [Gleiche Struktur]
│   │   Icon: SVG Support/Target (28px)
│   │   Text: "In den ersten 30 Tagen bleiben wir für Fragen und Feintuning erreichbar."
│   │
│   └── Feature-Card 4: "Modernste Tech"
│       [Gleiche Struktur]
│       Icon: SVG Lightning/Bolt (28px)
│       Text: "Neueste Frameworks und Best Practices - keine Altlasten, zukunftssicher."
│
└── Performance Metrics (border-top border-on-light-subtle, pt-12, max-width: 1024px, mx-auto)
    │
    ├── H3: "Messbare Qualitäts-Parameter"
    │   Font: Inter Bold, 1.5rem (24px)
    │   Farbe: var(--text-on-light-primary)
    │   Text-align: center
    │   Margin-bottom: 32px
    │
    └── Metrics-Grid (grid-cols-2 md:grid-cols-4, gap-8)
        │
        ├── Metric 1: "180 ms"
        │   Value: "180 ms"
        │   Font: Inter Bold, 1.875rem (30px) @ Mobile, 2.25rem (36px) @ Desktop
        │   Farbe: var(--text-on-light-primary)
        │   Label: "INP im Real-User-Monitoring"
        │   Font: Inter Regular, 14px
        │   Farbe: var(--text-on-light-secondary)
        │   Inline: <InfoTooltip termId="rum" />
        │
        ├── Metric 2: "0.32 s"
        │   Value: "0.32 s"
        │   Label: "TTFB auf deutschen Standorten"
        │   Inline: <InfoTooltip termId="ttfb" />
        │
        ├── Metric 3: "12×"
        │   Value: "12×"
        │   Label: "Automatisierte Checks vor Go-Live"
        │
        └── Metric 4: "24/7"
            Value: "24/7"
            Label: "Monitoring & Incident Alerts"
```

---

### SECTION 6: TECH STACK (Dark Fullbleed with Grid)

**Komponente:** `<TechBelt id="tech-stack" />`
**Layout-Pattern:** Tech-Logo-Belt (Horizontal Scroll @ Mobile, Grid @ Desktop)
**Hintergrund:** var(--surface-dark) (#04060D) + Gitter

```
SECTION#tech-stack (Komponente: TechBelt)
│ Background: var(--surface-dark) (#04060D)
│ Grid-Pattern: 40px × 40px, rgba(148, 163, 184, 0.05)
│ Padding: py-16 md:py-20
│
├── Header-Block (text-center, mb-12)
│   ├── Badge: "Tech Stack"
│   │   Background: bg-white-alpha-08, Border: 1px border-on-dark-subtle
│   │   Font: Inter SemiBold, 12px, uppercase, tracking: 0.26em
│   │   Farbe: var(--text-on-dark-secondary)
│   │
│   ├── H2: "Code-First Stack für Performance & Skalierbarkeit"
│   │   Font: Inter Bold, 1.875rem (30px) @ Mobile, 2.25rem (36px) @ Desktop
│   │   Farbe: #FFFFFF
│   │
│   └── Intro-Paragraph
│       Text: "Astro Islands, Edge Rendering und modulare Komponenten halten Core Web Vitals konstant grün."
│       Font: Inter Regular, 1.125rem (18px)
│       Farbe: rgba(226, 232, 240, 0.9)
│
└── Tech-Logos-Grid (grid-cols-3 md:grid-cols-6, gap-8)
    ├── Logo 1: Astro (SVG oder PNG, max-height: 48px)
    ├── Logo 2: Tailwind CSS
    ├── Logo 3: Cloudflare Workers
    ├── Logo 4: TypeScript
    ├── Logo 5: GitHub Actions
    └── Logo 6: [Weitere Logos]

    (Hinweis: TechBelt ist eine spezielle Komponente, die Logos horizontal scrollbar @ Mobile anzeigt)
```

---

### SECTION 7: CTA (Light Surface + Dark Premium Card)

**Komponente:** `<Section tone="light" />` + `<ContentBoxDark />`
**Layout-Pattern:** Centered Dark Card mit CTA-Cluster
**Hintergrund:** var(--surface-light) (#F9FAFB)

```
SECTION#cta (tone: light, padding: py-24 md:py-32)
│ Background: var(--surface-light) (#F9FAFB)
│
└── Container (max-width: 1024px, mx-auto, px-6)
    │
    └── ContentBoxDark
        Heading: "Ihr 30-Tage-Fahrplan zur neuen Kanzlei-Website & WebApp."
        HeadingLevel: "h2"
        Background: var(--surface-navy) (#0F172A)
        Border: 1px border-on-dark-subtle
        Border-radius: 24px (rounded-3xl)
        Shadow: var(--shadow-premium)
        Padding: p-10 md:p-14
        │
        ├── H2: "Ihr 30-Tage-Fahrplan zur neuen Kanzlei-Website & WebApp."
        │   Font: Inter Bold, 1.875rem (30px) @ Mobile, 2.25rem (36px) @ Desktop
        │   Farbe: #FFFFFF
        │   Margin-bottom: 32px
        │
        ├── Intro-Paragraph
        │   Text: "Strategie-Workshop, SEO-Konzept, Content-Produktion, WebApp-Intake und Launch: Wir führen Ihr Team strukturiert durch jede Phase."
        │   Font: Inter Regular, 1rem (16px) @ Mobile, 1.125rem (18px) @ Desktop
        │   Farbe: rgba(226, 232, 240, 0.85)
        │   Line-height: 1.75
        │   Margin-bottom: 32px
        │
        └── Grid-Layout (lg:grid-cols-[2fr,1.1fr], gap-10, items-start)
            │
            ├── Linke Spalte (CTA-Gruppe)
            │   │
            │   ├── Button-Group (flex-col sm:flex-row, gap-4 sm:gap-6)
            │   │   │
            │   │   ├── Button Primary
            │   │   │   Label: "Kostenfreie Strategie-Session sichern"
            │   │   │   Href: /kontakt
            │   │   │   Class: btn-gradient
            │   │   │   Background: linear-gradient Navy → Slate
            │   │   │   Farbe: #FFFFFF
            │   │   │   Font: Inter SemiBold, 16px
            │   │   │   Padding: px-6 py-3
            │   │   │   Border-radius: 12px (rounded-xl)
            │   │   │   Shadow: var(--shadow-premium)
            │   │   │   Icon: Pfeil rechts (20px)
            │   │   │
            │   │   └── Button Secondary
            │   │       Label: "Arbeitsweise & Methoden ansehen"
            │   │       Href: /capabilities
            │   │       Background: transparent
            │   │       Border: 1px border-on-dark-strong (rgba(209, 213, 219, 0.4))
            │   │       Farbe: #FFFFFF
            │   │       Font: Inter SemiBold, 16px
            │   │       Padding: px-6 py-3
            │   │       Border-radius: 12px
            │   │       Hover: bg-white-alpha-12
            │   │
            │   └── Disclaimer-Paragraph
            │       Text: "Response Promise: Antwort in < 1 Stunde (Mo–Fr 09–18 Uhr) · Kick-off in ≤ 5 Werktagen"
            │       Font: Inter Regular, 14px
            │       Farbe: rgba(255, 255, 255, 0.7) (white/70)
            │       Margin-top: 16px
            │
            └── Rechte Spalte (Feature-List-Card)
                Background: bg-white-alpha-08 (rgba(255, 255, 255, 0.08))
                Border: 1px border-on-dark-subtle
                Border-radius: 24px (rounded-3xl)
                Padding: p-8 (32px)
                Backdrop-filter: blur(8px)
                │
                ├── H3: "Was Sie erwarten dürfen"
                │   Font: Inter SemiBold, 1.25rem (20px)
                │   Farbe: #FFFFFF
                │
                └── Feature-List (space-y-3, text-sm)
                    ├── Item 1
                    │   Icon: Checkmark SVG (20px), Farbe: rgba(16, 185, 129, 1) (emerald-400)
                    │   Text: "Kick-off inklusive Ziel-Workshop innerhalb von 5 Werktagen"
                    │   Farbe: rgba(226, 232, 240, 1) (slate-200)
                    │
                    ├── Item 2
                    │   Text: "Garantierter Core Web Vitals Report (LCP & INP < 1,8s)"
                    │
                    ├── Item 3
                    │   Text: "Content- & GEO (AEO)-Kampagnen kontinuierlich begleitet"
                    │
                    └── Item 4
                        Text: "Onboarding Ihres Teams inklusive Videos & Dokumentation"
```

---

### SECTION 8: FAQ (Light Surface + Accordion)

**Komponente:** `<Section tone="light" grid={false} />`
**Layout-Pattern:** Accordion-FAQ mit Schema.org JSON-LD
**Hintergrund:** var(--surface-light) (#F9FAFB)

```
SECTION#faq (tone: light, grid: false, padding: py-20 md:py-28 lg:py-32)
│ Background: var(--surface-light) (#F9FAFB)
│
├── Header-Block (max-width: 768px, mx-auto, text-center, mb-14)
│   │
│   ├── Badge: "FAQ"
│   │   Class: chip-light caps-label-wide
│   │   Font: Inter SemiBold, 14px
│   │   Farbe: var(--text-on-light-primary)
│   │   Margin-bottom: 20px
│   │
│   ├── H2: "Häufige Fragen zur Zusammenarbeit"
│   │   Font: Inter Bold, 1.875rem (30px) @ Mobile, 2.25rem (36px) @ Desktop
│   │   Farbe: var(--text-on-light-primary)
│   │   Margin-bottom: 16px
│   │
│   └── Intro-Paragraph
│       Text: "Transparente Antworten auf die wichtigsten Fragen rund um Zeitplan, Performance, Prozess, Support und Budget."
│       Font: Inter Regular, 1rem (16px) @ Mobile, 1.125rem (18px) @ Desktop
│       Farbe: var(--text-on-light-secondary)
│
└── FAQ-Accordion (max-width: 1024px, mx-auto, space-y-4)
    │
    ├── FAQ-Item 1 (Details/Summary)
    │   Class: accordion-card
    │   Background: var(--surface-light)
    │   Border: 1px border-on-light-subtle
    │   Border-radius: 20px (rounded-[20px])
    │   Padding: p-6 (24px)
    │   │
    │   ├── Summary (Question)
    │   │   Text: "Wie schnell ist unsere neue Website live?"
    │   │   Font: Inter SemiBold, 1.125rem (18px)
    │   │   Farbe: var(--text-on-light-primary)
    │   │   Icon: Plus-Icon (20px), rotiert zu X bei open
    │   │   Cursor: pointer
    │   │
    │   └── Content (Answer, hidden until open)
    │       Text: "In der Regel planen wir 4–6 Wochen vom Kick-off bis zum Go-Live ein. Sie erhalten nach wenigen Tagen einen klickbaren Prototyp, danach folgen Content-, QA- und Launch-Phase mit klaren Meilensteinen."
    │       Font: Inter Regular, 16px
    │       Farbe: var(--text-on-light-secondary)
    │       Line-height: 1.75
    │       Margin-top: 16px
    │
    ├── FAQ-Item 2
    │   Question: "Garantiert ihr gute Core Web Vitals?"
    │   Answer: "Ja. Jede Seite erhält Performance-Budgets (LCP ≤ 2,5 s, INP ≤ 200 ms, CLS ≤ 0,1) und ein Real-User-Monitoring-Setup. Dadurch können wir Probleme früh erkennen und die Ergebnisse transparent im Dashboard zeigen."
    │
    ├── FAQ-Item 3
    │   Question: "Wie läuft die Zusammenarbeit genau ab?"
    │   Answer: "Wir starten mit einem Strategie-Workshop, definieren Persona, Ziele und Anforderungen und legen den Releaseplan fest. Sie sprechen durchgehend mit der Person, die baut – ohne Agentur-Umwege."
    │
    ├── FAQ-Item 4
    │   Question: "Bietet ihr Support nach dem Launch an?"
    │   Answer: "Ja. Wir übernehmen Wartung, Sicherheitsupdates, Performance-Monitoring und Content-Rollouts in flexiblen Service-Level-Agreements."
    │
    └── FAQ-Item 5
        Question: "Mit welchem Budget sollten wir rechnen?"
        Answer: "Projekte starten ab ca. 5.000 € für schnelle Kampagnen- oder Interimsseiten. Umfangreichere Relaunches inklusive WebApps, GEO (AEO)-Clustern und Tracking bewegen sich im fünfstelligen Bereich."
```

---

### FOOTER

**Komponente:** `<Footer />`
**Datei:** `/src/components/Footer.astro`
**Position:** Slot "footer" im Base-Layout
**Hintergrund:** var(--surface-dark) (#04060D)

```
FOOTER (role: contentinfo)
├── Container (max-width: 1280px, mx-auto, px-6, py-16)
│   │
│   ├── Logo-Section (mb-12)
│   │   Logo: "Wolf-Agents"
│   │   Font: Inter SemiBold, 18px
│   │   Farbe: #FFFFFF
│   │   Tagline: "Code-First Websites & WebApps für regulierte Teams"
│   │   Font: Inter Regular, 14px
│   │   Farbe: rgba(249, 250, 251, 0.72)
│   │
│   ├── Link-Grid (grid-cols-2 md:grid-cols-4, gap-8)
│   │   ├── Column 1: "Branchen" (9 Links)
│   │   ├── Column 2: "Leistungen" (12 Links)
│   │   ├── Column 3: "Wissen" (3 Links: Glossar, Blog, Code statt CMS)
│   │   └── Column 4: "Kontakt & Rechtliches" (4 Links: Kontakt, Über mich, Impressum, Datenschutz)
│   │
│   └── Copyright-Section (border-top, pt-8, mt-12)
│       Text: "© 2025 Wolf-Agents. Alle Rechte vorbehalten."
│       Font: Inter Regular, 14px
│       Farbe: rgba(249, 250, 251, 0.5)
```

---

## 🎨 4. DESIGN-SYSTEM-DETAILS

### Farbpalette (Section-spezifisch)

#### Hero (Dark)
| Element | CSS-Variable | Hex/rgba-Wert | Verwendung |
|---------|--------------|---------------|------------|
| Background | `var(--brand-primary-900)` | #04060D | Section-Hintergrund |
| Grid-Pattern | - | rgba(148, 163, 184, 0.05) | Gitter-Linien |
| Glow | - | rgba(156, 163, 184, 0.35) | Radialer Glow |
| H1-Text | `var(--text-primary-on-dark)` | #F9FAFB | Hauptüberschrift |
| Body-Text | `var(--text-secondary-on-dark)` | rgba(249, 250, 251, 0.72) | Paragraphen |
| Badge Background | `bg-white-alpha-08` | rgba(255, 255, 255, 0.08) | Badge-Hintergrund |
| Badge Border | `border-on-dark-subtle` | rgba(255, 255, 255, 0.18) | Badge-Umrandung |
| Button Gradient | - | linear-gradient(Navy → Slate) | CTA-Button |

#### TLDR (Light)
| Element | CSS-Variable | Hex/rgba-Wert | Verwendung |
|---------|--------------|---------------|------------|
| Background | `var(--surface-light)` | #F9FAFB | Section-Hintergrund |
| Card Background | `var(--surface-light)` | #F9FAFB | Premium-Card |
| Border | `border-on-light-subtle` | rgba(226, 232, 240, 0.7) | Card-Umrandung |
| H2-Text | `var(--text-on-light-primary)` | #0B101A | Überschriften |
| Body-Text | `var(--text-on-light-secondary)` | rgba(55, 65, 81, 0.9) | Paragraphen |
| Aside Background | `var(--surface-navy)` | #0F172A | Dark Aside ("Code statt CMS") |
| Aside Text | `var(--text-on-dark-primary)` | #F9FAFB | Text im Aside |

#### Segments (Dark)
| Element | CSS-Variable | Hex/rgba-Wert | Verwendung |
|---------|--------------|---------------|------------|
| Background | `var(--surface-dark)` | #04060D | Section-Hintergrund |
| Card Background | `bg-white-alpha-08` | rgba(255, 255, 255, 0.08) | Branch-Cards |
| Card Border | `border-on-dark-subtle` | rgba(255, 255, 255, 0.18) | Card-Umrandung |
| H3-Text | - | #FFFFFF | Card-Headlines |
| Body-Text | - | rgba(226, 232, 240, 0.85) | Card-Descriptions |

#### Trust (Light + Grid)
| Element | CSS-Variable | Hex/rgba-Wert | Verwendung |
|---------|--------------|---------------|------------|
| Background | `var(--surface-light)` | #F9FAFB | Section-Hintergrund |
| Grid-Pattern | - | rgba(148, 163, 184, 0.05) | Subtiles Gitter |
| Card Background | `var(--surface-light)` | #F9FAFB | Feature-Cards |
| Card Border | `border-on-light-subtle` | rgba(226, 232, 240, 0.7) | Card-Umrandung |

#### FAQ (Light)
| Element | CSS-Variable | Hex/rgba-Wert | Verwendung |
|---------|--------------|---------------|------------|
| Background | `var(--surface-light)` | #F9FAFB | Section-Hintergrund |
| Accordion Background | `var(--surface-light)` | #F9FAFB | FAQ-Items |
| Accordion Border | `border-on-light-subtle` | rgba(226, 232, 240, 0.7) | Item-Umrandung |
| Question-Text | `var(--text-on-light-primary)` | #0B101A | Fragen |
| Answer-Text | `var(--text-on-light-secondary)` | rgba(55, 65, 81, 0.9) | Antworten |

### Typografie-Details

| Element | Font-Family | Font-Size (Mobile → Desktop) | Font-Weight | Line-Height | Letter-Spacing |
|---------|-------------|------------------------------|-------------|-------------|----------------|
| H1 (Hero) | Inter | 36px → 48px → 72px | 900 (ExtraBold) | 1.15 (tight) | -0.02em |
| H2 (Section-Headlines) | Inter | 30px → 36px | 700 (Bold) | 1.25 | -0.01em |
| H3 (Card-Titles) | Inter | 20px | 600 (SemiBold) | 1.375 (snug) | -0.01em |
| Body (Large) | Inter | 16px → 18px | 400 (Regular) | 1.75 (relaxed) | 0 |
| Body (Standard) | Inter | 14px → 16px | 400 (Regular) | 1.6 | 0 |
| Badge / Label | Inter | 11px → 12px | 600 (SemiBold) | 1 | 0.18em - 0.3em |
| Button-Text | Inter | 16px | 600 (SemiBold) | 1.5 | 0 |
| Footer-Text | Inter | 14px | 400 (Regular) | 1.6 | 0 |

### Spacing-System

| Anwendung | Tailwind-Class | Pixel-Wert | Verwendung |
|-----------|----------------|------------|------------|
| Section Padding (Vertical) | py-20 / py-28 / py-32 | 80px / 112px / 128px | Outer Padding @ Mobile / Tablet / Desktop |
| Container Padding (Horizontal) | px-6 / px-12 | 24px / 48px | Seitenabstände @ Mobile / Desktop |
| Grid-Gap (Cards) | gap-6 / gap-8 | 24px / 32px | Abstand zwischen Cards |
| Element-Gap (Buttons) | gap-4 | 16px | Abstand in Button-Gruppen |
| Margin-Bottom (Headlines) | mb-4 / mb-6 / mb-12 | 16px / 24px / 48px | Abstand H2 → Content |

### Border-Radius-System

| Größe | Tailwind-Class | Pixel-Wert | Verwendung |
|-------|----------------|------------|------------|
| Small | rounded-lg | 8px | Kleine Elemente, Badges |
| Medium | rounded-xl | 12px | Buttons, Icon-Container |
| Large | rounded-[20px] | 20px | Cards, Accordions |
| XL | rounded-3xl | 24px | Premium-Cards, ContentBoxes |
| Full | rounded-full | 9999px | Badges, Avatar |

---

## 📱 5. RESPONSIVE BREAKPOINTS

### Haupt-Breakpoints

| Breakpoint | Screen-Width | Grid-Cols (Segments) | Font-Size H1 | Section Padding |
|------------|--------------|----------------------|--------------|-----------------|
| **Mobile** | < 640px | 1 | 2.25rem (36px) | py-20 (80px) |
| **Tablet** | 640px - 1023px | 2 | 3rem (48px) | py-28 (112px) |
| **Desktop** | ≥ 1024px | 3 | 4.5rem (72px) | py-32 (128px) |

### Section-spezifische Änderungen

**Hero:**
- Mobile: H1 36px, Founder-Card relative (unten)
- Desktop: H1 72px, Founder-Card absolute (bottom-right)

**TLDR:**
- Mobile: Grid 1 Spalte (Content + Aside übereinander)
- Desktop: Grid 2 Spalten (1.15fr + 0.85fr)

**Segments:**
- Mobile: Grid 1 Spalte, Cards übereinander
- Desktop: Grid 3 Spalten, Hover-Effekte aktiviert

**Painpoints (CardGroup):**
- Mobile: Accordion-Pattern (Details/Summary)
- Desktop: Grid 3 Spalten (Cards nebeneinander)

**Trust:**
- Mobile: Grid 1 Spalte
- Tablet: Grid 2 Spalten (2×2)
- Desktop: Grid 4 Spalten (1×4)

**FAQ:**
- Mobile: Volle Breite
- Desktop: Max-width 1024px, zentriert

---

## 🧩 6. KOMPONENTEN-BIBLIOTHEK

### Genutzte Astro-Components

| Komponente | Datei | Props (genutzt auf Startseite) |
|------------|-------|--------------------------------|
| `<Base>` | `/src/layouts/Base.astro` | title, description |
| `<Nav>` | `/src/components/Nav.astro` | slot="header" |
| `<Footer>` | `/src/components/Footer.astro` | slot="footer" |
| `<Hero>` | `/src/components/Hero.astro` | title, subtitle, ctaText, ctaHref, showSecondaryCta, tertiaryCtaText, tertiaryCtaHref, badge, variant="dark-grid", minHeightStyle, founderAvatarSrc, founderAvatarAlt, founderName, founderRole, founderQuote |
| `<Section>` | `/src/components/Section.astro` | tone="light"/"dark", id, glow="center"/"top"/none, grid={true/false}, class (Tailwind-Classes) |
| `<SectionBlack>` | `/src/components/SectionBlack.astro` | - (nicht genutzt auf Startseite) |
| `<ContentBoxDark>` | `/src/components/ContentBoxDark.astro` | heading, headingLevel="h2", class |
| `<InfoTooltip>` | `/src/components/InfoTooltip.astro` | termId (z.B. "geo", "core-web-vitals", "bfsg-2025", "gitops", "rum", "ttfb"), mode="auto"/"modal" |
| `<CardGroup>` | `/src/components/CardGroup.astro` | title, intro, mobilePattern="accordion", columns={3}, items=[{title, badge, description, bullets, metrics, link}] |
| `<TechBelt>` | `/src/components/TechBelt.astro` | id="tech-stack" |

### Hero-Props (vollständig)

```typescript
interface HeroProps {
  title: string;                    // H1-Text
  subtitle: string;                 // Subheadline
  ctaText: string;                  // Primary Button-Label
  ctaHref: string;                  // Primary Button-Link
  showSecondaryCta: boolean;        // false = nur Primary CTA
  tertiaryCtaText: string;          // Tertiary Link-Text
  tertiaryCtaHref: string;          // Tertiary Link-Href (z.B. mailto:)
  badge: string;                    // Badge-Text (oben)
  variant: 'dark-grid' | 'light';   // Hero-Variante
  minHeightStyle: string;           // CSS min-height (z.B. "min-height:100vh;")
  founderAvatarSrc: string;         // Founder-Bild-Pfad
  founderAvatarAlt: string;         // Alt-Text
  founderName: string;              // Name
  founderRole: string;              // Rolle
  founderQuote: string;             // Zitat
}
```

### Section-Props

```typescript
interface SectionProps {
  tone: 'light' | 'dark' | 'navy'; // Hintergrund-Tone
  id?: string;                     // Section-ID (für Anker-Links)
  glow?: 'center' | 'top' | 'none'; // Glow-Effekt-Position
  grid?: boolean;                  // Gitter-Pattern aktivieren
  class?: string;                  // Zusätzliche Tailwind-Classes
}
```

### CardGroup-Props

```typescript
interface CardGroupProps {
  title: string;
  intro: string;
  mobilePattern: 'accordion' | 'grid';
  columns: 2 | 3 | 4;
  items: CardGroupItem[];
}

interface CardGroupItem {
  title: string;
  badge: string;
  description: string;
  bullets: string[];
  metrics: { label: string; value: string }[];
  link: { href: string; label: string };
}
```

### InfoTooltip-Props

```typescript
interface InfoTooltipProps {
  termId: string;         // Glossar-Begriff-ID (z.B. "geo")
  mode: 'auto' | 'modal'; // Anzeige-Modus (auto = inline, modal = Modal-Overlay)
}
```

---

## 🔍 7. SEO & STRUKTURIERTE DATEN

### Meta-Tags (HTML Head)

```html
<title>Websites & WebApps für Kanzleien, Bildung & Behörden | Wolf-Agents</title>
<meta name="description" content="SEO + GEO optimierte, barrierefreie Webplattformen für Kanzleien, Schulen & Behörden in DACH. Automatisierte Intake-, Anmelde- und Bürger-Services, auditierbare Deployments, persönliche Betreuung." />
<link rel="canonical" href="https://www.wolf-agents.com/" />
```

### Schema.org Markup (JSON-LD)

**Typ:** FAQPage

```json
{
  "@context": "https://schema.org",
  "@type": "FAQPage",
  "mainEntity": [
    {
      "@type": "Question",
      "name": "Wie schnell ist unsere neue Website live?",
      "acceptedAnswer": {
        "@type": "Answer",
        "text": "Wir planen üblicherweise 4–6 Wochen vom Kick-off bis zum Go-Live. Sie erhalten früh einen Prototypen, anschließend folgen Content-, QA- und Launch-Phase mit klaren Meilensteinen."
      }
    },
    {
      "@type": "Question",
      "name": "Garantiert ihr gute Core Web Vitals?",
      "acceptedAnswer": {
        "@type": "Answer",
        "text": "Ja. Jede Seite erhält Performance-Budgets (LCP ≤ 2,5 s, INP ≤ 200 ms, CLS ≤ 0,1) und ein Real-User-Monitoring-Setup. So erkennen wir Abweichungen früh und optimieren transparent."
      }
    },
    {
      "@type": "Question",
      "name": "Wie läuft die Zusammenarbeit genau ab?",
      "acceptedAnswer": {
        "@type": "Answer",
        "text": "Wir starten mit einem Strategie-Workshop, definieren Persona, Ziele und Releaseplan und setzen das Projekt in klaren Sprints um. Sie erhalten Preview-Links und direkten Zugang zur Entwicklung."
      }
    },
    {
      "@type": "Question",
      "name": "Bietet ihr Support nach dem Launch an?",
      "acceptedAnswer": {
        "@type": "Answer",
        "text": "Ja. Wir betreuen Wartung, Sicherheitsupdates, Performance-Monitoring und Content-Rollouts in flexiblen Service-Level-Agreements."
      }
    },
    {
      "@type": "Question",
      "name": "Mit welchem Budget sollten wir rechnen?",
      "acceptedAnswer": {
        "@type": "Answer",
        "text": "Projekte starten ab etwa 5.000 € für Kampagnen- oder Interimsseiten. Umfangreiche Relaunches inklusive WebApps bewegen sich im fünfstelligen Bereich."
      }
    }
  ]
}
```

### Open Graph / Twitter Card

```html
<meta property="og:title" content="Websites & WebApps für Kanzleien, Bildung & Behörden | Wolf-Agents" />
<meta property="og:description" content="SEO + GEO optimierte, barrierefreie Webplattformen für Kanzleien, Schulen & Behörden in DACH." />
<meta property="og:url" content="https://www.wolf-agents.com/" />
<meta property="og:type" content="website" />
<meta name="twitter:card" content="summary_large_image" />
<meta name="twitter:title" content="Websites & WebApps für Kanzleien, Bildung & Behörden | Wolf-Agents" />
```

---

## ♿ 8. BARRIEREFREIHEIT (WCAG 2.2)

### Kontrast-Ratios

| Text-Element | Farbe | Hintergrund | Kontrast-Ratio | WCAG-Level |
|--------------|-------|-------------|----------------|------------|
| H1 (Hero) | #F9FAFB | #04060D | 18.5:1 | AAA |
| Body (Hero) | rgba(249, 250, 251, 0.72) | #04060D | 13.2:1 | AAA |
| H2 (Light) | #0B101A | #F9FAFB | 18.3:1 | AAA |
| Body (Light) | rgba(55, 65, 81, 0.9) | #F9FAFB | 8.7:1 | AAA |
| Button (Gradient) | #FFFFFF | Navy/Slate Gradient | ≥ 7:1 | AA |

### Semantische HTML-Struktur

✅ **Korrekt:**
- `<nav>` für Haupt-Navigation
- `<main>` für Haupt-Content (via Base-Layout)
- `<section>` für thematische Bereiche (Hero, TLDR, Segments, etc.)
- `<article>` für Feature-Cards und FAQ-Items
- `<aside>` für "Code statt CMS"-Box
- `<footer>` für Footer-Bereich

✅ **H1-H3-Hierarchie:**
- H1: 1× (Hero: "Code‑First Websites & Web‑Apps...")
- H2: 8× (pro Section: TLDR, Segments, Painpoints, Trust, Tech Stack, CTA, FAQ)
- H3: 9+ (Cards, Features, FAQ-Fragen)

### Interaktive Elemente

✅ **Focus-Rings:**
- Custom Focus-Styles: `focus-visible:outline-none focus-visible:ring-2 focus-visible:ring-offset-2`
- Farbe: Blue-400 (#60A5FA) auf Light, Blue-300 (#93C5FD) auf Dark

✅ **Button vs. Link:**
- Buttons für Aktionen (CTAs): `<button>` oder `<a>` mit Button-Styling
- Links für Navigation: `<a>` mit Underline (Tertiary CTA)

✅ **ARIA-Attribute:**
- `aria-labelledby` für Sections (verweist auf H2-IDs)
- `aria-hidden="true"` für dekorative Icons
- `aria-expanded` für Accordion-Items (automatisch via `<details>`)

✅ **Reduced Motion:**
- Media Query: `@media (prefers-reduced-motion: reduce)` reduziert Transitions/Animationen
- Hover-Effekte: translateY, scale bleiben erhalten, aber Dauer verkürzt

### Keyboard-Navigation

✅ **Navigierbarkeit:**
- Tab-Order: Navigation → Hero CTA → Section-Links → Cards → FAQ-Accordions → Footer
- Skip-Link (optional): "Zum Hauptinhalt springen" (nicht sichtbar im Code, aber Best Practice)

---

## 📈 9. CONTENT-STRATEGIE & TARGETING

### Hauptthema der Seite

Die Startseite positioniert Wolf-Agents als Code-First Plattform-Anbieter für **regulierte & öffentliche Teams** (Kanzleien, Bildung, Behörden). Sie kombiniert SEO/GEO-Expertise, WebApp-Entwicklung (Intake-Flows, Servicecockpits) und Compliance-Module (BFSG, GitOps, Audit-Trails) in einer klaren, messbaren Value Proposition.

### Primäre Keywords

1. **Code-First Websites für Kanzleien**
2. **WebApps für Bildungseinrichtungen**
3. **Barrierefreie Bürgerdienste (BFSG 2025)**
4. **SEO + GEO (AEO) optimiert**
5. **Automatisierte Intake-Flows**
6. **Servicecockpits für Behörden**

### Sekundäre Keywords (LSI)

- Mandatsreisen digitalisieren
- Core Web Vitals Optimierung
- GitOps Deployments
- Auditierbare Webplattformen
- WCAG 2.2 / BITV 2.0 konform
- Completion Rate steigern
- Digital Take-up erhöhen
- Response Time < 1 Stunde
- Lead-to-Call Rate Optimierung

### Zielgruppe

**Primär:**
- Geschäftsführung & Partner in Kanzleien (40-65 Jahre)
- IT-Leitung & Digitalisierungs-Verantwortliche in Behörden (35-55 Jahre)
- Schulleitungen & Verwaltungsleiter in Bildungseinrichtungen (40-60 Jahre)

**Sekundär:**
- Marketing-Verantwortliche (SEO/GEO-Fokus)
- Compliance-Beauftragte (BFSG/DSGVO-Fokus)
- Entwicklungs-Teams (Tech-Stack-Fokus)

### User Intent

**Primär:** Informational + Transactional
- Informational: "Wie digitalisiere ich Mandatsreisen?" / "Was ist BFSG 2025?" / "Wie messe ich Completion Rate?"
- Transactional: "Kostenfreie Strategie-Session sichern" / "Kontakt aufnehmen" / "Capabilities ansehen"

**Sekundär:** Navigational
- "Wolf-Agents" Brand-Search
- "Code statt CMS" (Unique Positioning)

### AIO/GEO/AEO-Status

#### AIO (Answer Intent Optimization)
**Zentrale Frage:** *"Wie digitalisiere ich Mandatsreisen / Campus-Anmeldungen / Bürgerdienste effizient?"*

**Antwort-Struktur:**
- Hero: Value Proposition (< 4 Minuten Intake, Response < 1 h)
- TLDR: Zusammenfassung in 3 Absätzen (Kanzlei, Bildung, Behörden)
- Painpoints (CardGroup): 3 Detailantworten mit KPIs
- FAQ: 5 konkrete Antworten zu Zeitplan, Performance, Prozess, Support, Budget

#### GEO (Generative Engine Optimization)
**Strukturierte Daten:** ✅ FAQPage Schema.org (5 Q&A-Paare)

**Entity-Referenzen:**
- InfoTooltips: 6× Glossar-Links (geo, core-web-vitals, bfsg-2025, gitops, rum, ttfb)
- Branch-Links: 3× Featured Branchen (Kanzleien, Bildung, Behörden)

**Zitatfähigkeit:**
- Metriken: "Lead-to-Call Rate +35 %", "Completion Rate ≥ 70 %", "INP < 200 ms"
- Response Promise: "Antwort in < 1 Stunde (Mo–Fr 09–18 Uhr)"

#### AEO (Answer Engine Optimization)
**Featured-Snippet-Potenzial:** Hoch

- FAQ-Format mit präzisen Antworten (Schema.org FAQPage)
- Metriken-Tabelle (Trust-Section): 180 ms INP, 0.32 s TTFB, 12× Checks, 24/7 Monitoring
- Listicle-Format: 3 Branchen, 4 Trust-Features, 5 FAQ-Fragen

**AI Overview Targeting:**
- Konkrete Zahlen & KPIs (35 %, 70 %, < 1 h, ≤ 5 Tage)
- Vergleiche: "Code statt CMS" (Unique Angle)
- Prozess-Beschreibungen: "4–6 Wochen Kick-off bis Go-Live"

---

## 📝 10. CONTENT-AUDIT-NOTIZEN

### Stärken

✅ **Klare Value Proposition:**
- Hero kommuniziert sofort Zielgruppen (Kanzleien, Bildung, Behörden)
- Konkrete Metriken (< 4 Minuten, +35 %, ≥ 70 %) statt vager Versprechen

✅ **Segment-spezifische Journeys:**
- TLDR-Section differenziert klar: Kanzlei (Intake), Bildung (Anmeldung), Behörden (Bürgerdienste)
- CardGroup liefert 3 detaillierte Use Cases mit Bullets, Metriken, CTAs

✅ **Trust-Elemente:**
- Founder-Card im Hero (persönlicher Ansprechpartner)
- 4 Trust-Features (Inhabergeführt, Faire Preise, Startphase, Modernste Tech)
- Konkrete Performance-Metriken (180 ms INP, 0.32 s TTFB, 24/7 Monitoring)

✅ **SEO & GEO-optimiert:**
- FAQ mit Schema.org FAQPage (5 Q&A-Paare)
- 6 InfoTooltips (Glossar-Verlinkung → Entity-Building)
- H1-H3-Hierarchie korrekt, Meta-Description konkret

✅ **Barrierefreiheit:**
- Kontrast-Ratios AAA (alle Text-Elemente ≥ 7:1)
- Semantisches HTML (`<nav>`, `<main>`, `<section>`, `<article>`, `<aside>`, `<footer>`)
- Focus-Rings vorhanden, Reduced Motion Support

### Altlasten / Schwächen

⚠️ **Hero-Subheadline zu kurz:**
- Aktuell: "Kanzleien digitalisieren Mandatsreisen effizient."
- Problem: Nur 1 Segment adressiert (Kanzleien), Bildung & Behörden fehlen
- Vorschlag (KEINE Umsetzung!): "Kanzleien, Bildung & Behörden digitalisieren Journeys effizient – von Intake bis Bürgerdienst."

⚠️ **CTA-Section (Section 7) generisch:**
- Headline: "Ihr 30-Tage-Fahrplan zur neuen Kanzlei-Website & WebApp."
- Problem: Fokus nur auf Kanzleien, obwohl Seite 3 Segmente adressiert
- Könnte verwirren: Bildungs- & Behörden-Besucher fühlen sich nicht angesprochen

⚠️ **TechBelt (Section 6) fehlt Content-Details:**
- Komponente rendert Logo-Grid, aber keine Text-Beschreibungen
- Für SEO/AIO: Logos allein liefern keinen crawlbaren Text-Content

### Fehlende Elemente

❌ **Testimonials / Case Studies:**
- Keine Kundenzitate oder Referenz-Projekte sichtbar
- Trust wäre höher mit 1-2 konkreten Erfolgsgeschichten (z.B. "Kanzlei XYZ steigerte Lead-to-Call Rate um 42 % in 3 Monaten")

❌ **Video-Content:**
- Keine Video-Einbettung (z.B. Explainer-Video zu "Code statt CMS" oder Servicecockpit-Demo)
- Video könnte Verweildauer & Engagement erhöhen

❌ **Live-Chat / Chatbot:**
- Keine Echtzeit-Support-Option (z.B. Intercom, Drift)
- Response Promise "< 1 h" ist gut, aber asynchron

❌ **Social Proof-Badges:**
- Keine Zertifizierungen, Awards oder "Featured in"-Logos (z.B. "Google Cloud Partner", "Accessibility Certified")

### Content-Refresh-Priorität

🟡 **MITTEL (Refresh in 3-6 Monaten)**

**Begründung:**
- Seite ist **technisch & inhaltlich solide** (gutes Design, klare Struktur, SEO-optimiert)
- Aber: Fehlende Social Proof-Elemente (Testimonials, Case Studies) limitieren Conversion-Potenzial
- CTA-Section könnte inklusiver formuliert werden (alle 3 Segmente ansprechen)

**Empfohlene Maßnahmen (nach Launch):**
1. **Testimonials hinzufügen:** 2-3 Kundenzitate (Kanzlei, Bildung, Behörden) in Trust-Section oder vor FAQ
2. **Hero-Subheadline erweitern:** Alle 3 Segmente adressieren (aktuell nur Kanzleien)
3. **TechBelt ergänzen:** Kurze Text-Beschreibungen unter Logos (z.B. "Astro: Static-Site-Generator für Performance" → crawlbar für SEO)
4. **Video-Embed testen:** Explainer-Video (2-3 Min.) in TLDR-Section oder vor CTA

---

## ⚡ 11. PERFORMANCE & TECHNISCHE DETAILS

### Core Web Vitals (Zielwerte)

| Metrik | Zielwert | Aktueller Stand | Status |
|--------|----------|-----------------|--------|
| **LCP** (Largest Contentful Paint) | < 2.5 s | ~1.8 s (geschätzt) | ✅ Gut |
| **INP** (Interaction to Next Paint) | < 200 ms | ~180 ms (Real-User-Monitoring) | ✅ Gut |
| **CLS** (Cumulative Layout Shift) | < 0.1 | ~0.05 (geschätzt) | ✅ Gut |
| **FCP** (First Contentful Paint) | < 1.8 s | ~1.2 s (geschätzt) | ✅ Gut |
| **TTFB** (Time to First Byte) | < 600 ms | ~320 ms (lt. Trust-Section) | ✅ Ausgezeichnet |

**Messverfahren:**
- Real-User-Monitoring (RUM) via Cloudflare/AWS CloudWatch (laut Trust-Section: "INP im Real-User-Monitoring")
- Lighthouse CI (automatisierte Checks vor Deployment, laut Trust-Section: "12× Automatisierte Checks vor Go-Live")

### Lazy Loading

✅ **Images:**
- Hero Founder-Avatar: `loading="lazy"` (impliziert via Astro Image-Komponente)
- Branch-Cards: Dynamisch geladen via Content-Collection (Astro optimiert automatisch)

✅ **Scripts:**
- Astro Islands: Hydration on-demand (nur interaktive Komponenten wie Accordion, Details/Summary)
- FAQ Schema.org JSON-LD: Inline im `<head>` (blocking, aber klein < 2 KB)

✅ **CSS:**
- Tailwind: Purged (nur genutzte Classes im Production-Build)
- Global CSS: `/src/styles/global.css` (inline im `<head>` für above-the-fold Styles)

### Mobile Optimierung

✅ **Responsive:**
- Breakpoints: < 640px (Mobile), 640-1023px (Tablet), ≥ 1024px (Desktop)
- Viewport Meta: `<meta name="viewport" content="width=device-width, initial-scale=1" />`

✅ **Touch-Targets:**
- Buttons: min. 48px × 48px (Hero CTA, Trust CTA)
- Links: min. 44px × 44px (Navigation, Footer)
- FAQ-Accordions: min. 60px Höhe (Summary-Element)

✅ **Mobile-First Design:**
- Hero: Stack-Layout @ Mobile (Badge → H1 → Subtitle → CTAs → Founder-Card)
- TLDR: 1 Spalte @ Mobile (Content → Aside übereinander)
- Segments: 1 Spalte @ Mobile (Cards übereinander, Hover-Effekte deaktiviert)
- Painpoints: Accordion @ Mobile (Details/Summary statt Grid)

### Performance-Optimierungen (Code-Ebene)

✅ **Astro Islands:**
- Hero, Section, CardGroup, InfoTooltip: Statisch gerendert (kein JS)
- Nur interaktive Elemente (Accordion, Details/Summary) erhalten client-side JS

✅ **Edge Rendering:**
- Deployment: Cloudflare Pages oder AWS CloudFront (laut Leistungen-Seiten)
- TTFB: 320 ms (laut Trust-Section) → Edge-Caching aktiv

✅ **Code-Splitting:**
- Astro: Automatisches Code-Splitting pro Route
- Komponenten-Chunks: Nur genutzte Komponenten im Bundle

---

## 📊 12. CONTENT-METRIKEN

### Textmenge

| Metrik | Wert |
|--------|------|
| **Gesamtzeichen** | ~15.400 (ohne Code/HTML) |
| **Gesamtwörter** | ~2.150 |
| **Lesedauer** | 9-11 Minuten (bei 200 Wörter/Min.) |

**Verteilung pro Section:**
- Hero: ~80 Wörter (Badge, H1, Subtitle, CTAs, Founder-Quote)
- TLDR: ~350 Wörter (Badge, H2, 3 Paragraphen, 2 KPI-Cards, Aside-Content)
- Segments: ~250 Wörter (Badge, H2, Intro, 3 Card-Descriptions, CTA)
- Painpoints: ~400 Wörter (Badge, H2, Intro, CardGroup-Content: 3 Cards mit Bullets)
- Trust: ~300 Wörter (Badge, H2, Intro, 4 Features, 4 Metriken)
- Tech Stack: ~80 Wörter (Badge, H2, Intro, Logo-Liste)
- CTA: ~150 Wörter (H2, Intro, CTA-Texte, Feature-Liste)
- FAQ: ~480 Wörter (Badge, H2, Intro, 5 Q&A-Paare)

### Link-Dichte

| Kategorie | Anzahl |
|-----------|--------|
| **Interne Links (Navigation)** | ~25 (Branchen-Dropdown: 9, Leistungen-Dropdown: 12, Wissen-Dropdown: 3, Kontakt: 1) |
| **Interne Links (Content)** | ~12 (Hero CTA, TLDR CTA, Segments: 4, Painpoints: 3, CTA: 2) |
| **Glossar-Tooltips (InfoTooltip)** | 6 (geo, core-web-vitals, bfsg-2025, gitops, rum, ttfb) |
| **Footer-Links** | ~28 (Branchen: 9, Leistungen: 12, Wissen: 3, Rechtliches: 4) |
| **Externe Links** | 1 (mailto:info@wolf-agents.com) |
| **Gesamt** | ~72 |

**Link-Dichte-Ratio:** 72 Links / 2.150 Wörter = **~3,3 % Link-Dichte** (gesund, nicht überladen)

### Content-Verteilung (Dark vs. Light)

| Tone | Anzahl Sections | Prozent |
|------|-----------------|---------|
| **Dark** | 5 (Hero, Segments, Painpoints, Tech Stack, Footer) | **62,5 %** |
| **Light** | 3 (TLDR, Trust, FAQ) | **37,5 %** |

**Hinweis:** CTA (Section 7) ist Light mit Dark-Card (ContentBoxDark) → zählt als Light.

### Interaktive Elemente

| Element-Typ | Anzahl | Beispiele |
|-------------|--------|-----------|
| **Buttons** | 7 | Hero CTA (2x), TLDR CTA, Segments CTA, CTA-Section (2x), Navigation CTA |
| **Links (Text)** | ~65 | Navigation, Footer, Segment-Cards, Branch-Cards, etc. |
| **Collapsibles (Details/Summary)** | 6 | TLDR "Mehr lesen" (1x), FAQ-Accordions (5x) |
| **InfoTooltips** | 6 | geo, core-web-vitals, bfsg-2025, gitops, rum, ttfb |
| **Hover-Cards** | 7 | 3 Branch-Cards, 4 Trust-Features |

**Gesamt:** ~91 interaktive Elemente

### Medien-Elemente

| Element-Typ | Anzahl | Beispiele |
|-------------|--------|-----------|
| **Images** | 1 | Founder-Avatar (/img/business-foto.jpg) |
| **SVG-Icons** | ~25 | Checkmarks (Trust, CTA), Pfeile (CTAs), Plus-Icons (FAQ), Segment-Icons |
| **Background-Patterns** | 5 | Grid-Pattern (Hero, Segments, Painpoints, Trust, Tech Stack) |
| **Glow-Effekte** | 3 | Hero (center), Segments (center), Painpoints (top) |

**Hinweis:** TechBelt enthält Tech-Logos (Astro, Tailwind, Cloudflare, etc.) – Anzahl variabel, geschätzt 6-8 Logos.

---

## ✅ DOKUMENTATIONS-CHECKLISTE

- [x] Alle 12 Haupt-Sections ausgefüllt
- [x] Metriken berechnet (Zeichen: ~15.400, Wörter: ~2.150, Lesedauer: 9-11 Min., Links: ~72)
- [x] Mindestens 3 Farb-Details pro Section dokumentiert (CSS-Variable + Hex/rgba)
- [x] Alle H1-H3-Headlines wortgetreu übernommen
- [x] Komponenten-Props vollständig aufgelistet (Hero, Section, CardGroup, InfoTooltip, etc.)
- [x] Responsive Breakpoints dokumentiert (Mobile/Tablet/Desktop Tabelle)
- [x] Content-Audit-Notizen hinzugefügt (Stärken: 5, Schwächen: 3, Fehlende Elemente: 4)
- [x] Verlinkungsstruktur vollständig (Navigation, Content-Links, Footer, InfoTooltips, Backlinks)
- [x] SEO & Schema.org dokumentiert (FAQPage mit 5 Q&A-Paaren)
- [x] Barrierefreiheit-Prüfung (Kontrast-Ratios AAA, Semantik, Focus-Rings, Reduced Motion)
- [x] Performance-Details (Core Web Vitals Zielwerte, Lazy Loading, Mobile Optimierung)
- [x] Code-Block-Format für Layout-Struktur (alle Sections als Baum-Ansicht)

---

**ENDE DER STARTSEITEN-DOKUMENTATION**

Diese Dokumentation folgt dem DOKUMENTATIONS-PROTOKOLL v1.0 und dient als Referenz für Content-Optimierung, Architektur-Analyse und strategische Planung.
