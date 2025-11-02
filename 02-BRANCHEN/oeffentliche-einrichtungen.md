# 🏛️ Öffentliche Einrichtungen – Branchen-Detailseite

**URL:** `/branchen/oeffentliche-einrichtungen`
**Template:** `/src/pages/branchen/[slug].astro` (Dynamic Route)
**Content-Quelle:** `/src/content/branchen/oeffentliche-einrichtungen.json`
**Wichtigkeit:** 🔴 Höchste Priorität (Featured auf Startseite)
**Letztes Update:** 2025-10-30

---

## 📊 Meta-Informationen

| Element | Wert |
|---------|------|
| **Title Tag** | "Öffentliche Einrichtungen · Barrierefreie Bürgerdienste · Wolf-Agents" |
| **Meta Description** | "Barrierefreie Top-Tasks, Formularstrecken und Servicecockpits für Verwaltungen, Kammern und Körperschaften. BFSG 2025 & WCAG 2.2 konform." |
| **Canonical** | `https://wolf-agents.com/branchen/oeffentliche-einrichtungen` |
| **Robots** | `index, follow` |
| **Locale** | `de_DE` |

**Geschätzte Metriken:**
- Zeichen (ohne Leerzeichen): ~9.400
- Wörter: ~1.320
- Lesezeit: ~5,5 min
- Sections: 11 (Hero → CTA → More Branches)
- Headings: H1(1) + H2(11) + H3(16)

---

## 🔗 Verlinkungsstruktur

### Internal Links Outgoing (Gesamt: ~44)

| Ziel | Anzahl | Context |
|------|--------|---------|
| `/kontakt` | 3× | CTA-Buttons in Hero, Path, Final CTA |
| `/glossar/bfsg-2025` | 3× | Hero Badge Source, Solution-1 Tooltip, Glossary Link |
| `/glossar/wcag-22` | 2× | Pain-1 Reference, Glossary Link |
| `/glossar/rum` | 2× | Solution-3 Tooltip, Glossary Link |
| `/glossar/gitops` | 2× | Solution-2 Tooltip, Glossary Link |
| `/branchen/kanzleien` | 1× | More Branches Card |
| `/branchen/steuerberater` | 1× | More Branches Card |
| `/branchen/schulen-bildung` | 1× | More Branches Card |
| `/branchen/notare` | 1× | More Branches Card |
| `/branchen/versicherungen` | 1× | More Branches Card |
| `/branchen/medizin` | 1× | More Branches Card |
| Top Tasks (3×) | 3× | Anchor-Links: #dienstleistungen, #termine, #verwaltung |

### External Links
- Keine direkten externen Links im Content
- Standards erwähnt (BFSG, WCAG 2.2, OZG, GoBD, DSGVO) ohne direkte Verlinkung
- CMS-Systeme erwähnt (GSB, WordPress, TYPO3, Drupal) ohne direkte Verlinkung

---

## 🏗️ Layout & Semantische Struktur

**WICHTIG:** Diese Seite nutzt die **identische Struktur** wie `/branchen/kanzleien` (siehe `kanzleien.md` für vollständige Layout-Details mit allen 11 Sections, Spacing, Typografie, Farben).

Die folgende Dokumentation fokussiert auf **branchenspezifische Content-Unterschiede** mit **Schwerpunkt auf dem 4-Phasen-StepFlow** (umfangreichster Flow aller Branchen!).

---

## 🎯 KEY CONTENT-UNTERSCHIEDE ZU KANZLEIEN

### Section 1: Hero

**Eyebrow Badge:**
```
"Segment · Verwaltung"
```

**H1 Headline:**
```
"Barrierefreie Bürgerdienste & Servicecockpits"
```

**Subtitle/Deck:**
```
"Wir digitalisieren Top-Tasks, Formularstrecken und KPI-Cockpits für Verwaltungen, Kammern und Körperschaften."
```

**KPI Badge:**
- Text: "Completion Rate: ≥ 70 %"
- Source: "GOV.UK & OZG Benchmarks"
- Link: `/glossar/bfsg-2025`
- Icon: `TrendingUp` (Steigerung der Abschlussrate)

**CTA Buttons:**
- Primary: "Termin buchen" → `/kontakt`
- Secondary: "Mehr erfahren" → `#dienstleistungen` (scroll-to anchor)

---

### Section 2: Top Tasks

**3 Tasks mit unterschiedlichen Zielgruppen:**

**Task 1: Dienstleistung beantragen**
- **Zielgruppe:** Bürger:innen
- **Icon:** `FileText`
- **Link:** `#dienstleistungen`
- **Description:**
  ```
  "Anträge, Genehmigungen oder Bescheinigungen online stellen – mit Guided Forms, Dokument-Upload und Status-Tracking."
  ```

**Task 2: Termin vereinbaren**
- **Zielgruppe:** Bürger:innen
- **Icon:** `Calendar`
- **Link:** `#termine`
- **Description:**
  ```
  "Warteschlangen vermeiden: Online-Terminbuchung für Bürgerbüro, Standesamt oder Zulassungsstelle mit Kalender-Sync."
  ```

**Task 3: Login Verwaltung**
- **Zielgruppe:** Sachbearbeitung
- **Icon:** `Lock`
- **Link:** `#verwaltung`
- **Description:**
  ```
  "Admin-Dashboard für Antragsbearbeitung, Vier-Augen-Freigaben, Archivierung und KPI-Reporting nach GoBD & DSGVO."
  ```

---

### Section 3: Path – 4-Phasen-StepFlow 🎯

**BESONDERHEIT:** Diese Seite hat den **umfangreichsten StepFlow** aller Branchen mit **4 Phasen** und den **längsten Step-Beschreibungen**!

**StepFlow Component:**
- **Eyebrow:** "Servicecockpit Journey"
- **Title:** "Bürgerdienst in 4 Phasen"
- **Description:**
  ```
  "Teams steuern Anträge end-to-end: vom klaren Einstieg über barrierefreie Formulare bis zum KPI-Reporting."
  ```

**Step 1:**
- **Title:** "1 · Top Tasks sichtbar machen"
- **Summary:**
  ```
  "Service-Navigation mit Plain Language, Voraussetzungen und Dokument-Checklisten reduziert Rückfragen schon vor dem Antrag."
  ```

**Step 2:**
- **Title:** "2 · Guided Form & Uploads"
- **Summary:**
  ```
  "Barrierefreie Formulare mit Zwischenspeicherung, Medien-Upload, Mehrsprachigkeit und Echtzeit-Validierung."
  ```

**Step 3:**
- **Title:** "3 · Bearbeitung & Governance"
- **Summary:**
  ```
  "Vier-Augen-Freigaben, Rollen- und Rechteverwaltung, Archivierung nach GoBD & DSGVO sowie automatisierte Mitteilungen."
  ```

**Step 4:**
- **Title:** "4 · KPI Monitoring & Feedback"
- **Summary:**
  ```
  "Servicecockpit mit Completion Rate, Digital Take-up, Zufriedenheit und Feedback-Widget, verknüpft mit Eskalationsprozessen."
  ```

**Grid:** `md:grid-cols-2 xl:grid-cols-4` (4 Spalten auf Desktop für 4 Steps)

**CTA nach StepFlow:**
- Text: "Servicecockpit testen"
- Link: `/kontakt`

**WICHTIG:** Dieser Flow ist der detaillierteste, da er den **kompletten Governance-Zyklus** von Bürgerdiensten abbildet (Einstieg → Antrag → Bearbeitung → Monitoring). Step 3 ist besonders umfangreich mit GoBD, DSGVO und Vier-Augen-Prinzip.

---

### Section 4: Pains

**3 Challenges mit Verwaltungs-Fokus:**

**Pain 1: BFSG 2025 & WCAG 2.2 Anforderungen**
- **Icon:** `AlertTriangle`
- **Title:** "BFSG 2025 & WCAG 2.2 Anforderungen"
- **Description:**
  ```
  "Ab 2025 müssen digitale Angebote barrierefrei sein – doch viele Portale scheitern an Kontrast, Tastaturbedienung oder Screen-Reader-Kompatibilität."
  ```
- **Reference:** `/glossar/wcag-22`

**Pain 2: Formulare brechen ab**
- **Icon:** `XCircle`
- **Title:** "Formulare brechen ab"
- **Description:**
  ```
  "Fehlende Validierung, Timeouts oder technische Fehler frustrieren Bürger:innen – Completion Rates liegen oft unter 40 %."
  ```

**Pain 3: Fehlendes Monitoring**
- **Icon:** `BarChart`
- **Title:** "Fehlendes Monitoring"
- **Description:**
  ```
  "Ohne KPI-Cockpit bleiben Abbruchstellen, langsame Formulare oder hohe Rückfragen unsichtbar – Teams reagieren erst auf Beschwerden."
  ```

---

### Section 5: Solutions

**3 Lösungen mit InfoTooltips (alle mit Tooltips!):**

**Solution 1: BFSG-konforme UX**
- **Icon:** `Check`
- **Title:** "BFSG-konforme UX"
- **Deck:** "Barrierefreie Formulare mit Kontrast-Check, Tastaturbedienung, Screen-Reader-Support und BITV-Prüfbericht."
- **Summary:**
  ```
  "Wir auditieren Ihre Formulare nach WCAG 2.2 AA, optimieren Kontraste, Fokus-Indikatoren und Alt-Texte und liefern den BFSG-Prüfbericht für den Nachweis."
  ```
- **Proof:** "BFSG Audit bestanden"
- **InfoTooltip:** `tooltipTerm: "bfsg-2025"` (Modal)

**Solution 2: Service-Flows mit Logging**
- **Icon:** `GitBranch`
- **Title:** "Service-Flows mit Logging"
- **Deck:** "Guided Forms mit Live-Validierung, Zwischenspeicherung, Medien-Upload und Event-Logging für Fehleranalyse."
- **Summary:**
  ```
  "Jeder Schritt wird geloggt (ohne personenbezogene Daten): Abbruchstellen, Validierungsfehler, Browser-Kompatibilität. Teams erkennen Probleme in Echtzeit."
  ```
- **Proof:** "Completion Rate ≥ 70 %"
- **InfoTooltip:** `tooltipTerm: "gitops"` (Modal)

**Solution 3: Servicecockpit**
- **Icon:** `BarChart3`
- **Title:** "Servicecockpit"
- **Deck:** "KPI-Dashboard mit Completion Rate, Digital Take-up, Zufriedenheit und Feedback-Widget, integriert mit Looker Studio."
- **Summary:**
  ```
  "Real User Monitoring (RUM) erfasst Core Web Vitals, Ladezeiten und Interaktionen. Teams priorisieren Optimierungen datenbasiert statt bauchgefühlt."
  ```
- **Proof:** "Digital Take-up +40 %"
- **InfoTooltip:** `tooltipTerm: "rum"` (Modal)

**HINWEIS:** Alle 3 Solutions haben InfoTooltips – höchste Dichte aller Branchen-Seiten, um regulatorische/technische Begriffe zu erklären.

---

### Section 6: WebApps & Automations

**3 WebApps mit Tech-Stack:**

**WebApp 1: Dienstleistungs-Flow**
- **Title:** "Dienstleistungs-Flow"
- **Description:**
  ```
  "Guided Formulare mit Live-Validierung, Dokument-Upload (PDF/Bild), Zwischenspeicherung und automatischer Bestätigung per E-Mail/SMS."
  ```
- **Tech Stack:**
  - Astro SSR
  - Live Form Validation
  - Cloudflare Workers
  - Resend/Twilio (Benachrichtigungen)
- **Features:** 4 items (Guided Flow, Validierung, Upload, Zwischenspeicherung)

**WebApp 2: Termin & Wartesystem**
- **Title:** "Termin & Wartesystem"
- **Description:**
  ```
  "Online-Terminbuchung mit Kalender-Sync, SMS-Erinnerung, Warteschlangen-Status und Check-in via QR-Code für hybride Abläufe."
  ```
- **Tech Stack:**
  - Astro SSR
  - Cloudflare D1 (Terminverwaltung)
  - Twilio (SMS)
  - iCal/Google Calendar Sync
- **Features:** 4 items (Buchung, Erinnerung, QR-Code, Kalender-Export)

**WebApp 3: Servicecockpit**
- **Title:** "Servicecockpit"
- **Description:**
  ```
  "KPI-Dashboard mit Completion Rate, Digital Take-up, Core Web Vitals und Feedback-Aggregation, verknüpft mit Eskalationsprozessen."
  ```
- **Tech Stack:**
  - Looker Studio (Dashboards)
  - BigQuery (Data Warehouse)
  - RUM (Real User Monitoring)
  - Feedback-Widget (Custom)
- **Features:** 4 items (KPIs, CWV, Feedback, Alerting)

---

### Section 7: KPI & Proof

**3 Metriken:**

**KPI 1:**
- **Label:** "Completion Rate"
- **Value:** "≥ 70 %"
- **Context:** "GOV.UK & OZG Benchmark für erfolgreiche Antragsabschlüsse"
- **Icon:** `TrendingUp`

**KPI 2:**
- **Label:** "Digital Take-up"
- **Value:** "+40 %"
- **Context:** "Mehr Bürger:innen nutzen digitale statt analoge Kanäle"
- **Icon:** `Users`

**KPI 3:**
- **Label:** "Barrierefreiheit"
- **Value:** "WCAG 2.2 AA"
- **Context:** "BFSG 2025-konform mit Prüfbericht und BITV-Test"
- **Icon:** `Check`

**Source:** "GOV.UK & OZG Benchmarks · Pilot Bürgerdienste DE/AT"

---

### Section 8: FAQ

**3 Items mit AI-Snippet-Hinweisen:**

**FAQ 1:**
- **Question:** "Wie stellen Sie BFSG 2025 & BITV-Compliance sicher?"
- **Answer:**
  ```
  "Wir auditieren nach WCAG 2.2 AA (Kontrast, Tastaturbedienung, Screen-Reader), liefern den BFSG-Prüfbericht und schulen Ihr Team in barrierefreier Content-Pflege."
  ```
- **AI Snippet:** Compliance-Liste (BFSG, WCAG 2.2, BITV, Prüfbericht)

**FAQ 2:**
- **Question:** "Können Sie bestehende CMS-Systeme migrieren?"
- **Answer:**
  ```
  "Ja. Wir migrieren Content aus GSB, WordPress, TYPO3 oder Drupal und übernehmen strukturierte Inhalte, Medien und Formulare in moderne Headless-Architekturen."
  ```
- **AI Snippet:** CMS-Namen (GSB, WordPress, TYPO3, Drupal)

**FAQ 3:**
- **Question:** "Wie integrieren Sie Fachverfahren?"
- **Answer:**
  ```
  "Entweder per Deeplink (z. B. OZG-Leistungen) oder REST-API für bidirektionale Datenübergabe (Anträge, Status-Updates, Archivierung nach GoBD)."
  ```
- **AI Snippet:** Technische Begriffe (Deeplink, REST-API, OZG, GoBD)

---

### Section 9: Glossary

**4 verlinkte Begriffe (höchste Dichte regulatorischer Begriffe):**

| Badge-Text | Link | Term-ID |
|------------|------|---------|
| "BFSG 2025" | `/glossar/bfsg-2025` | `bfsg-2025` |
| "WCAG 2.2" | `/glossar/wcag-22` | `wcag-22` |
| "RUM" | `/glossar/rum` | `rum` |
| "GitOps" | `/glossar/gitops` | `gitops` |

---

### Section 10: CTA (Final Call-to-Action)

**Headline:**
```
"Bürgerdienste barrierefrei digitalisieren?"
```

**Subline:**
```
"Wir zeigen Ihnen in 30 Minuten, wie Sie Top-Tasks, Formulare und Servicecockpit für Ihre Verwaltung BFSG-konform umsetzen."
```

**CTA Buttons:**
- Primary: "Termin buchen" → `/kontakt`
- Secondary: "Mehr Branchen entdecken" → scroll to More Branches

---

### Section 11: More Branches

**6 Sibling-Karten:**
- Kanzleien
- Steuerberater
- Schulen & Bildung
- Notare
- Versicherungen
- Medizin

(Automatisch generiert aus allen anderen Branchen außer der aktuellen)

---

## 🎨 Design-System-Details

**Farben (Verwaltungs-spezifisch):**
- Keine branchen-spezifischen Farben (nutzt globale Design-Tokens wie Kanzleien)
- Primary Accent: `--accent-primary` (#3b82f6)
- Dark Tone: `--bg-dark` (#0f172a)
- Light Tone: `--bg-light` (#f8fafc)
- Alert/Warning: `--color-warning` (#f59e0b) – für Pain 1 Icon

**Typografie:**
- Headline H1: `font-family: 'Plus Jakarta Sans', font-weight: 700, font-size: 36px → 72px`
- Badge: `font-family: 'Space Mono', font-size: 14px, text-transform: uppercase, letter-spacing: 0.1em`
- KPI Value: `font-family: 'Space Mono', font-size: 48px, font-weight: 700`

**Icons (Lucide):**
- Hero: `Building2` (Government Building)
- Tasks: `FileText`, `Calendar`, `Lock`
- Pains: `AlertTriangle`, `XCircle`, `BarChart`
- Solutions: `Check`, `GitBranch`, `BarChart3`

---

## 📱 Responsive Breakpoints

**Siehe `kanzleien.md` für vollständige Breakpoint-Tabelle.**

**Verwaltungs-spezifische Anpassungen:**
- StepFlow: `xl:grid-cols-4` (4 Steps → 4 Spalten, breiteste Grid)
- Servicecockpit Section: Desktop-optimiert (große Dashboards)
- Mobile: Vertikales Stacking für alle Sections

---

## 🧩 Komponenten-Bibliothek

**Verwendete Astro-Components:**

1. `<LayoutBranch>` – Wrapper mit SEO + Schema.org
2. `<Navigation>` – Sticky Header
3. `<HeroBranch>` – Hero mit Badge + KPI + CTA
4. `<TaskArticle>` – Top Tasks Grid
5. `<StepFlow>` – **4-Phasen-Flow** (conditional rendering bei `index === 0`)
6. `<PainCard>` – Pain-Grid
7. `<SolutionCard>` – Solutions mit **3× InfoTooltip** (höchste Dichte!)
8. `<WebAppCard>` – WebApps mit Tech-Stack
9. `<KPICard>` – KPI-Grid
10. `<FAQCard>` – FAQ-Accordion
11. `<GlossaryLinks>` – Badge-Grid (4 regulatorische Begriffe)
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

**InfoTooltip Conditional (3× auf dieser Seite):**
```astro
{solution.tooltipTerm && (
  <InfoTooltip termId={solution.tooltipTerm} mode="modal" />
)}
```

---

## 🔍 SEO & Strukturierte Daten

**Schema.org Markup:**

```json
{
  "@context": "https://schema.org",
  "@type": ["GovernmentOrganization", "Organization"],
  "name": "Wolf-Agents · Öffentliche Einrichtungen",
  "description": "Barrierefreie Top-Tasks, Formularstrecken und Servicecockpits für Verwaltungen, Kammern und Körperschaften.",
  "url": "https://wolf-agents.com/branchen/oeffentliche-einrichtungen",
  "audience": {
    "@type": "Audience",
    "audienceType": "Bürger:innen, Unternehmen, Sachbearbeitung, IT-Koordination Verwaltung"
  },
  "areaServed": {
    "@type": "Place",
    "name": "Deutschland, Österreich"
  },
  "knowsAbout": [
    "BFSG 2025 Compliance",
    "Barrierefreie Bürgerdienste",
    "OZG-konforme Portale",
    "Servicecockpit Public Sector"
  ]
}
```

**WICHTIG:** GeoCoverage ist **DE, AT** – **OHNE Schweiz** (im Gegensatz zu allen anderen Branchen!). Vermutlich wegen unterschiedlicher regulatorischer Anforderungen (BFSG/BITV ist DE/AT-spezifisch).

**Open Graph:**
- `og:title`: "Öffentliche Einrichtungen · Barrierefreie Bürgerdienste"
- `og:description`: "BFSG 2025 & WCAG 2.2 konform, Servicecockpit, ≥ 70 % Completion Rate"
- `og:type`: "website"
- `og:image`: `/og-images/oeffentliche-einrichtungen.png` (1200×630px)

---

## ♿ Barrierefreiheit (A11y)

**WCAG 2.2 AA Compliance (höchste Priorität für diese Branche!):**
- Kontrast Hero-Text (weiß auf dunkel): 15.6:1 ✅
- Kontrast Body-Text (dunkel auf hell): 12.8:1 ✅
- Kontrast Warning-Icon (orange auf weiß): 4.9:1 ✅ (Pain 1)
- Fokus-Indikatoren: 2px solid `--accent-primary`, min. 3:1 Kontrast
- Skip-Links: Vorhanden in Navigation

**Semantic HTML:**
- `<nav>`, `<main>`, `<section>`, `<article>`, `<footer>`
- Heading-Hierarchie: H1 → H2 → H3 (keine Sprünge)
- `<form>` mit `<fieldset>` + `<legend>`

**Interactive Elements:**
- Alle Buttons: Min. 44×44px Touch-Target
- InfoTooltips: `aria-describedby` für Screen-Reader
- StepFlow Steps: `role="list"` + `role="listitem"`
- FAQ Accordion: `aria-expanded`, `aria-controls`, `aria-labelledby`

**Keyboard Navigation:**
- Tab-Order: Logisch von oben nach unten
- Enter/Space: Aktiviert Buttons + Accordions
- Escape: Schließt Modals (InfoTooltip)

---

## 📝 Content-Strategie & Targeting

**Hauptthema:**
"Barrierefreie Bürgerdienste und Servicecockpits für öffentliche Verwaltungen"

**Primary Keywords:**
- BFSG 2025 Compliance
- Barrierefreie Bürgerdienste
- OZG-konforme Portale
- Servicecockpit Verwaltung
- Digitale Anträge Behörden

**Secondary Keywords:**
- WCAG 2.2 AA Umsetzung
- BITV-Test Verwaltung
- Formularstrecken barrierefrei
- GoBD-konforme Archivierung
- Digital Take-up Public Sector
- Fachverfahren-Integration
- CMS-Migration Verwaltung

**Zielgruppe:**
- Primär: Bürger:innen (Antragsteller:innen)
- Sekundär: Sachbearbeitung, IT-Koordination Verwaltung, Entscheider:innen (CIO, Digitalisierungsbeauftragte)

**User Intent:**
- 50 % Informational (Was bedeutet BFSG 2025? Wie funktioniert barrierefreies Formular?)
- 30 % Commercial Investigation (Welche Anbieter gibt es? Was kostet BFSG-Audit?)
- 20 % Transactional (Termin buchen, Prüfbericht anfragen)

**AIO/GEO/AEO-Optimierung:**
- ✅ **AIO:** FAQ mit AI-Snippet-Ready-Content (BFSG, WCAG 2.2, CMS-Namen, Fachverfahren-Begriffe)
- ✅ **GEO:** Lokale Geo-Coverage (DE, AT – ohne CH!) im Schema.org
- ✅ **AEO:** 4-Phasen-StepFlow strukturiert komplexe Governance-Fragen (End-to-End-Journey)

---

## 📊 Content-Audit-Notizen

### ✅ Stärken

1. **4-Phasen-StepFlow umfangreichster aller Branchen** – Bildet kompletten Governance-Zyklus ab (Einstieg → Antrag → Bearbeitung → Monitoring)
2. **BFSG 2025 & WCAG 2.2 prominent** – Trifft regulatorische Dringlichkeit (Deadline 2025)
3. **GOV.UK Benchmark als Referenz** – Erhöht Glaubwürdigkeit (internationale Best Practice)
4. **Servicecockpit als USP** – Differenziert von Standard-Formular-Lösungen
5. **3× InfoTooltip** – Höchste Tooltip-Dichte aller Branchen, erklärt komplexe Begriffe (BFSG, GitOps, RUM)
6. **GoBD & DSGVO in Step 3** – Zeigt Tiefgang in Governance-Anforderungen
7. **Konkrete KPIs** – "≥ 70 % Completion Rate" mit GOV.UK-Referenz
8. **Fachverfahren-Integration explizit** – Deeplink + REST-API erwähnt

### ⚠️ Schwächen & Legacy-Issues

1. **Keine visuellen Servicecockpit-Demos** – Dashboard-Screenshots fehlen (könnten KPI-Wert verdeutlichen)
2. **GeoCoverage ohne Schweiz** – Nicht erklärt, warum CH fehlt (regulatorische Unterschiede?)
3. **OZG nur erwähnt, nicht erklärt** – "Onlinezugangsgesetz" könnte als InfoTooltip ergänzt werden
4. **Keine Referenz-Verwaltungen genannt** – Pilotprojekt "Bürgerdienste DE/AT" bleibt abstrakt
5. **CMS-Migration nur FAQ** – Könnte als eigene Solution-Card hervorgehoben werden

### ❌ Fehlende Elemente

1. **Case Study/Referenz** – Pilotprojekt nur erwähnt, nicht verlinkt oder detailliert
2. **BFSG-Prüfbericht-Muster** – Könnte als Download (PDF) Vertrauen schaffen
3. **Verwaltungs-Logos** – Keine Stadtwappen/Behörden-Logos als Trust-Signal (datenschutzrechtlich schwierig?)
4. **Video-Demo** – Servicecockpit in Action (Live-Dashboard)
5. **Preisindikation** – "Ab X € für BFSG-Audit" oder "Individuell" fehlt
6. **OZG-Zertifikate** – Falls vorhanden, visuell einbinden

### 🔴 Content-Refresh-Priorität

**Priorität: KRITISCH** (Höchste Priorität + regulatorische Deadline BFSG 2025)

**Empfohlene Maßnahmen:**
1. **SOFORT:** BFSG-Prüfbericht-Muster als Download hinzufügen (vertrauensbildend)
2. **SOFORT:** Servicecockpit-Screenshots/Video in WebApp-Section integrieren
3. **Q1 2025:** Case Study mit Referenz-Verwaltung veröffentlichen (anonymisiert falls nötig)
4. **Q1 2025:** InfoTooltip für "OZG" ergänzen (häufig gegoogelter Begriff)
5. **Q2 2025:** CMS-Migration als eigene Solution-Card (aktuell nur FAQ)
6. **Langfristig:** GeoCoverage Schweiz prüfen (falls regulatorisch möglich)

---

## ⚡ Performance & Technische Details

**Core Web Vitals Targets:**
- LCP: < 2.5s (Hero-Bild optimiert, keine externe Dependencies)
- FID: < 100ms (minimales JavaScript, Astro SSR)
- CLS: < 0.1 (feste Dimensions für Images/Cards, reservierter Space für InfoTooltips)

**Lazy Loading:**
- Images: `loading="lazy"` ab Fold 2
- Servicecockpit-Dashboards: `<iframe loading="lazy">` falls eingebunden
- InfoTooltip-Content: Lazy-loaded per Modal-Click

**Barrierefreiheit-spezifische Performance:**
- Screen-Reader-Test: NVDA + JAWS kompatibel
- Tastaturbedienung: Alle Flows ohne Maus bedienbar
- Reduced Motion: `prefers-reduced-motion` berücksichtigt (keine Auto-Animations)

---

## 📈 Content-Metriken

| Metrik | Wert |
|--------|------|
| **Text-Volumen** | ~9.400 Zeichen, ~1.320 Wörter |
| **Link-Density** | ~44 interne Links, 0 externe Links |
| **Content-Verteilung** | 5 Dark Sections, 6 Light Sections |
| **Interactive Elements** | 3 Top Tasks, 4 StepFlow Steps, 3 FAQ Accordions, 3 InfoTooltips, 6 More Branches |
| **Glossary Coverage** | 4 Begriffe (BFSG, WCAG 2.2, RUM, GitOps) – höchste regulatorische Dichte |
| **InfoTooltip Density** | 3× (höchste Dichte aller Branchen-Seiten) |

---

## 🏁 Fazit

Die Öffentliche-Einrichtungen-Seite ist die **regulatorisch anspruchsvollste** aller Branchen-Seiten mit:
- **4-Phasen-StepFlow** (umfangreichster Flow, bildet kompletten Governance-Zyklus ab)
- **BFSG 2025 & WCAG 2.2** als zentrale Compliance-Themen (Deadline-Druck!)
- **Servicecockpit als USP** (differenziert von Standard-Formular-Lösungen)
- **3× InfoTooltip** (höchste Tooltip-Dichte, erklärt komplexe Begriffe)
- **GOV.UK Benchmark** (internationale Best Practice als Vertrauens-Anker)

**Stärken:** Tiefgang in Governance-Anforderungen (GoBD, DSGVO, Vier-Augen-Prinzip), konkrete KPIs, Fachverfahren-Integration.
**Verbesserungspotenzial:** Servicecockpit-Demo, BFSG-Prüfbericht-Muster, Case Study mit Referenz-Verwaltung.

**WICHTIG:** GeoCoverage ist **DE, AT** (ohne CH!) – vermutlich wegen unterschiedlicher regulatorischer Anforderungen.

**Für vollständige Layout-Details (Spacing, Typografie, Color-Tokens, Responsive-Grid) siehe `kanzleien.md`.**
