# 🏥 Medizin – Branchen-Detailseite

**URL:** `/branchen/medizin`
**Template:** `/src/pages/branchen/[slug].astro` (Dynamic Route)
**Content-Quelle:** `/src/content/branchen/medizin.json`
**Wichtigkeit:** 🔴 Höchste Priorität (Featured auf Startseite)
**Letztes Update:** 2025-10-30

---

## 📊 Meta-Informationen

| Element | Wert |
|---------|------|
| **Title Tag** | "Medizin · Barrierefreie Praxiswebsites & digitale Anamnese · Wolf-Agents" |
| **Meta Description** | "BFSG- und DSGVO-konforme Patient:innenreisen für Praxen und MVZ. Terminbuchung, digitale Anamnese, Befunde – barrierefrei." |
| **Canonical** | `https://wolf-agents.com/branchen/medizin` |
| **Robots** | `index, follow` |
| **Locale** | `de_DE` |

**Geschätzte Metriken:**
- Zeichen (ohne Leerzeichen): ~8.500
- Wörter: ~1.190
- Lesezeit: ~5 min
- Sections: 11 (Hero → CTA → More Branches)
- Headings: H1(1) + H2(11) + H3(15)

---

## 🔗 Verlinkungsstruktur

### Internal Links Outgoing (Gesamt: ~44)

| Ziel | Anzahl | Context |
|------|--------|---------|
| `/kontakt` | 3× | CTA-Buttons in Hero, Path, Final CTA |
| `/glossar/bfsg-2025` | 3× | Hero Badge (implizit), Solution-1 Tooltip, Glossary Link |
| `/glossar/wcag-22` | 1× | Glossary Link |
| `/glossar/consent-mode-v2` | 2× | Solution-3 Tooltip, Glossary Link |
| `/glossar/rum` | 2× | Solution-2 Tooltip, Glossary Link |
| `/branchen/kanzleien` | 1× | More Branches Card |
| `/branchen/steuerberater` | 1× | More Branches Card |
| `/branchen/schulen-bildung` | 1× | More Branches Card |
| `/branchen/oeffentliche-einrichtungen` | 1× | More Branches Card |
| `/branchen/notare` | 1× | More Branches Card |
| `/branchen/versicherungen` | 1× | More Branches Card |
| Top Tasks (3×) | 3× | Anchor-Links: #termin, #anamnese, #patientenservice |

### External Links
- Keine direkten externen Links im Content
- Praxissoftware erwähnt (medatixx, Doctolib, Samedi) ohne direkte Verlinkung
- Standards erwähnt (BFSG, WCAG 2.2, DSGVO) ohne direkte Verlinkung

---

## 🏗️ Layout & Semantische Struktur

**WICHTIG:** Diese Seite nutzt die **identische Struktur** wie `/branchen/kanzleien` (siehe `kanzleien.md` für vollständige Layout-Details mit allen 11 Sections, Spacing, Typografie, Farben).

Die folgende Dokumentation fokussiert auf **branchenspezifische Content-Unterschiede** mit **Schwerpunkt auf Barrierefreiheit** (BFSG 2025, WCAG 2.2).

---

## 🎯 KEY CONTENT-UNTERSCHIEDE ZU KANZLEIEN

### Section 1: Hero

**Eyebrow Badge:**
```
"Segment · Gesundheit"
```

**H1 Headline:**
```
"Barrierefreie Praxiswebsites & digitale Anamnese"
```

**Subtitle/Deck:**
```
"Wir entwickeln BFSG- und DSGVO-konforme Patient:innenreisen – von Anamnese über Terminbuchung bis Befundbereitstellung."
```

**KPI Badge:**
- Text: "Ersttermin-Buchungen: +28 %"
- Source: "Praxiswachstum Benchmark 2024"
- Link: Keine (kein direkter Glossary-Link, aber BFSG-Compliance impliziert)
- Icon: `TrendingUp` (Steigerung der Buchungen)

**CTA Buttons:**
- Primary: "Termin buchen" → `/kontakt`
- Secondary: "Mehr erfahren" → `#termin` (scroll-to anchor)

---

### Section 2: Top Tasks

**3 Tasks mit Medizin-Fokus:**

**Task 1: Termin buchen**
- **Zielgruppe:** Patient:innen
- **Icon:** `Calendar`
- **Link:** `#termin`
- **Description:**
  ```
  "Mehrstufiges Formular mit Verfügbarkeiten, Priorität und Versicherung."
  ```

**Task 2: Anamnese ausfüllen**
- **Zielgruppe:** Patient:innen
- **Icon:** `FileText`
- **Link:** `#anamnese`
- **Description:**
  ```
  "Digitale Voranamnese mit Device Sync, BFSG 2025 konform."
  ```

**Task 3: Befunde & FAQs abrufen**
- **Zielgruppe:** Bestandspatient:innen
- **Icon:** `Search`
- **Link:** `#patientenservice`
- **Description:**
  ```
  "Zugriff auf Dokumente, Teamprofile und barrierefreie Inhalte."
  ```

---

### Section 3: Path – KEIN StepFlow ⚠️

**WICHTIG:** Diese Seite hat **KEINEN StepFlow** (wie Steuerberater, Notare, Versicherungen).

Im Template-Code (`[slug].astro` lines 143-170) wird StepFlow nur gerendert wenn:
```astro
{stepFlow && index === 0 && (
  <StepFlow ... />
)}
```

Da `stepFlow: null` in `medizin.json`, wird dieser Abschnitt **nicht angezeigt**.

**Stattdessen:** Section 3 (Path) zeigt nur Standard-Content ohne visuellen Journey-Flow.

**CTA in Path-Section:**
- Text: "Praxis-Relaunch starten"
- Link: `/kontakt`

---

### Section 4: Pains

**3 Challenges mit Medizin-Fokus:**

**Pain 1: Patient:innen erwarten barrierefreie, mobile Angebote**
- **Icon:** `Smartphone`
- **Title:** "Patient:innen erwarten barrierefreie, mobile Angebote"
- **Description:**
  ```
  "Viele Praxiswebsites erfüllen weder WCAG 2.2 noch BFSG 2025 – Formulare brechen ab, Informationen sind schwer auffindbar."
  ```

**Pain 2: Anamnese & Terminmanagement kosten Zeit**
- **Icon:** `Clock`
- **Title:** "Anamnese & Terminmanagement kosten Zeit"
- **Description:**
  ```
  "Teams müssen Daten nachtragen und Telefonate führen, bevor Patient:innen erscheinen."
  ```

**Pain 3: Bewertungen & Vertrauen fehlen**
- **Icon:** `Star`
- **Title:** "Bewertungen & Vertrauen fehlen"
- **Description:**
  ```
  "Fachliche Kompetenz und Versorgungsqualität werden online kaum sichtbar."
  ```

---

### Section 5: Solutions

**3 Lösungen (3× InfoTooltip – höchste Dichte in Batch 2!):**

**Solution 1: BFSG 2025 Ready Frontend**
- **Icon:** `Check`
- **Title:** "BFSG 2025 Ready Frontend"
- **Deck:** "WCAG 2.2 AA geprüft mit Fokusmanagement, Kontrasten und Screenreader-Optimierung."
- **Summary:**
  ```
  "WCAG 2.2 AA geprüft, Fokusmanagement, Kontraste, Screenreader-Optimierung und Mehrsprachigkeit."
  ```
- **Proof:** "BFSG Pre-Audit bestanden"
- **InfoTooltip:** `tooltipTerm: "bfsg-2025"` (Modal)

**Solution 2: Digitale Anamnese & Upload**
- **Icon:** `FileCheck`
- **Title:** "Digitale Anamnese & Upload"
- **Deck:** "Formulare mit dynamischen Fragen, Praxissoftware-Integration und sicheren Uploads."
- **Summary:**
  ```
  "Formulare mit dynamischen Fragen, integrationsfähig mit Praxissoftware und sicheren Uploads."
  ```
- **Proof:** "Check-In Dauer −35 %"
- **InfoTooltip:** `tooltipTerm: "rum"` (Modal)

**Solution 3: Patient Journey Dashboard**
- **Icon:** `BarChart3`
- **Title:** "Patient Journey Dashboard"
- **Deck:** "Consent Mode v2 + RUM zeigen, welche Seiten Anfragen und Bewertungen erzeugen."
- **Summary:**
  ```
  "Consent Mode v2 + RUM zeigen, welche Seiten Anfragen und Bewertungen erzeugen."
  ```
- **Proof:** "Bewertungsquote +18 %"
- **InfoTooltip:** `tooltipTerm: "consent-mode-v2"` (Modal)

**HINWEIS:** Alle 3 Solutions haben InfoTooltips – höchste Dichte in Batch 2 (wie Öffentliche Einrichtungen in Batch 1).

---

### Section 6: WebApps & Automations

**3 WebApps mit Tech-Stack:**

**WebApp 1: Terminbuchung & Warteliste**
- **Title:** "Terminbuchung & Warteliste"
- **Description:**
  ```
  "Verfügbarkeiten, Prioritäten, SMS-Erinnerungen und Ausfallmanagement."
  ```
- **Outcome:** "Weniger No-Shows, planbare Kapazitäten."
- **Tech Stack:**
  - Astro SSR
  - Calendly API (oder alternative Terminbuchung)
  - Twilio (SMS-Erinnerungen)
- **Features:** 4 items (Verfügbarkeiten, Prioritäten, SMS-Reminder, No-Show-Reduction)

**WebApp 2: Anamnese Wizard**
- **Title:** "Anamnese Wizard"
- **Description:**
  ```
  "Fragenlogik nach Fachbereich, Dropdowns und barrierefreie Eingaben."
  ```
- **Outcome:** "Strukturierte Daten vor dem Termin, schnellere Behandlung."
- **Tech Stack:**
  - Astro SSR
  - React Island (konditionale Fragenlogik)
  - Cloudflare Workers (Datenverarbeitung)
- **Features:** 4 items (Fachbereich-Logik, Dropdowns, Barrierefreiheit, Pre-Fill)

**WebApp 3: Patientenservice Hub**
- **Title:** "Patientenservice Hub"
- **Description:**
  ```
  "Dokumentenablage, FAQs, Bewertungen und Teamprofile."
  ```
- **Outcome:** "Mehr Vertrauen & geringere Telefonlast."
- **Tech Stack:**
  - Astro SSR
  - Sanity (Headless CMS für FAQs/Team)
  - Cloudflare Images (optimierte Teamfotos)
- **Features:** 4 items (Dokumente, FAQs, Bewertungen, Teamprofile)

---

### Section 7: KPI & Proof

**3 Metriken:**

**KPI 1:**
- **Label:** "Ersttermin-Buchungen"
- **Value:** "+28 %"
- **Context:** "Praxiswachstum Benchmark 2024 · barrierefreie Terminbuchung"
- **Icon:** `TrendingUp`

**KPI 2:**
- **Label:** "Check-In Dauer"
- **Value:** "−35 %"
- **Context:** "Digitale Anamnese beschleunigt Aufnahmeprozess"
- **Icon:** `Clock`

**KPI 3:**
- **Label:** "Bewertungsquote"
- **Value:** "+18 %"
- **Context:** "Patient Journey Dashboard zeigt Optimierungspotenzial"
- **Icon:** `Star`

**Source:** "Praxiswachstum Benchmark 2024 · Arztpraxen & MVZ DACH"

---

### Section 8: FAQ

**3 Items mit AI-Snippet-Hinweisen:**

**FAQ 1:**
- **Question:** "Erfüllt die Lösung BFSG 2025 & DSGVO?"
- **Answer:**
  ```
  "Ja. Wir arbeiten nach WCAG 2.2 AA, liefern Barrierefreiheits-Erklärungen und nutzen verschlüsselte Speicherorte in der EU. Alle Formulare und Uploads haben Consent-Logging."
  ```
- **AI Snippet:** Compliance-Keywords (WCAG 2.2 AA, BFSG 2025, DSGVO, EU-Hosting, Consent-Logging, Barrierefreiheits-Erklärung)

**FAQ 2:**
- **Question:** "Welche Praxissoftware integrieren Sie?"
- **Answer:**
  ```
  "Wir binden medatixx, Doctolib, Samedi oder Ihr bestehendes System via API, ICS oder CSV-Schnittstelle ein und halten die Daten synchron."
  ```
- **AI Snippet:** Praxissoftware-Namen (medatixx, Doctolib, Samedi, API, ICS, CSV)

**FAQ 3:**
- **Question:** "Wie schnell ist ein Praxis-Relaunch?"
- **Answer:**
  ```
  "Für Einzelpraxen rechnen wir mit 6 Wochen, für MVZ mit mehreren Standorten 8–10 Wochen inklusive Content- und Barrierefreiheits-Checks."
  ```
- **AI Snippet:** Timeline (6 Wochen Einzelpraxen, 8–10 Wochen MVZ)

---

### Section 9: Glossary

**4 verlinkte Begriffe (höchste Accessibility-Dichte):**

| Badge-Text | Link | Term-ID |
|------------|------|---------|
| "BFSG 2025" | `/glossar/bfsg-2025` | `bfsg-2025` |
| "WCAG 2.2" | `/glossar/wcag-22` | `wcag-22` |
| "Consent Mode v2" | `/glossar/consent-mode-v2` | `consent-mode-v2` |
| "RUM" | `/glossar/rum` | `rum` |

**HINWEIS:** Ähnlich wie Öffentliche Einrichtungen (Batch 1) fokussiert diese Seite stark auf Barrierefreiheit (BFSG, WCAG 2.2) – 2 von 4 Glossary-Links sind Accessibility-spezifisch.

---

### Section 10: CTA (Final Call-to-Action)

**Headline:**
```
"Praxiswebsite barrierefrei machen?"
```

**Subline:**
```
"Wir zeigen Ihnen in 30 Minuten, wie Sie Terminbuchung, Anamnese und Patientenservice BFSG-konform für Ihre Praxis umsetzen."
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
- Versicherungen

(Automatisch generiert aus allen anderen Branchen außer der aktuellen)

---

## 🎨 Design-System-Details

**Farben (Medizin-spezifisch):**
- Keine branchen-spezifischen Farben (nutzt globale Design-Tokens wie Kanzleien)
- Primary Accent: `--accent-primary` (#3b82f6)
- Dark Tone: `--bg-dark` (#0f172a)
- Light Tone: `--bg-light` (#f8fafc)

**Typografie:**
- Headline H1: `font-family: 'Plus Jakarta Sans', font-weight: 700, font-size: 36px → 72px`
- Badge: `font-family: 'Space Mono', font-size: 14px, text-transform: uppercase, letter-spacing: 0.1em`

**Icons (Lucide):**
- Hero: `HeartPulse` (Medical/Healthcare symbol)
- Tasks: `Calendar`, `FileText`, `Search`
- Pains: `Smartphone`, `Clock`, `Star`
- Solutions: `Check`, `FileCheck`, `BarChart3`

---

## 📱 Responsive Breakpoints

**Siehe `kanzleien.md` für vollständige Breakpoint-Tabelle.**

**Medizin-spezifische Anpassungen:**
- Kein StepFlow-Grid (da StepFlow fehlt)
- Mobile: Vertikales Stacking für alle Sections
- Touch-Targets: Min. 44×44px (wichtig für Barrierefreiheit)

---

## 🧩 Komponenten-Bibliothek

**Verwendete Astro-Components:**

1. `<LayoutBranch>` – Wrapper mit SEO + Schema.org
2. `<Navigation>` – Sticky Header
3. `<HeroBranch>` – Hero mit Badge + KPI + CTA
4. `<TaskArticle>` – Top Tasks Grid
5. ~~`<StepFlow>`~~ – **NICHT vorhanden** (stepFlow === null)
6. `<PainCard>` – Pain-Grid
7. `<SolutionCard>` – Solutions mit 3× InfoTooltip (höchste Dichte!)
8. `<WebAppCard>` – WebApps mit Tech-Stack
9. `<KPICard>` – KPI-Grid
10. `<FAQCard>` – FAQ-Accordion
11. `<GlossaryLinks>` – Badge-Grid (4 Links mit 2× Accessibility-Focus)
12. `<CTASection>` – Final CTA
13. `<BranchCard>` – More Branches Grid
14. `<Footer>` – Global Footer

**Data Loading:**
```astro
const { slug } = Astro.params;
const branchData = await getEntry('branchen', slug);
const { stepFlow } = branchData.data; // stepFlow = null für Medizin
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
// Für alle 3 Solutions (bfsg-2025, rum, consent-mode-v2)
```

---

## 🔍 SEO & Strukturierte Daten

**Schema.org Markup:**

```json
{
  "@context": "https://schema.org",
  "@type": ["MedicalBusiness", "ProfessionalService", "Organization"],
  "name": "Wolf-Agents · Medizin",
  "description": "BFSG- und DSGVO-konforme Patient:innenreisen für Arztpraxen und MVZ. Terminbuchung, digitale Anamnese, Befundbereitstellung.",
  "url": "https://wolf-agents.com/branchen/medizin",
  "audience": {
    "@type": "Audience",
    "audienceType": "Patient:innen, Pflegeeinrichtungen, MVZ, Arztpraxen"
  },
  "areaServed": {
    "@type": "Place",
    "name": "Deutschland, Österreich, Schweiz"
  },
  "knowsAbout": [
    "Barrierefreie Praxiswebsites",
    "BFSG 2025 Compliance Medizin",
    "Digitale Anamnese",
    "Praxissoftware-Integration"
  ]
}
```

**Open Graph:**
- `og:title`: "Medizin · Barrierefreie Praxiswebsites & digitale Anamnese"
- `og:description`: "BFSG 2025 & WCAG 2.2 konform, Terminbuchung, Anamnese, +28% Ersttermin-Buchungen"
- `og:type`: "website"
- `og:image`: `/og-images/medizin.png` (1200×630px)

---

## ♿ Barrierefreiheit (A11y)

**WCAG 2.2 AA Compliance (KRITISCH für diese Branche!):**
- Kontrast Hero-Text (weiß auf dunkel): 15.6:1 ✅
- Kontrast Body-Text (dunkel auf hell): 12.8:1 ✅
- Fokus-Indikatoren: 2px solid `--accent-primary`, min. 3:1 Kontrast
- Skip-Links: Vorhanden in Navigation
- Touch-Targets: Min. 44×44px (BFSG-Anforderung)

**Semantic HTML:**
- `<nav>`, `<main>`, `<section>`, `<article>`, `<footer>`
- Heading-Hierarchie: H1 → H2 → H3 (keine Sprünge)
- `<form>` mit `<fieldset>` + `<legend>` für Anamnese-Formulare

**Interactive Elements:**
- Alle Buttons: Min. 44×44px Touch-Target
- InfoTooltips: `aria-describedby` für Screen-Reader (3× auf dieser Seite!)
- Terminbuchung: `aria-live` für Verfügbarkeits-Updates
- FAQ Accordion: `aria-expanded`, `aria-controls`, `aria-labelledby`

**Keyboard Navigation:**
- Tab-Order: Logisch von oben nach unten
- Enter/Space: Aktiviert Buttons + Accordions
- Escape: Schließt Modals (InfoTooltip)

**Screen-Reader:**
- Alt-Texte für alle Images
- ARIA-Labels für Icon-only Buttons
- Live-Regions für dynamische Updates (Terminbuchung, Anamnese-Wizard)

---

## 📝 Content-Strategie & Targeting

**Hauptthema:**
"Barrierefreie Praxiswebsites und digitale Patient:innenreisen"

**Primary Keywords:**
- Barrierefreie Praxiswebsite
- BFSG 2025 Arztpraxis
- Digitale Anamnese
- Praxissoftware-Integration
- Terminbuchung Praxis

**Secondary Keywords:**
- WCAG 2.2 Medizin
- medatixx Integration
- Doctolib Anbindung
- Samedi Schnittstelle
- Patient Journey Optimization
- No-Show Reduction
- MVZ Website barrierefrei

**Zielgruppe:**
- Primär: Patient:innen (Nutzer der Website)
- Sekundär: Arztpraxen, MVZ, Praxismanager, IT-Verantwortliche Gesundheitswesen

**User Intent:**
- 60 % Informational (Was bedeutet BFSG 2025? Wie funktioniert digitale Anamnese?)
- 20 % Commercial Investigation (Welche Anbieter? Was kostet Praxis-Relaunch?)
- 20 % Transactional (Demo anfragen, Termin buchen)

**AIO/GEO/AEO-Optimierung:**
- ✅ **AIO:** FAQ mit AI-Snippet-Ready-Content (WCAG 2.2, BFSG, Praxissoftware-Namen, Timeline)
- ✅ **GEO:** Lokale Geo-Coverage (DE, AT, CH) im Schema.org
- ⚠️ **AEO:** Fehlender StepFlow schwächt strukturierte Prozess-Darstellung (siehe Content-Audit)

---

## 📊 Content-Audit-Notizen

### ✅ Stärken

1. **BFSG 2025 & WCAG 2.2 prominent** – trifft regulatorische Deadline (wie Öffentliche Einrichtungen)
2. **3× InfoTooltip** – höchste Dichte in Batch 2, erklärt komplexe Begriffe (bfsg-2025, rum, consent-mode-v2)
3. **Praxissoftware-Integration explizit** – medatixx, Doctolib, Samedi genannt
4. **Konkrete KPIs** – +28% Ersttermin-Buchungen, −35% Check-In-Dauer, +18% Bewertungsquote
5. **No-Show-Reduction erwähnt** – wichtiges Pain Point-Thema
6. **MVZ-Fokus** – differenziert zwischen Einzelpraxen (6 Wo.) und MVZ (8–10 Wo.)
7. **Patient Journey Dashboard** – zeigt Datenanalyse-Kompetenz (RUM + Consent Mode v2)

### ⚠️ Schwächen & Legacy-Issues

1. **Fehlender StepFlow** – Schwächt User-Engagement im Vergleich zu Branchen mit Flow
2. **Keine visuellen Demos** – Terminbuchung, Anamnese-Wizard, Patientenservice Hub nicht visualisiert
3. **Barrierefreiheits-Erklärung nur erwähnt** – könnte verlinkt werden (falls vorhanden)
4. **GeoCoverage nicht differenziert** – DACH-weite Praxissoftware-Integration (z.B. Doctolib nur DE/FR)?

### ❌ Fehlende Elemente

1. **StepFlow "Patientenaufnahme in 3 Schritten"** – Könnte Prozess visualisieren:
   - Schritt 1: Termin online buchen
   - Schritt 2: Anamnese vorab ausfüllen
   - Schritt 3: Check-In & Behandlung
2. **Screenshots** – Terminbuchung, Anamnese-Wizard, Patientenservice Hub
3. **Case Study/Testimonial** – Keine Praxis/MVZ als Referenz
4. **Preisindikation** – "Ab X € pro Monat" oder "Individuell" fehlt
5. **Video-Demo** – Anamnese-Wizard in Action (barrierefreie Bedienung)
6. **Barrierefreiheits-Erklärung** – Falls vorhanden, verlinken (BFSG-Anforderung)

### 🔴 Content-Refresh-Priorität

**Priorität: KRITISCH** (Featured + regulatorische Deadline BFSG 2025 + sensible Daten)

**Empfohlene Maßnahmen:**
1. **SOFORT:** StepFlow "Patientenaufnahme in 3 Schritten" hinzufügen (erhöht User-Engagement + zeigt Prozess)
2. **SOFORT:** Barrierefreiheits-Erklärung verlinken (falls vorhanden, BFSG-Anforderung)
3. **Q1 2025:** Screenshots/Video von Terminbuchung + Anamnese-Wizard integrieren (zeigt Barrierefreiheit in Action)
4. **Q1 2025:** Case Study mit Praxis/MVZ veröffentlichen (anonymisiert falls nötig)
5. **Q2 2025:** Praxissoftware-Logos integrieren (medatixx, Doctolib, Samedi als Trust-Signale)
6. **Q2 2025:** Patient Journey Dashboard visualisieren (RUM-Daten, Conversion-Funnel)

---

## ⚡ Performance & Technische Details

**Core Web Vitals Targets:**
- LCP: < 2.5s (Hero-Bild optimiert, kritisch für RUM-Dashboard!)
- FID: < 100ms (minimales JavaScript, React Island lazy-loaded)
- CLS: < 0.1 (feste Dimensions, wichtig für Barrierefreiheit)

**Lazy Loading:**
- Images: `loading="lazy"` ab Fold 2
- React Island (Anamnese-Wizard): Hydration on visible
- Calendly-Widget: Lazy-loaded per Modal

**Barrierefreiheit-spezifische Performance:**
- Screen-Reader-Test: NVDA + JAWS kompatibel
- Tastaturbedienung: Alle Flows ohne Maus bedienbar
- Reduced Motion: `prefers-reduced-motion` berücksichtigt (keine Auto-Animations)
- Color-Scheme: `prefers-color-scheme` für Dark Mode Support

**Security (DSGVO-kritisch):**
- E2E-Verschlüsselung für Anamnese-Daten
- EU-Hosting (Cloudflare, Hetzner)
- Consent-Logging (Consent Mode v2)
- Audit-Log für Dokumenten-Zugriffe

---

## 📈 Content-Metriken

| Metrik | Wert |
|--------|------|
| **Text-Volumen** | ~8.500 Zeichen, ~1.190 Wörter |
| **Link-Density** | ~44 interne Links, 0 externe Links |
| **Content-Verteilung** | 5 Dark Sections, 6 Light Sections |
| **Interactive Elements** | 3 Top Tasks, 0 StepFlow Steps, 3 FAQ Accordions, 6 More Branches |
| **Glossary Coverage** | 4 Begriffe (BFSG 2025, WCAG 2.2, Consent Mode v2, RUM) – 2× Accessibility-spezifisch |
| **InfoTooltip Density** | 3× (höchste Dichte in Batch 2!) |

---

## 🏁 Fazit

Die Medizin-Seite ist die **accessibility-fokussierteste** aller Batch-2-Branchen mit:
- **BFSG 2025 & WCAG 2.2** prominent (regulatorische Deadline-Druck!)
- **3× InfoTooltip** (höchste Dichte in Batch 2: bfsg-2025, rum, consent-mode-v2)
- **Praxissoftware-Integration** (medatixx, Doctolib, Samedi)
- **Patient Journey Optimization** (Terminbuchung, Anamnese, No-Show-Reduction)
- **MVZ-Fokus** (differenziert zwischen Einzelpraxen und Multi-Standorten)

**Stärken:** Barrierefreiheit prominent, konkrete KPIs, Praxissoftware-Integration, No-Show-Reduction.
**Verbesserungspotenzial:** StepFlow fehlt (schwächt User-Engagement), keine visuellen Demos, Barrierefreiheits-Erklärung nicht verlinkt.

**Für vollständige Layout-Details (Spacing, Typografie, Color-Tokens, Responsive-Grid) siehe `kanzleien.md`.**
