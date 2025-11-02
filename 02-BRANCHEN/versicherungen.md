# 🛡️ Versicherungen – Branchen-Detailseite

**URL:** `/branchen/versicherungen`
**Template:** `/src/pages/branchen/[slug].astro` (Dynamic Route)
**Content-Quelle:** `/src/content/branchen/versicherungen.json`
**Wichtigkeit:** 🔴 Höchste Priorität (Featured auf Startseite)
**Letztes Update:** 2025-10-30

---

## 📊 Meta-Informationen

| Element | Wert |
|---------|------|
| **Title Tag** | "Versicherungen · Lead-Funnels & Beratungsstrecken · Wolf-Agents" |
| **Meta Description** | "Bedarfsermittlungen, Tarifvergleiche und Nachfass-Automationen für Versicherungen. IDD-konform, CRM-integriert, +22% Conversion." |
| **Canonical** | `https://wolf-agents.com/branchen/versicherungen` |
| **Robots** | `index, follow` |
| **Locale** | `de_DE` |

**Geschätzte Metriken:**
- Zeichen (ohne Leerzeichen): ~8.100
- Wörter: ~1.140
- Lesezeit: ~4,5 min
- Sections: 11 (Hero → CTA → More Branches)
- Headings: H1(1) + H2(11) + H3(15)

---

## 🔗 Verlinkungsstruktur

### Internal Links Outgoing (Gesamt: ~42)

| Ziel | Anzahl | Context |
|------|--------|---------|
| `/kontakt` | 3× | CTA-Buttons in Hero, Path, Final CTA |
| `/glossar/aeo` | 1× | Glossary Link |
| `/glossar/consent-mode-v2` | 1× | Glossary Link |
| `/glossar/automation` | 2× | Solution-3 Tooltip, Glossary Link |
| `/glossar/rum` | 1× | Glossary Link |
| `/branchen/kanzleien` | 1× | More Branches Card |
| `/branchen/steuerberater` | 1× | More Branches Card |
| `/branchen/schulen-bildung` | 1× | More Branches Card |
| `/branchen/oeffentliche-einrichtungen` | 1× | More Branches Card |
| `/branchen/notare` | 1× | More Branches Card |
| `/branchen/medizin` | 1× | More Branches Card |
| Top Tasks (3×) | 3× | Anchor-Links: #bedarfscheck, #tarifvergleich, #beratung |

### External Links
- Keine direkten externen Links im Content
- CRM-Systeme erwähnt (HubSpot, Salesforce, Weclapp) ohne direkte Verlinkung
- IDD-Compliance erwähnt ohne direkte Verlinkung

---

## 🏗️ Layout & Semantische Struktur

**WICHTIG:** Diese Seite nutzt die **identische Struktur** wie `/branchen/kanzleien` (siehe `kanzleien.md` für vollständige Layout-Details mit allen 11 Sections, Spacing, Typografie, Farben).

Die folgende Dokumentation fokussiert auf **branchenspezifische Content-Unterschiede**.

---

## 🎯 KEY CONTENT-UNTERSCHIEDE ZU KANZLEIEN

### Section 1: Hero

**Eyebrow Badge:**
```
"Segment · Versicherung"
```

**H1 Headline:**
```
"Lead-Funnels & Beratungsstrecken für Versicherungen"
```

**Subtitle/Deck:**
```
"Wir bauen Bedarfsermittlungen, Tarifvergleiche und Nachfass-Automationen, die Verträge schneller abschließen lassen."
```

**KPI Badge:**
- Text: "Angebots-Conversion: +22 %"
- Source: "Lead Funnel Benchmark 2024"
- Link: Keine (kein Glossary-Link für diese Metrik)
- Icon: `TrendingUp` (Steigerung der Conversion)

**CTA Buttons:**
- Primary: "Termin buchen" → `/kontakt`
- Secondary: "Mehr erfahren" → `#bedarfscheck` (scroll-to anchor)

---

### Section 2: Top Tasks

**3 Tasks mit Versicherungs-Fokus:**

**Task 1: Bedarfscheck durchführen**
- **Zielgruppe:** Interessent:innen
- **Icon:** `ClipboardCheck`
- **Link:** `#bedarfscheck`
- **Description:**
  ```
  "Geführter Fragebogen zur Risikoanalyse und Produktvorschlag."
  ```

**Task 2: Tarif vergleichen**
- **Zielgruppe:** KMU & Privat
- **Icon:** `BarChart2`
- **Link:** `#tarifvergleich`
- **Description:**
  ```
  "Vergleichstabellen mit Highlights, Ratings und Response-Promise."
  ```

**Task 3: Beratung buchen**
- **Zielgruppe:** Interessent:innen
- **Icon:** `Calendar`
- **Link:** `#beratung`
- **Description:**
  ```
  "Termin- und Rückrufstrecke mit Lead-Scoring und Dokumenten-Upload."
  ```

---

### Section 3: Path – KEIN StepFlow ⚠️

**WICHTIG:** Diese Seite hat **KEINEN StepFlow** (wie Steuerberater und Notare).

Im Template-Code (`[slug].astro` lines 143-170) wird StepFlow nur gerendert wenn:
```astro
{stepFlow && index === 0 && (
  <StepFlow ... />
)}
```

Da `stepFlow: null` in `versicherungen.json`, wird dieser Abschnitt **nicht angezeigt**.

**Stattdessen:** Section 3 (Path) zeigt nur Standard-Content ohne visuellen Journey-Flow.

**CTA in Path-Section:**
- Text: "Lead-Funnel testen"
- Link: `/kontakt`

---

### Section 4: Pains

**3 Challenges mit Versicherungs-Fokus:**

**Pain 1: Leads gehen im Prozess verloren**
- **Icon:** `UserX`
- **Title:** "Leads gehen im Prozess verloren"
- **Description:**
  ```
  "Kontaktformulare ohne Vorqualifizierung erzeugen zu viele ungeeignete Leads und Nachfass-Aufwand."
  ```

**Pain 2: Tarifvergleiche sind statisch und unübersichtlich**
- **Icon:** `Table`
- **Title:** "Tarifvergleiche sind statisch und unübersichtlich"
- **Description:**
  ```
  "User verstehen Unterschiede nicht oder brechen ab, bevor sie ein Angebot anfragen."
  ```

**Pain 3: Nachfass-Strecken fehlen**
- **Icon:** `Mail`
- **Title:** "Nachfass-Strecken fehlen"
- **Description:**
  ```
  "CRM und Website sprechen nicht miteinander, wichtige Follow-ups werden verpasst."
  ```

---

### Section 5: Solutions

**3 Lösungen (1× InfoTooltip!):**

**Solution 1: Bedarfsanalyse mit Lead-Scoring**
- **Icon:** `Target`
- **Title:** "Bedarfsanalyse mit Lead-Scoring"
- **Deck:** "Fragebogen identifiziert Risiken und priorisiert Leads im CRM."
- **Summary:**
  ```
  "Fragebogen identifiziert Risiken, generiert passgenaue Angebote und priorisiert Leads im CRM."
  ```
- **Proof:** "Qualifizierungszeit −30 %"
- **InfoTooltip:** Keine

**Solution 2: Tarifvergleich als Interactive Table**
- **Icon:** `LayoutGrid`
- **Title:** "Tarifvergleich als Interactive Table"
- **Deck:** "Filtern, Szenario-Rechner und Highlight Cards machen Mehrwert sofort sichtbar."
- **Summary:**
  ```
  "Filtern, Szenario-Rechner und Highlight Cards machen den Mehrwert sofort sichtbar."
  ```
- **Proof:** "Time on Comparison +45 %"
- **InfoTooltip:** Keine

**Solution 3: Nachfass-Automationen**
- **Icon:** `Zap`
- **Title:** "Nachfass-Automationen"
- **Deck:** "E-Mail/SMS-Sequences führen zum Abschluss ohne manuellen Aufwand."
- **Summary:**
  ```
  "Sequences via E-Mail/SMS erinnern an offene Schritte, liefern Zusatzinfos und führen zum Abschluss."
  ```
- **Proof:** "Nachfassquote +28 %"
- **InfoTooltip:** `tooltipTerm: "automation"` (Modal)

**HINWEIS:** Nur Solution 3 hat ein InfoTooltip (erklärt "Automation" als Glossary-Begriff).

---

### Section 6: WebApps & Automations

**3 WebApps mit Tech-Stack:**

**WebApp 1: Lead Funnel**
- **Title:** "Lead Funnel"
- **Description:**
  ```
  "Bedarfsanalyse, Dokumenten-Upload und CRM-Sync in einer Strecke."
  ```
- **Outcome:** "Mehr qualifizierte Leads und schnellerer Abschluss."
- **Tech Stack:**
  - Astro SSR
  - HubSpot API (CRM-Integration)
  - Cloudflare Workers (Lead-Scoring-Logic)
- **Features:** 4 items (Bedarfsanalyse, Upload, Scoring, CRM-Sync)

**WebApp 2: Tarifvergleich**
- **Title:** "Tarifvergleich"
- **Description:**
  ```
  "Vergleichstabellen mit Live-Filter, Ratings und Savings-Rechner."
  ```
- **Outcome:** "Verständliche Angebotskommunikation."
- **Tech Stack:**
  - Astro SSR
  - React Island (interaktive Tabellen-Komponente)
  - Cloudflare D1 (Tarif-Datenbank)
- **Features:** 4 items (Filter, Ratings, Savings-Rechner, Highlight Cards)

**WebApp 3: Nachfass-Automation**
- **Title:** "Nachfass-Automation"
- **Description:**
  ```
  "E-Mail/SMS-Flow mit personalisierten Nudges und Angebotslinks."
  ```
- **Outcome:** "Erhöhte Abschlussrate ohne manuellen Aufwand."
- **Tech Stack:**
  - Resend (E-Mail-Automation)
  - Twilio (SMS-Automation)
  - Cloudflare Workers KV (Sequence-Tracking)
- **Features:** 4 items (E-Mail/SMS-Sequences, Personalisierung, Angebotslinks, Tracking)

---

### Section 7: KPI & Proof

**3 Metriken:**

**KPI 1:**
- **Label:** "Angebots-Conversion"
- **Value:** "+22 %"
- **Context:** "Lead Funnel Benchmark 2024 · mehr Abschlüsse pro Lead"
- **Icon:** `TrendingUp`

**KPI 2:**
- **Label:** "Follow-up Rate"
- **Value:** "+28 %"
- **Context:** "Automatisierte Nachfass-Strecken erhöhen Kontakt-Quote"
- **Icon:** `Mail`

**KPI 3:**
- **Label:** "Qualifizierungszeit"
- **Value:** "−30 %"
- **Context:** "Lead-Scoring beschleunigt Vertriebsarbeit"
- **Icon:** `Clock`

**Source:** "Lead Funnel Benchmark 2024 · Versicherungsbranche DACH"

---

### Section 8: FAQ

**3 Items mit AI-Snippet-Hinweisen:**

**FAQ 1:**
- **Question:** "Welche CRM-Systeme integrieren Sie?"
- **Answer:**
  ```
  "Wir binden HubSpot, Salesforce, Weclapp oder Ihr Bestandssystem via API/Webhooks an und synchronisieren Scoring, Dokumente und Termine."
  ```
- **AI Snippet:** CRM-Namen (HubSpot, Salesforce, Weclapp, API/Webhooks)

**FAQ 2:**
- **Question:** "Wie stellen Sie Compliance (IDD, DSGVO) sicher?"
- **Answer:**
  ```
  "Wir dokumentieren Beratungsnachweise, Consent-Logs und nutzen EU-Hosting. Inhalte können IDD-konform versioniert werden."
  ```
- **AI Snippet:** Compliance-Keywords (IDD, DSGVO, Beratungsnachweise, Consent-Logs, EU-Hosting)

**FAQ 3:**
- **Question:** "Wie schnell lässt sich ein Funnel starten?"
- **Answer:**
  ```
  "MVP in 5 Wochen: 1 Woche Konzept, 2 Wochen Implementierung, 1 Woche QA, 1 Woche Launch & Training."
  ```
- **AI Snippet:** Timeline (5 Wochen MVP)

---

### Section 9: Glossary

**4 verlinkte Begriffe:**

| Badge-Text | Link | Term-ID |
|------------|------|---------|
| "AEO" | `/glossar/aeo` | `aeo` |
| "Consent Mode v2" | `/glossar/consent-mode-v2` | `consent-mode-v2` |
| "Automation" | `/glossar/automation` | `automation` |
| "RUM" | `/glossar/rum` | `rum` |

**HINWEIS:** "Automation" erscheint sowohl als InfoTooltip in Solution 3 als auch als Glossary-Link.

---

### Section 10: CTA (Final Call-to-Action)

**Headline:**
```
"Lead-Funnel optimieren?"
```

**Subline:**
```
"Wir zeigen Ihnen in 30 Minuten, wie Sie Bedarfsanalyse, Tarifvergleich und Nachfass-Automation für Ihre Versicherung umsetzen."
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
- Öffentliche Einrichtungen
- Notare
- Medizin

(Automatisch generiert aus allen anderen Branchen außer der aktuellen)

---

## 🎨 Design-System-Details

**Farben (Versicherungs-spezifisch):**
- Keine branchen-spezifischen Farben (nutzt globale Design-Tokens wie Kanzleien)
- Primary Accent: `--accent-primary` (#3b82f6)
- Dark Tone: `--bg-dark` (#0f172a)
- Light Tone: `--bg-light` (#f8fafc)

**Typografie:**
- Headline H1: `font-family: 'Plus Jakarta Sans', font-weight: 700, font-size: 36px → 72px`
- Badge: `font-family: 'Space Mono', font-size: 14px, text-transform: uppercase, letter-spacing: 0.1em`

**Icons (Lucide):**
- Hero: `Shield` (Insurance/Protection symbol)
- Tasks: `ClipboardCheck`, `BarChart2`, `Calendar`
- Pains: `UserX`, `Table`, `Mail`
- Solutions: `Target`, `LayoutGrid`, `Zap`

---

## 📱 Responsive Breakpoints

**Siehe `kanzleien.md` für vollständige Breakpoint-Tabelle.**

**Versicherungs-spezifische Anpassungen:**
- Kein StepFlow-Grid (da StepFlow fehlt)
- Tarifvergleich: Horizontales Scrolling auf Mobile (Tables)
- Mobile: Vertikales Stacking für alle Sections

---

## 🧩 Komponenten-Bibliothek

**Verwendete Astro-Components:**

1. `<LayoutBranch>` – Wrapper mit SEO + Schema.org
2. `<Navigation>` – Sticky Header
3. `<HeroBranch>` – Hero mit Badge + KPI + CTA
4. `<TaskArticle>` – Top Tasks Grid
5. ~~`<StepFlow>`~~ – **NICHT vorhanden** (stepFlow === null)
6. `<PainCard>` – Pain-Grid
7. `<SolutionCard>` – Solutions mit 1× InfoTooltip (Solution 3)
8. `<WebAppCard>` – WebApps mit Tech-Stack
9. `<KPICard>` – KPI-Grid
10. `<FAQCard>` – FAQ-Accordion
11. `<GlossaryLinks>` – Badge-Grid (4 Links)
12. `<CTASection>` – Final CTA
13. `<BranchCard>` – More Branches Grid
14. `<Footer>` – Global Footer

**Data Loading:**
```astro
const { slug } = Astro.params;
const branchData = await getEntry('branchen', slug);
const { stepFlow } = branchData.data; // stepFlow = null für Versicherungen
```

**Conditional Rendering:**
```astro
{stepFlow && index === 0 && (
  <StepFlow ... />
)}
// Wird NICHT gerendert, da stepFlow === null

{solution.tooltipTerm && (
  <InfoTooltip termId={solution.tooltipTerm} mode="modal" />
)}
// Nur für Solution 3 ("automation")
```

---

## 🔍 SEO & Strukturierte Daten

**Schema.org Markup:**

```json
{
  "@context": "https://schema.org",
  "@type": ["InsuranceAgency", "FinancialService", "Organization"],
  "name": "Wolf-Agents · Versicherungen",
  "description": "Bedarfsermittlungen, Tarifvergleiche und Nachfass-Automationen für Versicherungen und Makler.",
  "url": "https://wolf-agents.com/branchen/versicherungen",
  "audience": {
    "@type": "Audience",
    "audienceType": "KMU, Privatkunden, Makler, Versicherungsvertriebe"
  },
  "areaServed": {
    "@type": "Place",
    "name": "Deutschland, Österreich, Schweiz"
  },
  "knowsAbout": [
    "Lead-Funnels Versicherung",
    "Tarifvergleich digital",
    "IDD-konforme Beratungsstrecken",
    "Nachfass-Automation"
  ]
}
```

**Open Graph:**
- `og:title`: "Versicherungen · Lead-Funnels & Beratungsstrecken"
- `og:description`: "Bedarfsanalyse, Tarifvergleich, Nachfass-Automation – IDD-konform, +22% Conversion"
- `og:type`: "website"
- `og:image`: `/og-images/versicherungen.png` (1200×630px)

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
- `<table>` für Tarifvergleich mit `<thead>`, `<tbody>`, `scope="col/row"`

**Interactive Elements:**
- Alle Buttons: `aria-label` bei Icon-only
- Tarifvergleich-Filter: `aria-controls` für Live-Region
- FAQ Accordion: `aria-expanded`, `aria-controls`
- InfoTooltip: `aria-describedby` für "Automation"

---

## 📝 Content-Strategie & Targeting

**Hauptthema:**
"Lead-Funnels und Beratungsstrecken für Versicherungen und Makler"

**Primary Keywords:**
- Lead-Funnel Versicherung
- Tarifvergleich digital
- Nachfass-Automation Versicherung
- IDD-konforme Beratung
- Lead-Scoring Versicherung

**Secondary Keywords:**
- CRM-Integration HubSpot Salesforce
- Bedarfsanalyse Versicherung
- Interactive Tariff Comparison
- Follow-up Automation
- Insurance Lead Qualification

**Zielgruppe:**
- Primär: Interessent:innen (KMU, Privatkunden)
- Sekundär: Versicherungen, Makler, Vertriebsleiter, Marketing-Verantwortliche

**User Intent:**
- 40 % Informational (Wie funktioniert Lead-Funnel? Was ist Lead-Scoring?)
- 30 % Commercial Investigation (Welche Anbieter? Was kostet CRM-Integration?)
- 30 % Transactional (Demo anfragen, Termin buchen)

**AIO/GEO/AEO-Optimierung:**
- ✅ **AIO:** FAQ mit AI-Snippet-Ready-Content (CRM-Namen, IDD/DSGVO-Keywords, Timeline)
- ✅ **GEO:** Lokale Geo-Coverage (DE, AT, CH) im Schema.org
- ⚠️ **AEO:** Fehlender StepFlow schwächt strukturierte Prozess-Darstellung (siehe Content-Audit)

---

## 📊 Content-Audit-Notizen

### ✅ Stärken

1. **Conversion-Fokus prominent** – +22% Angebots-Conversion als KPI Badge im Hero
2. **CRM-Integration explizit** – HubSpot, Salesforce, Weclapp genannt
3. **IDD-Compliance hervorgehoben** – regulatorische Anforderung für Versicherungsberatung
4. **Interactive Table erwähnt** – differenziert von statischen PDF-Vergleichen
5. **Nachfass-Automation als Solution** – trifft Pain Point "Follow-ups werden verpasst"
6. **Konkrete KPIs** – +22% Conversion, +28% Follow-up Rate, −30% Qualifizierungszeit
7. **InfoTooltip für "Automation"** – erklärt technischen Begriff

### ⚠️ Schwächen & Legacy-Issues

1. **Fehlender StepFlow** – Schwächt User-Engagement im Vergleich zu Branchen mit Flow
2. **Tarifvergleich nicht visualisiert** – Keine Screenshots/Mockups der Interactive Table
3. **Lead-Scoring nicht detailliert** – Welche Kriterien? Wie wird Score berechnet?
4. **Nur 1× InfoTooltip** – Begriffe wie "IDD", "Lead-Scoring" könnten erklärt werden

### ❌ Fehlende Elemente

1. **StepFlow "Versicherungsabschluss in 3 Schritten"** – Könnte Prozess visualisieren:
   - Schritt 1: Bedarfsanalyse & Risikoprofil
   - Schritt 2: Tarifvergleich & Angebotserstellung
   - Schritt 3: Beratungstermin & Vertragsabschluss
2. **Tarifvergleich-Screenshots** – Interactive Table als visuelle Demo
3. **Case Study/Testimonial** – Kein Versicherungsunternehmen als Referenz
4. **Preisindikation** – "Ab X € pro Monat" oder "Individuell" fehlt
5. **InfoTooltips für IDD, Lead-Scoring** – falls Glossar erweitert wird

### 🔴 Content-Refresh-Priorität

**Priorität: HOCH** (Featured auf Startseite + conversion-kritische Branche)

**Empfohlene Maßnahmen:**
1. **SOFORT:** StepFlow "Versicherungsabschluss in 3 Schritten" hinzufügen (erhöht User-Engagement)
2. **Q1 2025:** Tarifvergleich-Screenshots in WebApp-Section integrieren (zeigt Interactive Table)
3. **Q1 2025:** Lead-Scoring-Kriterien detaillieren (z.B. Budget, Timing, Use-Case)
4. **Q2 2025:** Case Study mit Versicherungsunternehmen/Makler veröffentlichen
5. **Q2 2025:** InfoTooltips für "IDD", "Lead-Scoring" ergänzen (falls Glossar erweitert wird)
6. **Langfristig:** Video-Demo der Nachfass-Automation (E-Mail/SMS-Sequences in Action)

---

## ⚡ Performance & Technische Details

**Core Web Vitals Targets:**
- LCP: < 2.5s (Hero-Bild optimiert)
- FID: < 100ms (minimales JavaScript, React Island lazy-loaded)
- CLS: < 0.1 (feste Dimensions für Images/Cards/Tables)

**Lazy Loading:**
- Images: `loading="lazy"` ab Fold 2
- React Island (Tarifvergleich): Hydration on visible
- CRM-Sync: Asynchron im Background

**Interactive Features:**
- Tarifvergleich: Client-side Filtering (React Island)
- Lead-Scoring: Server-side Calculation (Workers)
- Nachfass-Automation: Event-driven (Workers + KV)

---

## 📈 Content-Metriken

| Metrik | Wert |
|--------|------|
| **Text-Volumen** | ~8.100 Zeichen, ~1.140 Wörter |
| **Link-Density** | ~42 interne Links, 0 externe Links |
| **Content-Verteilung** | 5 Dark Sections, 6 Light Sections |
| **Interactive Elements** | 3 Top Tasks, 0 StepFlow Steps, 3 FAQ Accordions, 6 More Branches |
| **Glossary Coverage** | 4 Begriffe (AEO, Consent Mode v2, Automation, RUM) |
| **InfoTooltip Density** | 1× (Solution 3: Automation) |

---

## 🏁 Fazit

Die Versicherungen-Seite fokussiert auf **Lead-Funnel-Optimierung** mit starkem Fokus auf **Conversion** (+22%), **CRM-Integration** (HubSpot, Salesforce, Weclapp) und **Nachfass-Automation** (+28% Follow-up Rate).

**Stärken:** IDD-Compliance, konkrete KPIs, Interactive Tariff Comparison, Automation-Fokus.
**Verbesserungspotenzial:** StepFlow fehlt (schwächt User-Engagement), Tarifvergleich nicht visualisiert, Lead-Scoring nicht detailliert.

**Für vollständige Layout-Details (Spacing, Typografie, Color-Tokens, Responsive-Grid) siehe `kanzleien.md`.**
