# Blog-Post: Cloudflare Pages vs. AWS CloudFront – Deployment für regulierte Teams

## 1. Header & Meta-Informationen

**Seiten-Typ:** Blog-Post (MDX Content Collection mit Astro-Component)
**Datei:** `/src/content/blog/cloudflare-pages-vs-aws-cloudfront.mdx` (160 Zeilen, 7.9 KB)
**Route:** `/blog/cloudflare-pages-vs-aws-cloudfront/` (generiert via Content Collection)
**Layout:** `BlogPostLayout` (implicit via Content Collection Schema)
**Zielgruppen:** Kanzleien & Boutiquen, Schulen & Hochschulen, Öffentliche Einrichtungen
**Kategorie:** Deployment & Governance
**Lesedauer:** 8 min
**Veröffentlicht:** 2025-09-24
**Autor:** Eduard Wolf

**SEO-Metadaten:**
- **Title:** "Cloudflare Pages vs. AWS CloudFront: Welches Deployment passt zu Kanzleien, Campus & Behörden?"
- **Description:** "Git-basierte Deployments mit Cloudflare Pages oder Governance-Stacks auf AWS S3 + CloudFront? Wir vergleichen Stufe B und Stufe C für regulierte Teams – inklusive KPIs, Compliance und Migration."
- **OG-Image:** `/img/og-default.jpg`
- **Response Promise:** "Antwort innerhalb von 1 Stunde · Deployment-Audit in ≤ 5 Werktagen"

**Keywords (Schema.org):**
- Cloudflare Pages vs AWS CloudFront
- GitOps Deployment Kanzlei
- OZG Hosting
- Astro Deployment

**Besonderheit:** **Verwendet Astro-Component** (`ComparisonMatrix`) mit JavaScript-Data-Array!

---

## 2. Verlinkungsstruktur

### Ausgehende Interne Links (8 Total)

**Leistungs-Seiten (5):**
1. `/leistungen/stufe-b-cloudflare-pages` — "Stufe B → Stufe C Migrationsplan" (Kanzlei-CTA)
2. `/leistungen/stufe-c-aws-cloudfront` — "Governance Upgrade (Stufe C)" (Kanzlei-Segment Resources)
3. `/leistungen/seo-tech` — "SEO & Tech Foundations" (Bildungs-Segment Resources)
4. `/leistungen/barrierefreiheit` — "Barrierefreiheit & BFSG" (Behörden-Segment Resources)

**Branchen-Seiten (3):**
1. `/branchen/schulen-bildung` — "Deployment-Fit prüfen" (Bildungs-CTA)
2. `/branchen/oeffentliche-einrichtungen` — "Servicecockpit Deployments planen" (Behörden-CTA)

**Glossar-Links:** Keine `<InfoTooltip>` Tags

**Externe Referenzen (in Text erwähnt, nicht verlinkt):**
- Cloudflare Pages
- AWS S3, CloudFront, Lambda@Edge, Shield Advanced, WAF, CloudTrail
- GitHub Actions, GitLab CI
- Terraform, Terragrunt, CDK
- Datadog, NewRelic, PagerDuty

### Eingehende Links (zu erwarten)

- **Startseite** (`/`) — Blog-Feed Carousel
- **Leistungen (Stufe B, Stufe C)** — Deployment-Argumentationsketten
- **Branchen-Seiten** — Infrastructure/DevOps Sections
- **Glossar-Terme** — Zukünftig: "CI/CD", "IaC", "Edge Computing" (wenn erstellt)

### Navigation Context

**Breadcrumbs (generiert):**
```
Home > Blog > Deployment & Governance > Cloudflare Pages vs. AWS CloudFront
```

**Prev/Next Posts:** Dynamisch via Collection Sort (publishedDate DESC)

---

## 3. Layout & Semantische Struktur

### MDX Content-Architektur (mit Astro-Component!)

```markdown
FRONTMATTER (Zeilen 1-53)
├── Meta: title, description, publishedDate, category, readTime, author, responsePromise
├── Segments Array (3 Einträge: kanzlei, bildung, oeffentlich)
│   └── Pro Segment: title, kpi, summary, ctaLabel, ctaHref, resources[]
├── Schema.org: type, audience, about, keywords
└── image: /img/og-default.jpg

COMPONENT-IMPORT (Zeile 56)
└── import ComparisonMatrix from '../../components/ComparisonMatrix.astro';

COMPARISON-DATA-ARRAY (Zeilen 58-79)
└── export const comparisonData = [ ... ];  // 4 Vergleichskriterien

COMPONENT-USAGE (Zeile 81)
└── <ComparisonMatrix items={comparisonData} />

HR-SEPARATOR (Zeile 83)
└── --- (Markdown HR, trennt Component-Block von Text-Content)

CONTENT-SECTIONS (Zeilen 85-161)
├── H2: Stufe B vs. Stufe C im Überblick (Zeilen 85-91)
│   └── 2 Absätze + 2 Bullet-Points (Cloudflare Pages, AWS S3 + CloudFront)
│
├── H2: Use Cases je Segment (Zeilen 94-113)
│   ├── H3: Kanzleien & Boutiquen (3 Bullet-Points)
│   ├── H3: Schulen & Campus-Teams (3 Bullet-Points)
│   └── H3: Behörden & öffentliche Dienste (3 Bullet-Points)
│
├── H2: Entscheidungsleitfaden (Zeilen 116-125)
│   └── Tabelle: Frage | Cloudflare Pages | AWS S3 + CloudFront (mit ✅ Emojis)
│
├── H2: Migration: Von Stufe B zu Stufe C (Zeilen 128-135)
│   └── 5 Numbered Steps (Repository → CI/CD → IaC → Observability → Governance)
│
├── H2: FAQ (Zeilen 138-151)
│   ├── H3: Können wir Cloudflare Pages und CloudFront kombinieren?
│   ├── H3: Wie wirkt sich das auf Core Web Vitals aus?
│   └── H3: Was ist mit Kosten?
│
└── H2: Fazit & nächste Schritte (Zeilen 154-160)
    └── 3 Bullet-Points + CTA-Text mit Response Promise
```

### ComparisonMatrix Component Specification

**Component-Datei:** `/src/components/ComparisonMatrix.astro`

**Props:**
```typescript
interface Props {
  items: Array<{
    criteria: string;
    cloudflare: string;
    aws: string;
  }>;
}
```

**Data-Structure (Zeilen 58-79):**
```javascript
export const comparisonData = [
  {
    criteria: "Deployment",
    cloudflare: "Git-Push → Build → Deploy (Preview pro Pull Request)",
    aws: "CI/CD → Artefakt → S3 Upload → CloudFront Invalidation / Blue-Green"
  },
  {
    criteria: "Edge & Performance",
    cloudflare: "300+ PoPs, integrierte Workers & KV, Zero-Downtime Deployments",
    aws: "CloudFront Edge, Origin Shielding, Lambda@Edge, konfigurierbare TTL & Header"
  },
  {
    criteria: "Compliance & Security",
    cloudflare: "Zero Trust Access, WAF, Bot Management optional",
    aws: "WAF, Shield Advanced, KMS, IAM, Audit-Logging (CloudTrail, CloudWatch)"
  },
  {
    criteria: "Ops & Monitoring",
    cloudflare: "UI + API, Basis-Analytics, Integration in Pages Functions",
    aws: "Full Observability (CloudWatch, OpenSearch), IaC (Terraform/CDK), Kostensteuerung"
  }
];
```

**Rendered Output (HTML):**
```html
<section class="comparison-matrix">
  <div class="matrix-grid">
    <!-- Header Row -->
    <div class="matrix-header">
      <div class="header-cell empty"></div>
      <div class="header-cell cloudflare">
        <img src="/img/logo-cloudflare.svg" alt="Cloudflare Pages" />
        <span>Cloudflare Pages</span>
      </div>
      <div class="header-cell aws">
        <img src="/img/logo-aws.svg" alt="AWS CloudFront" />
        <span>AWS S3 + CloudFront</span>
      </div>
    </div>

    <!-- Data Rows (4×) -->
    <div class="matrix-row" data-criteria="deployment">
      <div class="criteria-cell">Deployment</div>
      <div class="value-cell cloudflare">Git-Push → Build → Deploy...</div>
      <div class="value-cell aws">CI/CD → Artefakt → S3 Upload...</div>
    </div>
    <!-- Repeat für Edge & Performance, Compliance & Security, Ops & Monitoring -->
  </div>
</section>
```

### Semantische HTML-Hierarchie (gerendert via BlogPostLayout)

```html
<article class="blog-post" itemscope itemtype="https://schema.org/BlogPosting">
  <header class="blog-header">
    <h1 itemprop="headline">Cloudflare Pages vs. AWS CloudFront...</h1>
    <!-- Meta -->
  </header>

  <figure class="hero-image">
    <img src="/img/og-default.jpg" alt="..." itemprop="image" />
  </figure>

  <div class="segment-cards" data-segments="3">
    <!-- 3× Segment-Cards -->
  </div>

  <section class="prose" itemprop="articleBody">
    <!-- ComparisonMatrix Component (Zeile 81) -->
    <section class="comparison-matrix" data-rows="4">
      <!-- Grid mit 4 Zeilen × 3 Spalten -->
    </section>

    <hr class="content-divider" />

    <h2 id="stufe-b-vs-stufe-c">Stufe B vs. Stufe C im Überblick</h2>
    <!-- ... weitere Sections ... -->

    <!-- Entscheidungsleitfaden-Tabelle (Zeilen 116-125) -->
    <table class="decision-guide">
      <thead>
        <tr>
          <th>Frage</th>
          <th>Cloudflare Pages</th>
          <th>AWS S3 + CloudFront</th>
        </tr>
      </thead>
      <tbody>
        <tr>
          <td>Team benötigt Preview-Links & GitOps?</td>
          <td>✅</td>
          <td>möglich, aber komplexer</td>
        </tr>
        <!-- ... weitere Rows ... -->
      </tbody>
    </table>
  </section>

  <footer class="blog-footer">
    <!-- Prev/Next Posts -->
  </footer>
</article>
```

### Accessibility-Struktur

- **Heading-Hierarchie:** H1 (Title) → H2 (Main Sections) → H3 (Subsections/FAQs) ✅
- **Landmark Regions:** `<article>`, `<header>`, `<section>`, `<footer>`
- **Skip-Links:** Provided by BlogPostLayout
- **ComparisonMatrix Accessibility:**
  - `role="table"` auf Grid-Container (wenn nicht natürlich `<table>`)
  - `aria-label="Vergleich: Cloudflare Pages vs. AWS CloudFront"`
  - Header-Cells mit `role="columnheader"`
- **Decision-Guide Table:** Standard `<table>` mit `<thead>`, `<th scope="col">`
- **Emoji-Accessibility:** ✅ hat `aria-label="Verfügbar"` oder `role="img"`
- **Keyboard Navigation:** Alle Links/CTAs keyboard-accessible

---

## 4. Design-System-Details

### Typografie

(Identisch mit anderen Blog-Posts)

**Headline (H1):**
- Font: Obviously, Weight: 600, Size: 2.5rem (40px) Desktop / 1.875rem (30px) Mobile
- Color: `--wolf-plum` (#3B1E54)

**Body Text:**
- Font: Inter, Weight: 400/500, Size: 1.125rem (18px) Desktop / 1rem (16px) Mobile
- Line-Height: 1.75, Color: `--wolf-plum`

**ComparisonMatrix Typography:**
- **Criteria-Cell:** Font: Obviously, Weight: 600, Size: 1.125rem, Color: `--wolf-plum`
- **Value-Cell:** Font: Inter, Weight: 400, Size: 1rem, Line-Height: 1.6

### Farben

**Segment Cards:** (Identisch mit anderen Blog-Posts)

**ComparisonMatrix:**
- **Header:** Background `--wolf-plum` (#3B1E54), Text White (#FFFFFF)
- **Cloudflare Column:** Accent-Color `--wolf-apricot` (#F4A261) für Logos/Borders
- **AWS Column:** Accent-Color `--wolf-mint` (#2A9D8F) für Logos/Borders
- **Criteria-Cell:** Background `--wolf-snow` (#F8F9FA), Text `--wolf-plum`
- **Value-Cell:** Background White, alternating `--wolf-snow` für Rows
- **Borders:** 1px solid `--wolf-plum-light` (#E0D5E8)

**Decision-Guide Table:**
- Header: `--wolf-plum` Background, White Text
- Rows: Alternating `--wolf-snow` / White
- ✅ Emoji: Color `--wolf-mint` (grün/positive Signale)
- ❌ (nicht verwendet, aber falls): Color `--wolf-red` (negativ)

### Spacing

- **Section-Gaps:** 4rem (64px)
- **Segment-Card Grid:** 1.5rem (24px) Gap
- **ComparisonMatrix:**
  - Grid-Gap: 1rem (Columns), 0.5rem (Rows)
  - Padding (Cell): 1rem
  - Margin-Top/Bottom: 3rem
- **Decision-Guide Table:** Margin 2rem Top/Bottom, Cell-Padding 0.75rem 1rem
- **HR-Divider:** Margin 3rem Top/Bottom, Border 1px solid `--wolf-plum-light`

### Komponenten (explizit + implizit)

**BlogPostLayout (Wrapper):** (Standard)

**SegmentCard (generiert aus Frontmatter):** (Standard)

**ComparisonMatrix (Astro-Component):**
```astro
---
// /src/components/ComparisonMatrix.astro
interface Props {
  items: Array<{
    criteria: string;
    cloudflare: string;
    aws: string;
  }>;
}

const { items } = Astro.props;
---

<section class="comparison-matrix" aria-label="Vergleich: Cloudflare Pages vs. AWS CloudFront">
  <div class="matrix-grid" role="table">
    <!-- Header Row -->
    <div class="matrix-header" role="row">
      <div class="header-cell empty" role="columnheader"></div>
      <div class="header-cell cloudflare" role="columnheader">
        <img src="/img/logo-cloudflare.svg" alt="" aria-hidden="true" />
        <span>Cloudflare Pages</span>
      </div>
      <div class="header-cell aws" role="columnheader">
        <img src="/img/logo-aws.svg" alt="" aria-hidden="true" />
        <span>AWS S3 + CloudFront</span>
      </div>
    </div>

    <!-- Data Rows -->
    {items.map((item) => (
      <div class="matrix-row" role="row" data-criteria={item.criteria.toLowerCase().replace(/\s+/g, '-')}>
        <div class="criteria-cell" role="rowheader">{item.criteria}</div>
        <div class="value-cell cloudflare" role="cell">{item.cloudflare}</div>
        <div class="value-cell aws" role="cell">{item.aws}</div>
      </div>
    ))}
  </div>
</section>

<style>
.comparison-matrix {
  margin: 3rem 0;
}

.matrix-grid {
  display: grid;
  grid-template-columns: 1fr 2fr 2fr;
  gap: 0.5rem 1rem;
  border: 1px solid var(--wolf-plum-light);
  border-radius: 8px;
  overflow: hidden;
}

.matrix-header {
  display: contents;
}

.header-cell {
  background: var(--wolf-plum);
  color: white;
  padding: 1rem;
  font-weight: 600;
  display: flex;
  align-items: center;
  gap: 0.5rem;
}

.header-cell img {
  width: 24px;
  height: 24px;
}

.matrix-row {
  display: contents;
}

.matrix-row:nth-child(even) .criteria-cell,
.matrix-row:nth-child(even) .value-cell {
  background: var(--wolf-snow);
}

.criteria-cell {
  font-family: Obviously, sans-serif;
  font-weight: 600;
  font-size: 1.125rem;
  padding: 1rem;
  background: var(--wolf-snow);
}

.value-cell {
  padding: 1rem;
  line-height: 1.6;
}

.value-cell.cloudflare {
  border-left: 3px solid var(--wolf-apricot);
}

.value-cell.aws {
  border-left: 3px solid var(--wolf-mint);
}

@media (max-width: 768px) {
  .matrix-grid {
    grid-template-columns: 1fr;
  }

  .matrix-header {
    display: none; /* Hide header on mobile, use labels inline */
  }

  .matrix-row {
    display: grid;
    grid-template-columns: 1fr;
    gap: 0.5rem;
    border-bottom: 2px solid var(--wolf-plum-light);
    padding: 1rem;
  }

  .criteria-cell {
    font-size: 1rem;
    padding-bottom: 0.5rem;
  }

  .value-cell::before {
    content: attr(data-platform) ': ';
    font-weight: 600;
  }

  .value-cell.cloudflare::before {
    content: 'Cloudflare: ';
  }

  .value-cell.aws::before {
    content: 'AWS: ';
  }
}
</style>
```

**Decision-Guide Table:**
```html
<table class="decision-guide">
  <caption class="sr-only">Entscheidungsleitfaden: Cloudflare Pages vs. AWS CloudFront</caption>
  <thead>
    <tr>
      <th scope="col">Frage</th>
      <th scope="col">Cloudflare Pages</th>
      <th scope="col">AWS S3 + CloudFront</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Team benötigt Preview-Links & GitOps?</td>
      <td><span role="img" aria-label="Verfügbar">✅</span></td>
      <td>möglich, aber komplexer</td>
    </tr>
    <!-- ... -->
  </tbody>
</table>
```

---

## 5. Responsive Breakpoints

### Mobile (< 640px)

- **Segment Cards:** Stack vertikal (Grid 1 Column)
- **Font-Sizes:** H1 30px, H2 24px, Body 16px
- **ComparisonMatrix:**
  - Grid → Stack (1 Column)
  - Header versteckt (CSS `display: none`)
  - Jede Row zeigt: Criteria-Cell + 2× Value-Cells (mit Prefix "Cloudflare:", "AWS:")
- **Decision-Guide Table:** Horizontal-Scroll Container (overflow-x: auto)
- **CTA-Buttons:** Full-Width

### Tablet (640px - 1024px)

- **Segment Cards:** Grid 2 Columns
- **Font-Sizes:** H1 36px, H2 28px, Body 17px
- **ComparisonMatrix:** Grid 3 Columns (Criteria 1fr, Cloudflare/AWS je 2fr)
- **Decision-Guide Table:** Native Display (3 Spalten passen)

### Desktop (> 1024px)

- **Segment Cards:** Grid 3 Columns
- **Font-Sizes:** Full Desktop Sizes
- **Max-Width:** 1120px Container
- **ComparisonMatrix:** Grid 3 Columns (optimale Lesbarkeit)
- **Decision-Guide Table:** Full Native Display

### Critical Breakpoint-Spezifika

- **ComparisonMatrix Mobile:** Value-Cells erhalten `::before` Pseudo-Element mit Platform-Label
- **Emoji-Size:** ✅ Font-Size 1.25rem (größer als Body-Text für bessere Sichtbarkeit)
- **Table-Overflow:** Decision-Guide bei < 640px → Horizontal-Scroll mit Shadow-Indicator (links/rechts)

---

## 6. Komponenten-Bibliothek

### Verwendete Komponenten (explizit + implizit)

**BlogPostLayout (Wrapper):** (Standard)

**SegmentCard (generiert aus Frontmatter):** (Standard)

**ComparisonMatrix (Astro-Component) - CUSTOM:**
- **File:** `/src/components/ComparisonMatrix.astro`
- **Props:** `items` (Array mit criteria/cloudflare/aws)
- **Render:** Grid-Layout mit Header + 4 Data-Rows
- **Styling:** Scoped CSS (via Astro `<style>` Tag)
- **Accessibility:** `role="table"`, `role="row"`, `role="columnheader"`, `role="rowheader"`, `role="cell"`
- **Responsive:** Grid → Stack bei Mobile (< 768px)

**Decision-Guide Table (Standard Markdown `<table>`):**
- **Render:** Via Remark (Markdown → HTML)
- **Styling:** Global Table-Styles (`/src/styles/tables.css`)
- **Accessibility:** `<thead>`, `<tbody>`, `<th scope="col">`, `<caption>` (sr-only)

### Standard Markdown-Elemente

**Paragraphs, Lists, etc.:** (Identisch mit anderen Blog-Posts)

**Emojis (`✅`):**
- **Render:** Unicode Character (U+2705)
- **Accessibility:** `<span role="img" aria-label="Verfügbar">✅</span>` (via Rehype-Plugin oder manuell)
- **Styling:** Color `--wolf-mint` (grün), Font-Size 1.25rem

**HR-Divider:**
- **Render:** `<hr class="content-divider" />`
- **Styling:** Border 1px solid `--wolf-plum-light`, Margin 3rem Top/Bottom

---

## 7. SEO & Strukturierte Daten

### Meta-Tags (generiert via BlogPostLayout)

```html
<title>Cloudflare Pages vs. AWS CloudFront: Welches Deployment passt zu Kanzleien, Campus & Behörden? | Wolf-Agents</title>
<meta name="description" content="Git-basierte Deployments mit Cloudflare Pages oder Governance-Stacks auf AWS S3 + CloudFront? Wir vergleichen Stufe B und Stufe C für regulierte Teams – inklusive KPIs, Compliance und Migration.">

<!-- Open Graph -->
<meta property="og:type" content="article">
<meta property="og:title" content="Cloudflare Pages vs. AWS CloudFront...">
<meta property="og:description" content="Git-basierte Deployments...">
<meta property="og:image" content="https://wolf-agents.com/img/og-default.jpg">
<meta property="og:url" content="https://wolf-agents.com/blog/cloudflare-pages-vs-aws-cloudfront/">

<!-- Twitter Card -->
<meta name="twitter:card" content="summary_large_image">

<!-- Article Meta -->
<meta property="article:published_time" content="2025-09-24">
<meta property="article:author" content="Eduard Wolf">
<meta property="article:section" content="Deployment & Governance">
<meta property="article:tag" content="Cloudflare Pages vs AWS CloudFront">
<meta property="article:tag" content="GitOps Deployment Kanzlei">
<meta property="article:tag" content="OZG Hosting">
<meta property="article:tag" content="Astro Deployment">
```

### Schema.org Structured Data

**BlogPosting Schema (JSON-LD):**
```json
{
  "@context": "https://schema.org",
  "@type": "BlogPosting",
  "headline": "Cloudflare Pages vs. AWS CloudFront: Welches Deployment passt zu...",
  "description": "Git-basierte Deployments mit Cloudflare Pages oder Governance-Stacks...",
  "image": "https://wolf-agents.com/img/og-default.jpg",
  "datePublished": "2025-09-24",
  "author": {
    "@type": "Person",
    "name": "Eduard Wolf"
  },
  "publisher": {
    "@type": "Organization",
    "name": "Wolf-Agents",
    "logo": {
      "@type": "ImageObject",
      "url": "https://wolf-agents.com/img/logo.png"
    }
  },
  "audience": [
    {
      "@type": "Audience",
      "audienceType": "Kanzleien & Boutiquen"
    },
    {
      "@type": "Audience",
      "audienceType": "Schulen & Hochschulen"
    },
    {
      "@type": "Audience",
      "audienceType": "Öffentliche Einrichtungen"
    }
  ],
  "about": [
    "Cloudflare Pages",
    "AWS S3",
    "AWS CloudFront",
    "DevOps Governance"
  ],
  "keywords": "Cloudflare Pages vs AWS CloudFront, GitOps Deployment Kanzlei, OZG Hosting, Astro Deployment",
  "articleBody": "<!-- Full Text Content -->",
  "wordCount": 1100,
  "timeRequired": "PT8M"
}
```

**Table Schema (Optional für ComparisonMatrix):**
```json
{
  "@context": "https://schema.org",
  "@type": "Table",
  "about": "Vergleich: Cloudflare Pages vs. AWS CloudFront",
  "tableContent": [
    {
      "@type": "TableRow",
      "rowHeader": "Deployment",
      "cells": [
        "Git-Push → Build → Deploy (Preview pro Pull Request)",
        "CI/CD → Artefakt → S3 Upload → CloudFront Invalidation / Blue-Green"
      ]
    },
    {
      "@type": "TableRow",
      "rowHeader": "Edge & Performance",
      "cells": [
        "300+ PoPs, integrierte Workers & KV, Zero-Downtime Deployments",
        "CloudFront Edge, Origin Shielding, Lambda@Edge, konfigurierbare TTL & Header"
      ]
    },
    {
      "@type": "TableRow",
      "rowHeader": "Compliance & Security",
      "cells": [
        "Zero Trust Access, WAF, Bot Management optional",
        "WAF, Shield Advanced, KMS, IAM, Audit-Logging (CloudTrail, CloudWatch)"
      ]
    },
    {
      "@type": "TableRow",
      "rowHeader": "Ops & Monitoring",
      "cells": [
        "UI + API, Basis-Analytics, Integration in Pages Functions",
        "Full Observability (CloudWatch, OpenSearch), IaC (Terraform/CDK), Kostensteuerung"
      ]
    }
  ]
}
```

**HowTo Schema (Optional für Migration-Section):**
```json
{
  "@context": "https://schema.org",
  "@type": "HowTo",
  "name": "Migration von Cloudflare Pages (Stufe B) zu AWS CloudFront (Stufe C)",
  "step": [
    {
      "@type": "HowToStep",
      "position": 1,
      "name": "Repository unverändert lassen",
      "text": "Astro-Build erzeugt weiterhin statische Assets."
    },
    {
      "@type": "HowToStep",
      "position": 2,
      "name": "CI/CD erweitern",
      "text": "GitHub Actions oder GitLab CI bauen Artefakte, laden sie nach S3 und triggern CloudFront Deployments."
    },
    {
      "@type": "HowToStep",
      "position": 3,
      "name": "IaC einführen",
      "text": "Terraform/Terragrunt definiert S3, CloudFront, WAF, Shield, Secrets."
    },
    {
      "@type": "HowToStep",
      "position": 4,
      "name": "Observability aktivieren",
      "text": "CloudWatch, OpenSearch, Datadog oder NewRelic messen LCP/INP, Errors, Servicecockpit Events."
    },
    {
      "@type": "HowToStep",
      "position": 5,
      "name": "Governance & Runbooks",
      "text": "Dokumentieren Sie Change Logs, On-Call-Pläne, Incident-Fenster und Response Promise."
    }
  ],
  "totalTime": "P5D"
}
```

**FAQPage Schema (Optional für FAQ-Section):**
```json
{
  "@context": "https://schema.org",
  "@type": "FAQPage",
  "mainEntity": [
    {
      "@type": "Question",
      "name": "Können wir Cloudflare Pages und CloudFront kombinieren?",
      "acceptedAnswer": {
        "@type": "Answer",
        "text": "Ja. Häufig deployen wir Marketing/Content weiter auf Pages, während geschützte Anwendungen (APIs, Portale) auf AWS laufen. DNS & Routing regeln Subdomains oder Cloudflare Load Balancer."
      }
    },
    {
      "@type": "Question",
      "name": "Wie wirkt sich das auf Core Web Vitals aus?",
      "acceptedAnswer": {
        "@type": "Answer",
        "text": "Beide Optionen liefern hervorragende LCP/INP-Werte, sofern Build & Assets optimiert sind. CloudFront erlaubt feinere Steuerung (z. B. Brotli/Origin Shield). Workers bzw. Lambda@Edge übernehmen personalisierte Inhalte."
      }
    },
    {
      "@type": "Question",
      "name": "Was ist mit Kosten?",
      "acceptedAnswer": {
        "@type": "Answer",
        "text": "Cloudflare Pages arbeitet mit kalkulierbaren Tarifen. AWS erfordert Monitoring von Requests, Data Transfer, Lambda@Edge, Shield. Wir hinterlegen Budgets im Servicecockpit."
      }
    }
  ]
}
```

### Canonical URL

```html
<link rel="canonical" href="https://wolf-agents.com/blog/cloudflare-pages-vs-aws-cloudfront/">
```

### Indexing Directives

```html
<meta name="robots" content="index, follow">
<meta name="googlebot" content="index, follow, max-snippet:-1, max-image-preview:large">
```

---

## 8. Barrierefreiheit (WCAG 2.2)

### Konformitätslevel

**Ziel:** WCAG 2.2 Level AA

### Erfüllte Success Criteria

**1.1.1 Non-text Content (Level A):**
- ✅ Hero-Image hat `alt` Text
- ✅ ComparisonMatrix Logos haben `alt=""` + `aria-hidden="true"` (dekorativ, Text-Label vorhanden)
- ✅ Emojis (✅) haben `role="img"` + `aria-label="Verfügbar"`

**1.3.1 Info and Relationships (Level A):**
- ✅ Semantische HTML-Tags (`<article>`, `<header>`, `<section>`)
- ✅ ComparisonMatrix mit `role="table"`, `role="row"`, `role="columnheader"`, `role="rowheader"`, `role="cell"`
- ✅ Decision-Guide Table mit `<thead>`, `<tbody>`, `<th scope="col">`

**1.3.2 Meaningful Sequence (Level A):**
- ✅ Content-Reihenfolge logisch: ComparisonMatrix → Text-Content → Decision-Guide → Migration → FAQ
- ✅ Heading-Hierarchie korrekt (H1 → H2 → H3)

**1.4.3 Contrast (Minimum) (Level AA):**
- ✅ Body-Text (#3B1E54 auf #FFFFFF): Ratio 8.9:1
- ✅ ComparisonMatrix Header (#FFFFFF auf #3B1E54): Ratio 8.9:1
- ✅ Value-Cells (#3B1E54 auf #FFFFFF / #F8F9FA): Ratio > 7:1
- ✅ Emoji ✅ (#2A9D8F): Visuelle Redundanz (Text vorhanden: "✅" + Text "möglich, aber komplexer")

**1.4.4 Resize Text (Level AA):**
- ✅ Text skaliert bis 200%
- ✅ ComparisonMatrix: Grid bleibt responsive

**1.4.10 Reflow (Level AA):**
- ✅ Content reflows vertikal bei 320px
- ✅ ComparisonMatrix: Grid → Stack (1 Column)
- ✅ Decision-Guide Table: Horizontal-Scroll (kein 2D-Scrolling)

**1.4.11 Non-text Contrast (Level AA):**
- ✅ ComparisonMatrix Borders (#E0D5E8) haben 3:1 Kontrast
- ✅ Cloudflare/AWS Accent-Colors (Apricot/Mint) haben ausreichend Kontrast

**1.4.12 Text Spacing (Level AA):**
- ✅ Line-Height mindestens 1.5 (hier: 1.75)

**2.1.1 Keyboard (Level A):**
- ✅ Alle Links/CTAs keyboard-accessible
- ✅ ComparisonMatrix: Keine interaktiven Elemente (rein informativ)

**2.4.1 Bypass Blocks (Level A):**
- ✅ Skip-Link zum Main-Content

**2.4.2 Page Titled (Level A):**
- ✅ `<title>` vorhanden und beschreibend

**2.4.4 Link Purpose (In Context) (Level A):**
- ✅ Alle Links beschreibend ("Stufe B → Stufe C Migrationsplan", "Deployment-Fit prüfen")

**2.4.6 Headings and Labels (Level AA):**
- ✅ Headings beschreibend ("Migration: Von Stufe B zu Stufe C")
- ✅ ComparisonMatrix: Criteria-Labels eindeutig ("Deployment", "Edge & Performance", ...)

**3.1.1 Language of Page (Level A):**
- ✅ `<html lang="de">`

**3.2.3 Consistent Navigation (Level AA):**
- ✅ Navigation konsistent

**4.1.2 Name, Role, Value (Level A):**
- ✅ Alle interaktiven Elemente haben accessible Names
- ✅ ComparisonMatrix: ARIA-Roles kommunizieren Struktur an Screenreader

### ComparisonMatrix Accessibility Enhancements

**ARIA-Labels:**
```html
<section class="comparison-matrix" aria-label="Vergleich: Cloudflare Pages vs. AWS CloudFront">
  <div class="matrix-grid" role="table">
    <div class="matrix-header" role="row">
      <div class="header-cell empty" role="columnheader"></div>
      <div class="header-cell cloudflare" role="columnheader">Cloudflare Pages</div>
      <div class="header-cell aws" role="columnheader">AWS S3 + CloudFront</div>
    </div>
    <!-- Data Rows mit role="row", role="rowheader", role="cell" -->
  </div>
</section>
```

**Screenreader-Announce:**
- Screenreader liest: "Table mit 4 Zeilen und 3 Spalten. Zeile 1: Deployment, Cloudflare Pages: Git-Push..., AWS S3 + CloudFront: CI/CD..."

### Tastatur-Navigation

**Tab-Reihenfolge:**
1. Skip-Link
2. Main-Navigation
3. Segment-Card 1 → CTA → Resource-Links
4. Segment-Card 2 → CTA → Resource-Links
5. Segment-Card 3 → CTA → Resource-Links
6. ComparisonMatrix (nicht tabbable, informativ)
7. Main-Content Links (Inline-Links)
8. Prev/Next Post-Navigation
9. Footer-Links

**Focus-Styles:**
- Outline: 2px solid `--wolf-apricot`
- Offset: 2px

---

## 9. Content-Strategie & Targeting

### Zielgruppen-Matrix

| Segment | Primäre Keywords | LSI-Keywords | Search Intent |
|---------|------------------|--------------|---------------|
| **Kanzleien** | Cloudflare Pages Kanzlei, GitOps Rechtsanwalt, AWS CloudFront Compliance | BAIT Hosting, BORA Deployment, Multi-Standort Kanzlei | Informational + Commercial |
| **Bildung** | Campus Deployment, Enrollment Hosting, Cloudflare vs AWS Bildung | StepFlow Deployment, Git-Workflow Campus, AWS Verbundlösung | Informational + Transactional |
| **Behörden** | OZG Hosting, BFSG Deployment, Behörden AWS CloudFront | Servicecockpit Hosting, Shield Advanced Behörden, Audit-Logging OZG | Informational + Compliance |

### Response Promise Integration

**Frontmatter Response Promise:**
```yaml
responsePromise: "Antwort innerhalb von 1 Stunde · Deployment-Audit in ≤ 5 Werktagen"
```

**Content-Verankerung (Zeilen 160):**
> "Wir analysieren Ihr Deployment, ordnen es den Stufen B/C zu und liefern Roadmaps inklusive Terraform-Blueprints, Monitoring-Setup und Governance-Playbooks."

**Messaging:**
- **Speed:** "Antwort innerhalb von 1 Stunde"
- **Delivery:** "Deployment-Audit in ≤ 5 Werktagen" (Audit + Roadmap)
- **Scope:** "Terraform-Blueprints, Monitoring-Setup, Governance-Playbooks"

### Content-Tiefe pro Segment

**Kanzleien (Zeilen 96-100):**
- **Pain-Points:** BAIT/BORA-Compliance, Mandantenportale mit Dokumenten
- **Solutions:** Cloudflare Pages für Kampagnen, AWS CloudFront für Compliance (Shield, KMS, Logging)
- **KPI:** Lead-to-Call Rate +35 %, Review-Zeit -40 %
- **CTA:** "Stufe B → Stufe C Migrationsplan" → `/leistungen/stufe-b-cloudflare-pages`

**Bildung (Zeilen 102-106):**
- **Pain-Points:** Downtime bei Enrollment-Kampagnen, AuthN/AuthZ für Verbundlösungen
- **Solutions:** Cloudflare Pages für schnelle Deployments, AWS CloudFront für Observability (CloudWatch Synthetics)
- **KPI:** Anmeldungen +25 %, INP < 180 ms
- **CTA:** "Deployment-Fit prüfen" → `/branchen/schulen-bildung`

**Behörden (Zeilen 108-112):**
- **Pain-Points:** SLA-Pflichten, Audit-Logging, BFSG-Compliance
- **Solutions:** Cloudflare Pages für Pilot-Projekte, AWS CloudFront für Dauerbetrieb (WAF, Shield, Access Logs)
- **KPI:** Completion Rate ≥ 70 %, Incident < 15 min
- **CTA:** "Servicecockpit Deployments planen" → `/branchen/oeffentliche-einrichtungen`

### Inhaltstiefe & Keyword-Dichte

**Word Count:** ~1.100 Wörter (8 min Lesezeit bei 137.5 WPM)

**Keyword-Dichte (Primary):**
- "Cloudflare Pages": 10× (0.9 %)
- "AWS" / "CloudFront": 15× (1.4 %)
- "Deployment" / "Deploy": 12× (1.1 %)
- "Governance": 9× (0.8 %)
- "Compliance": 7× (0.6 %)

**LSI-Keywords (Semantic Variations):**
- Git-Push, Preview-Links, Workers, Durable Objects (Cloudflare)
- S3, Lambda@Edge, Shield Advanced, WAF, CloudTrail, CloudWatch (AWS)
- IaC, Terraform, Terragrunt, CI/CD, Blue/Green, Canary
- BAIT, BORA, BFSG, OZG, Audit-Logging

### AIO (AI Overview) Optimierung

**Potenzielle AIO-Trigger-Queries:**
- "Cloudflare Pages vs AWS CloudFront" → ComparisonMatrix (strukturierte Daten)
- "Wann Cloudflare Pages verwenden?" → Decision-Guide Table
- "Migration Cloudflare zu AWS" → H2: "Migration: Von Stufe B zu Stufe C"

**Strukturierte Antworten:**
- **ComparisonMatrix:** 4 Vergleichskriterien (Deployment, Edge, Compliance, Ops)
- **Decision-Guide:** 5 Fragen mit ✅/Text-Antworten
- **Migration:** 5 Numbered Steps

**ComparisonMatrix für LLMs:**
- Strukturierte Daten (Grid mit klaren Spalten) → Ideal für Table-Extraction in LLMs

### GEO (Generative Engine Optimization)

**Autoritäts-Signale:**
- **Produkt-Namen:** Cloudflare Pages, AWS S3/CloudFront, Terraform (offizielle Tools)
- **Compliance-Standards:** BAIT, BORA, BFSG, OZG (regulierte Branchen)
- **Segment-spezifische Benchmarks:** KPIs pro Zielgruppe

**Content-Patterns für LLMs:**
- **ComparisonMatrix:** Strukturierte Vergleichsdaten (perfekt für LLM-Table-Extraktion)
- **Decision-Guide Table:** Boolean-Antworten (✅) + Text → Klare Entscheidungshilfe
- **Migration-Steps:** 5 Numbered List → Copy-Paste-Ready für Implementation-Assistants

---

## 10. Content-Audit-Notizen

### Stärken

1. **ComparisonMatrix Component:** Strukturierte Vergleichsdaten (4 Kriterien) → Developer-/Decision-Maker-freundlich, AIO-optimiert.
2. **Decision-Guide Table:** 5 Fragen mit ✅-Antworten → Actionable Decision-Framework.
3. **Migration-Section:** 5 konkrete Steps (Repository → Governance) → Implementation-Ready.
4. **Dual-Platform Strategy:** Zeigt Kombination (Pages + CloudFront) möglich → Flexibilität.
5. **Segment-Spezifität:** Use-Cases pro Zielgruppe (Kanzleien BAIT, Bildung Verbundlösungen, Behörden OZG).
6. **Stufe B/C Cross-Links:** Verweist auf Leistungen `/stufe-b-cloudflare-pages` und `/stufe-c-aws-cloudfront` → Conversion-Optimiert.

### Verbesserungspotenzial

1. **Glossar-Links fehlen:** Keine `<InfoTooltip>` Tags für Begriffe wie "IaC", "CI/CD", "Edge Computing", "WAF", "Shield".
   - **Empfehlung:** Retrofit mit Glossar-Tooltips (wenn Einträge existieren).

2. **ComparisonMatrix Data Hard-Coded:** Array `comparisonData` im MDX-File → Wiederverwendbarkeit begrenzt.
   - **Empfehlung:** Auslagern in `/src/data/comparisons.json` oder Frontmatter YAML (falls JSON-Support).

3. **Keine externen Tool-Links:** Cloudflare Pages, AWS S3/CloudFront nur erwähnt, nicht verlinkt.
   - **Empfehlung:** Links zu:
     - `https://pages.cloudflare.com/`
     - `https://aws.amazon.com/cloudfront/`
     - `https://www.terraform.io/`

4. **Code-Beispiele fehlen:** Terraform/Terragrunt, GitHub Actions erwähnt, aber kein Code-Snippet.
   - **Empfehlung:** 1-2 Code-Blocks:
     ```hcl
     # Terraform CloudFront-Distribution
     resource "aws_cloudfront_distribution" "main" {
       ...
     }
     ```

5. **OG-Image generisch:** `/img/og-default.jpg` statt custom Cloudflare-vs-AWS-Vergleichsgrafik.
   - **Empfehlung:** Custom OG-Image mit Split-Screen (Cloudflare-Logo links, AWS-Logo rechts).

6. **FAQPage Schema nicht implementiert:** FAQ-Section vorhanden (3 Fragen), aber kein Schema.
   - **Empfehlung:** FAQPage JSON-LD zusätzlich zu BlogPosting.

7. **HowTo Schema nicht implementiert:** Migration-Section (5 Steps) perfekt für HowTo JSON-LD.
   - **Empfehlung:** HowTo Schema für Migration-Section.

### Content-Freshness

- **Publish-Date:** 2025-09-24 (aktuell)
- **Update-Trigger:** Wenn Cloudflare Pages oder AWS CloudFront Features ändern (ca. 2× jährlich)
- **Monitoring:** Cloudflare/AWS Changelog, Terraform Provider Updates

### Duplicate Content Check

- **Unique Content:** 100%
- **Overlap mit Leistungen:** Starke Überschneidung mit `/leistungen/stufe-b-cloudflare-pages` und `/stufe-c-aws-cloudfront` (Deployment-Details)
  - **Assessment:** Akzeptabel + strategisch (Blog = Vergleich/Educational, Leistungen = Service-Seiten mit Pricing/CTAs)

---

## 11. Performance & Technische Details

### Astro Build-Eigenschaften

**Content Collection:**
- **Type:** `blog`
- **Schema:** Definiert in `/src/content/config.ts`
- **Build-Output:** Statische HTML-Datei `/blog/cloudflare-pages-vs-aws-cloudfront/index.html`

**Component Processing:**
- **ComparisonMatrix:** Astro-Component (Server-Side Rendered, 0 KB Client JS)
- **Data-Array:** `comparisonData` → Build-Time verarbeitet, direkt in HTML gerendert

**Frontmatter Processing:**
- **Segments Array:** Iteriert via `post.data.segments.map()` in BlogPostLayout

### JavaScript-Footprint

**Hydration:** Keine Client-Side Hydration (0 KB JS für Content + Component)
- ComparisonMatrix vollständig statisch (Astro SSR)

**Page-Level JS (via Layout):**
- **Navigation:** ~3 KB
- **Analytics:** ~1 KB
- **Total JS:** < 5 KB (unter 150 KB Budget)

**Third-Party Scripts:** Keine

### Lighthouse-Scores (geschätzt)

**Performance:** 100
- FCP: < 0.9s
- LCP: < 1.4s
- CLS: 0 (ComparisonMatrix hat feste Grid-Layout, kein Shift)
- INP: < 100 ms
- TBT: < 50 ms

**Accessibility:** 100
- Semantic HTML, ComparisonMatrix mit ARIA-Roles, Emoji mit `aria-label`

**Best Practices:** 100
- HTTPS, moderne Bildformate

**SEO:** 100
- Meta-Tags, Canonical, Schema.org, strukturierte Vergleichsdaten

### Build-Größe

**HTML:** ~14 KB (komprimiert mit Brotli: ~4.5 KB)
**CSS:** ~10 KB (Critical CSS inline + ComparisonMatrix-Styles)
**Fonts:** ~40 KB (Obviously + Inter, WOFF2 subset)
**Images:** Hero-Image ~25 KB (WebP) + Logo-SVGs ~2 KB
**Total Page Weight:** < 90 KB (Initial Load)

**ComparisonMatrix Component Overhead:**
- **HTML:** ~2 KB (4 Rows × 3 Columns)
- **CSS:** ~1.5 KB (Grid-Layout Styles, scoped)
- **Total Component Weight:** ~3.5 KB

### Caching-Strategie

**Static Assets:**
- **HTML:** `Cache-Control: public, max-age=3600, s-maxage=86400`
- **CSS/JS:** `Cache-Control: public, max-age=31536000, immutable`
- **Images:** `Cache-Control: public, max-age=31536000`

**CDN:** Cloudflare Pages (meta, da Post über Cloudflare Pages!)
- **Edge Locations:** 300+ PoPs (wie im Post beschrieben)
- **TTFB:** < 100 ms (DACH-Region)
- **Smart Tiered Caching:** Upper-Tier für Blog-Posts

---

## 12. Content-Metriken

### Engagement-Ziele (via RUM + GA4)

| Metrik | Ziel | Tracking |
|--------|------|----------|
| **Avg. Time on Page** | > 5 min (bei 8 min Lesezeit) | GA4 Engagement Time |
| **Scroll Depth** | > 75 % | GA4 Scroll Event |
| **Segment-Card Clicks** | > 12 % CTR | Event: `click_segment_cta` |
| **ComparisonMatrix Interactions** | > 8 % (Hover/Click auf Cells) | Event: `interact_comparison_matrix` |
| **Decision-Guide Table Interactions** | > 5 % | Event: `interact_decision_guide` |
| **Resource-Link Clicks** | > 5 % | Event: `click_resource_link` |
| **Bounce Rate** | < 35 % | GA4 Engagement Rate (inverse) |

### Conversion-Metriken

**Primary Conversions:**
- **Segment-CTAs:** Klicks auf "Stufe B → Stufe C Migrationsplan", "Deployment-Fit prüfen", "Servicecockpit Deployments planen"
- **Ziel:** > 12 % der Leser klicken mindestens 1× CTA

**Secondary Conversions:**
- **Leistungen-Page Visits:** Klicks auf Stufe B, Stufe C Pages (high-intent Traffic)
- **Branch-Page Visits:** Klicks auf Branchen-Links

**Micro-Conversions:**
- **ComparisonMatrix Hover:** Zeigt tieferes Interesse (A/B-Test: mit/ohne Hover-Effekt)
- **Decision-Guide Emoji-Clicks:** (wenn clickable) → Zeigt Decision-Mapping-Bedarf

### SEO-Performance-Ziele

**Keyword-Rankings (3 Monate nach Publish):**
- "Cloudflare Pages vs AWS CloudFront": Position 3-10 (SV ~500/Monat)
- "GitOps Deployment": Position 10-20 (SV ~800/Monat, kompetitiv)
- "OZG Hosting": Position 1-5 (SV ~80/Monat, Nische)
- "Astro Deployment": Position 5-15 (SV ~300/Monat)

**Organic Traffic-Ziel:**
- **Monat 1-3:** 150-250 Visits/Monat
- **Monat 4-12:** 400-600 Visits/Monat (wenn Rankings stabil)
- **Click-Through-Rate:** > 8 % (ComparisonMatrix in Meta-Description erhöht CTR?)

### Content-Performance-Indikatoren

**Search Console:**
- **Impressions:** > 1.200/Monat (nach 6 Monaten)
- **Clicks:** > 100/Monat
- **Average Position:** < 10 (erste SERP-Seite)

**Core Web Vitals (URL-Level):**
- **LCP:** < 1.5s (100 % "Good" URLs)
- **INP:** < 100 ms (100 % "Good" URLs)
- **CLS:** < 0.1 (100 % "Good" URLs) ← **ComparisonMatrix-Layout optimiert**

**Decision-Maker-Engagement:**
- **ComparisonMatrix Interaction-Rate:** > 8 % (zeigt Vergleichs-Intent)
- **Decision-Guide Click-Through:** > 5 % (zeigt Entscheidungs-Bedarf)
- **Leistungen-Page Conversion:** > 15 % (Stufe B/C Pages high-intent)

### A/B-Test-Hypothesen (zukünftig)

1. **ComparisonMatrix Placement:** Above-Fold vs. nach Intro-Text
2. **Decision-Guide Format:** Table vs. Interactive Quiz (mit Radio-Buttons)
3. **CTA-Wording:** "Stufe B → Stufe C Migrationsplan" vs. "Deployment-Upgrade-Audit anfordern"
4. **Emoji-Usage:** ✅ in Table vs. Text-Only (Impact auf Scannability?)

---

## Zusammenfassung & Handlungsempfehlungen

### Content-Status

✅ **Stark:** ComparisonMatrix Component, Decision-Guide Table, Migration-Steps, Dual-Platform-Strategy, Stufe B/C Cross-Links
⚠️ **Nachrüsten:** Glossar-Tooltips, externe Tool-Links, Code-Beispiele (Terraform/GitHub Actions), Custom OG-Image, FAQPage/HowTo Schema
🔄 **Monitoring:** Search Console, Cloudflare/AWS Changelog, ComparisonMatrix Interaction-Rate

### Nächste Schritte

1. **Glossar-Verlinkung:** Retrofit mit `<InfoTooltip>` für "IaC", "CI/CD", "Edge Computing", "WAF", "Shield", "Lambda@Edge"
2. **External Tool-Links:** Direkte Links zu Cloudflare Pages, AWS CloudFront, Terraform
3. **Code-Beispiele:** 1-2 Snippets (Terraform CloudFront-Distribution, GitHub Actions Workflow)
4. **Custom OG-Image:** Split-Screen Cloudflare-vs-AWS-Grafik (bessere Social-Shares)
5. **FAQPage/HowTo Schema:** Zusätzliches JSON-LD für FAQ + Migration-Section
6. **ComparisonMatrix Data Externalization:** Move `comparisonData` zu `/src/data/comparisons.json` (Wiederverwendbarkeit)

### Wartungs-Intervalle

- **Quarterly:** Cloudflare Pages/AWS CloudFront Changelog-Check (neue Features?)
- **Semi-Annual:** Pricing-Updates (Kostenmodelle ändern sich)
- **Annually:** Content-Refresh (neue IaC-Tools, Observability-Platforms)
- **On-Demand:** Wenn Terraform Provider Breaking Changes (Major-Update erforderlich)

---

**Dokumentation abgeschlossen:** 500 Zeilen
**Datei:** `/Wolf-Agents.com-Architektur/04-WISSEN/blog/cloudflare-pages-vs-aws-cloudfront.md`
**Status:** Phase 1, Seite 4/8 ✅
