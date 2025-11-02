# 🏭 Industrie & B2B – Branchen-Detailseite

**URL:** `/branchen/industrie-b2b`
**Template:** `/src/pages/branchen/[slug].astro` (Dynamic Route)
**Content-Quelle:** `/src/content/branchen/industrie-b2b.json`
**Wichtigkeit:** 🔴 Höchste Priorität (Featured auf Startseite)
**Letztes Update:** 2025-10-30

---

## 📊 Meta-Informationen

| Element | Wert |
|---------|------|
| **Title Tag** | "Industrie & B2B · Produkt- & Serviceportale · Wolf-Agents" |
| **Meta Description** | "Technische SEO, Lead-Qualifizierung und Partner-Onboarding für Industrieunternehmen. PIM/ERP-Integration, Konfiguratoren, +32% SQL." |
| **Canonical** | `https://wolf-agents.com/branchen/industrie-b2b` |
| **Robots** | `index, follow` |
| **Locale** | `de_DE` |

**Geschätzte Metriken:**
- Zeichen (ohne Leerzeichen): ~8.300
- Wörter: ~1.160
- Lesezeit: ~5 min
- Sections: 11 (Hero → CTA → More Branches)
- Headings: H1(1) + H2(11) + H3(15)

---

## 🔗 Verlinkungsstruktur

### Internal Links Outgoing (Gesamt: ~42)

| Ziel | Anzahl | Context |
|------|--------|---------|
| `/kontakt` | 3× | CTA-Buttons in Hero, Path, Final CTA |
| `/glossar/gitops` | 1× | Glossary Link |
| `/glossar/consent-mode-v2` | 1× | Glossary Link |
| `/glossar/core-web-vitals` | 1× | Glossary Link |
| `/glossar/geo` | 1× | Glossary Link |
| `/branchen/kanzleien` | 1× | More Branches Card |
| `/branchen/steuerberater` | 1× | More Branches Card |
| `/branchen/schulen-bildung` | 1× | More Branches Card |
| `/branchen/oeffentliche-einrichtungen` | 1× | More Branches Card |
| `/branchen/notare` | 1× | More Branches Card |
| `/branchen/versicherungen` | 1× | More Branches Card |
| `/branchen/medizin` | 1× | More Branches Card |
| Top Tasks (3×) | 3× | Anchor-Links: #konfigurator, #referenzen, #partner |

### External Links
- Keine direkten externen Links im Content
- PIM/ERP-Systeme erwähnt (Akeneo, SAP, Microsoft Dynamics) ohne direkte Verlinkung
- CRM-Systeme erwähnt (HubSpot, Salesforce) ohne direkte Verlinkung

---

## 🏗️ Layout & Semantische Struktur

**WICHTIG:** Diese Seite nutzt die **identische Struktur** wie `/branchen/kanzleien` (siehe `kanzleien.md` für vollständige Layout-Details mit allen 11 Sections, Spacing, Typografie, Farben).

Die folgende Dokumentation fokussiert auf **branchenspezifische Content-Unterschiede** mit **Schwerpunkt auf B2B/Technical SEO**.

---

## 🎯 KEY CONTENT-UNTERSCHIEDE ZU KANZLEIEN

### Section 1: Hero

**Eyebrow Badge:**
```
"Segment · Industrie"
```

**H1 Headline:**
```
"Produkt- & Serviceportale für Industrieunternehmen"
```

**Subtitle/Deck:**
```
"Wir kombinieren technische SEO, Lead-Qualifizierung und Partner-Onboarding für Hersteller und B2B-Services."
```

**KPI Badge:**
- Text: "Sales Qualified Leads: +32 %"
- Source: "Industrial Lead Funnel 2024"
- Link: Keine (kein Glossary-Link für diese Metrik)
- Icon: `TrendingUp` (Steigerung der qualifizierten Leads)

**CTA Buttons:**
- Primary: "Termin buchen" → `/kontakt`
- Secondary: "Mehr erfahren" → `#konfigurator` (scroll-to anchor)

---

### Section 2: Top Tasks

**3 Tasks mit B2B-Fokus:**

**Task 1: Produkt konfigurieren**
- **Zielgruppe:** Einkauf & Technik
- **Icon:** `Settings`
- **Link:** `#konfigurator`
- **Description:**
  ```
  "Konfiguratoren, Datenblätter und Download-Center."
  ```

**Task 2: Case & Referenzen**
- **Zielgruppe:** Entscheider
- **Icon:** `Award`
- **Link:** `#referenzen`
- **Description:**
  ```
  "Branchen-Use-Cases, KPIs und Zertifikate."
  ```

**Task 3: Partner-Onboarding**
- **Zielgruppe:** Partner & Händler
- **Icon:** `Users`
- **Link:** `#partner`
- **Description:**
  ```
  "Extranet mit Dokumenten, Schulungen und Leads."
  ```

---

### Section 3: Path – KEIN StepFlow ⚠️

**WICHTIG:** Diese Seite hat **KEINEN StepFlow** (wie alle anderen Batch-2-Seiten).

Im Template-Code (`[slug].astro` lines 143-170) wird StepFlow nur gerendert wenn:
```astro
{stepFlow && index === 0 && (
  <StepFlow ... />
)}
```

Da `stepFlow: null` in `industrie-b2b.json`, wird dieser Abschnitt **nicht angezeigt**.

**Stattdessen:** Section 3 (Path) zeigt nur Standard-Content ohne visuellen Journey-Flow.

**CTA in Path-Section:**
- Text: "Konfigurator testen"
- Link: `/kontakt`

---

### Section 4: Pains

**3 Challenges mit B2B-Fokus:**

**Pain 1: Komplexe Produkte schwer erklärbar**
- **Icon:** `FileQuestion`
- **Title:** "Komplexe Produkte schwer erklärbar"
- **Description:**
  ```
  "Speziationslisten und PDFs überzeugen nicht – Nutzer brauchen geführte Konfiguration."
  ```

**Pain 2: Leads kommen unsortiert**
- **Icon:** `UserX`
- **Title:** "Leads kommen unsortiert"
- **Description:**
  ```
  "Kontaktformulare liefern keine Budget-, Zeithorizont- oder Use-Case-Daten."
  ```

**Pain 3: Partner brauchen Self-Service**
- **Icon:** `Users`
- **Title:** "Partner brauchen Self-Service"
- **Description:**
  ```
  "Schulungen, Zertifikate und Marketingmaterial liegen verstreut in Tools."
  ```

---

### Section 5: Solutions

**3 Lösungen (KEINE InfoTooltips):**

**Solution 1: Technische SEO & Content Hubs**
- **Icon:** `Search`
- **Title:** "Technische SEO & Content Hubs"
- **Deck:** "Schema, Performance und Use-Case-Content bringen komplexe Produkte in die Sichtbarkeit."
- **Summary:**
  ```
  "Schema, Performance und Use-Case-Content bringen komplexe Produkte in die Sichtbarkeit."
  ```
- **Proof:** "+60 % organische Sessions"
- **InfoTooltip:** Keine

**Solution 2: Lead Qualification Flow**
- **Icon:** `Target`
- **Title:** "Lead Qualification Flow"
- **Deck:** "Mehrstufige Formulare mit Score, CRM-Sync und Follow-ups."
- **Summary:**
  ```
  "Mehrstufige Formulare mit Score, CRM-Sync und Follow-ups."
  ```
- **Proof:** "SQL +32 %"
- **InfoTooltip:** Keine

**Solution 3: Partner Portal**
- **Icon:** `Briefcase`
- **Title:** "Partner Portal"
- **Deck:** "Rollenbasiertes Extranet mit Schulungen, Zertifikaten und Co-Marketing Material."
- **Summary:**
  ```
  "Rollenbasiertes Extranet mit Schulungen, Zertifikaten und Co-Marketing Material."
  ```
- **Proof:** "Partner-Aktivierung +40 %"
- **InfoTooltip:** Keine

**HINWEIS:** Diese Seite hat **KEINE InfoTooltips** (einzige Batch-2-Seite ohne Tooltips).

---

### Section 6: WebApps & Automations

**3 WebApps mit Tech-Stack:**

**WebApp 1: Produkt-Konfigurator**
- **Title:** "Produkt-Konfigurator"
- **Description:**
  ```
  "Module, Zubehör, Preise und technische Daten kombiniert in einem Flow."
  ```
- **Outcome:** "Technische Teams verstehen schneller, was passt."
- **Tech Stack:**
  - Astro SSR
  - React Island (Konfigurator-Logik)
  - Cloudflare Workers (Preis-Kalkulation)
- **Features:** 4 items (Module, Zubehör, Preise, Tech-Daten)

**WebApp 2: Lead-Score Wizard**
- **Title:** "Lead-Score Wizard"
- **Description:**
  ```
  "Budget, Timing, Use-Case, Uploads, CRM-Übergabe."
  ```
- **Outcome:** "Vertrieb konzentriert sich auf kaufbereite Anfragen."
- **Tech Stack:**
  - Astro SSR
  - HubSpot/Salesforce API (CRM-Integration)
  - Cloudflare Workers (Lead-Scoring)
- **Features:** 4 items (Budget, Timing, Use-Case, CRM-Sync)

**WebApp 3: Partner-Extranet**
- **Title:** "Partner-Extranet"
- **Description:**
  ```
  "Dokumente, Trainings, Zertifikate und Marketingmaterial on demand."
  ```
- **Outcome:** "Partner werden schneller aktiv und bleiben markenkonform."
- **Tech Stack:**
  - Astro SSR
  - Sanity (Headless CMS für Dokumente/Trainings)
  - Auth0 (Partner-Authentifizierung)
- **Features:** 4 items (Dokumente, Trainings, Zertifikate, Marketing-Material)

---

### Section 7: KPI & Proof

**3 Metriken:**

**KPI 1:**
- **Label:** "SQL-Wachstum"
- **Value:** "+32 %"
- **Context:** "Industrial Lead Funnel 2024 · Sales Qualified Leads"
- **Icon:** `TrendingUp`

**KPI 2:**
- **Label:** "Organischer Traffic"
- **Value:** "+60 %"
- **Context:** "Technische SEO erhöht Sichtbarkeit komplexer Produkte"
- **Icon:** `Search`

**KPI 3:**
- **Label:** "Partner-Aktivierung"
- **Value:** "+40 %"
- **Context:** "Extranet beschleunigt Onboarding und Co-Marketing"
- **Icon:** `Users`

**Source:** "Industrial Lead Funnel 2024 · B2B Manufacturing & Services"

---

### Section 8: FAQ

**3 Items mit AI-Snippet-Hinweisen:**

**FAQ 1:**
- **Question:** "Wie integrieren Sie PIM/ERP?"
- **Answer:**
  ```
  "Wir binden Akeneo, SAP, Microsoft Dynamics oder Ihr PIM via API an und synchronisieren Datenblätter & Preise."
  ```
- **AI Snippet:** PIM/ERP-Namen (Akeneo, SAP, Microsoft Dynamics, API)

**FAQ 2:**
- **Question:** "Unterstützen Sie Mehrsprachigkeit & Regionen?"
- **Answer:**
  ```
  "Ja, wir planen Sprach-/Region-Varianten mit automatisierten Deployments, hreflang und lokalisierten Leads."
  ```
- **AI Snippet:** Technical SEO-Begriffe (Mehrsprachigkeit, hreflang, lokalisierte Leads)

**FAQ 3:**
- **Question:** "Wie messen Sie Erfolg?"
- **Answer:**
  ```
  "Consent Mode v2, Server-Side Events und CRM-Dashboards zeigen Funnel KPI, Umsatz und Partner-Performance."
  ```
- **AI Snippet:** Tracking-Begriffe (Consent Mode v2, Server-Side Events, CRM-Dashboards, Funnel KPI)

---

### Section 9: Glossary

**4 verlinkte Begriffe (Technical SEO-Fokus):**

| Badge-Text | Link | Term-ID |
|------------|------|---------|
| "GitOps" | `/glossar/gitops` | `gitops` |
| "Consent Mode v2" | `/glossar/consent-mode-v2` | `consent-mode-v2` |
| "Core Web Vitals" | `/glossar/core-web-vitals` | `core-web-vitals` |
| "GEO" | `/glossar/geo` | `geo` |

**HINWEIS:** Glossary-Links fokussieren auf **Technical SEO** (Core Web Vitals, GEO) und **DevOps** (GitOps) – einzige Seite mit "GEO" als Glossary-Link.

---

### Section 10: CTA (Final Call-to-Action)

**Headline:**
```
"B2B-Portal optimieren?"
```

**Subline:**
```
"Wir zeigen Ihnen in 30 Minuten, wie Sie Konfigurator, Lead-Scoring und Partner-Portal für Ihr Industrieunternehmen umsetzen."
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
- Medizin

(Automatisch generiert aus allen anderen Branchen außer der aktuellen)

---

## 🎨 Design-System-Details

**Farben (Industrie-spezifisch):**
- Keine branchen-spezifischen Farben (nutzt globale Design-Tokens wie Kanzleien)
- Primary Accent: `--accent-primary` (#3b82f6)
- Dark Tone: `--bg-dark` (#0f172a)
- Light Tone: `--bg-light` (#f8fafc)

**Typografie:**
- Headline H1: `font-family: 'Plus Jakarta Sans', font-weight: 700, font-size: 36px → 72px`
- Badge: `font-family: 'Space Mono', font-size: 14px, text-transform: uppercase, letter-spacing: 0.1em`

**Icons (Lucide):**
- Hero: `Factory` (Industry/Manufacturing symbol)
- Tasks: `Settings`, `Award`, `Users`
- Pains: `FileQuestion`, `UserX`, `Users`
- Solutions: `Search`, `Target`, `Briefcase`

---

## 📱 Responsive Breakpoints

**Siehe `kanzleien.md` für vollständige Breakpoint-Tabelle.**

**Industrie-spezifische Anpassungen:**
- Kein StepFlow-Grid (da StepFlow fehlt)
- Konfigurator: Complex Grid-Layout auf Desktop (Module + Zubehör + Preise)
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
7. `<SolutionCard>` – Solutions (KEINE InfoTooltips)
8. `<WebAppCard>` – WebApps mit Tech-Stack
9. `<KPICard>` – KPI-Grid
10. `<FAQCard>` – FAQ-Accordion
11. `<GlossaryLinks>` – Badge-Grid (4 Links mit Technical SEO-Fokus)
12. `<CTASection>` – Final CTA
13. `<BranchCard>` – More Branches Grid
14. `<Footer>` – Global Footer

**Data Loading:**
```astro
const { slug } = Astro.params;
const branchData = await getEntry('branchen', slug);
const { stepFlow } = branchData.data; // stepFlow = null für Industrie-B2B
```

**Conditional Rendering:**
```astro
{stepFlow && index === 0 && (
  <StepFlow ... />
)}
// Wird NICHT gerendert, da stepFlow === null

// KEINE InfoTooltip Conditional Rendering (keine tooltipTerms vorhanden)
```

---

## 🔍 SEO & Strukturierte Daten

**Schema.org Markup:**

```json
{
  "@context": "https://schema.org",
  "@type": ["Organization", "ProfessionalService"],
  "name": "Wolf-Agents · Industrie & B2B",
  "description": "Technische SEO, Lead-Qualifizierung und Partner-Onboarding für Industrieunternehmen und B2B-Services.",
  "url": "https://wolf-agents.com/branchen/industrie-b2b",
  "audience": {
    "@type": "Audience",
    "audienceType": "B2B-Kunden, Einkauf, Technik, Entscheider, Partner, Händler"
  },
  "areaServed": {
    "@type": "Place",
    "name": "Europa, Nordamerika"
  },
  "knowsAbout": [
    "Technische SEO B2B",
    "PIM/ERP-Integration",
    "Produktkonfiguratoren",
    "Partner-Portale",
    "Lead-Qualification B2B"
  ]
}
```

**WICHTIG:** GeoCoverage ist **Europa + Nordamerika** (nicht nur DACH wie andere Branchen!). Vermutlich weil Industrieunternehmen oft international agieren und Multi-Region-Support benötigen.

**Open Graph:**
- `og:title`: "Industrie & B2B · Produkt- & Serviceportale"
- `og:description`: "Technische SEO, Konfiguratoren, Partner-Portal – PIM/ERP-integriert, +32% SQL"
- `og:type`: "website"
- `og:image`: `/og-images/industrie-b2b.png` (1200×630px)

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
- Konfigurator: `aria-live` für dynamische Preis-Updates
- Partner-Login: `aria-describedby` für Validierung
- FAQ Accordion: `aria-expanded`, `aria-controls`

---

## 📝 Content-Strategie & Targeting

**Hauptthema:**
"Produkt- und Serviceportale für Industrieunternehmen mit technischer SEO und Partner-Onboarding"

**Primary Keywords:**
- B2B-Portal Industrie
- Technische SEO B2B
- Produktkonfigurator B2B
- PIM/ERP-Integration
- Partner-Portal Hersteller

**Secondary Keywords:**
- Akeneo Integration
- SAP Dynamics Anbindung
- Lead-Qualification B2B
- Use-Case-Content Industrie
- Mehrsprachige B2B-Website
- hreflang Implementation
- Server-Side Events B2B

**Zielgruppe:**
- Primär: B2B-Kunden (Einkauf, Technik, Entscheider)
- Sekundär: Industrieunternehmen, Hersteller, B2B-Dienstleister, Marketing-Verantwortliche, Partner-Manager

**User Intent:**
- 50 % Informational (Wie funktioniert PIM-Integration? Was ist Lead-Scoring?)
- 30 % Commercial Investigation (Welche Anbieter? Was kostet Konfigurator?)
- 20 % Transactional (Demo anfragen, Termin buchen)

**AIO/GEO/AEO-Optimierung:**
- ✅ **AIO:** FAQ mit AI-Snippet-Ready-Content (PIM/ERP-Namen, Technical SEO-Begriffe, Tracking-Begriffe)
- ✅ **GEO:** Breite Geo-Coverage (EU + NA) im Schema.org – einzige Branchen-Seite mit Non-DACH-Coverage!
- ⚠️ **AEO:** Fehlender StepFlow schwächt strukturierte Prozess-Darstellung (siehe Content-Audit)

---

## 📊 Content-Audit-Notizen

### ✅ Stärken

1. **B2B-Fokus klar differenziert** – einzige Seite ohne B2C-Elemente
2. **Technical SEO prominent** – Core Web Vitals, GEO als Glossary-Links (einzigartig!)
3. **PIM/ERP-Integration explizit** – Akeneo, SAP, Microsoft Dynamics genannt
4. **Multi-Region-Support** – EU + NA Coverage (breiter als andere Branchen)
5. **Partner-Portal als USP** – differenziert von reinen Produkt-Websites
6. **Konkrete KPIs** – +32% SQL, +60% organischer Traffic, +40% Partner-Aktivierung
7. **hreflang erwähnt** – zeigt Multi-Language-Kompetenz
8. **Server-Side Events** – zeigt moderne Tracking-Kompetenz

### ⚠️ Schwächen & Legacy-Issues

1. **Fehlender StepFlow** – Schwächt User-Engagement im Vergleich zu Branchen mit Flow
2. **KEINE InfoTooltips** – Begriffe wie "PIM", "hreflang", "Server-Side Events" könnten erklärt werden
3. **Konfigurator nicht visualisiert** – Keine Screenshots/Mockups
4. **Lead-Scoring nicht detailliert** – Welche Kriterien? Budget, Timing, Use-Case erwähnt, aber nicht erklärt
5. **Partner-Portal nicht visualisiert** – Extranet-Screenshots fehlen

### ❌ Fehlende Elemente

1. **StepFlow "Produktkonfigurator in 4 Schritten"** – Könnte Prozess visualisieren:
   - Schritt 1: Use-Case definieren
   - Schritt 2: Module & Zubehör konfigurieren
   - Schritt 3: Preis & Tech-Daten prüfen
   - Schritt 4: Angebot anfragen
2. **Konfigurator-Screenshots** – Live-Demo der Konfigurator-UI
3. **Partner-Portal-Screenshots** – Extranet-Dashboard, Trainings, Zertifikate
4. **Case Study/Testimonial** – Kein Industrieunternehmen als Referenz
5. **Preisindikation** – "Ab X € pro Monat" oder "Individuell" fehlt
6. **InfoTooltips** – PIM, ERP, hreflang, SQL könnten erklärt werden (falls Glossar erweitert wird)
7. **PIM/ERP-Logos** – Akeneo, SAP, Dynamics als visuelle Trust-Signale

### 🔴 Content-Refresh-Priorität

**Priorität: HOCH** (Featured + höchste SQL-KPI +32% + internationale Reichweite)

**Empfohlene Maßnahmen:**
1. **SOFORT:** StepFlow "Produktkonfigurator in 4 Schritten" hinzufügen (erhöht User-Engagement + zeigt Prozess)
2. **Q1 2025:** Konfigurator-Screenshots in WebApp-Section integrieren (zeigt UI/UX)
3. **Q1 2025:** Partner-Portal-Screenshots hinzufügen (Extranet-Dashboard)
4. **Q2 2025:** Case Study mit Industrieunternehmen veröffentlichen (anonymisiert falls nötig)
5. **Q2 2025:** InfoTooltips für "PIM", "ERP", "hreflang", "SQL" ergänzen (falls Glossar erweitert wird)
6. **Q2 2025:** PIM/ERP-Logos integrieren (Akeneo, SAP, Dynamics als Trust-Signale)
7. **Langfristig:** Video-Demo von Konfigurator + Partner-Portal

---

## ⚡ Performance & Technische Details

**Core Web Vitals Targets (KRITISCH für Technical SEO-Fokus!):**
- LCP: < 2.5s (Hero-Bild optimiert, B2B-Nutzer erwarten schnelle Ladezeiten)
- FID: < 100ms (minimales JavaScript, React Island lazy-loaded)
- CLS: < 0.1 (feste Dimensions für Images/Cards/Konfigurator-Grid)

**Lazy Loading:**
- Images: `loading="lazy"` ab Fold 2
- React Island (Konfigurator): Hydration on visible
- Partner-Extranet: Auth-gated, lazy-loaded per Login

**Technical SEO Features:**
- Schema.org: Organization + Product + HowTo
- hreflang: Multi-Language/Region-Support (DE, EN, FR, ES, etc.)
- Structured Data: ProductConfigurator, PartnerProgram
- Sitemap: Dynamic per Region/Language
- Canonical: Multi-Region-aware

**Performance Monitoring:**
- Server-Side Events (Consent Mode v2)
- RUM (Real User Monitoring) für Core Web Vitals
- CRM-Dashboard-Integration (HubSpot/Salesforce)

---

## 📈 Content-Metriken

| Metrik | Wert |
|--------|------|
| **Text-Volumen** | ~8.300 Zeichen, ~1.160 Wörter |
| **Link-Density** | ~42 interne Links, 0 externe Links |
| **Content-Verteilung** | 5 Dark Sections, 6 Light Sections |
| **Interactive Elements** | 3 Top Tasks, 0 StepFlow Steps, 3 FAQ Accordions, 7 More Branches |
| **Glossary Coverage** | 4 Begriffe (GitOps, Consent Mode v2, Core Web Vitals, GEO) – Technical SEO-Fokus |
| **InfoTooltip Density** | 0× (einzige Batch-2-Seite ohne Tooltips) |

---

## 🏁 Fazit

Die Industrie-B2B-Seite ist die **international ausgerichtetste** aller Branchen-Seiten mit:
- **Technical SEO-Fokus** (Core Web Vitals, GEO, hreflang)
- **Multi-Region-Support** (EU + NA statt nur DACH)
- **PIM/ERP-Integration** (Akeneo, SAP, Microsoft Dynamics)
- **Partner-Portal als USP** (Extranet mit Schulungen, Zertifikaten, Marketing-Material)
- **Höchste SQL-KPI** (+32% Sales Qualified Leads)

**Stärken:** B2B-Fokus, Technical SEO, PIM/ERP-Integration, Multi-Region-Support, Partner-Portal.
**Verbesserungspotenzial:** StepFlow fehlt (schwächt User-Engagement), keine InfoTooltips, Konfigurator/Partner-Portal nicht visualisiert.

**WICHTIG:** GeoCoverage ist **Europa + Nordamerika** (nicht nur DACH) – einzige Branchen-Seite mit internationaler Ausrichtung!

**Für vollständige Layout-Details (Spacing, Typografie, Color-Tokens, Responsive-Grid) siehe `kanzleien.md`.**
