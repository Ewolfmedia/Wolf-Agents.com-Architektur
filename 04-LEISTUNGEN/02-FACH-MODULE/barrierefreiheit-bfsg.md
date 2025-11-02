# BARRIEREFREIHEIT & BFSG

**Verweis:** Siehe `/04-LEISTUNGEN/00-LEISTUNGEN-TEMPLATE.md` für gemeinsame Struktur

**Dokumentiert am:** 2025-10-30
**Status:** IST-Zustand

---

## 📊 META-INFORMATIONEN

| Attribut | Wert |
|----------|------|
| **URL** | https://www.wolf-agents.com/leistungen/barrierefreiheit |
| **Datei** | `/src/pages/leistungen/barrierefreiheit.astro` |
| **Title Tag** | "BFSG, BITV & Accessibility Sprints \| Wolf-Agents" |
| **Meta Description** | "Barrierefreiheit für Kanzleien, Bildung & Behörden: Audits nach WCAG 2.2 AA, BFSG-Checks, Remediations, Design Tokens, Tooling & Monitoring." |
| **Canonical URL** | https://www.wolf-agents.com/leistungen/barrierefreiheit |
| **Noindex** | Nein |
| **Geschätzte Zeichenanzahl** | ~9.000 Zeichen (ohne Code/HTML) |
| **Geschätzte Wortanzahl** | ~1.250 Wörter |
| **Geschätzte Lesedauer** | 5-7 Minuten |
| **Anzahl Sections** | 3 (Hero, Light TL;DR+Segments+Deliverables, Footer) |
| **Anzahl H1** | 1 |
| **Anzahl H2** | 5 |
| **Anzahl H3** | 9 (3 Segment-Cards × 2 Sections) |

---

## 🏗️ HERO-BEREICH

**Badge:** "Audit in 10–15 Tagen"
**H1 (Title):** "Barrierefreiheit & BFSG Compliance"
**Subtitle:** "Wir prüfen, beheben und dokumentieren Barrierefreiheit für Kanzleien, Schulen und Behörden – WCAG 2.2 AA, BFSG 2025, BITV, inklusive Testing-Playbooks und Monitoring."

**Primary CTA:** "BFSG Audit sichern" → `/kontakt`
**Secondary CTA:** "Stufen vergleichen" → `/leistungen#module`

---

## 📊 TL;DR + STATS

### TL;DR-Box

**Badge:** "TL;DR"
**H2:** "Accessibility als Pflicht & Conversion-Hebel"

**Intro:**
"Wir kombinieren Accessibility-Audit, Remediation und Governance. Ziel: BFSG-Konformität, bessere Nutzerführung und Nachweise für Prüfstellen. Kanzleien reduzieren Rückfragen, Schulen verbessern mobile Nutzung, Behörden erfüllen BFSG/BITV und stärken Completion Rate."

**3 Checkmark Items:**
1. "WCAG 2.2 AA Manual & Automated Audits (axe, Pa11y, Screenreader, Keyboard, Color Contrast) mit Prioritäten & Aufwandsschätzung."
2. "Remediation-Kits: Design Tokens, Komponenten-Updates, Copy Guidelines, Barrierefreiheitserklärung & Feedback-Mechanismen."
3. "Governance & Monitoring: Regression Tests, Accessibility CI, Jour-fixe Reporting, Servicecockpit KPIs (Completion Rate, Zufriedenheit, Feedback)."

### Stats-Cards (3)

**Card 1: Audit Dauer**
- **Label:** "Audit Dauer"
- **Value:** "10–15 Tage"
- **Context:** "Analyse, Quick Fixes, Reporting, Roadmap, Workshop – auf Wunsch inkl. Schulung."

**Card 2: Tools**
- **Label:** "Tools"
- **Value:** "axe · Pa11y · Wave"
- **Context:** "Lighthouse, Screenreader (NVDA/VoiceOver), Keyboard, Colour Contrast Analyser, Chrome Recorder."

**Card 3: Nachweise**
- **Label:** "Nachweise"
- **Value:** "Audit Ready"
- **Context:** "BFSG/BITV Dokumentation, Barrierefreiheitserklärung, Monitoring-Plan, Feedback-Flow."

---

## 📦 SEGMENT-SZENARIEN & BFSG OUTCOMES (ContentBoxDark)

**BESONDERHEIT:** Diese Seite hat die **erste Segment-Section in ContentBoxDark** (dunkler Hintergrund) statt normalem Light-Background!

**ContentBoxDark-Wrapper:**
- Nested Box: `rounded-3xl border border-on-light-subtle/10 surface-light-alpha-05 p-8 md:p-10`
- Background: Leicht transparentes Weiß auf Dunkel (`surface-light-alpha-05`)
- Shadow: `0_25px_80px_-60px_rgba(0,0,0,0.3)`

**H2:** "Segment-Szenarien & BFSG Outcomes"

**Intro-Paragraph:**
"Barrierefreiheit steigert Nutzung und reduziert Beschwerden. Wir priorisieren Findings, Remediations und Monitoring je Segment – so bestehen Sie Audits und verbessern Conversion."

---

## 👥 SEGMENT USE CASES

### segmentCases-Array (3 Cards)

```javascript
const segmentCases = [
  {
    title: 'Kanzleien & Sozietäten',
    kpi: 'Lead-Form Completion +20 % · BFSG Ready',
    description: 'Mandantenportale, Intake-Formulare und CMS-Komponenten, die WCAG 2.2 AA erfüllen – inkl. Schulung & Dokumentation für Prüfstellen.',
    link: '/branchen/kanzleien',
    linkLabel: 'Kanzlei-Accessibility ansehen'
  },
  {
    title: 'Schulen & Bildung',
    kpi: 'Mobile UX ≥ 60 % · Einschreibung barrierefrei',
    description: 'Digitale Einschreibungen, Kursübersichten und Eltern-Informationen mit Accessibility Tokens, StepFlow und Feedback-Mechanismen.',
    link: '/branchen/schulen-bildung',
    linkLabel: 'Enrollment-Guides öffnen'
  },
  {
    title: 'Behörden & öffentliche Dienste',
    kpi: 'BFSG 2025 Konform · Completion Rate ≥ 70 %',
    description: 'Bürgerdienste mit BITV/BFSG Checks, Gebärden- & Leichte-Sprache-Optionen, Monitoring und Servicecockpit Reporting für Aufsichten.',
    link: '/branchen/oeffentliche-einrichtungen',
    linkLabel: 'Behörden-Top Tasks prüfen'
  }
];
```

### Segment-Cards (3) - ERSTE SECTION (in ContentBoxDark)

**Card-Styling (Dark):**
- Background: `bg-slate-800/40` (dunkel-transparent)
- Border: `border-slate-700/50`
- Text-Farben: text-white (H3), text-slate-200/90 (Description)
- Hover: hover:text-white (Link)

**Card 1: Kanzleien & Sozietäten**
- **KPI-Badge:** "Lead-Form Completion +20 % · BFSG Ready"
- **H3:** "Kanzleien & Sozietäten"
- **Description:** "Mandantenportale, Intake-Formulare und CMS-Komponenten, die WCAG 2.2 AA erfüllen – inkl. Schulung & Dokumentation für Prüfstellen."
- **Link:** "Kanzlei-Accessibility ansehen" → `/branchen/kanzleien`

**Card 2: Schulen & Bildung**
- **KPI-Badge:** "Mobile UX ≥ 60 % · Einschreibung barrierefrei"
- **H3:** "Schulen & Bildung"
- **Description:** "Digitale Einschreibungen, Kursübersichten und Eltern-Informationen mit Accessibility Tokens, StepFlow und Feedback-Mechanismen."
- **Link:** "Enrollment-Guides öffnen" → `/branchen/schulen-bildung`

**Card 3: Behörden & öffentliche Dienste**
- **KPI-Badge:** "BFSG 2025 Konform · Completion Rate ≥ 70 %"
- **H3:** "Behörden & öffentliche Dienste"
- **Description:** "Bürgerdienste mit BITV/BFSG Checks, Gebärden- & Leichte-Sprache-Optionen, Monitoring und Servicecockpit Reporting für Aufsichten."
- **Link:** "Behörden-Top Tasks prüfen" → `/branchen/oeffentliche-einrichtungen`

### Segment-Cards (3) - ZWEITE SECTION (Standard Light)

**H2:** "Segment Cases"

**Card-Styling (Light):**
- Background: `surface-light`
- Border: `border-on-light-subtle`
- Text-Farben: text-on-light-primary (H3), text-on-light-secondary (Description)

**Card 1: Kanzleien & Boutiquen**
- **Badge:** "Kanzleien & Boutiquen" (chip-light)
- **H3:** "Mandats Intake zugänglicher machen"
- **KPI:** "Lead-Form Completion +20 % · BFSG Ready" (als Text, nicht Badge)
- **Description:** "Formulare, Dokument-Upload, Terminbuchung, Content – barrierearm, mobil optimiert, DSGVO-konform."
- **Link:** "Kanzlei-Accessibility ansehen" → `/branchen/kanzleien`

**Card 2: Schulen & Bildung**
- **Badge:** "Schulen & Bildung" (chip-success)
- **H3:** "Digitale Einschreibung & Campus Infos"
- **KPI:** "Mobile UX ≥ 60 % · Zufriedenheit ≥ 4/5"
- **Description:** "WCAG-konforme Navigation, StepFlow, Medien, Videos, Dokumente, Mehrsprachigkeit, Simple Language."
- **Link:** "Enrollment-Guides öffnen" → `/branchen/schulen-bildung`

**Card 3: Behörden & öffentliche Dienste**
- **Badge:** "Behörden & öffentliche Dienste" (chip-brand)
- **H3:** "Bürgerdienste BFSG-ready"
- **KPI:** "Completion Rate ≥70 % · Audit Nachweis"
- **Description:** "Service-Seiten, Formulare, Medien, Feedbackkanäle, Barrierefreiheitserklärung, Monitoring Dashboard."
- **Link:** "Behörden-Top Tasks prüfen" → `/branchen/oeffentliche-einrichtungen`

**Unterschied:**
- **Section 1 (Dark):** Kürzere H3-Titel (nur Segment-Name), umfassendere Descriptions
- **Section 2 (Light):** Detaillierte H3-Titel (Use-Case), spezifischere Descriptions

---

## 📋 DELIVERABLES & ABLAUF

### Deliverables (4)

**H2:** "Deliverables"

1. "Accessibility Audit Report (Issues, Schweregrad, Impact, Aufwand), Prioritäten-Backlog, Quick Wins."
2. "Design Tokens & Komponenten-Updates (Fokus-Styling, Kontrast, Labels, Error Handling, ARIA, Responsivität)."
3. "Barrierefreiheitserklärung, Feedback-Prozess, Monitoring-Plan, KPI Framework (Completion Rate, Response Time, Zufriedenheit)."
4. "Schulungen für Redaktion, Dev, Support; Checklisten, QA Playbooks, Jour-fixe Agenda."

### Ablauf (4)

**H2:** "Ablauf"

1. "Phase 1: Kick-off, Scope, KPI, User Journeys, Tools, Content & Komponenten Audit."
2. "Phase 2: Audit & Quick Fixes – Tests, Code Reviews, Content Checks, Priorisierung."
3. "Phase 3: Umsetzung & QA, Regression Tests, Feedback, Dokumentation."
4. "Phase 4: Übergabe, Schulung, Monitoring Setup, optional kontinuierliche Betreuung."

---

## 🎯 FINAL CTA

**ContentBoxDark**

**Heading (H2):** "Barrierefreiheit priorisieren?"

**Description:**
"Wir sorgen für BFSG- und WCAG-konforme Auftritte, klare Nachweise und bessere Conversion – quer über Kanzlei-, Campus- und Bürgerdienste."

**CTAs:**
- **Primary:** "Audit & Umsetzung starten" → `/kontakt`
- **Secondary:** "Weitere Pakete ansehen" → `/leistungen`

---

## 🔍 BESONDERHEITEN

### 1. Erste Segment-Section in ContentBoxDark

**EINZIGARTIG:** Diese Seite ist die **einzige Leistung**, die die erste Segment-Section in **ContentBoxDark** (dunkler Hintergrund) statt normalem Light-Background platziert.

**Nested Box:**
- Outer: ContentBoxDark (Brand-Primary-900 #04060D)
- Inner: `surface-light-alpha-05` (leicht transparentes Weiß auf Dunkel)
- Border: `border-on-light-subtle/10` (10% Opacity)

**Grund:** Visueller Fokus auf Compliance-Thema (BFSG = gesetzliche Pflicht ab 2025).

### 2. Accessibility-Tools detailliert aufgelistet

**Stats-Card 2 nennt 7 Tools:**
- axe (Haupt-Tool im Value)
- Pa11y (Haupt-Tool im Value)
- Wave (Haupt-Tool im Value)
- Lighthouse (Context)
- Screenreader: NVDA (Windows), VoiceOver (macOS/iOS) (Context)
- Keyboard (Tastatur-Navigation) (Context)
- Colour Contrast Analyser (Context)
- Chrome Recorder (Context)

**Andere Leistungen:** Meist nur 1-3 Tools genannt.

**Zeigt:** Umfassender Tooling-Stack für WCAG 2.2 AA Audits.

### 3. BFSG 2025 & BITV Fokus

**Mehrfach erwähnt:**
- Hero-Badge: "Audit in 10–15 Tagen" (Deadline-Orientierung)
- Hero-Subtitle: "WCAG 2.2 AA, BFSG 2025, BITV"
- Stats-Card 3: "BFSG/BITV Dokumentation"
- Segment-Cases: "BFSG Ready", "BFSG 2025 Konform"

**BFSG-Kontext:**
- **BFSG:** Barrierefreiheitsstärkungsgesetz (Deutschland)
- **Deadline:** 28. Juni 2025 (für Unternehmen ab 10 Mitarbeiter)
- **BITV:** Barrierefreie-Informationstechnik-Verordnung (öffentliche Stellen)

**Zeitkritisch:** 2025-Deadline macht diese Seite sehr aktuell!

### 4. Gebärden- & Leichte-Sprache-Optionen

**Deliverable für Behörden (Segment-Case 3):**
"Gebärden- & Leichte-Sprache-Optionen, Monitoring und Servicecockpit Reporting für Aufsichten."

**Compliance-Level:**
- **Leichte Sprache:** Vereinfachte Texte (WCAG AAA)
- **Gebärdensprache:** Videos für Gehörlose (WCAG AAA)

**Nur Behörden erwähnt** (für Kanzleien/Schulen meist AA ausreichend, Behörden AAA-Pflicht).

### 5. Design Tokens für Accessibility

**Deliverable 2:**
"Design Tokens & Komponenten-Updates (Fokus-Styling, Kontrast, Labels, Error Handling, ARIA, Responsivität)."

**Design Tokens:**
- Fokus-Ringe (CSS-Variablen für :focus)
- Kontrast-Ratios (Text-on-Light, Text-on-Dark)
- Accessible Labels (ARIA-Labels, Visually Hidden Text)
- Error-States (Rot mit ausreichend Kontrast + Icons)

**Zeigt:** Wolf-Agents nutzt Design-System-Ansatz (nicht "Fix pro Seite").

### 6. Schulungen für 3 Rollen

**Deliverable 4:**
"Schulungen für Redaktion, Dev, Support; Checklisten, QA Playbooks, Jour-fixe Agenda."

**3 Zielgruppen:**
1. **Redaktion:** Accessible Content Writing (Alt-Texte, Link-Texte, Überschriften-Hierarchie)
2. **Dev:** Accessible Components (ARIA, Keyboard, Focus Management)
3. **Support:** Accessibility-Anfragen beantworten (Feedback-Mechanismus, Eskalation)

**Ganzheitlich:** Nicht nur technische Fixes, sondern organisatorische Verankerung.

### 7. Accessibility CI (Continuous Integration)

**Deliverable 3:**
"Governance & Monitoring: Regression Tests, Accessibility CI, Jour-fixe Reporting, Servicecockpit KPIs."

**Accessibility CI:**
- Automatisierte axe/Pa11y-Tests in CI/CD-Pipeline
- Verhindert neue Accessibility-Issues bei Deployments
- Pre-Commit Hooks oder GitHub Actions

**Unterschied zu einmaligem Audit:** Kontinuierliche Überwachung.

---

## 📊 CONTENT-AUDIT

### ✅ Stärken

- ✅ **BFSG 2025-Deadline:** Zeitkritisches Thema perfekt kommuniziert
- ✅ **Umfassender Tooling-Stack:** 7 Tools dokumentiert (axe, Pa11y, Wave, Lighthouse, Screenreader, Keyboard, CCA, Chrome Recorder)
- ✅ **Design Tokens-Ansatz:** Skalierbare Lösung (nicht "Fix pro Seite")
- ✅ **3-Rollen-Schulungen:** Redaktion + Dev + Support (ganzheitlich)
- ✅ **Accessibility CI:** Kontinuierliche Überwachung (nicht nur einmaliges Audit)
- ✅ **Gebärden- & Leichte Sprache:** AAA-Level für Behörden
- ✅ **ContentBoxDark für Segment-Szenarien:** Visueller Fokus auf Compliance
- ✅ **2× Segment-Sections:** Mehr Detail zu Branchen-Anpassungen (wie GEO)
- ✅ **Konkrete KPIs:** Lead-Form Completion +20 %, Mobile UX ≥ 60 %, Completion Rate ≥ 70 %
- ✅ **Barrierefreiheitserklärung erwähnt:** Gesetzliche Pflicht dokumentiert

### ⚠️ Schwächen

- ⚠️ **BFSG-Deadline nicht explizit:** "2025" erwähnt, aber kein "28. Juni 2025" (Dringlichkeit!)
- ⚠️ **Keine Before/After-Beispiele:** Kein Screenshot "WCAG-Fehler vs. WCAG-konforme Lösung"
- ⚠️ **Audit-Report-Format unklar:** Wie sieht der Report aus? Excel? PDF? Dashboard?
- ⚠️ **Quick Wins nicht definiert:** Was sind "Quick Wins"? (z.B. Alt-Texte, Kontrast-Fixes)
- ⚠️ **Segment-Szenarien & Segment Cases sehr ähnlich:** 2× fast gleiche Infos (Repetition)
- ⚠️ **NVDA/VoiceOver ohne Erklärung:** Laien wissen nicht, was das ist

### ❌ Fehlende Elemente

- ❌ **Schema.org-Markup:** Kein Service-Schema (wie alle Leistungen)
- ❌ **FAQ-Section:** Keine FAQs zu BFSG/WCAG (z.B. "Was ist der Unterschied WCAG AA vs. AAA?")
- ❌ **BFSG-Deadline-Countdown:** Kein "Noch 8 Monate bis BFSG-Deadline" (Dringlichkeit!)
- ❌ **Barrierefreiheitserklärung-Beispiel:** Kein Link zu Wolf-Agents' eigener Erklärung (Dogfooding!)
- ❌ **Accessibility-Statement für diese Seite:** ⚠️ **Ironie:** Seite verkauft Accessibility, hat aber keine Barrierefreiheitserklärung!
- ❌ **Vor/Nachher-KPIs:** Kein "Kunde X: Formulare +25 % Completion nach Remediation"
- ❌ **Checklisten-Vorschau:** Kein Link zu Beispiel-Checkliste (z.B. "Redaktions-Checkliste: 10 Punkte für accessible Content")
- ❌ **BITV-Link:** Keine Verlinkung zu BITV-Gesetz oder BFSG-Gesetz (Kontext für Laien)
- ❌ **Prüfstellen-Liste:** Keine Erwähnung von Prüfstellen (z.B. BITV-Test, BIK BITV-Test)

### 🔴 PRIORITÄT

**Content-Refresh-Priorität:** 🔴 **HOCH**

**Begründung:**
- **Zeitkritisch:** BFSG-Deadline 28. Juni 2025 (< 8 Monate!) → hohe Nachfrage erwartet
- **Gesetzliche Pflicht:** Alle Unternehmen ab 10 MA betroffen (breiter Markt)
- **Segment-Relevanz:** Behörden MÜSSEN (BITV), Kanzleien/Schulen SOLLTEN (BFSG)
- **SEO-Potenzial:** "BFSG 2025", "WCAG 2.2 AA", "Barrierefreiheit Audit" = High-Value-Keywords
- **Wettbewerbsvorteil:** Wenig spezialisierte Anbieter für regulierte Branchen

**ABER:** ⚠️ **Ironie-Problem:** Seite verkauft Accessibility, ist aber selbst nicht optimal accessible (kein Schema, keine FAQ, keine Barrierefreiheitserklärung verlinkt).

**Empfohlene Maßnahmen:**

1. **BFSG-Deadline-Countdown hinzufügen** - Timeline: 2 Tage
   - Badge oder Stats-Card: "Noch X Monate bis BFSG-Deadline (28. Juni 2025)"
   - Dringlichkeit visualisieren (ohne Panik zu machen)

2. **FAQ-Section hinzufügen** - Timeline: 1 Woche
   - 10-12 FAQs zu BFSG/WCAG (z.B. "Was ist BFSG 2025?", "AA vs. AAA?", "Was kostet ein Audit?", "Wie lange dauert Remediation?")
   - FAQPage-Schema.org-Markup
   - Accordion-Format

3. **Barrierefreiheitserklärung-Link** - Timeline: 1 Tag
   - Wolf-Agents' eigene Barrierefreiheitserklärung erstellen (falls nicht vorhanden)
   - Link in Stats-Card 3 oder Deliverables: "Beispiel-Erklärung ansehen"
   - **Dogfooding:** "Wir praktizieren, was wir predigen"

4. **Schema.org-Markup hinzufügen** - Timeline: 1 Woche
   - `Service`-Schema mit serviceType: "WCAG 2.2 AA Audit"
   - `Offer`-Schema mit Audit-Dauer (10-15 Tage), Pricing-Hints
   - `Organization`-Schema mit Accessibility-Certifications (falls vorhanden)

5. **Vor/Nachher-Beispiele** - Timeline: 2 Wochen
   - Screenshot-Paar: WCAG-Fehler (schlechter Kontrast) vs. WCAG-konform (guter Kontrast)
   - Case Study: "Kanzlei X: Lead-Form Completion +25 % nach WCAG-Remediation"
   - **Visueller Proof** (statt nur Text)

6. **Quick Wins definieren** - Timeline: 3 Tage
   - In TL;DR oder Deliverables: "Quick Wins z.B. Alt-Texte, Kontrast-Fixes, Link-Texte, Überschriften-Hierarchie"
   - Macht Audit-Output greifbarer

7. **BITV/BFSG-Links hinzufügen** - Timeline: 1 Tag
   - Externe Links zu BFSG-Gesetz (bundesrecht.juris.de) und BITV
   - Oder: Wolf-Agents Blog-Artikel "BFSG 2025: Was Unternehmen wissen müssen"
   - Kontextualisierung für Laien

8. **Audit-Report-Visualisierung** - Timeline: 1 Woche
   - Screenshot eines Beispiel-Audit-Reports (anonymisiert)
   - Zeigt: Struktur (Issues, Schweregrad, Impact, Aufwand), Format (Dashboard oder PDF)
   - Reduziert Unsicherheit ("Was bekomme ich?")

9. **Segment-Sections konsolidieren** - Timeline: 3 Tage
   - Option 1: Nur 1× Segment-Section behalten (detaillierter)
   - Option 2: Section 1 = Compliance-Fokus (BFSG Ready), Section 2 = UX-Fokus (Completion Rate)
   - Reduziert Repetition

10. **Accessibility-Statement auf Seite selbst** - Timeline: 1 Woche
    - Footer-Link: "Barrierefreiheitserklärung Wolf-Agents"
    - WCAG 2.2 AA Konformität dokumentieren
    - **Eliminiert Ironie-Problem!**

---

## 🎯 CONTENT-STRATEGIE

**Primäre Keywords:**
- BFSG 2025 (Barrierefreiheitsstärkungsgesetz)
- WCAG 2.2 AA (Web Content Accessibility Guidelines)
- BITV (Barrierefreie-Informationstechnik-Verordnung)
- Accessibility Audit
- Barrierefreiheit Websites
- Barrierefreiheitserklärung

**Sekundäre Keywords (LSI):**
- axe DevTools
- Pa11y
- Screenreader-Tests
- Kontrast-Ratio
- ARIA-Labels
- Keyboard-Navigation
- Design Tokens Accessibility
- Leichte Sprache
- Gebärdensprache Videos
- Accessibility CI/CD

**Zielgruppe:**
- **Primär:** Compliance-Verantwortliche, IT-Leiter, Geschäftsführer in Unternehmen ab 10 MA (BFSG-Pflicht ab 2025)
- **Sekundär:** Marketing-Leiter, UX-Designer (Accessibility als UX-Verbesserung)
- **Tertiär:** Öffentliche Stellen (Behörden, Schulen) mit BITV-Pflicht
- **Alter:** 30-60 Jahre
- **Kaufkraft:** Mittel-Hoch (Audit-Budget 5.000-15.000 €)

**User Intent:**
- **Primär:** Commercial Investigation (Audit-Service evaluieren, BFSG-Deadline einhalten)
- **Sekundär:** Informational (Was ist BFSG? WCAG AA vs. AAA?)
- **Dringlichkeit:** HOCH (Deadline 28. Juni 2025)

**AIO/GEO/AEO-Status:**
- **AIO:** "Was ist BFSG 2025?" → FAQ würde beantworten
- **GEO:** ⚠️ Kein Schema.org-Markup → geringe GEO-Optimierung
- **AEO:** Hohe Featured-Snippet-Potenzial mit FAQ (wenn hinzugefügt)
- **AI Overviews:** "BFSG 2025 Anforderungen", "WCAG 2.2 AA Checkliste" = häufige Queries

**Paradox (wie GEO):** Seite verkauft Accessibility, ist aber selbst nicht optimal accessible (keine Barrierefreiheitserklärung, kein Schema). **Dringender Handlungsbedarf!**

---

## 📏 CONTENT-METRIKEN

**Textmenge:**
- Gesamtzeichen: ~9.000
- Gesamtwörter: ~1.250
- Lesedauer: 5-7 Minuten

**Link-Dichte:**
- Interne Links: ~12 (3 Branchen × 2 Sections + Navigation + CTAs + Footer)
- Externe Links: 0 (⚠️ Keine Links zu BFSG/BITV-Gesetz!)
- CTAs: 3 (Hero Primary, Hero Secondary, Final CTA Primary + Secondary)

**Content-Verteilung:**
- Light Sections: ~70 % (TL;DR + Stats, Segment Cases Section 2, Deliverables + Ablauf)
- Dark Sections: ~30 % (Hero, ContentBoxDark mit Segment-Szenarien, Final CTA)

**Interaktive Elemente:**
- Buttons/Links: ~8 (2 Hero CTAs + 3 Branchen-Links × 2 + 2 Final CTAs)
- InfoTooltips: 0 (keine!)
- Segment-Cards: 6 (3 × 2 Sections)

**Segment-Card-Dichte:** **HÖCHSTE** (6 Cards, wie GEO)

---

## 📐 RESPONSIVE ANPASSUNGEN

**Hero:**
- Mobile: H1 36px, Subtitle 18px
- Desktop: H1 72px, Subtitle 20px

**TL;DR + Stats:**
- Mobile: Stack (TL;DR-Box über Stats-Cards, 1-col Stats)
- Desktop: Side-by-Side (1.35fr TL;DR, 0.65fr Stats-Grid)

**ContentBoxDark-Segment-Szenarien:**
- Mobile: 1-col Cards
- Desktop: 3-col Grid (md:grid-cols-3)

**Segment Cases (Section 2):**
- Mobile: 1-col Cards
- Desktop: 3-col Grid (md:grid-cols-3)

**Deliverables + Ablauf:**
- Mobile: Stack (Deliverables über Ablauf)
- Desktop: Side-by-Side (lg:grid-cols-2)

---

**ENDE DER DOKUMENTATION - BARRIEREFREIHEIT & BFSG**

**Umfang:** ~1.150 Wörter (Kompakt-Stil)
**Besonderheit:** Erste Segment-Section in ContentBoxDark (einzigartig), BFSG 2025-Deadline-Fokus, 7 Accessibility-Tools
**Priorität:** 🔴 HOCH (BFSG-Deadline < 8 Monate, gesetzliche Pflicht, aber Seite selbst nicht optimal accessible!)
**Status:** ✅ Vollständig dokumentiert
