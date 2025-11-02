# 📚 Schulen & Bildung – Branchen-Detailseite

**URL:** `/branchen/schulen-bildung`
**Template:** `/src/pages/branchen/[slug].astro` (Dynamic Route)
**Content-Quelle:** `/src/content/branchen/schulen-bildung.json`
**Wichtigkeit:** 🔴 Höchste Priorität (Featured auf Startseite)
**Letztes Update:** 2025-10-30

---

## 📊 Meta-Informationen

| Element | Wert |
|---------|------|
| **Title Tag** | "Schulen & Bildung · Digitale Einschreibungen · Wolf-Agents" |
| **Meta Description** | "Digitale Aufnahmestellen, Kurswahl und Campus-Erlebnisse für Schulen, Hochschulen und Bildungsträger. Mobile-first, barrierefrei, 3 Schritte." |
| **Canonical** | `https://wolf-agents.com/branchen/schulen-bildung` |
| **Robots** | `index, follow` |
| **Locale** | `de_DE` |

**Geschätzte Metriken:**
- Zeichen (ohne Leerzeichen): ~8.200
- Wörter: ~1.150
- Lesezeit: ~5 min
- Sections: 11 (Hero → CTA → More Branches)
- Headings: H1(1) + H2(11) + H3(15)

---

## 🔗 Verlinkungsstruktur

### Internal Links Outgoing (Gesamt: ~42)

| Ziel | Anzahl | Context |
|------|--------|---------|
| `/kontakt` | 3× | CTA-Buttons in Hero, Path, Final CTA |
| `/glossar/bfsg-2025` | 3× | Hero Badge Source, Solution-1 Tooltip, Glossary Link |
| `/glossar/core-web-vitals` | 1× | Glossary Link |
| `/glossar/consent-mode-v2` | 1× | Glossary Link |
| `/glossar/rum` | 1× | Glossary Link |
| `/branchen/kanzleien` | 1× | More Branches Card |
| `/branchen/steuerberater` | 1× | More Branches Card |
| `/branchen/notare` | 1× | More Branches Card |
| `/branchen/versicherungen` | 1× | More Branches Card |
| `/branchen/medizin` | 1× | More Branches Card |
| `/branchen/industrie` | 1× | More Branches Card |
| Top Tasks (3×) | 3× | Anchor-Links: #aufnahme, #campus, #verwaltung |

### External Links
- Keine direkten externen Links im Content
- Schulsoftware erwähnt (SORMAS, LUSD, Untis, Moodle) ohne direkte Verlinkung

---

## 🏗️ Layout & Semantische Struktur

**WICHTIG:** Diese Seite nutzt die **identische Struktur** wie `/branchen/kanzleien` (siehe `kanzleien.md` für vollständige Layout-Details mit allen 11 Sections, Spacing, Typografie, Farben).

Die folgende Dokumentation fokussiert auf **branchenspezifische Content-Unterschiede**.

---

## 🎯 KEY CONTENT-UNTERSCHIEDE ZU KANZLEIEN

### Section 1: Hero

**Eyebrow Badge:**
```
"Segment · Bildung"
```

**H1 Headline:**
```
"Digitale Einschreibungen & Campus-Erlebnisse"
```

**Subtitle/Deck:**
```
"Wir digitalisieren Aufnahmestellen, Kurswahl und Informationsarchitektur für Schulen, Hochschulen und Bildungsträger."
```

**KPI Badge:**
- Text: "Anmeldeprozess: 3 Schritte"
- Source: "Pilot DigiSchulanmeldung"
- Link: `/glossar/bfsg-2025`
- Icon: `TrendingDown` (Reduzierung von Komplexität)

**CTA Buttons:**
- Primary: "Termin buchen" → `/kontakt`
- Secondary: "Mehr erfahren" → `#aufnahme` (scroll-to anchor)

---

### Section 2: Top Tasks

**3 Tasks mit unterschiedlichen Zielgruppen:**

**Task 1: Aufnahme beantragen**
- **Zielgruppe:** Eltern & Bewerber:innen
- **Icon:** `ClipboardCheck`
- **Link:** `#aufnahme`
- **Description:**
  ```
  "Schulanmeldung, Kurswahl oder Immatrikulation: Guided Flows mit Dokumenten-Upload, Validierung und automatischer Bestätigung."
  ```

**Task 2: Stundenplan & News**
- **Zielgruppe:** Schüler:innen
- **Icon:** `Calendar`
- **Link:** `#campus`
- **Description:**
  ```
  "Personalisierte Übersicht mit Vertretungsplan, Terminen, Mensa-Menü und Nachrichten – optimiert für mobile Nutzung."
  ```

**Task 3: Räume & Ressourcen verwalten**
- **Zielgruppe:** Schulleitung
- **Icon:** `Settings`
- **Link:** `#verwaltung`
- **Description:**
  ```
  "Admin-Dashboard für Raumbelegung, Equipment-Buchungen, Genehmigungen und Reporting – mit Rollen- und Rechtekonzept."
  ```

---

### Section 3: Path – 3-Schritt-StepFlow 🎯

**BESONDERHEIT:** Diese Seite hat einen **3-Schritt-StepFlow** (kürzer als Kanzleien mit 4 Schritten, aber ausführlicher als Steuerberater ohne Flow).

**StepFlow Component:**
- **Eyebrow:** "Digitale Aufnahme"
- **Title:** "Einschreibung in 3 Schritten"
- **Description:**
  ```
  "So führen wir Eltern, Schüler:innen und Verwaltung vom Antrag bis zur Bestätigung – nachvollziehbar, barrierefrei und ohne Medienbruch."
  ```

**Step 1:**
- **Title:** "1 · Voraussetzungen prüfen"
- **Summary:**
  ```
  "Checkliste mit Alter, Dokumenten, Gebühren und individuellen Anforderungen. Tooltips erklären BFSG, Nachweise und Fristen."
  ```

**Step 2:**
- **Title:** "2 · Online-Formular ausfüllen"
- **Summary:**
  ```
  "Geführter Flow mit Validierung, Dokument-Upload, Mehrsprachigkeit und Zwischenspeicherung für mobile Nutzung."
  ```

**Step 3:**
- **Title:** "3 · Termin & Status bestätigen"
- **Summary:**
  ```
  "Automatische E-Mail/SMS, Dashboard für Verwaltung, Status-Tracking für Eltern sowie Übergabe an Schulsoftware."
  ```

**Grid:** `md:grid-cols-2 xl:grid-cols-3` (3 Spalten auf Desktop für 3 Steps)

**CTA nach StepFlow:**
- Text: "Anmeldeprozess testen"
- Link: `/kontakt`

---

### Section 4: Pains

**3 Challenges mit Bildungs-Fokus:**

**Pain 1: Papierbasierte Prozesse**
- **Icon:** `FileX`
- **Title:** "Papierbasierte Prozesse"
- **Description:**
  ```
  "Anmeldeformulare per Post, Scans per E-Mail oder Fax: Medienbrüche verzögern Aufnahmen und verursachen Rückfragen."
  ```

**Pain 2: Mobile Nutzung bleibt unbedient**
- **Icon:** `Smartphone`
- **Title:** "Mobile Nutzung bleibt unbedient"
- **Description:**
  ```
  "Schüler:innen und Eltern greifen zu 60+ % mobil zu – doch alte Portale sind weder responsive noch thumb-friendly."
  ```

**Pain 3: Inhalte schwer auffindbar**
- **Icon:** `Search`
- **Title:** "Inhalte schwer auffindbar"
- **Description:**
  ```
  "Ohne Content-Hierarchie, Suchfunktion oder Topic-Tags gehen wichtige Infos in PDF-Friedhöfen unter."
  ```

---

### Section 5: Solutions

**3 Lösungen mit InfoTooltips:**

**Solution 1: Anmeldung in 3 Schritten**
- **Icon:** `Workflow`
- **Title:** "Anmeldung in 3 Schritten"
- **Deck:** "Geführter Flow mit Validierung, Zwischenspeicherung und Status-Tracking – barrierefrei und BFSG-konform."
- **Summary:**
  ```
  "Guided Forms mit Live-Validierung, Dokument-Upload, E-Mail-Bestätigung und Übergabe an Schulsoftware (SORMAS, LUSD, Moodle)."
  ```
- **Proof:** "Bearbeitungszeit −45 %"
- **InfoTooltip:** `tooltipTerm: "bfsg-2025"` (Modal)

**Solution 2: Mobile-first Campus Hub**
- **Icon:** `Smartphone`
- **Title:** "Mobile-first Campus Hub"
- **Deck:** "Personalisiertes Dashboard für Stundenplan, News, Mensa-Menü und Vertretungsplan – optimiert für Thumb-Zone."
- **Summary:**
  ```
  "Content-Cards mit Live-Sync zu Untis, iCal-Export, Push-Benachrichtigungen und Offline-Cache für unterwegs."
  ```
- **Proof:** "Mobile Zufriedenheit +30 %"
- **InfoTooltip:** Keine

**Solution 3: Content-Module statt PDF**
- **Icon:** `FileText`
- **Title:** "Content-Module statt PDF"
- **Deck:** "Strukturierte Inhalte mit Search, Filter und Topic-Tags – statt 200-seitigem Schulhandbuch."
- **Summary:**
  ```
  "Markdown-basierte Content-Modules mit Full-Text-Search, automatischem Inhaltsverzeichnis und PDF-Export on demand."
  ```
- **Proof:** "Support-Anfragen −25 %"
- **InfoTooltip:** Keine

---

### Section 6: WebApps & Automations

**3 WebApps mit Tech-Stack:**

**WebApp 1: Online-Aufnahme**
- **Title:** "Online-Aufnahme"
- **Description:**
  ```
  "Geführter Anmeldeflow mit Live-Validierung, Dokument-Upload (PDF/Bild), automatischer Bestätigung und Übergabe an Schulsoftware."
  ```
- **Tech Stack:**
  - Astro SSR
  - Cloudflare Workers
  - Resend (E-Mail)
  - Live Form Validation
- **Features:** 4 items (Guided Flow, Upload, E-Mail, Sync)

**WebApp 2: Stundenplan & News Hub**
- **Title:** "Stundenplan & News Hub"
- **Description:**
  ```
  "Personalisiertes Dashboard mit Vertretungsplan-Sync, Mensa-Menü, Push-Benachrichtigungen und Kalender-Export."
  ```
- **Tech Stack:**
  - Astro SSR
  - Svelte Island (interaktive Kalender-Komponente)
  - Cloudflare D1 (Stundenplan-Cache)
  - iCal Export
- **Features:** 4 items (Sync, Notifications, Export, Offline-Cache)

**WebApp 3: Ressourcen-Manager**
- **Title:** "Ressourcen-Manager"
- **Description:**
  ```
  "Admin-Tool für Raumbelegung, Equipment-Buchungen, Genehmigungen und Reporting mit Rollen- und Rechtekonzept."
  ```
- **Tech Stack:**
  - Astro SSR
  - Cloudflare Workers
  - Supabase (Datenbank + Auth)
  - RBAC (Role-Based Access Control)
- **Features:** 4 items (Buchungen, Genehmigungen, Reporting, RBAC)

---

### Section 7: KPI & Proof

**3 Metriken:**

**KPI 1:**
- **Label:** "Anmeldeprozess"
- **Value:** "3 Schritte"
- **Context:** "Statt 7 Schritte mit PDF + Briefpost"
- **Icon:** `TrendingDown`

**KPI 2:**
- **Label:** "Bearbeitungszeit"
- **Value:** "−45 %"
- **Context:** "Weniger Rückfragen durch Validierung"
- **Icon:** `Clock`

**KPI 3:**
- **Label:** "Mobile Zufriedenheit"
- **Value:** "+30 %"
- **Context:** "Thumb-friendly Design für 60+ % mobile Zugriffe"
- **Icon:** `Smartphone`

**Source:** "Pilot DigiSchulanmeldung · Bayern & NRW"

---

### Section 8: FAQ

**3 Items mit AI-Snippet-Hinweisen:**

**FAQ 1:**
- **Question:** "Welche Schnittstellen zu Schulsoftware gibt es?"
- **Answer:**
  ```
  "Wir integrieren REST-APIs, WebHooks oder CSV-Export/Import zu gängigen Systemen wie SORMAS (Hessen), LUSD (Bayern), Untis (Stundenplan), Moodle (LMS) und SIS-Lösungen."
  ```
- **AI Snippet:** Technische Liste (Schulsoftware-Namen)

**FAQ 2:**
- **Question:** "Wie wird Datenschutz für Schüler:innen sichergestellt?"
- **Answer:**
  ```
  "EU-Hosting (Cloudflare, Hetzner), Ende-zu-Ende-Verschlüsselung für Uploads, DSGVO-konforme Consent-Flows und WORM-Backups nach GoBD. Pen-Tests jährlich."
  ```
- **AI Snippet:** Compliance-Keywords (DSGVO, EU-Hosting, GoBD)

**FAQ 3:**
- **Question:** "Wie lange dauert Go-Live?"
- **Answer:**
  ```
  "MVP mit Online-Aufnahme und Stundenplan-Sync in 6 Wochen. Full Rollout mit Ressourcen-Manager und CMS-Integration in 8–12 Wochen, abhängig von Schnittstellen."
  ```
- **AI Snippet:** Timeline-Angaben (6 Wochen MVP, 8–12 Wochen Full)

---

### Section 9: Glossary

**4 verlinkte Begriffe:**

| Badge-Text | Link | Term-ID |
|------------|------|---------|
| "BFSG 2025" | `/glossar/bfsg-2025` | `bfsg-2025` |
| "Core Web Vitals" | `/glossar/core-web-vitals` | `core-web-vitals` |
| "Consent Mode v2" | `/glossar/consent-mode-v2` | `consent-mode-v2` |
| "RUM" | `/glossar/rum` | `rum` |

---

### Section 10: CTA (Final Call-to-Action)

**Headline:**
```
"Anmeldeprozesse digitalisieren?"
```

**Subline:**
```
"Wir zeigen Ihnen in 30 Minuten, wie Sie Aufnahme, Campus-Hub und Ressourcen-Manager für Ihre Schule umsetzen."
```

**CTA Buttons:**
- Primary: "Termin buchen" → `/kontakt`
- Secondary: "Mehr Branchen entdecken" → scroll to More Branches

---

### Section 11: More Branches

**6 Sibling-Karten:**
- Kanzleien
- Steuerberater
- Notare
- Versicherungen
- Medizin
- Industrie

(Automatisch generiert aus allen anderen Branchen außer der aktuellen)

---

## 🎨 Design-System-Details

**Farben (Schulen-spezifisch):**
- Keine branchen-spezifischen Farben (nutzt globale Design-Tokens wie Kanzleien)
- Primary Accent: `--accent-primary` (#3b82f6)
- Dark Tone: `--bg-dark` (#0f172a)
- Light Tone: `--bg-light` (#f8fafc)

**Typografie:**
- Headline H1: `font-family: 'Plus Jakarta Sans', font-weight: 700, font-size: 36px → 72px`
- Badge: `font-family: 'Space Mono', font-size: 14px, text-transform: uppercase, letter-spacing: 0.1em`

**Icons (Lucide):**
- Hero: `GraduationCap`
- Tasks: `ClipboardCheck`, `Calendar`, `Settings`
- Pains: `FileX`, `Smartphone`, `Search`
- Solutions: `Workflow`, `Smartphone`, `FileText`

---

## 📱 Responsive Breakpoints

**Siehe `kanzleien.md` für vollständige Breakpoint-Tabelle.**

**Schulen-spezifische Anpassungen:**
- StepFlow: `xl:grid-cols-3` (3 Steps → 3 Spalten statt 4)
- Mobile: Vertikales Stacking für alle Sections

---

## 🧩 Komponenten-Bibliothek

**Verwendete Astro-Components:**

1. `<LayoutBranch>` – Wrapper mit SEO + Schema.org
2. `<Navigation>` – Sticky Header
3. `<HeroBranch>` – Hero mit Badge + KPI + CTA
4. `<TaskArticle>` – Top Tasks Grid
5. `<StepFlow>` – **3-Schritt-Flow** (conditional rendering bei `index === 0`)
6. `<PainCard>` – Pain-Grid
7. `<SolutionCard>` – Solutions mit InfoTooltip
8. `<WebAppCard>` – WebApps mit Tech-Stack
9. `<KPICard>` – KPI-Grid
10. `<FAQCard>` – FAQ-Accordion
11. `<GlossaryLinks>` – Badge-Grid
12. `<CTASection>` – Final CTA
13. `<BranchCard>` – More Branches Grid
14. `<Footer>` – Global Footer

**Data Loading:**
```astro
const { slug } = Astro.params;
const branchData = await getEntry('branchen', slug);
const { stepFlow } = branchData.data;
```

**Conditional Rendering:**
```astro
{stepFlow && index === 0 && (
  <StepFlow
    eyebrow={stepFlow.eyebrow}
    title={stepFlow.title}
    description={stepFlow.description}
    steps={stepFlow.steps}
  />
)}
```

---

## 🔍 SEO & Strukturierte Daten

**Schema.org Markup:**

```json
{
  "@context": "https://schema.org",
  "@type": ["EducationalOrganization", "Organization"],
  "name": "Wolf-Agents · Schulen & Bildung",
  "description": "Digitale Aufnahmestellen, Kurswahl und Campus-Erlebnisse für Schulen, Hochschulen und Bildungsträger.",
  "url": "https://wolf-agents.com/branchen/schulen-bildung",
  "audience": {
    "@type": "Audience",
    "audienceType": "Eltern, Schüler:innen, Studierende, Schulleitung, Hochschulverwaltung"
  },
  "areaServed": {
    "@type": "Place",
    "name": "Deutschland, Österreich, Schweiz"
  },
  "knowsAbout": [
    "Digitale Schulanmeldung",
    "Campus Management",
    "Barrierefreie Bildungsportale",
    "BFSG Compliance"
  ]
}
```

**Open Graph:**
- `og:title`: "Schulen & Bildung · Digitale Einschreibungen"
- `og:description`: "Mobile-first Campus-Hub, 3-Schritt-Anmeldung, BFSG-konform"
- `og:type`: "website"
- `og:image`: `/og-images/schulen-bildung.png` (1200×630px)

---

## ♿ Barrierefreiheit (A11y)

**WCAG 2.2 AA Compliance:**
- Kontrast Hero-Text (weiß auf dunkel): 15.6:1 ✅
- Kontrast Body-Text (dunkel auf hell): 12.8:1 ✅
- Fokus-Indikatoren: 2px solid `--accent-primary`
- Skip-Links: Vorhanden in Navigation

**Semantic HTML:**
- `<nav>`, `<main>`, `<section>`, `<article>`, `<footer>`
- Heading-Hierarchie: H1 → H2 → H3 (keine Sprünge)

**Interactive Elements:**
- Alle Buttons: `aria-label` bei Icon-only
- StepFlow Steps: `role="list"` + `role="listitem"`
- FAQ Accordion: `aria-expanded`, `aria-controls`

---

## 📝 Content-Strategie & Targeting

**Hauptthema:**
"Digitale Einschreibungen und Campus-Erlebnisse für Schulen und Hochschulen"

**Primary Keywords:**
- Digitale Schulanmeldung
- Campus Management System
- Barrierefreie Bildungsportale
- Online-Einschreibung
- Mobile-first Schul-App

**Secondary Keywords:**
- BFSG-konforme Aufnahme
- Schulsoftware-Integration (SORMAS, LUSD, Untis)
- Ressourcen-Manager Schule
- Stundenplan-App
- Content-Module Bildung

**Zielgruppe:**
- Primär: Eltern, Schüler:innen, Bewerber:innen
- Sekundär: Schulleitung, Hochschulverwaltung, IT-Koordinatoren

**User Intent:**
- 60 % Informational (Wie funktioniert digitale Anmeldung?)
- 40 % Transactional (Termin buchen, Demo anfragen)

**AIO/GEO/AEO-Optimierung:**
- ✅ **AIO:** FAQ mit AI-Snippet-Ready-Content (Schulsoftware-Liste, DSGVO-Keywords, Timeline)
- ✅ **GEO:** Lokale Geo-Coverage (DE, AT, CH) im Schema.org
- ✅ **AEO:** 3-Schritt-StepFlow strukturiert Prozess-Fragen

---

## 📊 Content-Audit-Notizen

### ✅ Stärken

1. **3-Schritt-StepFlow klar strukturiert** – Vereinfacht Komplexität im Vergleich zu 4-7 Schritten
2. **Mobile-first Fokus prominent** – Trifft 60+ % Zielgruppen-Verhalten (Schüler:innen, Eltern)
3. **BFSG-Compliance hervorgehoben** – Regulatorische Anforderung ab 2025
4. **Konkrete Schulsoftware-Integration** – SORMAS, LUSD, Untis, Moodle erwähnt
5. **KPIs mit Proof** – "−45 % Bearbeitungszeit", "+30 % Mobile Zufriedenheit"
6. **Pain → Solution Mapping** – Jeder Pain hat direkte Solution-Antwort

### ⚠️ Schwächen & Legacy-Issues

1. **Keine visuellen Demos** – Campus-Hub-Screenshots fehlen (könnten UX verdeutlichen)
2. **Fehlende Testimonials** – Keine Referenz von Schulen/Hochschulen
3. **Integration nur erwähnt, nicht detailliert** – REST-API-Dokumentation fehlt
4. **Keine Unterscheidung Schule vs. Hochschule** – Content vermischt beide Zielgruppen

### ❌ Fehlende Elemente

1. **Case Study/Referenz** – Pilotprojekt "DigiSchulanmeldung" nur erwähnt, nicht verlinkt
2. **Schulsoftware-Logos** – SORMAS, LUSD, Untis als vertrauensbildende visuelle Anker
3. **Preisindikation** – "Ab X € pro Monat" oder "Individuell" fehlt
4. **Video-Demo** – Campus-Hub in Action (mobile Nutzung)

### 🔴 Content-Refresh-Priorität

**Priorität: HOCH** (Featured auf Startseite + regulatorische Dringlichkeit BFSG 2025)

**Empfohlene Maßnahmen:**
1. Pilotprojekt-Referenz als Case Study ausbauen (eigene Unterseite oder Pop-up)
2. Screenshots/Video von Campus-Hub hinzufügen (mobile Ansicht)
3. Schulsoftware-Logos in WebApp-Section integrieren
4. FAQ um Frage "Schnittstellen-Dokumentation verfügbar?" erweitern
5. Trennung Schule/Hochschule prüfen (ggf. 2 separate Branchen-Seiten)

---

## ⚡ Performance & Technische Details

**Core Web Vitals Targets:**
- LCP: < 2.5s (Hero-Bild optimiert)
- FID: < 100ms (minimales JavaScript)
- CLS: < 0.1 (feste Dimensions für Images/Cards)

**Lazy Loading:**
- Images: `loading="lazy"` ab Fold 2
- Svelte Island (Stundenplan): Hydration on visible

**Mobile Optimization:**
- Touch-Targets: min. 44×44px
- Thumb-Zone: CTA-Buttons unten
- Viewport-Units: `vh` für Hero

---

## 📈 Content-Metriken

| Metrik | Wert |
|--------|------|
| **Text-Volumen** | ~8.200 Zeichen, ~1.150 Wörter |
| **Link-Density** | ~42 interne Links, 0 externe Links |
| **Content-Verteilung** | 5 Dark Sections, 6 Light Sections |
| **Interactive Elements** | 3 Top Tasks, 3 StepFlow Steps, 3 FAQ Accordions, 6 More Branches |
| **Glossary Coverage** | 4 Begriffe (BFSG, CWV, Consent Mode, RUM) |

---

## 🏁 Fazit

Die Schulen-Bildung-Seite nutzt die bewährte Branchen-Template-Struktur mit **3-Schritt-StepFlow** als Alleinstellungsmerkmal. Der Fokus auf **Mobile-first** und **BFSG-Compliance** trifft regulatorische Anforderungen und Zielgruppen-Verhalten.

**Stärken:** Klare Struktur, konkrete Schulsoftware-Integration, messbare KPIs.
**Verbesserungspotenzial:** Visuelle Demos, Testimonials, Case-Study-Link.

**Für vollständige Layout-Details (Spacing, Typografie, Color-Tokens, Responsive-Grid) siehe `kanzleien.md`.**
