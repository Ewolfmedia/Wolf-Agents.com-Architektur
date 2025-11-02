# ANALYTICS & CONSENT

**Verweis:** Siehe `/04-LEISTUNGEN/00-LEISTUNGEN-TEMPLATE.md` für gemeinsame Struktur

**Dokumentiert am:** 2025-10-31
**Status:** IST-Zustand

---

## 📊 META-INFORMATIONEN

| Attribut | Wert |
|----------|------|
| **URL** | https://www.wolf-agents.com/leistungen/analytics-consent |
| **Datei** | `/src/pages/leistungen/analytics-consent.astro` |
| **Title Tag** | "Analytics, Consent & Servicecockpit KPIs \| Wolf-Agents" |
| **Meta Description** | "GA4, Matomo, Consent Mode v2, Server-Side-Tracking und Servicecockpit-Dashboards – zugeschnitten auf Kanzleien, Bildung und öffentliche Dienste mit klaren KPI-Budgets." |
| **Canonical URL** | https://www.wolf-agents.com/leistungen/analytics-consent |
| **Noindex** | Nein |
| **Geschätzte Zeichenanzahl** | ~10.500 Zeichen (ohne Code/HTML) |
| **Geschätzte Wortanzahl** | ~1.350 Wörter |
| **Geschätzte Lesedauer** | 6-8 Minuten |
| **Anzahl Sections** | 4 (Hero, Light TL;DR+Stats+Segments, Einsatzfelder+Deliverables, Footer) |
| **Anzahl H1** | 1 |
| **Anzahl H2** | 6 |
| **Anzahl H3** | 6 (3 Segment-Cards + 3 Einsatzfeld-Cards) |

---

## 🏗️ HERO-BEREICH

**Badge:** "Kick-off in 5 Werktagen"
**H1 (Title):** "Analytics & Consent für regulierte Teams"
**Subtitle:** "Wir richten Tracking, Consent Mode v2, Server-Side-Events und KPI-Cockpits ein – damit Kanzleien, Schulen und Behörden Lead-to-Call, Completion Rate und Zufriedenheit transparent messen."

**Primary CTA:** "Audit & Setup buchen" → `/kontakt`
**Secondary CTA:** "Stufen vergleichen" → `/leistungen#module`

---

## 📊 TL;DR + STATS

### TL;DR-Box

**Badge:** "TL;DR"
**H2:** "Messbarkeit & Compliance aus einer Hand"

**Intro:**
"Wir konfigurieren Analytics-Stacks für regulierte Organisationen: Consent Mode v2, Matomo/GA4 Dual-Setup, Server-Side Events, KPI-Dashboards und Reporting-Playbooks. Kanzleien sehen Lead-to-Call Rate & Response Time, Bildungseinrichtungen verfolgen Einschreibungen und Completion Rate, Behörden monitoren digitale Serviceabschlüsse."

**3 Checkmark Items:**
1. "Consent Mode v2 + CMP-Integration (Usercentrics, Borlabs, Cookiebot), DSGVO-konforme Datenflüsse, Audit-Logs & Privacy Impact Assessment."
2. "Server-Side Tracking (GA4, Matomo, BigQuery) mit modellierten Conversions, Offline-Sync und Servicecockpit-Fokus auf Lead-to-Call & Completion Rate."
3. "KPI-Dashboards, Alerts & Reporting-Playbooks für Partner-Meetings, Campus-Leitung und Verwaltungsdirektion – inklusive Response-Promise SLA Tracking."

### Stats-Cards (3)

**Card 1: Setup-Fenster**
- **Label:** "Setup-Fenster"
- **Value:** "10–15 Tage"
- **Context:** "Audit, Consent-Konfiguration, Tracking-Plan, Implementierung & QA – inklusive Doku und Training."

**Card 2: Tools**
- **Label:** "Tools"
- **Value:** "GA4 · Matomo · BQ"
- **Context:** "Consent CMPs, Cloudflare Zaraz, Tag Manager, Server-Side Containers, Looker Studio/QuickSight."

**Card 3: Segment KPIs**
- **Label:** "Segment KPIs"
- **Value:** "12+"
- **Context:** "Lead-to-Call Rate, Completion Rate, Satisfaction ≥ 4/5, Response Time < 1 h, Digital Take-up +40 pp."

---

## 📦 SEGMENT-KPIS & DASHBOARDS (ContentBoxDark)

**BESONDERHEIT:** Diese Seite platziert die **Segment-Szenarien in ContentBoxDark** (wie barrierefreiheit.md), nicht im Standard-Light-Background.

**ContentBoxDark-Wrapper:**
- Nested Box: `rounded-3xl border border-on-light-subtle/10 surface-light-alpha-05 p-8 md:p-10`
- Background: Leicht transparentes Weiß auf Dunkel (`surface-light-alpha-05`)
- Shadow: `0_25px_80px_-60px_rgba(0,0,0,0.3)`

**H2:** "Segment-KPIs & Dashboards"

**Intro-Paragraph:**
"Jedes Tracking-Setup richtet sich an konkrete Ziele: Intake-Quote, Enrollment-Conversion oder Completion Rate. Wir liefern vorkonfigurierte Dashboards, Alerts und Jour-fixe Reports für jedes Segment."

---

## 👥 SEGMENT USE CASES

### segmentCases-Array (3 Cards)

**Card-Styling (Dark):**
- Background: `bg-slate-800/40` (dunkel-transparent)
- Border: `border-slate-700/50`
- Text-Farben: text-white (H3), text-slate-200/90 (Description)
- Hover: hover:-translate-y-1 hover:shadow-md transition

**Card 1: Kanzleien & Sozietäten**
- **KPI-Badge:** "Lead-to-Call Tracking · Response < 1 h"
- **H3:** "Kanzleien & Sozietäten"
- **Description:** "Intake-Funnel Tracking, Telefon/Mail Attribution, Jour-fixe KPI-Reports und Consent-konforme CRM-Syncs für Partnerteams."
- **Link:** "Kanzlei-KPI Playbook ansehen" → `/branchen/kanzleien`

**Card 2: Schulen & Bildung**
- **KPI-Badge:** "Anmeldungen in 3 Steps · Mobile > 60 %"
- **H3:** "Schulen & Bildung"
- **Description:** "StepFlow-Events, RUM-Dashboards & Enrollment KPIs (Conversion, Abbrüche, Mobile Share) – inkl. DSGVO-konformer Elternkommunikation."
- **Link:** "Enrollment-Guides öffnen" → `/branchen/schulen-bildung`

**Card 3: Behörden & öffentliche Dienste**
- **KPI-Badge:** "Completion Rate ≥ 70 % · Zufriedenheit ≥ 4/5"
- **H3:** "Behörden & öffentliche Dienste"
- **Description:** "Servicecockpit-KPIs, Digital Take-up & OZG-Tracking, Consent Mode v2, Audit-Logs und GA4/Matomo Dual-Setup für BFSG/DSGVO."
- **Link:** "Behörden-Top Tasks prüfen" → `/branchen/oeffentliche-einrichtungen`

---

## 🏢 EINSATZFELDER (Zusätzliche Section)

**BESONDERHEIT:** Diese Seite hat eine **zusätzliche "Einsatzfelder" Section** mit 3 Cards – nicht im Standard-Template!

**H2:** "Einsatzfelder"

**Layout:** grid gap-6 md:grid-cols-3

### Card 1: Kanzleien & Boutiquen

**Badge:** "Kanzleien & Boutiquen" (chip-light)
**H3:** "Mandats-KPI Cockpit"
**Description:** "Server-Side GA4 + Matomo, Lead-Scoring, Anruf-Tracking, Intake-Funnel, Response-Time Alerts – Reporting für Partner-Meetings & Jour-fixe."

### Card 2: Schulen & Bildung

**Badge:** "Schulen & Bildung" (chip-success)
**H3:** "Einschreibungs-Dashboard"
**Description:** "Conversion-Tracking für Aufnahmeflows, Mobile vs. Desktop, Kurs-Anmeldungen, Status-E-Mails, KPI-Sharing für Campus-Leitung & Förderer."

### Card 3: Behörden & öffentliche Dienste

**Badge:** "Behörden & öffentliche Dienste" (chip-brand)
**H3:** "Servicecockpit für Bürgerdienste"
**Description:** "Completion Rate, Digital Take-up, Zufriedenheit, Feedback-Widget, Barrierefreiheitsreporting – Berichte für Amtsleitung & politische Gremien."

**Unterschied zu Segment-Szenarien:** Diese Cards sind **use-case-spezifischer** (Cockpit-Namen) statt nur Segment-Namen.

---

## 📋 DELIVERABLES & PROZESS

**BESONDERHEIT:** Diese Seite benennt die beiden 2-Spalten-Sections **"Leistungsumfang" + "Prozess & Enablement"** (statt Standard "Deliverables" + "Projektablauf").

### Leistungsumfang (4)

**H2:** "Leistungsumfang"

1. "Consent-Audit, CMP-Konfiguration, Tagging-Konzept (Events, Conversions, Funnels) für Kanzlei-, Campus- und Bürgerdienst-Szenarien."
2. "Server-Side Container (GA4/Matomo) inkl. Debugging, Data-Layer, Offline-Sync, CRM/Servicecockpit Connectors."
3. "KPI-Framework (Lead-to-Call, Completion Rate, Zufriedenheit, Response Time) mit Dashboards in Looker Studio/QuickSight."
4. "Alerting & Governance: wöchentliche KPI-Reports, Jour-fixe Agenda, Data Dictionaries, Nachweisdokumentation für Compliance."

### Prozess & Enablement (4)

**H2:** "Prozess & Enablement"

1. "Kick-off mit KPI-Alignment, Dateninventar, Legal/IT-Check, CMP-Review – Ergebnis ist eine priorisierte Roadmap."
2. "Implementierung & QA: Consent-Tests, DebugView, Server-Side Validierung, Regression Tests, Documentation."
3. "Trainings & Playbooks: Analytics Reporting, KPI-Interpretation, Jour-fixe Agenda, Servicecockpit Updates, Data Governance."
4. "Optionaler Managed Service: monatliche QA, KPI-Review, A/B-Test-Roadmap, Consent-Audit, Incident Response innerhalb SLA."

**Unique:** Punkt 4 erwähnt **optionalen Managed Service** (kontinuierliche Betreuung) – nicht auf allen Leistungen-Seiten!

---

## 🔄 PROJEKTVERLAUF IN VIER PHASEN

**H2:** "Projektverlauf in vier Phasen"

**Layout:** gradient-Box mit grid gap-4 md:grid-cols-4

**Phase 1: Audit & KPI Alignment**
"Ist-Analyse, Dateninventar, KPI-Definition, CMP-Review, Roadmap."

**Phase 2: Consent & Tracking Build**
"Tagging-Konzept, Consent Mode, Server-Side Container, QA & Debugging."

**Phase 3: Dashboards & Alerts**
"Looker/QuickSight, KPI-Alerts, Jour-fixe Reports, Servicecockpit Feed."

**Phase 4: Enablement & Run**
"Trainings, Playbooks, Übergabe, optional Managed Service & SLA."

---

## 🎯 FINAL CTA

**ContentBoxDark**

**Heading (H2):** "Analytics & Consent auf Enterprise-Niveau?"

**Description:**
"Wir verbinden Tracking, Datenschutz und KPI-Transparenz. Sie erhalten nachvollziehbare Dashboards, konsistente Reports und Playbooks für Jour-fixe, Audits und Roadmaps."

**CTAs:**
- **Primary:** "Audit & Setup buchen" → `/kontakt`
- **Secondary:** "Weitere Pakete ansehen" → `/leistungen`

---

## 🔍 BESONDERHEITEN

### 1. ContentBoxDark für Segment-Szenarien

**Wie barrierefreiheit.md:** Erste Segment-Section in dunklem Hintergrund (nicht Standard-Light).

**Nested Box:** Transparentes Weiß (`surface-light-alpha-05`) auf Brand-Primary-900 (#04060D).

**Visueller Fokus:** KPI-Dashboards als Premium-Feature hervorheben.

### 2. Zusätzliche "Einsatzfelder" Section

**Einzigartig:** Keine andere Leistung hat eine zweite Segment-Cards-Section (neben Segment-Szenarien).

**Unterschied:**
- **Segment-Szenarien (Dark):** Tracking-Fokus (Lead-to-Call Tracking, StepFlow-Events, Servicecockpit-KPIs)
- **Einsatzfelder (Light):** Dashboard-Fokus (Mandats-KPI Cockpit, Einschreibungs-Dashboard, Servicecockpit)

**Grund:** Analytics-Leistung ist **umfangreicher** (12+ KPIs) → mehr Detail nötig.

### 3. Deliverables-Namen abweichend

**Standard-Template:** "Deliverables" + "Projektablauf"
**Diese Seite:** "Leistungsumfang" + "Prozess & Enablement"

**Grund:** "Enablement" betont **Wissenstransfer** (Trainings, Playbooks, Managed Service).

### 4. Managed Service erwähnt

**Einzigartig:** Punkt 4 in "Prozess & Enablement" + Phase 4 in Projektverlauf erwähnen **optionalen Managed Service**.

**Details:**
- Monatliche QA
- KPI-Review
- A/B-Test-Roadmap
- Consent-Audit
- Incident Response innerhalb SLA

**Andere Leistungen:** Keine Erwähnung von kontinuierlicher Betreuung nach Projektabschluss.

### 5. 12+ Segment-KPIs dokumentiert

**Stats-Card 3:** "12+" KPIs genannt.

**Auflistung im Context:**
- Lead-to-Call Rate
- Completion Rate
- Satisfaction ≥ 4/5
- Response Time < 1 h
- Digital Take-up +40 pp
- (weitere 7+ impliziert: Conversion, Abbrüche, Mobile Share, etc.)

**Andere Leistungen:** Meist 3-5 KPIs genannt.

### 6. Consent Mode v2 & CMPs detailliert

**3 CMPs namentlich genannt:**
1. Usercentrics
2. Borlabs Cookie
3. Cookiebot

**Consent Mode v2:** Google's neueste Consent-API (2023) – DSGVO-konform mit Modeling für nicht-eingewilligte User.

**Privacy Impact Assessment:** DSGVO-Pflicht für Datenverarbeitungen mit hohem Risiko.

### 7. Server-Side Tracking-Fokus

**TL;DR Checkmark 2:** "Server-Side Tracking (GA4, Matomo, BigQuery) mit modellierten Conversions, Offline-Sync und Servicecockpit-Fokus."

**Warum Server-Side?**
- Umgeht Ad-Blocker
- Bessere Datenqualität (kein Client-Side Sampling)
- DSGVO-konformer (Daten auf eigenen Servern)
- Offline-Sync mit CRMs/Servicecockpits

**Tools:** Cloudflare Zaraz (erwähnt in Stats-Card 2), Google Tag Manager Server-Side Container.

### 8. Keine InfoTooltips

**Anzahl:** 0

**Auffällig:** Trotz technischer Begriffe (Consent Mode v2, Server-Side Container, BigQuery) keine Glossar-Tooltips.

**Vergleich:** barrierefreiheit.md (0×), geo.md (1×), stufe-0.md (0×) – Leistungen nutzen InfoTooltips sehr selten.

---

## 📊 CONTENT-AUDIT

### ✅ Stärken

- ✅ **12+ Segment-KPIs dokumentiert:** Umfangreichste KPI-Suite aller Leistungen
- ✅ **Server-Side Tracking-Fokus:** Modernes, DSGVO-konformes Setup (nicht nur Client-Side)
- ✅ **Consent Mode v2:** Neueste Google-API (2023) genannt
- ✅ **3 CMPs namentlich:** Usercentrics, Borlabs, Cookiebot (Wahlfreiheit)
- ✅ **Managed Service erwähnt:** Kontinuierliche Betreuung nach Projektabschluss (einzigartig)
- ✅ **Offline-Sync & CRM-Connectors:** Integration mit bestehenden Systemen
- ✅ **2× Segment-Sections:** Mehr Detail zu Dashboards & Use-Cases (wie barrierefreiheit.md)
- ✅ **Privacy Impact Assessment:** DSGVO-Compliance dokumentiert
- ✅ **Jour-fixe Reports:** Recurring Reporting für Partner-Meetings
- ✅ **Response-Promise SLA Tracking:** KPI für Response Time < 1 h (Kanzleien)

### ⚠️ Schwächen

- ⚠️ **Consent Mode v2 nicht erklärt:** Laien wissen nicht, was das ist (Glossar-Link fehlt)
- ⚠️ **12+ KPIs nicht alle aufgelistet:** Nur 5 genannt, Rest impliziert
- ⚠️ **Managed Service-Preise unklar:** Kein Hinweis auf Kosten (SLA-Stufen?)
- ⚠️ **"Einsatzfelder" vs. "Segment-Szenarien" repetitiv:** ~70% Überlappung, könnte konsolidiert werden
- ⚠️ **BigQuery ohne Kontext:** Warum BigQuery? (Data Warehouse für Advanced Analytics)
- ⚠️ **Cloudflare Zaraz nicht erklärt:** Tool-Name ohne Erklärung (Server-Side Tag Manager)
- ⚠️ **Looker Studio vs. QuickSight:** Keine Erklärung, wann welches Tool (Google vs. AWS)

### ❌ Fehlende Elemente

- ❌ **Schema.org-Markup:** Kein Service-Schema (wie alle Leistungen)
- ❌ **FAQ-Section:** Keine FAQs zu Consent Mode v2, Server-Side Tracking, KPI-Dashboards
- ❌ **Consent Mode v2 Glossar-Link:** Keine InfoTooltip oder Querverweise zu `/glossar/consent-mode-v2`
- ❌ **Dashboard-Screenshots:** Kein Beispiel für Looker Studio/QuickSight Dashboard (Visualisierung fehlt)
- ❌ **Before/After-KPIs:** Kein "Kunde X: Lead-to-Call Rate +35% nach Server-Side Setup"
- ❌ **CMP-Vergleichstabelle:** Keine Übersicht Usercentrics vs. Borlabs vs. Cookiebot (Wahlhilfe)
- ❌ **Managed Service SLA-Stufen:** Keine Details zu Managed Service (Bronze/Silber/Gold?)
- ❌ **DSGVO-Checkliste-Link:** Kein Link zu "DSGVO-konforme Analytics Checkliste" (Lead-Magnet?)
- ❌ **GA4 vs. Matomo Vergleich:** Wann welches Tool? (Google vs. Self-Hosted)

### 🔴 PRIORITÄT

**Content-Refresh-Priorität:** 🟠 **MITTEL**

**Begründung:**
- **Relevant:** DSGVO/Consent Mode v2 = Dauerthema, aber keine Deadline (wie BFSG)
- **Wettbewerb:** Viele Analytics-Agenturen, aber wenige mit Segment-Fokus (Kanzleien/Schulen/Behörden)
- **SEO-Potenzial:** "Consent Mode v2", "Server-Side Tracking", "GA4 Setup" = Medium-Value-Keywords
- **Managed Service:** Recurring Revenue-Potenzial (nach Projekt-Abschluss)

**ABER:** ⚠️ **Kein Schema.org-Markup** (GEO-Optimierung fehlt) + **keine FAQ** (AIO-Optimierung fehlt).

**Empfohlene Maßnahmen:**

1. **FAQ-Section hinzufügen** - Timeline: 1 Woche
   - 10-12 FAQs: "Was ist Consent Mode v2?", "GA4 vs. Matomo?", "Server-Side vs. Client-Side?", "Was kostet Managed Service?"
   - FAQPage-Schema.org-Markup
   - Accordion-Format

2. **Dashboard-Screenshots hinzufügen** - Timeline: 1 Woche
   - Anonymisiertes Looker Studio Dashboard (Lead-to-Call Rate, Completion Rate)
   - Zeigt: Struktur, Visualisierung, KPI-Cards
   - Reduziert Unsicherheit ("Was bekomme ich?")

3. **Schema.org-Markup hinzufügen** - Timeline: 1 Woche
   - `Service`-Schema mit serviceType: "Analytics & Consent Setup"
   - `Offer`-Schema mit Setup-Dauer (10-15 Tage), Managed Service Pricing-Hints
   - `Organization`-Schema mit Certifications (Google Analytics Certified, etc.)

4. **Consent Mode v2 Glossar-Link** - Timeline: 2 Tage
   - InfoTooltip oder Badge-Link zu `/glossar/consent-mode-v2`
   - Erklärt: Was ist CMv2? Warum wichtig? Modeling für non-consented users
   - AIO-Optimierung

5. **Managed Service-Details** - Timeline: 3 Tage
   - Neue Section oder Stats-Card: "Managed Service Bronze/Silber/Gold" (3 Stufen)
   - Preise: ab 500 €/Monat (Bronze: monatliche QA), ab 1.500 €/Monat (Silber: + KPI-Review), ab 3.000 €/Monat (Gold: + A/B-Tests)
   - Recurring Revenue-Fokus

6. **12+ KPIs vollständig auflisten** - Timeline: 2 Tage
   - Neue Section oder expandable List: Alle 12+ KPIs mit Definitionen
   - Lead-to-Call Rate, Completion Rate, Satisfaction, Response Time, Digital Take-up, Conversion Rate, Bounce Rate, Mobile Share, RUM Score, etc.
   - Macht "12+" greifbar

7. **CMP-Vergleichstabelle** - Timeline: 1 Woche
   - Table: Usercentrics vs. Borlabs vs. Cookiebot (Features, Preise, DSGVO-Konformität, Ease of Use)
   - Wahlhilfe für Kunden
   - Reduziert Beratungsaufwand (Self-Service)

8. **Before/After-Case Study** - Timeline: 2 Wochen
   - "Kanzlei X: Lead-to-Call Rate +35%, Response Time < 1 h nach Server-Side Setup"
   - Screenshot: Vorher-Dashboard (schlechte Datenqualität) vs. Nachher-Dashboard (saubere KPIs)
   - Social Proof

9. **"Einsatzfelder" Section konsolidieren** - Timeline: 3 Tage
   - Option 1: Nur "Segment-Szenarien" behalten (mit mehr Detail)
   - Option 2: "Segment-Szenarien" = KPI-Fokus, "Einsatzfelder" = Tool-Fokus (klarere Trennung)
   - Reduziert Repetition

10. **GA4 vs. Matomo Decision Tree** - Timeline: 1 Woche
    - Flowchart oder Table: Wann GA4? (Google Workspace, Google Ads Integration) vs. Wann Matomo? (Self-Hosted, DSGVO-sensitiv, EU-Server)
    - Wahlhilfe für Kunden
    - Positioniert Wolf-Agents als Tool-agnostisch

---

## 🎯 CONTENT-STRATEGIE

**Primäre Keywords:**
- GA4 Setup (Google Analytics 4)
- Consent Mode v2
- Server-Side Tracking
- KPI-Dashboards
- Analytics DSGVO
- Matomo Setup
- Servicecockpit KPIs

**Sekundäre Keywords (LSI):**
- Usercentrics Integration
- Borlabs Cookie
- Cookiebot
- Cloudflare Zaraz
- BigQuery Data Warehouse
- Looker Studio Dashboards
- Lead-to-Call Tracking
- Completion Rate Monitoring
- Jour-fixe Reports
- Managed Analytics Service

**Zielgruppe:**
- **Primär:** Marketing-Leiter, IT-Leiter in regulierten Organisationen (Kanzleien, Schulen, Behörden)
- **Sekundär:** Geschäftsführer, Partner, Campus-Leitung, Verwaltungsdirektion (KPI-Reporting-Empfänger)
- **Tertiär:** Datenschutzbeauftragte (DSGVO-Compliance)
- **Alter:** 35-60 Jahre
- **Kaufkraft:** Mittel-Hoch (Setup-Budget 8.000-15.000 €, Managed Service 500-3.000 €/Monat)

**User Intent:**
- **Primär:** Commercial Investigation (Analytics-Setup evaluieren, Consent-Compliance sicherstellen)
- **Sekundär:** Informational (Was ist Consent Mode v2? Server-Side vs. Client-Side?)
- **Dringlichkeit:** MITTEL (DSGVO = Dauerthema, aber keine Deadline wie BFSG)

**AIO/GEO/AEO-Status:**
- **AIO:** "Was ist Consent Mode v2?" → FAQ würde beantworten
- **GEO:** ⚠️ Kein Schema.org-Markup → geringe GEO-Optimierung
- **AEO:** Mittlere Featured-Snippet-Potenzial (mit FAQ + Dashboard-Screenshots)
- **AI Overviews:** "Consent Mode v2 Setup", "GA4 vs Matomo", "Server-Side Tracking DSGVO" = häufige Queries

**Paradox (wie barrierefreiheit.md):** Seite verkauft Analytics-Compliance, hat aber selbst kein Schema.org-Markup (Analytics-Tracking schlecht auffindbar für Bots). **Handlungsbedarf!**

---

## 📏 CONTENT-METRIKEN

**Textmenge:**
- Gesamtzeichen: ~10.500
- Gesamtwörter: ~1.350
- Lesedauer: 6-8 Minuten

**Link-Dichte:**
- Interne Links: ~12 (3 Branchen × 2 Sections + Navigation + CTAs + Footer)
- Externe Links: 0 (⚠️ Keine Links zu Google Consent Mode Docs, Matomo, etc.!)
- CTAs: 3 (Hero Primary, Hero Secondary, Final CTA Primary + Secondary)

**Content-Verteilung:**
- Light Sections: ~60 % (TL;DR + Stats, Einsatzfelder, Deliverables + Prozess)
- Dark Sections: ~40 % (Hero, ContentBoxDark mit Segment-Szenarien, Final CTA)

**Interaktive Elemente:**
- Buttons/Links: ~9 (2 Hero CTAs + 3 Segment-Links + 3 Einsatzfeld-Implicit + 2 Final CTAs)
- InfoTooltips: 0
- Segment-Cards: 6 (3 Segment-Szenarien + 3 Einsatzfelder)

**Segment-Card-Dichte:** **HÖCHSTE** (6 Cards, wie barrierefreiheit.md)

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

**Einsatzfelder:**
- Mobile: 1-col Cards
- Desktop: 3-col Grid (md:grid-cols-3)

**Deliverables + Prozess:**
- Mobile: Stack (Leistungsumfang über Prozess)
- Desktop: Side-by-Side (lg:grid-cols-2)

**Projektverlauf:**
- Mobile: 1-col Cards
- Desktop: 4-col Grid (md:grid-cols-4)

---

**ENDE DER DOKUMENTATION - ANALYTICS & CONSENT**

**Umfang:** ~1.050 Wörter (Kompakt-Stil)
**Besonderheit:** ContentBoxDark für Segment-Szenarien, zusätzliche "Einsatzfelder" Section (6 Segment-Cards total), Managed Service erwähnt, 12+ KPIs
**Priorität:** 🟠 MITTEL (DSGVO = Dauerthema, Managed Service = Recurring Revenue, aber kein Schema.org-Markup)
**Status:** ✅ Vollständig dokumentiert
