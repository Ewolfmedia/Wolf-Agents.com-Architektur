# LEISTUNGEN-INDEX (Hub-Seite)

**Verweis:** Siehe `/04-LEISTUNGEN/00-LEISTUNGEN-TEMPLATE.md` für gemeinsame Struktur

**⚠️ WICHTIG:** Diese Seite weicht vom Standard-Leistungen-Template ab! Sie ist eine **Hub-Seite** mit 3 Hauptbereichen statt der typischen Struktur.

**Dokumentiert am:** 2025-10-30
**Status:** IST-Zustand

---

## 📊 META-INFORMATIONEN

| Attribut | Wert |
|----------|------|
| **URL** | https://www.wolf-agents.com/leistungen |
| **Datei** | `/src/pages/leistungen/index.astro` |
| **Title Tag** | "Leistungen & Betriebsmodelle für regulierte Teams \| Wolf-Agents" |
| **Meta Description** | "Vier Betriebsstufen (Rapid Response, Astro Hub, Cloudflare Multi-Site, AWS Governance) plus Fach-Module für Analytics, SEO/GEO, UX & Barrierefreiheit – zugeschnitten auf Kanzleien, Bildung & Behörden." |
| **Canonical URL** | https://www.wolf-agents.com/leistungen |
| **Noindex** | Nein |
| **Geschätzte Zeichenanzahl** | ~9.500 Zeichen (ohne Code/HTML) |
| **Geschätzte Wortanzahl** | ~1.350 Wörter |
| **Geschätzte Lesedauer** | 5-7 Minuten |
| **Anzahl Sections** | 6 Hauptbereiche |
| **Anzahl H1** | 1 |
| **Anzahl H2** | 5 |
| **Anzahl H3** | 13 (4 Stufen + 6 Module + 3 Engagement) |

---

## 🏗️ ABWEICHUNGEN VOM TEMPLATE

**Diese Seite folgt NICHT dem Standard-Leistungen-Pattern (TL;DR → Segment-Cases → Deliverables).**

**Stattdessen: Hub-Struktur**
1. Hero (Standard)
2. Warum Wolf-Agents (Intro-Section mit TL;DR-Box + 3 KPI-Cards)
3. **Betriebsstufen** (Dark Section mit 4 Stage-Cards)
4. **Fach-Module** (Light Section mit 6 Module-Cards)
5. **Engagement-Modelle** (Navy Section mit 3 Engagement-Cards)
6. Final CTA (Standard)

---

## 🏗️ HERO-BEREICH

**Badge:** "Mo–Sa 8–20 Uhr erreichbar"
**H1 (Title):** "Betriebsmodelle & Module für regulierte Projekte"
**Subtitle:** "Von Rapid-Response Microsites bis zum AWS Governance Stack – wir liefern Websites, WebApps und Servicecockpits für Kanzleien, Bildung und Behörden inklusive KPIs, Compliance und persönlichem SLA."

**Primary CTA:** "Kontakt aufnehmen" → `/kontakt`
**Secondary CTA:** ❌ Keine (showSecondaryCta={false})

**Props:**
```astro
<Hero
  title="Betriebsmodelle & Module für regulierte Projekte"
  subtitle="Von Rapid-Response Microsites bis zum AWS Governance Stack – wir liefern Websites, WebApps und Servicecockpits für Kanzleien, Bildung und Behörden inklusive KPIs, Compliance und persönlichem SLA."
  badge="Mo–Sa 8–20 Uhr erreichbar"
  ctaText="Kontakt aufnehmen"
  ctaHref="/kontakt"
  showSecondaryCta={false}  ← Keine Secondary CTA!
  variant="dark-grid"
  minHeightStyle="min-height:100vh;min-height:100dvh;"
/>
```

---

## 📊 SECTION 1: WARUM WOLF-AGENTS (Light)

**Layout:** ContentBoxLight (große TL;DR-Box) + 3 KPI-Cards

### TL;DR-Box ("Warum Wolf-Agents")

**Badge:** "Warum Wolf-Agents"
**H2:** "Ein Code-Stack, vier Betriebsstufen, modulare Fachleistungen"

**Content (2-Spalten-Grid @ Desktop):**

**Spalte 1 (Links):**
- "Jede Stufe basiert auf einem gemeinsamen Astro-Code-Stack und liefert unterschiedliche Infrastruktur-Level – von bestehendem Hosting (Stufe 0) bis zu AWS Governance (Stufe C). Upgrades funktionieren ohne Replatforming, Core Web Vitals bleiben stabil und Deployments sind nachvollziehbar."
- "Ergänzende Module wie Analytics & Consent, Technical SEO & GEO, Barrierefreiheit (BFSG 2025), UX/Redesign und Migration sorgen dafür, dass Content, KPIs und Governance auf einer Linie bleiben."
  - **InfoTooltip:** `<InfoTooltip termId="bfsg-2025" />` (einziger Tooltip auf Seite!)

**Spalte 2 (Rechts):**
- "Wir arbeiten segment-spezifisch: Kanzleien steigern Lead-to-Call Rate & Response Time, Bildungseinrichtungen optimieren Einschreibungen und mobile Nutzung, Behörden erhöhen Completion Rate & Digital Take-up. Alle Maßnahmen werden in Servicecockpits, Jour-fixe Reports und Governance-Dokumenten festgehalten."
- "Unser Response Promise: Antwort in < 1 Stunde (Mo–Fr 09–18 Uhr), Kick-off innerhalb von 5 Werktagen, dokumentierte Entscheidungen und persönliche Betreuung."

### ContentBoxDark (Nested!)

**Badge:** "Code statt CMS"
**Heading:** "Warum modulare Komponenten?"

**Content:**
"Astro Islands & Edge Rendering halten **INP < 200 ms** und **LCP < 2.3 s** als Budget. Servicecockpits zeigen Completion Rate, Response Time & Digital Take-up – ideal für Intake-Teams. GitOps Deployments mit Audit-Log, Feature Flags und Rollbacks sichern Governance ab."

**CTA-Link:** "Code-First Ansatz im Detail" → `/code-statt-cms`

### KPI-Highlights (3 Cards)

**Grid:** grid-cols-1 sm:grid-cols-3 gap-4

**Card 1:**
- **Value:** "< 1 h"
- **Label:** "Response Promise"
- **Context:** "Mo–Fr 09–18 Uhr, direkter Ansprechpartner"

**Card 2:**
- **Value:** "≤ 5 Tage"
- **Label:** "Kick-off"
- **Context:** "Rapid Response & Audit-Projekte"

**Card 3:**
- **Value:** "INP < 200 ms"
- **Label:** "Performance-Budget"
- **Context:** "Shared Code-Stack für alle Stufen"

---

## 🏢 SECTION 2: BETRIEBSSTUFEN (Dark)

**Section-Tone:** `tone="dark"`
**ID:** `id="stufen"` (Anchor-Link-Ziel)
**Scroll-Margin:** `scroll-mt-28 md:scroll-mt-36` (für Sticky Nav)

**Badge:** "Betriebsmodelle"
**H2:** "Vier Stufen – vom Notfall-Launch bis zur Enterprise-Governance"
**Intro:** "Wählen Sie das Betriebsmodell, das zu Ihrer Infrastruktur, Compliance und Teamstruktur passt. Upgrades bleiben einfach, weil Code, Komponenten und Prozesse identisch bleiben."

### Stage-Cards (4)

**Grid:** grid-cols-1 sm:grid-cols-2 lg:grid-cols-4 gap-6

**Card-Styling:**
- Class: `stage-card-base stage-card--[foundation/standard/advanced/governance]`
- Custom Styling: Surface-Light Background mit leichtem Gradient
- Border: 1px solid var(--border-on-light-subtle)
- Padding: p-6
- Border-radius: rounded-2xl
- Hover: hover:-translate-y-1 hover:shadow-lg

**Card 1: Stufe 0 – Rapid Response**
- **Label:** "Stufe 0" (xs, uppercase, tracking 0.3em, text-on-light-muted)
- **H3:** "Rapid Response"
- **Description:** "≤ 10 Tage live auf bestehendem Hosting – Interim Microsites, Kampagnen, Service-Updates."
- **Link:** "Details ansehen" → `/leistungen/stufe-0-ftp-classic`

**Card 2: Stufe A – Astro Knowledge Hub**
- **Label:** "Stufe A"
- **H3:** "Astro Knowledge Hub"
- **Description:** "Modulare Astro-Plattform, Content-Workflows, KPIs – ideal für Kanzleien, Campus & Bürgerdienste."
- **Link:** "Details ansehen" → `/leistungen/stufe-a-astro-ftp`

**Card 3: Stufe B – Cloudflare Multi-Site**
- **Label:** "Stufe B"
- **H3:** "Cloudflare Multi-Site"
- **Description:** "GitOps, Edge-Caching, Workers, Zero-Downtime Deployments & Security für internationale Teams."
- **Link:** "Details ansehen" → `/leistungen/stufe-b-cloudflare-pages`

**Card 4: Stufe C – AWS Governance Stack**
- **Label:** "Stufe C"
- **H3:** "AWS Governance Stack"
- **Description:** "CloudFront, WAF, IaC, SLA & Observability – für höchste Compliance- und Verfügbarkeitsanforderungen."
- **Link:** "Details ansehen" → `/leistungen/stufe-c-aws-cloudfront`

---

## 🔧 SECTION 3: FACH-MODULE (Light)

**Section-Tone:** `tone="light"`
**ID:** `id="module"` (Anchor-Link-Ziel)
**Scroll-Margin:** `scroll-mt-28 md:scroll-mt-36`

**Badge:** "Fach-Module"
**H2:** "Module für KPIs, UX & Compliance"
**Intro:** "Ergänzen Sie Ihr Betriebsmodell mit spezialisierten Sprints: Analytics & Consent, Technical SEO & GEO, Accessibility/BFSG, UX Redesign, Migration & Governance."

### Module-Cards (6)

**Grid:** grid gap-6 md:grid-cols-3

**Card-Styling:**
- Background: `surface-light`
- Border: 1px solid var(--border-on-light-subtle)
- Border-radius: rounded-2xl
- Padding: p-6
- Shadow: shadow-sm
- Hover: hover:-translate-y-1 hover:shadow-lg transition duration-300
- **Alle Cards sind Links** (`<a href="...">`)

**Card 1: Analytics & Consent**
- **H3:** "Analytics & Consent"
- **Description:** "Consent Mode v2, Server-Side Tracking, KPI Dashboards für Lead-to-Call, Completion Rate & Zufriedenheit."
- **Link:** `/leistungen/analytics-consent`

**Card 2: SEO, GEO & Performance**
- **H3:** "SEO, GEO & Performance"
- **Description:** "Technical SEO, GEO/AEO, Performance Budgets und Schema Automationen für regulierte Domains."
- **Link:** `/leistungen/seo-tech`

**Card 3: GEO & Location Clusters**
- **H3:** "GEO & Location Clusters"
- **Description:** "Entity Maps, AI Overview Snippets, Location Templates und KPI-Reporting für lokale Sichtbarkeit."
- **Link:** `/leistungen/geo`

**Card 4: Barrierefreiheit & BFSG**
- **H3:** "Barrierefreiheit & BFSG"
- **Description:** "WCAG 2.2 AA Audits, BFSG Nachweise, Remediation Kits, Monitoring & Schulungen."
- **Link:** `/leistungen/barrierefreiheit`

**Card 5: Redesign & UX Sprints**
- **H3:** "Redesign & UX Sprints"
- **Description:** "Research, UX/UI, Prototyping, Testing, KPI-Budgets und Handover für regulierte Journeys."
- **Link:** `/leistungen/redesign`

**Card 6: Migration & Redirect Ops**
- **H3:** "Migration & Redirect Ops"
- **Description:** "Content Inventory, Redirect Maps, QA & Hypercare – zero-downtime Migrationen inklusive KPI Monitoring."
- **Link:** `/leistungen/migration-redirects`

---

## 🤝 SECTION 4: ENGAGEMENT-MODELLE (Navy)

**Section-Tone:** `tone="navy"` (dunklerer Blauton statt Dark)
**ID:** `id="engagement"` (Anchor-Link-Ziel)
**Scroll-Margin:** `scroll-mt-28 md:scroll-mt-36`

**Badge:** "Engagement Modelle"
**H2:** "So arbeiten wir zusammen"
**Intro:** "Wählen Sie den Einstieg, der zu Ihren Ressourcen passt – vom Audit bis zum Managed Ops Modell. Alle Optionen enthalten klare KPIs, Reporting und Governance."

### Engagement-Cards (3)

**Grid:** grid grid-cols-1 md:grid-cols-3 gap-8

**Card-Styling:**
- Background: `bg-white-alpha-08` (transparentes Weiß auf Navy)
- Border: 1px solid var(--border-on-dark-subtle)
- Border-radius: rounded-2xl
- Padding: p-8
- Shadow: `0_30px_80px_-60px_rgba(15,23,42,0.55)`
- Text-Farbe: text-white (Headlines), text-white/80 (Body), text-white/70 (List)

**Card 1: Audit & Quick Wins**
- **H3:** "Audit & Quick Wins"
- **Description:** "2–4 Wochen Fokus auf Technical SEO, GEO, Performance oder Barrierefreiheit – inkl. Roadmap & Umsetzung."
- **UL (3 Items):**
  - "Priorisierte To-do-Liste & Aufwand"
  - "KPI-Baselines & Dashboards"
  - "Enablement Workshop"

**Card 2: Design & Build Sprint**
- **H3:** "Design & Build Sprint"
- **Description:** "4–6 Wochen Design/Build Iterationen – von UX/Content bis Deployment, inklusive QA & KPI Reviews."
- **UL (3 Items):**
  - "UX/Content + Dev Sprint"
  - "Testing & Regression"
  - "Handover & Playbooks"

**Card 3: Managed Ops & SLA**
- **H3:** "Managed Ops & SLA"
- **Description:** "Langfristige Betreuung mit Jour-fixe, KPI Reporting, Incident Response, Backlog Pflege & Skalierung."
- **UL (3 Items):**
  - "Response Promise & Servicecockpit"
  - "Backlog & Roadmap Pflege"
  - "Performance/Accessibility Monitoring"

---

## 🎯 SECTION 5: FINAL CTA (Light)

**ContentBoxDark (wie Template)**

**Heading (H2):** "Projekt einordnen lassen?"
**Description:** "Wir klären Ziele, KPIs, Zeitfenster und Governance in einem kurzen Call. Sie erhalten eine priorisierte Roadmap und klare nächste Schritte."

**CTAs:**
- **Primary:** "Erstgespräch sichern" → `/kontakt`
- **Secondary:** "Wissen & Playbooks ansehen" → `/wissen`

---

## 🔗 VERLINKUNGSSTRUKTUR

### Interne Links (ausgehend)

**Navigation:** `/`, `/branchen/`, `/leistungen/`, `/wissen/`

**Hero:**
- Primary CTA: `/kontakt`

**Warum Wolf-Agents Section:**
- Code-First-Link: `/code-statt-cms`
- InfoTooltip: `/wissen/glossar/bfsg-2025` (via InfoTooltip-Component)

**Betriebsstufen Section (4 Links):**
- `/leistungen/stufe-0-ftp-classic`
- `/leistungen/stufe-a-astro-ftp`
- `/leistungen/stufe-b-cloudflare-pages`
- `/leistungen/stufe-c-aws-cloudfront`

**Fach-Module Section (6 Links):**
- `/leistungen/analytics-consent`
- `/leistungen/seo-tech`
- `/leistungen/geo`
- `/leistungen/barrierefreiheit`
- `/leistungen/redesign`
- `/leistungen/migration-redirects`

**Final CTA:**
- `/kontakt`
- `/wissen`

**Footer:** Diverse Links

**Gesamtanzahl interne Links:** ~25-30 (inkl. Navigation, Footer)

### Anchor-Links (Intra-Page)

**Keine Hero-Quicklinks auf dieser Seite** (im Gegensatz zu heroQuickLinks-Array im Code, der definiert ist, aber nicht gerendert wird)

**Anchor-IDs:**
- `#stufen` → Betriebsstufen Section
- `#module` → Fach-Module Section
- `#engagement` → Engagement-Modelle Section

**Verlinkt von anderen Leistungen-Seiten:**
- `/leistungen/geo` → Secondary CTA: "Stufen vergleichen" → `/leistungen#module`
- Andere Leistungen haben ähnliche Links zu `#stufen` oder `#module`

---

## 🔍 BESONDERHEITEN

### 1. Hero-Quicklinks-Array (nicht gerendert)

**Im Code definiert, aber nicht genutzt:**
```javascript
const heroQuickLinks = [
  {
    label: 'Betriebsstufen',
    href: '#stufen',
    description: 'Rapid Response bis AWS Governance',
    badge: 'Vergleich'
  },
  {
    label: 'Module & KPIs',
    href: '#module',
    description: 'Analytics, SEO, BFSG, Migration'
  },
  {
    label: 'Engagement-Modelle',
    href: '#engagement',
    description: 'Audit, Sprint, Managed Ops',
    duration: 'Kick-off ≤ 5 Tage'
  }
];
```

**Nicht im Hero-Component gerendert** (Hero-Component hat kein Prop für Quicklinks).

**Vermutung:** Geplantes Feature, aber noch nicht implementiert oder entfernt.

### 2. KPI-Highlights-Array

**Hardcoded Array für 3 KPI-Cards:**
```javascript
const kpiHighlights = [
  {
    value: '< 1 h',
    label: 'Response Promise',
    context: 'Mo–Fr 09–18 Uhr, direkter Ansprechpartner'
  },
  {
    value: '≤ 5 Tage',
    label: 'Kick-off',
    context: 'Rapid Response & Audit-Projekte'
  },
  {
    value: 'INP < 200 ms',
    label: 'Performance-Budget',
    context: 'Shared Code-Stack für alle Stufen'
  }
];
```

**Gerendert als 3 Cards nach der Warum-Wolf-Agents-Box.**

### 3. Stage-Card-Classes

**Custom CSS-Classes (vermutlich in global.css):**
- `stage-card-base` (Basis-Styling)
- `stage-card--foundation` (Stufe 0, leichter Grau-Ton)
- `stage-card--standard` (Stufe A, leichter Blau-Ton)
- `stage-card--advanced` (Stufe B, leichter Grün-Ton?)
- `stage-card--governance` (Stufe C, leichter Gold-Ton?)

**Vermutung:** Farbliche Differenzierung der Betriebsstufen (nicht in Template dokumentiert).

### 4. Navy-Tone (statt Dark)

**Section-Tone "navy"** ist einzigartig für Engagement-Modelle Section.

**Unterschied zu "dark":**
- Navy: Dunklerer Blauton (vermutlich `--brand-primary-800` oder ähnlich)
- Dark: Schwarz (#04060D)

**Nur auf Index-Seite genutzt!**

### 5. Keine Segment-Cases

**Im Gegensatz zu allen anderen Leistungen-Seiten:**
- ❌ Keine Segment-Cards (Kanzleien, Schulen, Behörden)
- ❌ Keine segmentCases-Array

**Grund:** Index ist Hub-Seite, verlinkt direkt zu Stufen + Modulen statt Segmenten.

### 6. InfoTooltip-Usage

**Nur 1× InfoTooltip auf gesamter Seite:**
- `<InfoTooltip termId="bfsg-2025" />` in Warum-Wolf-Agents-Section

**Niedrigste Dichte** aller Leistungen-Seiten (außer Seiten ohne Tooltips).

---

## 📊 CONTENT-AUDIT

### ✅ Stärken

- ✅ **Klare Hub-Struktur:** 3 Hauptbereiche (Stufen, Module, Engagement) übersichtlich getrennt
- ✅ **Anchor-Links:** #stufen, #module, #engagement ermöglichen direktes Anspringen von anderen Seiten
- ✅ **KPI-Highlights:** Response Promise, Kick-off-Zeit, Performance-Budget sofort sichtbar
- ✅ **Engagement-Modelle:** Einzigartig auf Index-Seite, hilft bei Pricing/Scope-Fragen
- ✅ **Konsistente Card-Layouts:** Alle Stage/Module/Engagement-Cards folgen gleichem Muster
- ✅ **Verlinkung zu Detail-Seiten:** Jede Stufe/Modul hat "Details ansehen"-Link
- ✅ **ContentBoxDark-Nested:** "Code statt CMS" als Nested-Box in TL;DR-Section (interessantes Pattern)

### ⚠️ Schwächen

- ⚠️ **Hero-Quicklinks nicht gerendert:** Array definiert, aber nicht genutzt (tote Code?)
- ⚠️ **Keine Segment-Fokussierung:** Im Gegensatz zu anderen Leistungen keine Branchen-Cards
- ⚠️ **Stage-Card-Classes undokumentiert:** Custom CSS-Classes (stage-card--foundation, etc.) ohne Farbdoku
- ⚠️ **Navy-Tone unklar:** Was ist der genaue Unterschied zu Dark? Farbe nicht dokumentiert
- ⚠️ **Keine Quick Wins/Proof:** Keine KPI-Badges wie "+35 % Anfragen" (wie auf anderen Leistungen)
- ⚠️ **Lange TL;DR-Section:** 2-Spalten-Text + Nested ContentBoxDark + 3 KPI-Cards = viel Content

### ❌ Fehlende Elemente

- ❌ **Schema.org-Markup:** Kein Service/Offer-Schema (wie alle Leistungen-Seiten)
- ❌ **FAQ-Section:** Keine FAQs zu Stufen/Modulen/Engagement
- ❌ **Vergleichstabelle:** Stufen 0-C könnten als Tabelle mit Features verglichen werden
- ❌ **Pricing-Hints:** Keine Preisangaben oder Ranges für Stufen/Module
- ❌ **Testimonials:** Keine Client-Zitate für Engagement-Modelle
- ❌ **Case Studies:** Keine Verlinkung zu Projekt-Beispielen
- ❌ **Hero-Quicklinks:** Definiert im Code, aber nicht gerendert (vermutlich geplant)

### 🔴 PRIORITÄT

**Content-Refresh-Priorität:** 🟡 **MITTEL**

**Begründung:**
- **Wichtig:** Hub-Seite verlinkt alle anderen Leistungen → hoher Traffic erwartet
- **Aber:** Gut strukturiert, alle Infos vorhanden, keine kritischen Lücken
- **Verbesserungspotenzial:** Schema.org, FAQ, Vergleichstabelle würden SEO/UX steigern

**Empfohlene Maßnahmen:**

1. **Schema.org-Markup hinzufügen** - Timeline: 1 Woche
   - `Service`-Schema für Stufen + Module
   - `Offer`-Schema für Engagement-Modelle
   - `FAQPage`-Schema falls FAQ hinzugefügt wird

2. **Hero-Quicklinks aktivieren** - Timeline: 2 Tage
   - Quicklinks-Array wird bereits im Code definiert
   - Hero-Component erweitern um Quicklinks-Prop
   - Oder: Hero-Quicklinks als separate Section unter Hero

3. **Stufen-Vergleichstabelle** - Timeline: 1 Woche
   - Tabelle mit Features (Hosting, GitOps, SLA, Pricing-Hints, Timeline)
   - Hilft bei Stufen-Auswahl (Stufe 0 vs. C schwer vergleichbar aktuell)

4. **FAQ-Section hinzufügen** - Timeline: 1 Woche
   - 5-8 FAQs zu Stufen-Wahl, Upgrades, Engagement-Modellen
   - Schema.org FAQPage-Markup
   - Accordion-Format (wie Branchen-Seiten)

5. **Stage-Card-Colors dokumentieren** - Timeline: 1 Tag
   - CSS-Variablen für stage-card--foundation, --standard, --advanced, --governance
   - Falls nicht vorhanden: Definieren (leichte Farb-Töne für visuelle Differenzierung)

---

## 🎯 CONTENT-STRATEGIE

**Primäre Keywords:**
- Leistungen für regulierte Branchen
- Betriebsmodelle für Websites
- Astro Hub vs. AWS Governance
- Fach-Module für Compliance
- Engagement-Modelle Webentwicklung

**Sekundäre Keywords (LSI):**
- Rapid Response Launch
- GitOps Deployment
- BFSG 2025 Audit
- Consent Mode v2 Setup
- Technical SEO für Kanzleien
- GEO für Bildung
- Migration & Redirects

**Zielgruppe:**
- IT-Entscheider in Kanzleien, Bildung, Behörden
- Marketing-Leiter regulierter Organisationen
- Compliance-Verantwortliche (BFSG, DSGVO)
- Geschäftsführer kleiner/mittelständischer Firmen

**User Intent:**
- **Primär:** Commercial Investigation (Leistungen vergleichen, Stufen-Wahl treffen)
- **Sekundär:** Informational (Was ist Stufe A? Was kostet Migration?)

**AIO/GEO/AEO-Status:**
- **AIO:** "Welche Betriebsmodelle gibt es für regulierte Websites?"
- **GEO:** ⚠️ Kein Schema.org-Markup → geringe GEO-Optimierung
- **AEO:** Vergleichstabelle + FAQ würden Featured-Snippet-Potenzial erhöhen

---

## 📏 CONTENT-METRIKEN

**Textmenge:**
- Gesamtzeichen: ~9.500
- Gesamtwörter: ~1.350
- Lesedauer: 5-7 Minuten

**Link-Dichte:**
- Interne Links: ~25-30 (Navigation, Stufen, Module, Engagement, Footer)
- Externe Links: 0
- CTAs: 3 (Hero, Warum-Wolf-Agents ContentBox, Final CTA)

**Content-Verteilung:**
- Light Sections: 2 (Warum Wolf-Agents, Fach-Module, Final CTA)
- Dark Sections: 1 (Betriebsstufen)
- Navy Sections: 1 (Engagement-Modelle)
- Hero: 1

**Interaktive Elemente:**
- Buttons/Links: ~15 (4 Stufen + 6 Module + 2 Final CTAs + 1 Code-First)
- InfoTooltips: 1
- Collapsibles/Accordions: 0

---

## 📐 RESPONSIVE ANPASSUNGEN

**Hero:**
- Mobile: H1 36px, 1-spaltig
- Desktop: H1 72px, 1-spaltig (zentriert)

**Warum Wolf-Agents:**
- Mobile: 2-Spalten-Grid stackt zu 1-Spalte
- Desktop: 2-Spalten-Grid (grid-cols-2)

**KPI-Highlights:**
- Mobile: 1-Spalte (sm:grid-cols-3 greift erst ab 640px)
- Tablet: 3-Spalten-Grid
- Desktop: 3-Spalten-Grid

**Betriebsstufen (Stage-Cards):**
- Mobile: 1-Spalte
- Tablet (sm): 2-Spalten-Grid (sm:grid-cols-2)
- Desktop (lg): 4-Spalten-Grid (lg:grid-cols-4)

**Fach-Module:**
- Mobile: 1-Spalte
- Desktop (md): 3-Spalten-Grid (md:grid-cols-3)

**Engagement-Modelle:**
- Mobile: 1-Spalte
- Desktop (md): 3-Spalten-Grid (md:grid-cols-3)

---

**ENDE DER DOKUMENTATION - LEISTUNGEN-INDEX**

**Umfang:** ~1.200 Wörter (Kompakt-Stil)
**Besonderheit:** Hub-Seite mit Abweichungen vom Standard-Template
**Status:** ✅ Vollständig dokumentiert
