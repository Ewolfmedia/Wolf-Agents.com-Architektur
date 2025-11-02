# Stufe B · Cloudflare Multi-Site

**Verweis:** Siehe `/04-LEISTUNGEN/00-LEISTUNGEN-TEMPLATE.md` für gemeinsame Struktur und Design-Patterns.

---

## 📊 META-INFORMATIONEN

- **URL**: `/leistungen/stufe-b-cloudflare-pages`
- **Title**: `Stufe B · Cloudflare Multi-Site | Wolf-Agents`
- **Description**: `Git-basierte Deployments, globale Edge-Performance und Sicherheitslayer für Kanzleien, Bildung & Behörden. Preview-Links, Rollenrechte, Servicecockpit-Integrationen und Compliance-Logging inklusive.`
- **Geschätzte Wortanzahl**: ~2.300 Wörter
- **Geschätzte Lesedauer**: 9-10 Minuten
- **Anzahl Sections**: 7 Hauptsektionen
- **Anzahl Segment-Sections**: 2 – "Einsatzfelder & Outcomes" + "Segment-Szenarien & Governance-Benefits"
- **Kategorie**: Betriebsstufe

---

## 🏗️ HERO-BEREICH

### Badge
```
"Rollout in 6–8 Wochen"
```

### H1-Headline
```
"Stufe B · Cloudflare Multi-Site"
```

### Subtitle
```
Git-Previews, Edge-Caching, Rollen & Governance – ideal für Kanzleien mit mehreren Standorten, Campus-Teams und Bürgerdienste, die international verfügbar sein müssen.
```

### Primary CTA
- **Text**: "Projekt einordnen lassen"
- **Link**: `/kontakt`

### Secondary CTA
- **Text**: "Stufen vergleichen"
- **Link**: `/leistungen#stufen`

### Hero-Variante
- **Variant**: `dark-grid`
- **MinHeight**: `min-height:100vh;min-height:100dvh;`

---

## 🔙 ZURÜCK-NAVIGATION (Betriebsstufen-spezifisch)

**Link-Text**: "Zurück zur Übersicht"
**Link-Ziel**: `/leistungen`
**Icon**: Pfeil nach links (chevron-left)
**Styling**: `text-on-light-primary hover:text-on-light-primary transition-colors`

⚠️ **Besonderheit**: Nur Betriebsstufen haben diesen Zurück-Link! Fach-Module nicht.

---

## 📊 TL;DR + STATS

### TL;DR-Box

**Badge**: `TL;DR`

**H2-Headline**: `Globale Edge-Performance plus Git-Governance`

**Intro-Text**:
```
Stufe B kombiniert Astro mit Cloudflare Pages & Workers. Jede Änderung läuft über Git-Workflows, erhält Preview-Links, wird weltweit über das 300+ PoP-CDN ausgeliefert
und lässt sich mit Zero-Downtime deployen. Ideal für Teams mit mehreren Standorten, mehrsprachigen Inhalten, Servicecockpits und Compliance-Anforderungen.
```

**3 Checkmarks**:
1. ✅ **GitOps-Workflow** mit Preview-Deployments pro Branch, Review-Status, Comments und Release-Logs – perfekt für Kanzlei-Partner, Campus-Redaktionen & Behördenleitungen.
2. ✅ **Edge Caching, Smart Routing & Workers**: LCP ≤ 2,0 s weltweit, INP ≤ 200 ms, Response Time für APIs & Intake-Flows drastisch reduziert.
3. ✅ **Workers & KV/D1** für Intake, Formular-Validierung, Annahme-Status, Servicecockpit-APIs – inklusive Consent Mode v2 (InfoTooltip!) & Server-Side Tracking.

### Stats-Cards (3)

**Card 1: Go-Live**
- **Label**: `Go-Live`
- **Value**: `6–8 Wochen`
- **Context**: `Discovery, GitOps-Setup, Workers-Integrationen & QA – iterativ mit Preview-Reviews.`

**Card 2: CDN & Edge**
- **Label**: `CDN & Edge`
- **Value**: `300+ PoPs`
- **Context**: `Anycast Routing, Tiered Cache, HTTP/3, Brotli, Web Application Firewall, Bot Management.`

**Card 3: Segment-Kits**
- **Label**: `Segment-Kits`
- **Value**: `7+`
- **Context**: `Kanzlei, Bildung, Behörden, Industrie, Versicherungen: Multi-Site Navigation, StepFlow, Intake Dashboards.`

---

## 👥 SEGMENT USE CASES

### ⚠️ BESONDERHEIT: 2× SEGMENT-SECTIONS (Betriebsstufen)

Diese Seite hat **zwei separate Segment-Sections** (typisch für Betriebsstufen):

#### Section 1: "Einsatzfelder & Outcomes"
- **H2**: "Einsatzfelder & Outcomes"
- **Anzahl Cards**: 3
- **Card-Typ**: Standard Cards mit Badges (chip-light, chip-success, chip-brand)

#### Section 2: "Segment-Szenarien & Governance-Benefits"
- **H2**: "Segment-Szenarien & Governance-Benefits"
- **Intro**: "Mit Stufe B skalieren wir Git-basierte Workflows, Edge-Performance und Compliance für unterschiedliche Teams. Jede Plattform erhält klare KPI-Budgets, Servicecockpit-Anbindung und Dokumentation für Jour-fixe & Audits."
- **Anzahl Cards**: 3 (aus `segmentCases`-Array)

### Section 1: "Einsatzfelder & Outcomes" (3 Cards)

**Card 1: Kanzleien & Boutiquen**
- **Badge**: `Kanzleien & Boutiquen` (chip-light)
- **Title**: `Multi-Standort Kanzlei-Portale`
- **Description**: `Git-basierte Content-Freigaben, Intake-Workflows mit Workers, GEO-/AEO-Cluster, SLA für Lead-to-Call Rate +35 % und Response Time < 1 h.`

**Card 2: Schulen & Bildung**
- **Badge**: `Schulen & Bildung` (chip-success)
- **Title**: `Internationaler Campus-Hub`
- **Description**: `Mehrsprachige Programme, Austauschprojekte, Formular-Workflows, Live-Status via Workers, Integration in LMS/CRM über APIs.`

**Card 3: Behörden & Körperschaften**
- **Badge**: `Behörden & Körperschaften` (chip-brand)
- **Title**: `Top-Task Portal & Servicecockpit`
- **Description**: `Rollen & Rechte, Audit-Logs, Barrierefreiheit, Formular-Persistenz, KPI-Dashboards mit Workers KV/D1, Completion Rate ≥ 70 %.`

### Section 2: segmentCases-Array (für "Segment-Szenarien & Governance-Benefits")

**Segment 1: Kanzleien & Sozietäten**
- **KPI**: `Lead-to-Call Rate +35 % · GitOps Intake`
- **Title**: `Kanzleien & Sozietäten`
- **Description**: `Mehrere Standorte und Fachbereiche mit Rollen-Workflows, Preview-Links für Partner und Edge-optimierte Intake-Formulare.`
- **Link**: `/branchen/kanzleien`
- **Link-Label**: `Kanzlei-Blueprint ansehen`

**Segment 2: Schulen & Bildung**
- **KPI**: `Anmeldung in 3 Schritten · 99,9 % Uptime`
- **Title**: `Schulen & Bildung`
- **Description**: `Multi-Campus Plattformen mit StepFlow, Event-/Kursseiten, RUM-Tracking und globalem CDN für internationale Zielgruppen.`
- **Link**: `/branchen/schulen-bildung`
- **Link-Label**: `Enrollment-Guides öffnen`

**Segment 3: Behörden & öffentliche Dienste**
- **KPI**: `Digital Take-up ≥70 % · SLA Reporting`
- **Title**: `Behörden & öffentliche Dienste`
- **Description**: `Top-Task Portale mit Workers-APIs, Audit-Logging, WAF & Zero Trust Policies sowie KPI-Dashboards für Completion Rate & Zufriedenheit.`
- **Link**: `/branchen/oeffentliche-einrichtungen`
- **Link-Label**: `Behörden-Top Tasks prüfen`

---

## 📋 DELIVERABLES & PROJEKTABLAUF

### Deliverables

**H2**: "Lieferumfang & KPIs"

**4 Checkmarks**:
1. ✅ **Astro Islands + Headless CMS/MDX-Setup**, Cloudflare Workers Middleware, Auth, Rate Limiting & Logging.
2. ✅ **KPI-Budgets**: Lead-to-Call Rate +35 %, Completion Rate ≥ 70 %, Response Time < 1 h, Availability ≥ 99,9 %.
3. ✅ **Consent Mode v2** (InfoTooltip!), **RUM Monitoring** (InfoTooltip!), Error-Tracking & Alerting für Intake- und Service-Flows.
4. ✅ **Servicecockpit-Schnittstellen** (KV/D1/Queues) für Intake-Status, Completion Rate, Feedback-Widget & SLA Tracking.

### Governance & Sicherheit

**H2**: "Governance & Sicherheit"

**4 Checkmarks**:
1. ✅ **Rollen- & Rechteverwaltung** via Cloudflare Access, Audit-Logs, Adaptive MFA, Zero Trust Policies.
2. ✅ **Infrastructure-as-Code Templates** (Terraform, Wrangler), Secrets-Management, Preview/Prod-Policies.
3. ✅ **Security-Layer**: WAF, Bot Management, DDoS-Schutz, TLS 1.3, automatisches Zertifikat-Management & Logging.
4. ✅ **Schulungen & Playbooks** für Dev/Content/Ops: Git-Flows, Incident Response, KPI-Review, Servicecockpit.

### Projektablauf

**H2**: "Projektverlauf & Automatisierung"

**Anzahl Sprints**: 5 (Sprint 0-4) ⚠️ Betriebsstufen haben 5 Sprints, Fach-Module nur 4!

**Sprint 0**: Discovery & KPI Alignment
- Stakeholder-Interviews, KPI-Budgets, GitOps-Plan, Content & Data Mapping.

**Sprint 1**: Design System & Git Pipelines
- Tailwind Tokens, Komponenten, GitHub/Cloudflare Integration, CI/CD Scripts.

**Sprint 2**: Workers & Integrationen
- Intake-APIs, Servicecockpit-Anbindung, Monitoring, RUM & Consent.

**Sprint 3**: QA & Barrierefreiheit
- Lighthouse, axe, Pa11y, Security Tests, Load/SLA Checks, Preview Reviews.

**Sprint 4**: Launch & Enablement
- Go-Live, Analytics Dashboards, Governance Playbook, Team-Trainings, Upgrade Roadmap.

---

## 🔗 STAGE LINKS (Betriebsstufen-Navigation)

**H2**: "Nächster Schritt nach Stufe B"

**stageLinks-Array** (3 Cross-Links):

**Link 1: Stufe 0 – Rapid Response**
- **Label**: `Stufe 0 – Rapid Response`
- **Href**: `/leistungen/stufe-0-ftp-classic`
- **Description**: `≤ 10 Tage live auf bestehendem Hosting – ideal für Übergangs-Microsites und Kampagnen.`

**Link 2: Stufe A – Astro Knowledge Hub**
- **Label**: `Stufe A – Astro Knowledge Hub`
- **Href**: `/leistungen/stufe-a-astro-ftp`
- **Description**: `Modulare Astro-Plattform mit Content-Workflows, bereit für Git-Upgrade.`

**Link 3: Stufe C – AWS CloudFront**
- **Label**: `Stufe C – AWS CloudFront`
- **Href**: `/leistungen/stufe-c-aws-cloudfront`
- **Description**: `Enterprise Governance, Logging, Observability & SLA für mission-critical Services.`

⚠️ **Besonderheit**: Nur Betriebsstufen haben stageLinks! Fach-Module nicht.

---

## 🎯 FINAL CTA

**Component**: `ContentBoxDark`

**Heading** (H2): `Bereit für GitOps & Edge-Performance?`

**Description**:
```
Wir orchestrieren Ihren GitOps-Workflow, richten Workers & Security-Layer ein und begleiten Redaktion sowie Dev/IT-Teams – vom Training bis zur SLA-Evaluierung.
```

**Primary CTA**:
- **Text**: "Capability Call sichern"
- **Link**: `/kontakt`

**Secondary CTA**:
- **Text**: "Weitere Pakete ansehen"
- **Link**: `/leistungen`

---

## 🔍 BESONDERHEITEN

### 🎨 Betriebsstufen-Struktur
- ✅ **stageLinks-Array** (3 Cross-Links zu Stufe 0, A, C)
- ✅ **"Zurück zur Übersicht" Link** (nur Betriebsstufen!)
- ✅ **2× Segment-Sections** ("Einsatzfelder & Outcomes" + "Segment-Szenarien & Governance-Benefits")
- ✅ **5 Sprints** (Sprint 0-4, nicht nur 4 wie bei Fach-Modulen!)
- ✅ **Section tone="light"** (Stufe C hat tone="dark"!)

### 💡 InfoTooltip-Usage (HÖCHSTE DICHTE!)
- **Anzahl**: 2 ⚠️ (höchste InfoTooltip-Dichte aller Leistungs-Seiten!)
- **Term 1**: "Consent Mode v2" (in Deliverables-Section, Zeile 104)
  - **Usage**: `<InfoTooltip termId="consent-mode-v2" />`
  - **Context**: Workers & KV/D1 für Intake, inklusive Consent Mode v2 & Server-Side Tracking
- **Term 2**: "RUM Monitoring" (in Deliverables-Section, Zeile 168)
  - **Usage**: `<InfoTooltip termId="rum" />`
  - **Context**: Consent Mode v2, RUM Monitoring, Error-Tracking & Alerting

### 🛠️ Cloudflare-Stack
- **Cloudflare Pages**: Git-basierte Deployments, Preview-Links, Branch-Deployments
- **Cloudflare Workers**: Middleware, APIs, Intake-Validierung, Servicecockpit-Schnittstellen
- **Cloudflare KV/D1**: Key-Value Store, D1 (SQLite), Queues für Status-Persistenz
- **Cloudflare CDN**: 300+ PoPs, Anycast Routing, Tiered Cache, HTTP/3, Brotli
- **Cloudflare Access**: Rollen- & Rechteverwaltung, Adaptive MFA, Zero Trust Policies
- **Cloudflare WAF**: Web Application Firewall, Bot Management, DDoS-Schutz, Rate Limiting

### 📊 GitOps-Workflow
- **Preview-Deployments**: Jeder Branch erhält eigene Preview-URL
- **Review-Status**: Comments, Approvals, Release-Logs
- **CI/CD**: GitHub Actions Integration, automatisierte Tests
- **Rollback**: Zero-Downtime Deployments mit automatischem Rollback

### 📈 KPI-Fokus
- **Kanzleien**: Lead-to-Call Rate +35%, GitOps Intake, Response Time < 1 h
- **Bildung**: Anmeldung in 3 Schritten, 99,9% Uptime, RUM-Tracking
- **Behörden**: Digital Take-up ≥70%, SLA Reporting, Completion Rate ≥ 70%

### 🔒 Security-Layer
- **Cloudflare Access**: Zero Trust Policies, Adaptive MFA
- **WAF**: Managed Rules & Custom Rules
- **Bot Management**: Bot-Erkennung & -Abwehr
- **DDoS-Schutz**: Layer 3/4/7 DDoS Protection
- **TLS 1.3**: Automatisches Zertifikat-Management
- **Audit-Logs**: Zentrale Logging für Compliance

### 🔄 Upgrade-Pfade
- **Von Stufe A**: Migration von FTP/S3 zu Cloudflare Pages, Git-Workflow einführen
- **Zu Stufe C**: Upgrade zu AWS CloudFront für Enterprise-Governance, Observability, SLA

---

## 📊 CONTENT-AUDIT

### ✅ Stärken

1. **Höchste InfoTooltip-Dichte** – 2 InfoTooltips (Consent Mode v2 + RUM Monitoring) erklären moderne Tracking-Konzepte
2. **Cloudflare-Stack gut dokumentiert** – Workers, KV/D1, WAF, Bot Management, Access, CDN (300+ PoPs)
3. **GitOps-Workflow detailliert** – Preview-Deployments, Review-Status, CI/CD, Rollback
4. **Security-Layer umfassend** – WAF, Bot Management, DDoS, TLS 1.3, Zero Trust Policies
5. **2× Segment-Sections** – "Einsatzfelder & Outcomes" + "Segment-Szenarien & Governance-Benefits"
6. **Internationale Ausrichtung** – 300+ PoPs, Mehrsprachigkeit, globale Verfügbarkeit
7. **SLA-Garantien** – 99,9% Uptime, Response Time < 1 h

### ⚠️ Schwächen

1. **Cloudflare-Pricing fehlt** – Was kosten Workers, KV/D1, WAF? Budget-Range?
2. **Git-Kenntnisse vorausgesetzt** – Ist Git-Training Teil des Angebots?
3. **Vergleich zu Stufe A fehlt** – Wann lohnt sich Upgrade von Stufe A zu B?
4. **Team-Größe fehlt** – Wie viele Personen arbeiten in 6-8 Wochen?
5. **Case Studies fehlen** – Keine konkreten Erfolgsbeispiele

### ❌ Fehlende Elemente

1. **Weitere InfoTooltips** – "GitOps", "Workers", "KV/D1", "WAF", "Zero Trust" sollten erklärt werden
2. **Preis-Tabelle** – Budget-Range für 6-8 Wochen-Projekt + laufende Cloudflare-Kosten
3. **Upgrade-Kostenrechner** – Von Stufe A zu B: Was kostet der Umstieg?
4. **Git-Training** – Ist Git-Schulung Teil des Angebots?
5. **Performance-Vergleich** – Vorher (Stufe A) / Nachher (Stufe B) CDN-Metriken

### 🔴 Priorität: NIEDRIG

**Begründung**: Technische Nische, sehr niedriger Traffic. Wichtig für Skalierungs-Story, aber weniger SEO-relevant.

**Maßnahmen**:
1. **InfoTooltips ergänzen** – Mindestens 3 weitere InfoTooltips (GitOps, Workers, KV/D1)
2. **Case Study ergänzen** – Mindestens 1 konkretes Beispiel (z.B. Multi-Campus-Plattform mit 99,9% Uptime)
3. **Preis-Indikation** – Budget-Range + laufende Cloudflare-Kosten kommunizieren
4. **Upgrade-Rechner** – Von Stufe A zu B: Was ändert sich? Was kostet es?
5. **Git-Training** – Explizit kommunizieren, dass Git-Schulung Teil des Angebots ist

---

## 🎯 CONTENT-STRATEGIE

### Primäre Keywords
- `Cloudflare Pages` (niedriges Volumen, sehr spezifisch)
- `Cloudflare Workers` (niedriges Volumen)
- `GitOps` (mittleres Volumen)
- `Edge Computing` (mittleres Volumen)
- `CDN Performance` (niedriges Volumen)

### Sekundäre Keywords
- `Git-basierte Deployments`
- `Preview-Links`
- `Cloudflare KV`
- `Cloudflare D1`
- `Web Application Firewall`
- `Zero Trust Policies`
- `RUM Monitoring`

### Zielgruppe
- **Primär**: CTO, DevOps-Teams, IT-Leiter bei Kanzleien, Bildungseinrichtungen, Behörden mit internationaler Ausrichtung
- **Sekundär**: Tech-affine Digital Marketing Manager, Webmaster mit GitOps-Interesse

### User Intent
- **Informational**: Was ist Cloudflare Pages? Wie funktioniert GitOps?
- **Commercial Investigation**: Welche Agentur bietet Cloudflare-Integration für regulierte Branchen?
- **Transactional**: Projekt einordnen lassen, Capability Call sichern

### AIO/GEO/AEO-Status
- **AIO**: ⚠️ Teilweise – Content vorhanden, aber keine dedizierte FAQ-Section
- **GEO**: ✅ Optimiert – GEO-Cluster, Multi-Standort-Portale dokumentiert
- **AEO**: ✅ Optimiert – RUM Monitoring, Consent Mode v2, strukturierte Daten

---

## 📎 VERWANDTE SEITEN

- `/branchen/kanzleien` – Multi-Standort Kanzlei-Portale
- `/branchen/schulen-bildung` – Internationaler Campus-Hub
- `/branchen/oeffentliche-einrichtungen` – Top-Task Portal mit Workers-APIs
- `/leistungen/stufe-0-ftp-classic` – Rapid Response (Einstieg)
- `/leistungen/stufe-a-astro-ftp` – Astro Knowledge Hub (Vorgänger)
- `/leistungen/stufe-c-aws-cloudfront` – AWS CloudFront Governance (Nachfolger)
- `/leistungen/analytics-consent` – Consent Mode v2 Setup (InfoTooltip-Referenz)

---

**Dokumentiert am**: 2025-10-31
**Status**: ✅ Vollständig dokumentiert
**Review-Status**: 🟢 Priorität NIEDRIG – Weitere InfoTooltips + Case Study + Preis-Indikation optional ergänzen
