# STUFE 0 – RAPID RESPONSE MICROSITES

**Verweis:** Siehe `/04-LEISTUNGEN/00-LEISTUNGEN-TEMPLATE.md` für gemeinsame Struktur

**⚠️ WICHTIG:** Diese Seite weicht stark vom Standard-Template ab! Umfangreichste Leistungen-Seite mit mehreren einzigartigen Sections.

**Dokumentiert am:** 2025-10-30
**Status:** IST-Zustand

---

## 📊 META-INFORMATIONEN

| Attribut | Wert |
|----------|------|
| **URL** | https://www.wolf-agents.com/leistungen/stufe-0-ftp-classic |
| **Datei** | `/src/pages/leistungen/stufe-0-ftp-classic.astro` |
| **Title Tag** | "Stufe 0 · Rapid Response Microsites \| Wolf-Agents" |
| **Meta Description** | "In ≤ 10 Tagen live auf bestehendem Hosting: Kanzleien, Schulen & Behörden erhalten Interim-Microsites, Kampagnen- oder Service-Updates ohne Infrastrukturwechsel – inklusive Response Promise < 1 h und dokumentierten Upgrade-Pfaden." |
| **Canonical URL** | https://www.wolf-agents.com/leistungen/stufe-0-ftp-classic |
| **Noindex** | Nein |
| **Geschätzte Zeichenanzahl** | ~11.500 Zeichen (ohne Code/HTML) |
| **Geschätzte Wortanzahl** | ~1.600 Wörter |
| **Geschätzte Lesedauer** | 7-9 Minuten |
| **Anzahl Sections** | 7 Hauptbereiche (mehr als Standard!) |
| **Anzahl H1** | 1 |
| **Anzahl H2** | 7 |
| **Anzahl H3** | 9 (3 Wo Wirkung + 3 Segment-Beispiele + 3 Nächster Schritt) |

---

## 🏗️ ABWEICHUNGEN VOM TEMPLATE

**Diese Seite ist die **UMFANGREICHSTE** aller Leistungen-Seiten!**

**Einzigartige Elemente:**
1. **Breadcrumb-Link** zurück zu /leistungen (kein Footer-Link!)
2. **"Wo Stufe 0 Wirkung entfaltet"** Section (3 Use-Case-Cards ohne KPI-Badges)
3. **Projektverlauf als 4-Etappen-Timeline** (Tag 0-10) statt Deliverables/Ablauf
4. **"Nächster Schritt nach Stufe 0"** Section (3 Stufen-A/B/C-Links) statt More-Siblings
5. **1× InfoTooltip** (core-web-vitals) in Deliverables
6. **stageLinks-Array** (Stufen A/B/C) statt allgemeiner Leistungen-Links

---

## 🏗️ HERO-BEREICH

**Badge:** "Launch in ≤ 10 Tagen"
**H1 (Title):** "Stufe 0 · Rapid Response Microsites"
**Subtitle:** "Wir launchen Kanzlei-, Campus- oder Bürgerdienstseiten in ≤ 10 Tagen auf Ihrem bestehenden Hosting – als sichere Brücke, bis Stufe A–C bereitstehen."

**Primary CTA:** "Projekt anfragen" → `/kontakt`
**Secondary CTA:** "Stufenvergleich öffnen" → `/leistungen#stufen` (Anchor-Link zur Index-Seite!)

---

## 🔙 BREADCRUMB (Einzigartig!)

**BESONDERHEIT:** Diese Seite hat einen **Breadcrumb-Link** zurück zur Leistungen-Übersicht.

**HTML:**
```html
<div class="container pt-6 md:pt-8">
  <a href="/leistungen" class="inline-flex items-center text-on-light-primary hover:text-on-light-primary transition-colors">
    <svg class="w-4 h-4 mr-2" fill="none" stroke="currentColor" viewBox="0 0 24 24">
      <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M15 19l-7-7 7-7" />
    </svg>
    Zurück zur Übersicht
  </a>
</div>
```

**Position:** Zwischen Hero und erster Light Section
**Styling:** Left-Arrow Icon + "Zurück zur Übersicht"
**Keine anderen Leistungen haben diesen Link!**

---

## 📊 TL;DR + STATS

### TL;DR-Box

**Badge:** "TL;DR"
**H2:** "Interim-Microsites, die morgen live gehen können"

**Intro:**
"Stufe 0 ist unser Rapid-Response Setup für Kanzleien, Bildungsträger und Behörden, die sofort live gehen müssen – etwa für Kampagnen, Service-Updates oder Übergangsseiten. Wir exportieren Ihr Astro/Static-Projekt in optimierten HTML/CSS-Code, deployen auf bestehendem Hosting und dokumentieren klar, wie der spätere Umzug auf Stufe A–C gelingt."

**3 Checkmark Items:**
1. "Launch in ≤ 10 Tagen – inklusive Content, Mobile-Optimierung und Redirect-Plan für den späteren Relaunch."
2. "Response Promise < 1 h und Kick-off in 3–5 Werktagen – wir priorisieren Notfälle, Events oder Compliance-Deadlines."
3. "KPIs bleiben messbar: wir setzen Tracking & Consent-Baselines auf, damit Lead-to-Call Rate oder Completion Rate trotz Interim-Lösung sichtbar bleiben."

**Checkmark-Icon-Farbe:** **text-emerald-500** (Grün statt Standard-Primary-Color!)

### Stats-Cards (3)

**Card 1: Go-Live Fenster**
- **Label:** "Go-Live Fenster"
- **Value:** "≤ 10 Tage" (mit non-breaking space!)
- **Context:** "Entwurf, Copy, QA und Deploy erfolgen in einem konzentrierten Sprint – inklusive Backups & Rollback."

**Card 2: Hosting**
- **Label:** "Hosting"
- **Value:** "Bestehend"
- **Context:** "Wir arbeiten auf Ihrem FTP/SFTP oder WebDAV – ohne neue Accounts, Verträge oder Freigaben."

**Card 3: Segment-Kits**
- **Label:** "Segment-Kits"
- **Value:** "3"
- **Context:** "Vorlagen für Kanzlei-Kampagnen, Campus-Events und Behörden-Servicehinweise inklusive Microcopy & CTA-Vorlagen."

---

## 💡 SECTION: "WO STUFE 0 WIRKUNG ENTFALTET"

**EINZIGARTIG:** Diese Section ist **nicht im Standard-Template**!

**H2:** "Wo Stufe 0 Wirkung entfaltet"

**Layout:** grid gap-6 md:grid-cols-3 (3 Cards)

**Card-Styling:**
- Background: `surface-light`
- Border: `border-on-light-subtle`
- Border-radius: rounded-2xl
- Padding: p-6
- Shadow: shadow-sm
- **KEIN Hover-Effect** (im Gegensatz zu Segment-Cards!)

**Card 1: Kanzleien & Boutiquen**
- **Badge:** "Kanzleien & Boutiquen" (chip-light)
- **H3:** "Mandatskampagnen ohne Wartezeit"
- **Description:** "Interim-Landingpages für neue Rechtsgebiete, Litigation-Taskforces oder Standorteröffnungen – inklusive Mandatsaufnahme-Formular und Response-Promise < 1 h."
- **Kein Link!** (nur Info-Card, keine CTA)

**Card 2: Schulen & Bildung**
- **Badge:** "Schulen & Bildung" (chip-success)
- **H3:** "Tag der offenen Tür & Austauschprogramme"
- **Description:** "Mobile-first Microsites mit Programmen, Quicklinks zur Anmeldung und FAQ-Komponenten halten Eltern & Schüler:innen informiert, bis der Campus-Hub ausgerollt ist."
- **Kein Link!**

**Card 3: Behörden & Körperschaften**
- **Badge:** "Behörden & Körperschaften" (chip-brand)
- **H3:** "Service-Updates & Wartungsfenster"
- **Description:** "Bürger:innen erhalten aktuelle Infos, Download-Links und barrierearme Kontaktmöglichkeiten, während die neue Plattform (Stufe B/C) vorbereitet wird."
- **Kein Link!**

**Unterschied zu Segment-Cases:**
- **Keine KPI-Badges**
- **Keine Links** zu Branchen-Seiten
- **Kein Hover-Effect**
- **Fokus:** Konkrete Use-Cases statt generische Segment-Beschreibungen

---

## 📋 LIEFERUMFANG & KPI-BASIS + GOVERNANCE & UPGRADE-PLAN

**ABWEICHUNG:** Statt "Deliverables & Projektablauf" hat diese Seite **andere Titel**!

### Lieferumfang & KPI-Basis (4)

**H2:** "Lieferumfang & KPI-Basis"

1. "Astro/Static Export in optimierten HTML/CSS, inklusive minifizierter Assets, strukturierter Komponenten und Core Web Vitals Budget (LCP ≤ 2,5 s, INP ≤ 200 ms)."
   - **InfoTooltip:** `<InfoTooltip termId="core-web-vitals" mode="auto" />` (einziger Tooltip auf Seite!)

2. "Formular-Varianten für Intake, Anmeldung oder Servicekontakt mit Double-Opt-in und datenschutzkonformen Logs."

3. "Tracking-Basics: Consent-Banner, GA4/Matomo Events, Call-to-Action Tracking und KPI-Handbuch für Lead-to-Call, Completion Rate oder Feedbackscores."

4. "Backup & Rollback-Paket: vollständige Sicherung des alten Auftritts sowie Dokumentation für Ihr IT-/Kommunikationsteam."

### Governance & Upgrade-Plan (4)

**H2:** "Governance & Upgrade-Plan"

1. "Übergabedokument mit Checkliste für den späteren Wechsel auf Stufe A/B/C – inklusive DNS-, Redirect- und Content-Migrationsplan."

2. "Compliance-Review (DSGVO/BFSG/BRAO) mit Handlungsempfehlungen, was für Stufe B/C vorbereitet werden sollte."

3. "Service-Level-Vereinbarung für akute Änderungen (24–48h Turnaround) bis das langfristige Setup live ist."

4. "Optionale Schulung für Ihr Team: FTP-Deploy, Content-Updates und KPI-Monitoring in eigenem Tempo."

---

## 👥 SEGMENT-BEISPIELE & KPI-ZIELE

**H2:** "Segment-Beispiele & KPI-Ziele"

**Intro:**
"Rapid Response wird für jedes Segment anders priorisiert. Wir richten Inhalte, Intake-Flows und Success-Metriken sofort auf Ihre Zielgruppe aus und halten alle Schritte im Servicecockpit fest."

### segmentCases-Array (3 Cards)

```javascript
const segmentCases = [
  {
    title: 'Kanzleien & Sozietäten',
    kpi: 'Lead-to-Call Rate +35 %',
    description: 'Rapid-Response Landingpages für neue Praxisbereiche, Krisenkommunikation oder Kampagnen – inklusive Intake-Formularen, Consent-Setup und KPI-Dashboards.',
    link: '/branchen/kanzleien',
    linkLabel: 'Kanzlei-Blueprint ansehen'
  },
  {
    title: 'Schulen & Bildung',
    kpi: 'Anmeldung in 3 statt 5 Schritten',
    description: 'Temporäre Infoportale für Einschreibungen, Kursstarts oder Krisenkommunikation – mobil optimiert mit StepFlow, RUM-Tracking und Eltern-Kommunikation.',
    link: '/branchen/schulen-bildung',
    linkLabel: 'Enrollment-Guides öffnen'
  },
  {
    title: 'Behörden & öffentliche Dienste',
    kpi: 'Digital Take-up ≥70 %',
    description: 'Interimsseiten für Bürgerdienste, BFSG-/OZG-Informationen oder Formular-Redirects – barrierefrei, auditierbar und mit Servicecockpit-Logging.',
    link: '/branchen/oeffentliche-einrichtungen',
    linkLabel: 'Behörden-Top Tasks prüfen'
  }
];
```

**Card-Styling:** Standard-Segment-Cards (wie Template)
- Surface-light-muted Background
- KPI-Badge
- H3
- Description
- Link mit Arrow-Icon

---

## 🕐 PROJEKTVERLAUF IN VIER ETAPPEN (EINZIGARTIG!)

**ABWEICHUNG:** Statt "Projektablauf" als Checkmark-Liste hat diese Seite eine **4-Etappen-Timeline**!

**H2:** "Projektverlauf in vier Etappen"

**Layout:**
- Ordered List: `<ol class="grid gap-4 md:grid-cols-4 text-sm text-on-light-secondary">`
- 4 Spalten @ Desktop
- Jede Etappe als Card

**Card-Styling:**
- Background: `surface-light`
- Border: `border-on-dark-strong` (⚠️ Dark-Border auf Light-Card, ungewöhnlich!)
- Border-radius: rounded-2xl
- Padding: p-4
- Shadow: shadow-sm

**Gradient-Background der Outer-Box:**
- `bg-gradient-to-br from-slate-50 via-white to-slate-100` (leichter Gradient)

**Etappe 1: Tag 0–1**
- **Label:** "Tag 0–1" (xs, uppercase, tracking 0.22em, text-on-light-primary)
- **Heading:** "Kick-off & Priorisierung" (font-semibold, text-on-light-primary)
- **Content:** "Briefing, Content-Sourcing, KPI-Zielbild, Infrastruktur-Check." (xs, text-on-light-secondary)

**Etappe 2: Tag 2–4**
- **Label:** "Tag 2–4"
- **Heading:** "Design & Copy"
- **Content:** "Hero, Microcopy, Segment-Benefits, Formulare & Tracking-Plan."

**Etappe 3: Tag 5–7**
- **Label:** "Tag 5–7"
- **Heading:** "Build & QA"
- **Content:** "Astro → Static Export, Performance-Budgets, Accessibility-Check."

**Etappe 4: Tag 8–10**
- **Label:** "Tag 8–10"
- **Heading:** "Launch & Enablement"
- **Content:** "FTP-Deploy, Backup, KPI-Dashboard, Upgrade-Roadmap & Schulung."

**Gesamt:** 10 Tage (Hero-Badge: "≤ 10 Tagen")

---

## 🔗 SECTION: "NÄCHSTER SCHRITT NACH STUFE 0"

**EINZIGARTIG:** Diese Section ist **statt** der normalen More-Siblings Section!

**H2:** "Nächster Schritt nach Stufe 0"

**Layout:** grid gap-6 md:grid-cols-3 (3 Cards)

### stageLinks-Array (3 Cards)

```javascript
const stageLinks = [
  {
    label: 'Stufe A – Astro Hub',
    href: '/leistungen/stufe-a-astro-ftp',
    description: 'Modularer Content-Hub für Kanzleien, Schulen & Behörden auf bestehendem Hosting mit klaren Upgrade-Pfaden.'
  },
  {
    label: 'Stufe B – Cloudflare Pages',
    href: '/leistungen/stufe-b-cloudflare-pages',
    description: 'Git-Previews, Rollenrechte und Edge-Caching für Teams mit mehreren Standorten und Fachbereichen.'
  },
  {
    label: 'Stufe C – AWS CloudFront',
    href: '/leistungen/stufe-c-aws-cloudfront',
    description: 'Enterprise-Governance, Audit-Logging und globale SLAs für mission-critical Services.'
  }
];
```

**Card-Styling:**
- `<a>` (gesamte Card ist Link!)
- Background: `surface-light`
- Border: `border-on-light-subtle`
- Border-radius: rounded-2xl
- Padding: p-6
- Shadow: shadow-sm
- Hover: hover:-translate-y-1 hover:shadow-lg transition-all duration-300
- H3: {link.label}
- Description: {link.description}
- CTA-Text: "Mehr erfahren" + Arrow-Right-Icon

**Unterschied zu More-Siblings (Branchen):**
- **Stufen-fokussiert** (nur A/B/C, nicht alle Leistungen)
- **Upgrade-Path** (Stufe 0 → A → B → C)
- **Branchen:** 3 Sibling-Branchen (z.B. Kanzleien zeigt Steuerberater, Schulen, Notare)

---

## 🎯 FINAL CTA

**ContentBoxDark**

**Heading (H2):** "Bereit für den Rapid Response Launch?"

**Description:**
"Wir sichern Ihnen einen Kick-off in 3–5 Werktagen, dokumentieren jede Maßnahme und halten Ihr Team über Slack, Signal oder E-Mail auf dem Laufenden. Parallel planen wir bereits, wie Stufe A/B aussieht – damit Sie ohne Downtime weiter skalieren."

**CTAs:**
- **Primary:** "Projekt anfragen" → `/kontakt`
- **Secondary:** "Weitere Pakete ansehen" → `/leistungen`

---

## 🔍 BESONDERHEITEN

### 1. Breadcrumb-Link (Einzigartig!)

**Nur diese Seite hat einen Breadcrumb** zurück zu /leistungen.
- Position: Zwischen Hero und Light Section
- Icon: Left-Arrow
- Text: "Zurück zur Übersicht"

**Vermutung:** Stufen-Seiten sollen Navigation zur Übersicht haben (aber nur Stufe 0 implementiert es).

### 2. Umfangreichste Leistungen-Seite

**~1.600 Wörter** (vs. ~1.200-1.350 bei anderen Leistungen)
**7 H2-Sections** (vs. 5 bei Standard)

**Grund:** Stufe 0 ist Einstiegs-Angebot → braucht mehr Erklärung (FTP/SFTP, Upgrade-Path, Timeline).

### 3. Emerald-Checkmarks (Grün statt Primary)

**TL;DR-Box-Checkmarks:**
- `text-emerald-500` (Grün #10b981)
- Standard: `text-on-light-primary` (Schwarz #0F172A)

**Grund:** "Rapid Response" = Grünes Licht, Go-Signal, Schnelligkeit visualisieren.

### 4. Projektverlauf als Timeline (4 Etappen)

**Keine Checkmark-Liste**, sondern **4-Spalten-Grid mit Tag-Angaben** (Tag 0-1, 2-4, 5-7, 8-10).

**Besser als Checkmarks für Timeline-Visualisierung.**

### 5. InfoTooltip für Core Web Vitals

**Einziger InfoTooltip auf Seite:**
- termId: "core-web-vitals"
- mode: "auto"
- Position: Lieferumfang Item 1

**Text:** "Core Web Vitals Budget (LCP ≤ 2,5 s, INP ≤ 200 ms)"

**Andere Leistungen:** 0-1 Tooltips pro Seite (Stufe 0 hat genau 1).

### 6. FTP/SFTP/WebDAV-Erwähnung

**Stats-Card 2:**
"Wir arbeiten auf Ihrem FTP/SFTP oder WebDAV – ohne neue Accounts, Verträge oder Freigaben."

**Legacy-Hosting:**
- FTP: File Transfer Protocol (unverschlüsselt, veraltet)
- SFTP: Secure FTP (verschlüsselt)
- WebDAV: Web Distributed Authoring and Versioning (HTTP-basiert)

**Zielgruppe:** Kanzleien/Schulen/Behörden mit bestehendem Legacy-Hosting (oft kein Git/CI/CD).

### 7. Compliance-Review (DSGVO/BFSG/BRAO)

**Governance Item 2:**
"Compliance-Review (DSGVO/BFSG/BRAO) mit Handlungsempfehlungen..."

**3 Compliance-Standards:**
- **DSGVO:** Datenschutz-Grundverordnung (EU)
- **BFSG:** Barrierefreiheitsstärkungsgesetz (Deutschland, 2025)
- **BRAO:** Bundesrechtsanwaltsordnung (Deutschland, Kanzleien-spezifisch)

**Segment-spezifisch:** BRAO nur für Kanzleien, aber Stufe 0 erwähnt alle 3 (da alle Branchen).

### 8. Non-Breaking Space in Stats-Card 1

**Value:** "≤ 10&nbsp;Tage" (statt "≤ 10 Tage")

**Verhindert:** Zeilenumbruch zwischen Zahl und Einheit.
**Best Practice:** &nbsp; für Maßeinheiten, Uhrzeiten, etc.

### 9. Gradient-Background für Projektverlauf

**Outer-Box:**
`bg-gradient-to-br from-slate-50 via-white to-slate-100`

**Andere Sections:** Flat `surface-light` Background.
**Grund:** Visueller Fokus auf Timeline (wichtigstes Feature).

### 10. Stufen-Links statt More-Siblings

**Standard-Leistungen:** Keine More-Siblings Section (nur Branchen haben Siblings)
**Stufe 0:** Hat **"Nächster Schritt"** Section mit Stufen A/B/C-Links

**Upgrade-Path-Logik:** Stufe 0 → A → B → C (progressive Verbesserung).

---

## 📊 CONTENT-AUDIT

### ✅ Stärken

- ✅ **Breadcrumb-Navigation:** Hilft Usern zurück zur Übersicht (gute UX)
- ✅ **Timeline-Visualisierung:** 4-Etappen-Timeline besser als Checkmark-Liste
- ✅ **Emerald-Checkmarks:** Grün = Schnelligkeit, passt zu "Rapid Response"
- ✅ **Upgrade-Path klar:** "Nächster Schritt" Section mit Stufen A/B/C
- ✅ **Legacy-Hosting-Support:** FTP/SFTP/WebDAV explizit erwähnt (Zielgruppen-fit!)
- ✅ **Compliance-Review:** DSGVO + BFSG + BRAO abgedeckt
- ✅ **"Wo Stufe 0 Wirkung entfaltet":** Konkrete Use-Cases (Mandatskampagnen, Tag der offenen Tür, Service-Updates)
- ✅ **KPI-Handbuch:** Lead-to-Call, Completion Rate, Feedbackscores erwähnt
- ✅ **Backup & Rollback:** Explizit erwähnt (Risikominimierung)
- ✅ **Schulung optional:** "in eigenem Tempo" (flexibel)
- ✅ **Astro → Static Export:** Technologie transparent kommuniziert

### ⚠️ Schwächen

- ⚠️ **Breadcrumb-Inkonsistenz:** Nur Stufe 0 hat Breadcrumb, Stufen A/B/C nicht (warum?)
- ⚠️ **2× Segment-Sections repetitiv:** "Wo Wirkung entfaltet" + "Segment-Beispiele" = Redundanz
- ⚠️ **FTP unverschlüsselt erwähnt:** FTP ist unsicher, SFTP sollte bevorzugt werden (FTP=Fallback)
- ⚠️ **Timeline-Cards border-on-dark-strong:** Dunkler Border auf Light-Card wirkt inkonsistent
- ⚠️ **Keine Pricing-Hints:** "≤ 10 Tage" ohne Budget-Range (z.B. "ab 5.000 €")
- ⚠️ **BRAO ohne Erklärung:** Laien wissen nicht, was BRAO ist

### ❌ Fehlende Elemente

- ❌ **Schema.org-Markup:** Kein Service-Schema (wie alle Leistungen)
- ❌ **FAQ-Section:** Keine FAQs zu Stufe 0 (z.B. "Wann Stufe 0 vs. Stufe A?", "Was kostet Stufe 0?")
- ❌ **Case Studies:** Keine Beispiele "Kanzlei X: Kampagne in 7 Tagen live, Lead-to-Call +40 %"
- ❌ **Stufen-Vergleichstabelle:** Kein Feature-Vergleich Stufe 0 vs. A vs. B vs. C
- ❌ **Pricing-Range:** Keine Budget-Hints (Stufe 0 = günstigste Option?)
- ❌ **Screenshot Static Export:** Kein Bild "So sieht Ihr Static Export aus" (technisch für Laien unklar)
- ❌ **Backup-Format unklar:** "vollständige Sicherung" = Zip? SQL? Git-Repo?
- ❌ **SLA-Details:** "24–48h Turnaround" ohne Preis/Bedingungen
- ❌ **FTP-Anleitung:** Kein Link zu "Wie deploye ich auf FTP?"
- ❌ **Rollback-Prozess:** Wie funktioniert Rollback? (1-Click? Manual FTP-Upload?)

### 🔴 PRIORITÄT

**Content-Refresh-Priorität:** 🟡 **MITTEL-HOCH**

**Begründung:**
- **Wichtig:** Einstiegs-Angebot (Stufe 0 = Tür zu Stufe A/B/C)
- **Zeitkritisch:** "≤ 10 Tage" = Notfall-Lösung (Krisenkommunikation, Kampagnen)
- **Zielgruppen-Fit:** Legacy-Hosting (FTP/SFTP) passt zu Kanzleien/Behörden
- **Aber:** Nischen-Angebot (nicht langfristig, nur Interim)

**Empfohlene Maßnahmen:**

1. **Stufen-Vergleichstabelle** - Timeline: 1 Woche
   - Tabelle mit Features: Hosting, GitOps, Upgrade-Aufwand, Timeline, Pricing-Hints
   - Vergleich Stufe 0 vs. A vs. B vs. C
   - Hilft bei Stufen-Wahl ("Wann Stufe 0? Wann Stufe A?")

2. **FAQ-Section hinzufügen** - Timeline: 1 Woche
   - 8-10 FAQs zu Stufe 0 (z.B. "Was kostet Stufe 0?", "Wann Stufe 0 statt Stufe A?", "Wie funktioniert FTP-Deploy?", "Was ist Static Export?")
   - FAQPage-Schema.org-Markup

3. **Case Study hinzufügen** - Timeline: 2 Wochen
   - 1-2 Beispiele: "Kanzlei X: Krisenkommunikation in 7 Tagen live, Lead-to-Call +40 %"
   - "Schule Y: Tag der offenen Tür-Portal in 5 Tagen, Anmeldungen +25 %"

4. **FTP-Sicherheitshinweis** - Timeline: 1 Tag
   - Stats-Card 2: "Wir arbeiten auf Ihrem **SFTP** oder WebDAV (FTP-Fallback falls nötig)."
   - Priorisiert verschlüsseltes SFTP statt unsicherem FTP

5. **Backup-Format klären** - Timeline: 2 Tage
   - Governance Item 4: "Backup als Zip-Archiv inkl. Datenbank-Export (MySQL/PostgreSQL) und Datei-Struktur"
   - Macht greifbarer ("Was bekomme ich?")

6. **Pricing-Hints hinzufügen** - Timeline: 3 Tage
   - Stats-Card 1 oder Hero: "ab 4.500 €" oder "Budget: 4.500-8.500 € je nach Umfang"
   - Reduziert Unsicherheit

7. **SLA-Details** - Timeline: 2 Tage
   - Governance Item 3: "SLA für akute Änderungen (24-48h Turnaround, max. 3 Requests/Monat, +500 €/Request)"
   - Macht Leistung vertraglich greifbar

8. **Breadcrumbs auf Stufen A/B/C** - Timeline: 1 Tag
   - Gleichen Breadcrumb-Code auf stufe-a/b/c.astro kopieren
   - Konsistenz über alle Stufen-Seiten

9. **Segment-Sections konsolidieren** - Timeline: 3 Tage
   - Option 1: "Wo Wirkung entfaltet" entfernen (Info in "Segment-Beispiele" integrieren)
   - Option 2: "Wo Wirkung entfaltet" = konkrete Use-Cases, "Segment-Beispiele" = KPI-fokussiert
   - Reduziert Repetition

10. **BRAO-Tooltip** - Timeline: 1 Tag
    - `<InfoTooltip termId="brao" />` in Compliance-Review
    - Glossar-Eintrag "BRAO: Bundesrechtsanwaltsordnung – Standesrecht für Rechtsanwälte in Deutschland"

---

## 🎯 CONTENT-STRATEGIE

**Primäre Keywords:**
- Rapid Response Websites
- Microsite Launch
- FTP Hosting Websites
- Legacy Hosting Migration
- Interim Websites
- Kampagnen-Landingpages

**Sekundäre Keywords (LSI):**
- Astro Static Export
- FTP/SFTP Deploy
- 10 Tage Website Launch
- Backup & Rollback
- Upgrade-Path Website
- Krisenkommunikation Website
- Event-Landingpages

**Zielgruppe:**
- **Primär:** Kanzleien/Schulen/Behörden mit Legacy-Hosting (FTP/SFTP) und akutem Launch-Bedarf
- **Sekundär:** Marketing-Teams mit kurzfristigen Kampagnen-Deadlines
- **Tertiär:** IT-Verantwortliche, die schrittweise zu Stufe A/B/C migrieren wollen
- **Alter:** 30-55 Jahre
- **Kaufkraft:** Mittel (Budget 4.500-8.500 € geschätzt, niedriger als Stufe A/B/C)

**User Intent:**
- **Primär:** Transactional (Notfall-Lösung buchen, sofort live gehen)
- **Sekundär:** Commercial Investigation (Stufe 0 vs. Stufe A evaluieren)
- **Dringlichkeit:** HOCH (Krisenkommunikation, Event-Deadline, Compliance-Deadline)

**AIO/GEO/AEO-Status:**
- **AIO:** "Wann Stufe 0 statt Stufe A?" → FAQ würde beantworten
- **GEO:** ⚠️ Kein Schema.org-Markup → geringe GEO-Optimierung
- **AEO:** Hohe Featured-Snippet-Potenzial mit FAQ (wenn hinzugefügt)
- **AI Overviews:** "FTP Website Deploy", "Rapid Website Launch 10 Tage" = potenzielle Queries

---

## 📏 CONTENT-METRIKEN

**Textmenge:**
- Gesamtzeichen: ~11.500
- Gesamtwörter: ~1.600
- Lesedauer: 7-9 Minuten

**Link-Dichte:**
- Interne Links: ~10 (Breadcrumb, 3 Branchen-Links, 3 Stufen-A/B/C-Links, Navigation, CTAs, Footer)
- Externe Links: 0
- CTAs: 3 (Hero Primary, Hero Secondary, Final CTA Primary + Secondary)

**Content-Verteilung:**
- Light Sections: ~90 % (TL;DR, Wo Wirkung entfaltet, Lieferumfang, Segment-Beispiele, Projektverlauf, Nächster Schritt)
- Dark Sections: ~10 % (Hero, Final CTA)

**Interaktive Elemente:**
- Buttons/Links: ~10 (Breadcrumb + 2 Hero CTAs + 3 Branchen-Links + 3 Stufen-Links + 2 Final CTAs)
- InfoTooltips: 1 (core-web-vitals)
- Segment-Cards: 3 (Standard-Count)

**Sections-Count:** **7** (höchste aller Leistungen!)

---

## 📐 RESPONSIVE ANPASSUNGEN

**Hero:**
- Mobile: H1 36px, Subtitle 18px
- Desktop: H1 72px, Subtitle 20px

**Breadcrumb:**
- Mobile/Desktop: Gleich (inline-flex, kein Breakpoint)

**TL;DR + Stats:**
- Mobile: Stack (TL;DR über Stats, 1-col Stats)
- Desktop: Side-by-Side (1.35fr TL;DR, 0.65fr Stats-Grid)

**Wo Wirkung entfaltet:**
- Mobile: 1-col Cards
- Desktop: 3-col Grid (md:grid-cols-3)

**Lieferumfang + Governance:**
- Mobile: Stack
- Desktop: Side-by-Side (lg:grid-cols-2)

**Segment-Beispiele:**
- Mobile: 1-col Cards
- Desktop: 3-col Grid (md:grid-cols-3)

**Projektverlauf-Timeline:**
- Mobile: 1-col Cards (stack)
- Desktop: 4-col Grid (md:grid-cols-4)

**Nächster Schritt:**
- Mobile: 1-col Cards
- Desktop: 3-col Grid (md:grid-cols-3)

---

**ENDE DER DOKUMENTATION - STUFE 0 RAPID RESPONSE**

**Umfang:** ~1.300 Wörter (Kompakt-Stil, aber umfangreich wegen vieler Besonderheiten)
**Besonderheit:** Breadcrumb, Timeline-Visualisierung, Stufen-Links, Emerald-Checkmarks, umfangreichste Leistungen-Seite
**Priorität:** 🟡 MITTEL-HOCH (Einstiegs-Angebot, Notfall-Lösung, aber Nischen-Service)
**Status:** ✅ Vollständig dokumentiert
