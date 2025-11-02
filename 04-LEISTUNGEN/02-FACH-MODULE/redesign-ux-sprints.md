# REDESIGN & UX SPRINTS

**Verweis:** Siehe `/04-LEISTUNGEN/00-LEISTUNGEN-TEMPLATE.md` für gemeinsame Struktur

**Dokumentiert am:** 2025-10-31
**Status:** IST-Zustand

---

## 📊 META-INFORMATIONEN

| Attribut | Wert |
|----------|------|
| **URL** | https://www.wolf-agents.com/leistungen/redesign |
| **Datei** | `/src/pages/leistungen/redesign.astro` |
| **Title Tag** | "Redesign & UX Sprints für regulierte Teams \| Wolf-Agents" |
| **Meta Description** | "UX-Design, Content, Prototyping und Governance für Kanzleien, Bildung & Behörden – inklusive Accessibility, KPI-Budgets und personalisierter Journeys." |
| **Canonical URL** | https://www.wolf-agents.com/leistungen/redesign |
| **Noindex** | Nein |
| **Geschätzte Zeichenanzahl** | ~9.200 Zeichen (ohne Code/HTML) |
| **Geschätzte Wortanzahl** | ~1.150 Wörter |
| **Geschätzte Lesedauer** | 5-6 Minuten |
| **Anzahl Sections** | 4 (Hero, Light TL;DR+ContentBoxDark, Navy Segments, Light Deliverables+Ablauf+Governance) |
| **Anzahl H1** | 1 |
| **Anzahl H2** | 5 |
| **Anzahl H3** | 4 (1 TL;DR ContentBoxDark + 3 Segment-Cards) |

---

## 🏗️ HERO-BEREICH

**Badge:** "Design Sprint in 4 Wochen"
**H1 (Title):** "Redesign & UX Sprints"
**Subtitle:** "Wir gestalten Websites & Service-Interfaces, die Mandate, Einschreibungen und Bürgerdienste auf den Punkt bringen – mit Accessibility, KPI-Fokus und Governance."

**Primary CTA:** "Design Sprint starten" → `/kontakt`
**Secondary CTA:** "Stufen vergleichen" → `/leistungen#module`

---

## 📊 TL;DR + CONTENTBOXDARK (Hybrid-Layout)

**BESONDERHEIT:** Diese Seite hat ein **einzigartiges Layout** – TL;DR-Box NEBEN ContentBoxDark (nicht darunter)!

### Layout-Struktur

**Grid:** `grid gap-10 lg:grid-cols-[1.35fr,1fr] items-stretch`
- Links: TL;DR-Article (1.35fr)
- Rechts: ContentBoxDark "Sprint Canvas" (1fr)

**Vergleich zu anderen Leistungen:**
- **Standard:** TL;DR-Box (1.35fr) + Stats-Cards (0.65fr)
- **Diese Seite:** TL;DR-Box (1.35fr) + ContentBoxDark (1fr) – ContentBoxDark **ersetzt** Stats-Cards!

### TL;DR-Box (Links)

**Badge:** "TL;DR"
**H2:** "Design, Content, Experience – messbar"

**Intro:**
"Wir liefern Redesign Sprints mit UX Research, Content, Komponenten, Accessibility und KPI-gesteuerten Journeys. Kanzleien fokussieren Mandatsaufnahme, Bildungseinrichtungen erleichtern Einschreibungen, Behörden liefern verständliche Bürgerdienste."

**3 Checkmark Items:**
1. "UX Research & Journey Mapping, Stakeholder Interviews, Taskflows, KPI Definition, Hypothesen."
2. "UI Design System (Tailwind Tokens), Komponenten, Layouts, Copy Kits, Accessibility, Motion Guidelines."
3. "Prototyping & Testing: Figma, Interactive Demos, Usability Tests, KPI Validation, Handover & Playbooks."

### ContentBoxDark "Sprint Canvas" (Rechts)

**EINZIGARTIG:** ContentBoxDark als **Ersatz für Stats-Cards** – keine andere Leistung macht das!

**Styling:**
- Background: Brand-Primary-900 (#04060D)
- Flex-Layout: `flex flex-col gap-8 md:gap-10`
- Full-Height: `h-full` (dehnt sich auf TL;DR-Box-Höhe)

**Content:**

#### Badge + H3 + Intro
- **Badge:** "Sprint Canvas" (chip-dark)
- **H3:** "Operations-ready in vier Wochen"
- **Intro:** "Kickoff, Research, Journeys, UI Kits und Testing laufen in einem klar getakteten Sprint. Wir liefern fertige Komponenten, Copy und KPI-Checks."

#### 2 Stats-Boxes nebeneinander

**Layout:** `flex flex-col gap-4 xl:flex-row xl:gap-6` (Stack @ Mobile, Side-by-Side @ XL)

**Box 1: Sprintdauer**
- **Label:** "Sprintdauer" (uppercase, tracking-[0.24em])
- **Value:** "4 Wochen" (2xl → 3xl @ XL)
- **Context:** "Kickoff, Research, Journeys, UI Design, Content, Testing."

**Box 2: KPI Outcome**
- **Label:** "KPI Outcome"
- **Value:** "+25 %" (2xl → 3xl @ XL)
- **Context:** "Mandats Leads, Einschreibungen, Completion Rate & Zufriedenheit ≥ 4/5."

#### Badges unten

**Layout:** `flex flex-wrap gap-3 pt-2 border-t border-on-dark-subtle`

**Badges (chip-dark):**
- "Mandate · Enrollment · Bürgerdienste"
- "Governance & Accessibility"

**Zeigt:** Sprint deckt alle 3 Segmente + Compliance ab.

---

## 🌊 UX-SZENARIEN NACH SEGMENT (Section Navy)

**EINZIGARTIG:** Diese Seite nutzt **Section Navy** (tone="navy" glow="top") für Segment-Szenarien – keine andere Leistung macht das!

**Styling:**
- Background: Brand-Primary-900 (#04060D) mit Top-Glow
- Text-Farben: text-white (H2), text-slate-200/80 (Intro)

**Badge:** "Segment Fit" (chip-dark)
**H2:** "UX-Szenarien nach Segment"

**Intro:**
"Die Sprints adaptieren mandantenkritische Journeys je Branche – Intake-Flows, Enrollment, Bürgerdienste. Die Cases zeigen, wie wir KPIs und Governance pro Segment zuschneiden."

---

## 👥 SEGMENT USE CASES

**EINZIGARTIG:** Diese Seite nutzt **ContentBoxLight-Component** für segmentCases (mit **Badge-Prop**) – keine andere Leistung macht das!

### segmentCases-Array (3 Cards)

**Component:** `<ContentBoxLight badge="..." heading="..." class="h-full space-y-4 px-6 py-6 shadow-[0_30px_80px_-60px_rgba(15,23,42,0.55)]" />`

**Grid:** `grid gap-6 md:grid-cols-3`

**Card 1: Kanzleien & Sozietäten**
- **Badge (Prop):** "Mandats Intake & Pitch"
- **H3 (Prop: heading):** "Kanzleien & Sozietäten"
- **KPI (als Text, nicht Badge):** "Lead-to-Call Rate +35 % · Response < 1 h"
- **Description:** "Intake Flow, Mandat-Status, Case Vault, KPI-Cockpit und Vertrauensmodule – abgestimmt auf Partner-Boards."
- **Link:** "Kanzlei-UX ansehen" → `/branchen/kanzleien`

**Card 2: Schulen & Bildung**
- **Badge (Prop):** "Einschreibungs & Campus UX"
- **H3 (Prop: heading):** "Schulen & Bildung"
- **KPI:** "Anmeldung in 3 Steps · Zufriedenheit ≥ 4/5"
- **Description:** "StepFlow, Mobile-first Navigation, Kursfilter, Accessibility und KPI Monitoring für Enrollment Journeys."
- **Link:** "Enrollment-Guides öffnen" → `/branchen/schulen-bildung`

**Card 3: Behörden & öffentliche Dienste**
- **Badge (Prop):** "Top-Task & Servicecockpit UX"
- **H3 (Prop: heading):** "Behörden & öffentliche Dienste"
- **KPI:** "Completion Rate ≥ 70 % · BFSG Ready"
- **Description:** "Bürgerdienst Journeys, Plain Language, Formular UX, KPI Cockpits (Completion, Zufriedenheit, Digital Take-up) und Governance."
- **Link:** "Behörden-Top Tasks prüfen" → `/branchen/oeffentliche-einrichtungen`

**Unterschied zu anderen Leistungen:**
- **Standard:** Segment-Cards als Article-Tags mit hardcoded Badge-Spans
- **Diese Seite:** ContentBoxLight-Component mit **Badge als Prop** (wiederverwendbar!)

---

## 📋 DELIVERABLES, ABLAUF & GOVERNANCE (3 Separate Boxes)

**EINZIGARTIG:** Diese Seite nutzt **3 separate ContentBoxes** (statt 2-Spalten-Grid) – **Deliverables (Dark)** + **Sprint Ablauf (Light)** + **Governance & Übergabe (Light)**!

**Layout:** `grid gap-8 xl:grid-cols-[1.1fr,0.9fr] items-start`
- Links: ContentBoxDark "Deliverables" (1.1fr)
- Rechts: 2× ContentBoxLight gestackt (Sprint Ablauf + Governance)

### Deliverables (ContentBoxDark)

**Heading (Prop):** "Deliverables"
**headingLevel (Prop):** "h2"
**Class:** "space-y-6"

**4 Items mit Icon-Checkmarks:**

**Icon-Styling:** `inline-flex h-8 w-8 items-center justify-center rounded-xl surface-light-alpha-08 text-white/80`

1. "Research-Report, Personas, Service Blueprints, KPI Hypothesen, Journey Maps."
2. "UI Kits (Tailwind Tokens, Komponenten, Layouts, Modulbibliothek), Content Patterns, Accessibility Guidelines."
3. "Interaktive Prototypen (Figma), Testplan, Feedback-Board, KPI Validation."
4. "Handover Playbook, Journey-basierte KPIs, Roadmap, Agile Setup, Monitoring."

**Unique:** Icons sind **8×8 mit rounded-xl** (andere Leistungen: 5×5 ohne Background).

### Sprint Ablauf (ContentBoxLight)

**Heading (Prop):** "Sprint Ablauf"
**Class:** "space-y-4 px-6 py-6 shadow-[0_30px_80px_-60px_rgba(15,23,42,0.3)]"

**4 Wochen mit Checkmarks:**

1. "Woche 1: Research, KPI, Personas, Journeys, Content Audit."
2. "Woche 2: UX Konzepte, Wireframes, Copy, Accessibility."
3. "Woche 3: UI Design, Prototyping, KPI Hypothesen, QA, Feedback Schleifen."
4. "Woche 4: Testing, Iteration, Handover, Roadmap, Implementation Briefings."

**Checkmark-Icon:** 5×5, text-on-light-muted (weniger prominent als Deliverables).

### Governance & Übergabe (ContentBoxLight)

**Heading (Prop):** "Governance & Übergabe"
**Class:** "space-y-4 px-6 py-6 shadow-[0_30px_80px_-60px_rgba(15,23,42,0.3)]"

**3 Items mit Checkmarks:**

1. "Governance Kits, Accessibility Checklisten, Content Styleguides & Tone of Voice."
2. "Team Workshops, Recorded Walkthroughs, priorisiertes Backlog & Implementation Briefings."
3. "Monitoring Templates (Looker Studio, Matomo, Plausible) & KPI Alerts für Launch und Betrieb."

**Unique:** Einzige Leistung mit **3 Deliverable-Sections** (Deliverables + Ablauf + Governance).

---

## 🎯 FINAL CTA

**ContentBoxDark**

**Heading (Prop):** "Design Sprint starten?"
**headingLevel (Prop):** "h2"
**Class:** "max-w-4xl mx-auto text-center px-8 py-12 space-y-6"

**Description:**
"Wir gestalten KPI-orientierte Experiences für regulierte Organisationen – vom ersten Entwurf bis zum Handover. Lassen Sie uns Ihren Sprint planen."

**CTAs:**
- **Primary:** "Sprint anfragen" → `/kontakt`
- **Secondary:** "Weitere Pakete ansehen" → `/leistungen`

---

## 🔍 BESONDERHEITEN

### 1. ContentBoxDark in TL;DR Section (neben TL;DR-Box)

**EINZIGARTIG:** Keine andere Leistung platziert ContentBoxDark **neben** TL;DR-Box (normalerweise: TL;DR-Box + Stats-Cards).

**Layout:** TL;DR (1.35fr) + ContentBoxDark (1fr) – Side-by-Side @ Desktop.

**Grund:** UX-Sprints = Premium-Service → ContentBoxDark betont "Operations-ready in vier Wochen".

**Vergleich:**
- **barrierefreiheit.md + analytics-consent.md:** ContentBoxDark **unter** TL;DR-Box (für Segment-Szenarien)
- **Diese Seite:** ContentBoxDark **neben** TL;DR-Box (ersetzt Stats-Cards)

### 2. Section Navy für Segment-Szenarien

**EINZIGARTIG:** Keine andere Leistung nutzt `<Section tone="navy" glow="top">` für Segment-Szenarien.

**Andere Leistungen:**
- **Standard:** Section Light mit ContentBoxDark für Segment-Szenarien
- **Diese Seite:** Section Navy (dunkler Hintergrund mit Top-Glow)

**Visueller Effekt:** Segment-Cases heben sich stärker ab (Design-Fokus).

### 3. ContentBoxLight mit Badge-Prop

**EINZIGARTIG:** Keine andere Leistung nutzt `<ContentBoxLight badge="..." heading="..." />` für segmentCases.

**Andere Leistungen:**
- **Standard:** Hardcoded Article-Tags mit `<span class="chip-light">Badge</span>` + `<h3>Heading</h3>`
- **Diese Seite:** ContentBoxLight-Component mit **Badge als Prop** (cleaner, wiederverwendbar)

**Vorteile:**
- Konsistente Styling (Component-Level)
- Weniger Code-Duplikation
- Einfachere Wartung

**Zeigt:** Wolf-Agents migriert zu Component-basierten Patterns (statt Hardcoding).

### 4. 3 Separate ContentBoxes (Deliverables + Ablauf + Governance)

**EINZIGARTIG:** Keine andere Leistung hat **3 Deliverable-Sections** (normalerweise: 2-Spalten-Grid mit "Deliverables" + "Projektablauf").

**Layout:**
- Links: ContentBoxDark "Deliverables" (1.1fr)
- Rechts: 2× ContentBoxLight gestackt (Sprint Ablauf 0.9fr + Governance 0.9fr)

**Grund:** UX-Sprints sind **umfangreicher** (Research + Design + Testing + Governance) → 3 Sections nötig.

**Andere Leistungen:** 2 Sections (Deliverables + Projektablauf).

### 5. Tailwind Tokens erwähnt

**TL;DR Checkmark 2:** "UI Design System (Tailwind Tokens), Komponenten, Layouts, Copy Kits, Accessibility, Motion Guidelines."

**Tailwind Tokens:** CSS-Variablen für Design-System (Farben, Spacing, Typography) – Wolf-Agents nutzt Tailwind CSS.

**Deliverable 2:** "UI Kits (Tailwind Tokens, Komponenten, Layouts, Modulbibliothek), Content Patterns, Accessibility Guidelines."

**Zeigt:** Wolf-Agents liefert **Code-ready Design-Systems** (nicht nur Figma-Mockups).

### 6. Figma Prototyping genannt

**TL;DR Checkmark 3:** "Prototyping & Testing: Figma, Interactive Demos, Usability Tests, KPI Validation, Handover & Playbooks."

**Deliverable 3:** "Interaktive Prototypen (Figma), Testplan, Feedback-Board, KPI Validation."

**Figma:** Industry-Standard für UX-Design & Prototyping – Wolf-Agents nutzt moderne Tools.

**Andere Leistungen:** Keine Tool-Namen für Design (nur Tracking/Analytics-Tools).

### 7. Service Blueprints erwähnt

**Deliverable 1:** "Research-Report, Personas, Service Blueprints, KPI Hypothesen, Journey Maps."

**Service Blueprints:** UX-Methode für Service-Design (Frontend + Backend Journeys) – fortgeschrittenes UX-Toolset.

**Zeigt:** Wolf-Agents macht **echte UX Research** (nicht nur visuelle Redesigns).

### 8. Motion Guidelines erwähnt

**TL;DR Checkmark 2:** "UI Design System (Tailwind Tokens), Komponenten, Layouts, Copy Kits, Accessibility, Motion Guidelines."

**Motion Guidelines:** Animation/Transition-Regeln für UI (z.B. "Buttons: hover:scale-105, Modals: fade-in 300ms").

**Zeigt:** Wolf-Agents liefert **umfassende Design-Systems** (inkl. Micro-Interactions).

### 9. Plain Language erwähnt (Behörden)

**Segment-Case 3:** "Bürgerdienst Journeys, Plain Language, Formular UX, KPI Cockpits..."

**Plain Language:** Verständliche Behördensprache (USA: Plain Writing Act 2010, EU: Better Regulation).

**Zeigt:** Wolf-Agents versteht **Behörden-Compliance** (nicht nur Design).

### 10. Recorded Walkthroughs

**Governance & Übergabe 2:** "Team Workshops, Recorded Walkthroughs, priorisiertes Backlog & Implementation Briefings."

**Recorded Walkthroughs:** Loom/Screen-Recording für async Wissenstransfer – modern, remote-freundlich.

**Andere Leistungen:** Keine Erwähnung von Recorded Content (nur "Trainings").

### 11. Keine InfoTooltips

**Anzahl:** 0

**Auffällig:** Trotz UX-Fachbegriffen (Service Blueprints, Tailwind Tokens, Motion Guidelines) keine Glossar-Tooltips.

**Vergleich:** Alle Leistungen nutzen InfoTooltips sehr selten (0-1 pro Seite).

---

## 📊 CONTENT-AUDIT

### ✅ Stärken

- ✅ **4-Wochen-Sprint:** Klare Zeitbox (vs. unklare Projekt-Dauer bei Wettbewerbern)
- ✅ **Tailwind Tokens:** Code-ready Design-Systems (nicht nur Figma-Mockups)
- ✅ **Figma Prototyping:** Industry-Standard-Tool genannt
- ✅ **Service Blueprints:** Fortgeschrittene UX-Methode (Backend + Frontend Journeys)
- ✅ **Motion Guidelines:** Umfassende Design-Systems (inkl. Animations-Regeln)
- ✅ **Plain Language:** Behörden-Compliance verstanden
- ✅ **Recorded Walkthroughs:** Moderne Wissenstransfer-Methode
- ✅ **ContentBoxLight mit Badge-Prop:** Component-basiertes Pattern (cleaner als Hardcoding)
- ✅ **3 Deliverable-Sections:** Umfassendere Dokumentation (Deliverables + Ablauf + Governance)
- ✅ **+25% KPI Outcome:** Konkreter Performance-Lift genannt

### ⚠️ Schwächen

- ⚠️ **Service Blueprints nicht erklärt:** Laien wissen nicht, was das ist (Glossar-Link fehlt)
- ⚠️ **Tailwind Tokens nicht erklärt:** Technischer Begriff ohne Kontext
- ⚠️ **Motion Guidelines-Beispiele fehlen:** Kein "z.B. hover:scale-105" (zu abstrakt)
- ⚠️ **Figma ohne Alternative:** Kein Hinweis auf andere Tools (Sketch, Adobe XD) – zu tool-spezifisch?
- ⚠️ **KPI Validation unklar:** Wie werden KPIs validiert? (A/B-Tests? Usability-Metrics?)
- ⚠️ **Recorded Walkthroughs-Tool unklar:** Loom? Screen Studio? (Tool-Name fehlt)
- ⚠️ **Plain Language ohne Beispiel:** Kein Vorher/Nachher-Textbeispiel

### ❌ Fehlende Elemente

- ❌ **Schema.org-Markup:** Kein Service-Schema (wie alle Leistungen)
- ❌ **FAQ-Section:** Keine FAQs zu UX-Sprints, Figma, Tailwind (z.B. "Was ist ein Design Sprint?")
- ❌ **Before/After-Designs:** Keine Screenshots von Redesigns (vorher: altes Design, nachher: neues Design)
- ❌ **Figma-Prototype-Beispiel:** Kein Link zu Beispiel-Prototyp (anonym) oder Video-Demo
- ❌ **Tailwind Tokens-Visualisierung:** Keine Code-Snippets oder Token-Tabelle
- ❌ **Case Study:** Kein "Kanzlei X: Lead-to-Call Rate +35% nach Redesign"
- ❌ **Service Blueprint-Beispiel:** Kein Screenshot oder Erklär-Diagramm
- ❌ **Pricing-Hinweise:** Kein "Sprint ab 15.000 €" (Budget-Orientierung fehlt)
- ❌ **Timeline-Visualisierung:** Kein Gantt-Chart oder Sprint-Board für 4 Wochen
- ❌ **Stakeholder-Anzahl:** Kein "Interviews mit 5-10 Stakeholdern" (Scope-Klarheit fehlt)

### 🔴 PRIORITÄT

**Content-Refresh-Priorität:** 🟡 **MITTEL-NIEDRIG**

**Begründung:**
- **Nischenservice:** UX-Sprints = High-Budget-Service (15.000-30.000 €) → kleine Zielgruppe
- **Wettbewerb:** Viele Design-Agenturen, wenige mit Segment-Fokus (Kanzleien/Schulen/Behörden)
- **SEO-Potenzial:** "UX Sprints", "Redesign Agentur" = niedrige Search-Volume (vs. "Website erstellen")
- **Lead-Qualität:** HOCH (High-Budget-Projekte), aber niedrige Lead-Anzahl

**ABER:** ✅ **Best Practice-Implementierung** (ContentBoxLight mit Props, 3 Deliverable-Sections) → Referenz für andere Leistungen!

**Empfohlene Maßnahmen:**

1. **Before/After-Redesign-Screenshots** - Timeline: 2 Wochen
   - 3 Beispiele: Kanzlei (Intake-Form), Schule (Enrollment-Page), Behörde (Service-Page)
   - Anonymisiert, zeigt: Vorher (schlechte UX) vs. Nachher (Wolf-Agents Redesign)
   - Visueller Proof (wichtiger als Text bei Design-Services)

2. **FAQ-Section hinzufügen** - Timeline: 1 Woche
   - 8-10 FAQs: "Was ist ein Design Sprint?", "Figma vs. Adobe XD?", "Tailwind vs. Bootstrap?", "Was kostet ein Sprint?", "Wie viele Stakeholder-Interviews?"
   - FAQPage-Schema.org-Markup
   - Accordion-Format

3. **Figma-Prototype-Beispiel verlinken** - Timeline: 3 Tage
   - Anonymisiertes Figma-File (Public View-Only Link) oder Video-Walkthrough
   - Zeigt: Interaktive Prototypen, Component Library, Design Tokens
   - Reduziert Unsicherheit ("Was bekomme ich?")

4. **Service Blueprint-Visualisierung** - Timeline: 1 Woche
   - Beispiel-Blueprint: Kanzlei-Intake-Journey (Frontend: Formular → Nachricht → Rückruf, Backend: CRM-Sync → Partner-Notification → Termin-Buchung)
   - Infografik oder Screenshot
   - Erklärt: Was ist Service Design? (vs. nur UI-Design)

5. **Tailwind Tokens Code-Snippet** - Timeline: 2 Tage
   - Beispiel-CSS-Variablen: `--color-primary: #1E40AF; --spacing-lg: 2rem; --font-heading: Inter`
   - Zeigt: Code-ready Output (nicht nur Figma)
   - Positioniert Wolf-Agents als Developer-friendly

6. **Motion Guidelines-Beispiele** - Timeline: 2 Tage
   - Beispiel-Regeln: "Buttons: hover:scale-105 transition-transform 200ms", "Modals: opacity-0 → opacity-100 fade-in 300ms"
   - Zeigt: Detail-Level von Design-Systems
   - Reduziert Scope-Unklarheit

7. **Pricing-Hinweise hinzufügen** - Timeline: 1 Tag
   - Stats-Card oder Badge: "Sprint ab 15.000 €" oder "4-Wochen-Sprint: 15.000-30.000 €"
   - Budget-Orientierung (qualifiziert Leads vor)
   - Reduziert "Was kostet das?"-Anfragen

8. **Schema.org-Markup hinzufügen** - Timeline: 1 Woche
   - `Service`-Schema mit serviceType: "UX Design Sprint"
   - `Offer`-Schema mit Sprint-Dauer (4 Wochen), Pricing (15.000-30.000 €)
   - `Organization`-Schema mit Design-Certifications (falls vorhanden)

9. **Case Study hinzufügen** - Timeline: 2 Wochen
   - "Kanzlei X: Lead-to-Call Rate +35%, Response Time < 1 h nach Redesign"
   - Before/After-Screenshots + KPI-Charts
   - Social Proof (wichtiger bei High-Budget-Services)

10. **Timeline-Visualisierung** - Timeline: 1 Woche
    - Sprint-Board oder Gantt-Chart: Woche 1-4 mit Milestones (Kickoff, Research, Design, Testing, Handover)
    - Zeigt: Strukturierter Prozess (vs. "wir machen irgendwas")
    - Reduziert Unsicherheit

---

## 🎯 CONTENT-STRATEGIE

**Primäre Keywords:**
- UX Sprints
- Redesign Agentur
- UX Design
- Prototyping Figma
- Design System Tailwind
- Service Design
- Accessibility Design

**Sekundäre Keywords (LSI):**
- Journey Mapping
- User Research
- Personas
- Service Blueprints
- UI Kits
- Design Tokens
- Motion Guidelines
- Plain Language
- Content Styleguides
- Governance Kits

**Zielgruppe:**
- **Primär:** Marketing-Leiter, Geschäftsführer in regulierten Organisationen (Kanzleien, Schulen, Behörden) mit Redesign-Bedarf
- **Sekundär:** IT-Leiter (technische Integration von Design-Systems)
- **Tertiär:** Partner, Campus-Leitung, Verwaltungsdirektion (Budget-Entscheider)
- **Alter:** 35-60 Jahre
- **Kaufkraft:** HOCH (Sprint-Budget 15.000-30.000 €)

**User Intent:**
- **Primär:** Commercial Investigation (UX-Sprint-Anbieter evaluieren, Design-Refresh planen)
- **Sekundär:** Informational (Was ist ein Design Sprint? Figma vs. Adobe XD?)
- **Dringlichkeit:** NIEDRIG-MITTEL (Redesigns meist geplant, nicht dringend)

**AIO/GEO/AEO-Status:**
- **AIO:** "Was ist ein Design Sprint?" → FAQ würde beantworten
- **GEO:** ⚠️ Kein Schema.org-Markup → geringe GEO-Optimierung
- **AEO:** Niedrige Featured-Snippet-Potenzial (Design-Keywords wenig text-basiert, mehr visuell)
- **AI Overviews:** "UX Sprint Ablauf", "Figma Prototyping", "Design System Tailwind" = mittlere Search-Volumes

**Challenge:** Design-Services sind **visuell** (Before/After-Screenshots wichtiger als Text) → SEO-Potenzial begrenzt, Visuals fehlen!

---

## 📏 CONTENT-METRIKEN

**Textmenge:**
- Gesamtzeichen: ~9.200
- Gesamtwörter: ~1.150
- Lesedauer: 5-6 Minuten

**Link-Dichte:**
- Interne Links: ~9 (3 Branchen + Navigation + CTAs + Footer)
- Externe Links: 0 (⚠️ Keine Links zu Figma, Tailwind Docs, etc.!)
- CTAs: 3 (Hero Primary, Hero Secondary, Final CTA Primary + Secondary)

**Content-Verteilung:**
- Light Sections: ~45 % (TL;DR, Deliverables+Ablauf+Governance)
- Dark Sections: ~55 % (Hero, ContentBoxDark in TL;DR, Section Navy, Final CTA)

**Interaktive Elemente:**
- Buttons/Links: ~8 (2 Hero CTAs + 3 Segment-Links + 2 Final CTAs)
- InfoTooltips: 0
- Segment-Cards: 3 (ContentBoxLight-Components)

**Component-Usage:**
- ContentBoxDark: 2× (TL;DR + Final CTA)
- ContentBoxLight: 5× (3 Segment-Cards + Sprint Ablauf + Governance)
- Section Navy: 1× (einzigartig!)

---

## 📐 RESPONSIVE ANPASSUNGEN

**Hero:**
- Mobile: H1 36px, Subtitle 18px
- Desktop: H1 72px, Subtitle 20px

**TL;DR + ContentBoxDark:**
- Mobile: Stack (TL;DR-Box über ContentBoxDark)
- Desktop: Side-by-Side (1.35fr TL;DR, 1fr ContentBoxDark)

**ContentBoxDark "Sprint Canvas":**
- Mobile: 2 Stats-Boxes gestackt (flex-col)
- XL: 2 Stats-Boxes nebeneinander (flex-row)

**Section Navy Segment-Cards:**
- Mobile: 1-col Cards
- Desktop: 3-col Grid (md:grid-cols-3)

**Deliverables + Ablauf + Governance:**
- Mobile: Stack (Deliverables → Sprint Ablauf → Governance)
- XL: Side-by-Side (Deliverables 1.1fr links, Sprint Ablauf + Governance 0.9fr rechts gestackt)

---

**ENDE DER DOKUMENTATION - REDESIGN & UX SPRINTS**

**Umfang:** ~1.050 Wörter (Kompakt-Stil)
**Besonderheit:** ContentBoxDark neben TL;DR (einzigartig!), Section Navy, ContentBoxLight mit Badge-Prop, 3 Deliverable-Sections, Tailwind Tokens + Figma + Service Blueprints
**Priorität:** 🟡 MITTEL-NIEDRIG (Nischenservice, hohe Lead-Qualität, aber niedrige Volumes – ABER: Best Practice-Implementierung!)
**Status:** ✅ Vollständig dokumentiert
