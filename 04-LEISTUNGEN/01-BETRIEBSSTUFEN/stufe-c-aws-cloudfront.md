# Stufe C · AWS CloudFront Governance Stack

**Verweis:** Siehe `/04-LEISTUNGEN/00-LEISTUNGEN-TEMPLATE.md` für gemeinsame Struktur und Design-Patterns.

---

## 📊 META-INFORMATIONEN

- **URL**: `/leistungen/stufe-c-aws-cloudfront`
- **Title**: `Stufe C · AWS CloudFront Governance Stack | Wolf-Agents`
- **Description**: `Enterprise-Plattform für streng regulierte Kanzleien, öffentliche Dienste und Bildungsträger: AWS CloudFront, WAF, Shield, IaC-Pipelines, Observability, SLA-gesteuerte Deployments und Compliance-Playbooks.`
- **Geschätzte Wortanzahl**: ~2.500 Wörter
- **Geschätzte Lesedauer**: 10-11 Minuten
- **Anzahl Sections**: 7 Hauptsektionen
- **Anzahl Segment-Sections**: 2 – "Einsatzfelder & Outcomes" + "Segment-Governance im Überblick"
- **Kategorie**: Betriebsstufe (Enterprise)

---

## 🏗️ HERO-BEREICH

### Badge
```
"Enterprise Launch in 8–12 Wochen"
```

### H1-Headline
```
"Stufe C · Governance & SLA Ready"
```

### Subtitle
```
AWS CloudFront, WAF, Shield, Observability und Compliance-Playbooks – für Kanzleien, Behörden und Bildungsträger mit höchsten Sicherheits- und Verfügbarkeitsanforderungen.
```

### Primary CTA
- **Text**: "Governance-Workshop sichern"
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
**Styling**: `text-gray-300 hover:text-white transition-colors` ⚠️

⚠️ **WICHTIG**: Wegen `Section tone="dark"` verwendet der Zurück-Link **text-gray-300** statt `text-on-light-primary`!

---

## 🌑 SECTION DARK (EINZIGARTIGE BESONDERHEIT!)

⚠️ **KRITISCH**: Stufe C ist die **EINZIGE Leistungs-Seite** mit `<Section tone="dark">`!

- **Alle anderen Leistungen**: `tone="light"`
- **Nur Stufe C**: `tone="dark"`

### Auswirkungen auf Styling:
- **Background**: Dunkler Hintergrund (surface-dark)
- **Text**: Weiß/Hell (text-white, text-slate-100/85)
- **Cards**: `surface-light-alpha-05` mit `border-on-dark-subtle`
- **Badges**: `surface-light-alpha-08` mit `text-on-dark-secondary`
- **Zurück-Link**: `text-gray-300` statt `text-on-light-primary`
- **Checkmarks**: `text-gray-300` statt `text-on-light-primary`
- **Shadows**: Dunklere Schatten (rgba(5,10,30,0.75))

---

## 📊 TL;DR + STATS

### TL;DR-Box

**Badge**: `TL;DR` (surface-light-alpha-08, text-on-dark-secondary)

**H2-Headline**: `Compliance, Observability, Skalierung ohne Kompromisse`

**Intro-Text**:
```
Stufe C ist unser AWS-basierter Governance-Stack: CloudFront, S3, Lambda@Edge, WAF, Shield Advanced, KMS und vollautomatisierte IaC-Pipelines.
Für Kanzleien mit BAIT/GoBD-Vorgaben, Behörden mit BFSG/BITV-Anforderungen und Bildungseinrichtungen mit Auditpflichten – inklusive SLA, Incident-Playbooks und 24/7 Monitoring-Hand-off.
```

**3 Checkmarks** (text-gray-300 wegen dark tone!):
1. ✅ **Infrastructure-as-Code** (Terraform/Terragrunt), GitOps Pipelines, Blue/Green & Canary Releases, automatisierte Tests sowie Secrets- und Key-Management.
2. ✅ **Observability & Security Layers**: CloudWatch, OpenSearch, GuardDuty, Security Hub, zentrale Audit-Logs, Compliance Dashboards und KPI-Playbooks.
3. ✅ **SLA-Modelle** (99,9–99,99 %), Incident-Response Playbooks, On-Call Übergabe, Servicecockpit Integration sowie Real User & Synthetic Monitoring.

### Stats-Cards (3)

**Card 1: Go-Live**
- **Label**: `Go-Live` (text-on-dark-secondary)
- **Value**: `8–12 Wochen` (text-white)
- **Context**: `Discovery, IaC, Security Layers, Observability, QA & Runbooks – gemeinsam mit Ihrem IT/Legal-Team.` (text-slate-100/70)

**Card 2: Compliance**
- **Label**: `Compliance` (text-on-dark-secondary)
- **Value**: `Audit Ready` (text-white)
- **Context**: `BAIT, GoBD, BFSG, BITV, ISO 27001, DSGVO: Policies, Logs, Reports & Nachweise.` (text-slate-100/70)

**Card 3: Segment-Kits**
- **Label**: `Segment-Kits` (text-on-dark-secondary)
- **Value**: `9+` (text-white)
- **Context**: `Kanzlei, Behörden, Bildung, Gesundheitswesen, Versicherer: Governance Guides, KPI-Module, Servicecockpits.` (text-slate-100/70)

---

## 👥 SEGMENT USE CASES

### ⚠️ BESONDERHEIT: 2× SEGMENT-SECTIONS (Betriebsstufen)

Diese Seite hat **zwei separate Segment-Sections** (typisch für Betriebsstufen):

#### Section 1: "Einsatzfelder & Outcomes"
- **H2**: "Einsatzfelder & Outcomes" (text-white)
- **Anzahl Cards**: 3
- **Card-Typ**: Dark Cards mit `surface-light-alpha-05`, `border-on-dark-subtle`, `text-white`

#### Section 2: "Segment-Governance im Überblick"
- **H2**: "Segment-Governance im Überblick" (text-white)
- **Intro**: "Für jede Branche definieren wir Sicherheits-, Compliance- und KPI-Anforderungen. Die folgenden Beispiele zeigen, wie Stufe C auf Kanzlei-, Campus- und Behördenziele einzahlt." (text-slate-200/85)
- **Anzahl Cards**: 3 (aus `segmentCases`-Array)

### Section 1: "Einsatzfelder & Outcomes" (3 Cards)

**Card 1: Kanzleien & Corporate**
- **Badge**: `Kanzleien & Corporate` (surface-light-alpha-08, text-on-dark-secondary, uppercase)
- **Title**: `Mandatsplattform mit Audit-Trail` (text-white)
- **Description**: `Mandantenportale, verschlüsselte Uploads, DMS/CRM-Integrationen, KMS, CloudTrail Logs, WORM Backups – Lead-to-Call Rate +35 %, SLA 99,95 %.` (text-slate-100/80)

**Card 2: Behörden & Körperschaften**
- **Badge**: `Behörden & Körperschaften` (surface-light-alpha-08, text-on-dark-secondary, uppercase)
- **Title**: `Bürgerdienste mit BFSG & GRC` (text-white)
- **Description**: `OZG-konforme Dienste, StepFlow, Servicecockpit, eID/De-Mail Integrationen, Service Monitoring, zertifizierte Deployment-Protokolle.` (text-slate-100/80)

**Card 3: Bildung & Forschung**
- **Badge**: `Bildung & Forschung` (surface-light-alpha-08, text-on-dark-secondary, uppercase)
- **Title**: `Campus & Research Platform` (text-white)
- **Description**: `Multi-Campus Seiten, Zugriffssicherheit, Observability, automatisierte Zertifikate, SLA & Incident Management – Completion Rate ≥ 75 %.` (text-slate-100/80)

### Section 2: segmentCases-Array (für "Segment-Governance im Überblick")

**Segment 1: Kanzleien & Legal Ops**
- **KPI**: `Availability ≥ 99,95 % · SLA Audits`
- **Title**: `Kanzleien & Legal Ops`
- **Description**: `Mandantenportale und Knowledge Hubs mit BAIT/BORA-Compliance, Audit-Logs, verschlüsselter Ablage und Incident-Playbooks.`
- **Link**: `/branchen/kanzleien`
- **Link-Label**: `Kanzlei-Governance ansehen`

**Segment 2: Schulen & Hochschulen**
- **KPI**: `INP ≤ 200 ms · Enrollment Security`
- **Title**: `Schulen & Hochschulen`
- **Description**: `Globale Bewerbungssysteme, CloudFront Edge Authorisation, DSGVO-konformes Logging und Observability für Peaks (Bewerbungsphasen).`
- **Link**: `/branchen/schulen-bildung`
- **Link-Label**: `Campus-Plattformen prüfen`

**Segment 3: Behörden & öffentliche Dienste**
- **KPI**: `Completion Rate ≥ 75 % · Incident ≤ 15 min`
- **Title**: `Behörden & öffentliche Dienste`
- **Description**: `BFSG/BITV-geprüfte Bürgerdienste mit WAF, Shield Advanced, SOC-Integration, Servicecockpit Dashboards und OZG-konformen Logs.`
- **Link**: `/branchen/oeffentliche-einrichtungen`
- **Link-Label**: `Behörden-Top Tasks prüfen`

---

## 📋 DELIVERABLES & PROJEKTABLAUF

### Deliverables

**H2**: "Lieferumfang & KPIs" (text-white)

**4 Checkmarks** (text-on-dark-secondary wegen dark tone!):
1. ✅ **AWS Landing Zone** (Organizations, Accounts, IAM, KMS), Terraform/Terragrunt Repos, GitOps Pipelines, Policy-as-Code.
2. ✅ **KPI-Budgets**: Completion Rate ≥ 75 %, Availability ≥ 99,95 %, INP ≤ 200 ms, Incident Response ≤ 15 min, Recovery Time ≤ 30 min.
3. ✅ **Observability Stack**: CloudWatch, Logs Insights, X-Ray, OpenTelemetry, RUM Monitoring, Synthetic Tests, SLA Dashboards.
4. ✅ **Data & Servicecockpit Pipelines**: Glue/Athena, QuickSight/Looker, KPI-Backups, Consent/Event Streaming, Compliance Reports.

### Governance & Sicherheit

**H2**: "Governance & Sicherheit" (text-white)

**4 Checkmarks** (text-on-dark-secondary wegen dark tone!):
1. ✅ **Zero Trust Policies**, IAM Permission Boundaries, SSO/SCIM, GuardDuty, Security Hub, AWS Config, Conformance Packs.
2. ✅ **WAF** (Managed Rules & Custom Rules), Bot Management, Rate Limiting, Token-Autorisierung, Secrets Manager, KMS CMK Rotation.
3. ✅ **Incident Response Playbooks**, SIEM Integration, Drills, Reporting für Aufsichtsbehörden, Audit-Dashboards & Runbooks.
4. ✅ **Schulungen & Enablement**: DevSecOps, Monitoring, Compliance-Reporting, Servicecockpit, KPI Reviews.

### Projektablauf

**H2**: "Projektverlauf & SLA-Implementierung" (text-white)

**Anzahl Sprints**: 5 (Sprint 0-4) ⚠️ Betriebsstufen haben 5 Sprints, Fach-Module nur 4!

**Sprint 0**: Governance Discovery
- Audit, Risikoanalyse, Compliance Scope, SLA/KPI Definition, Stakeholder Alignment.

**Sprint 1**: Landing Zone & IaC
- Accounts, IAM, KMS, Terraform/Terragrunt Setup, Security Baselines, GitOps Flows.

**Sprint 2**: App & Workers Integrationen
- Astro Artefakte, Lambda@Edge, API Gateway, Workers, Servicecockpit, Consent/Tracking.

**Sprint 3**: Observability & Security Validation
- CloudWatch + OpenTelemetry, WAF Tests, Pen-Test Coordination, Performance & Availability Checks.

**Sprint 4**: Launch, SLA & Übergabe
- Go-Live, Runbooks, On-Call Übergabe, Servicecockpit KPIs, Compliance Report, Uptime Guarantees.

---

## 🔗 STAGE LINKS (Betriebsstufen-Navigation)

**H2**: "Nächster Schritt nach Stufe C" (text-white)

**stageLinks-Array** (3 Cross-Links):

**Link 1: Stufe 0 – Rapid Response**
- **Label**: `Stufe 0 – Rapid Response` (text-white)
- **Href**: `/leistungen/stufe-0-ftp-classic`
- **Description**: `≤ 10 Tage live auf bestehendem Hosting – ideal für Übergangs-Microsites und Kampagnen.` (text-slate-100/80)

**Link 2: Stufe A – Astro Knowledge Hub**
- **Label**: `Stufe A – Astro Knowledge Hub` (text-white)
- **Href**: `/leistungen/stufe-a-astro-ftp`
- **Description**: `Modulare Astro-Plattform mit Content-Workflows, bereit für Git-Upgrade.` (text-slate-100/80)

**Link 3: Stufe B – Cloudflare Multi-Site**
- **Label**: `Stufe B – Cloudflare Multi-Site` (text-white)
- **Href**: `/leistungen/stufe-b-cloudflare-pages`
- **Description**: `Git-Previews, Edge-Caching und Workers-Integrationen für internationale Rollouts.` (text-slate-100/80)

⚠️ **Besonderheit**: Nur Betriebsstufen haben stageLinks! Fach-Module nicht.

---

## 🎯 FINAL CTA

**Component**: `ContentBoxDark`

**Heading** (H2): `Enterprise-Rollout planen?`

**Description**:
```
Wir bauen Governance-Frameworks, richten Observability & Security ein und begleiten Ihre Teams in Runbooks, Incident Handling und KPI-Review. Auf Wunsch übernehmen wir den Betrieb, bis Ihr internes Team bereit ist.
```

**Primary CTA**:
- **Text**: "Governance Call buchen"
- **Link**: `/kontakt`

**Secondary CTA**:
- **Text**: "Weitere Pakete ansehen"
- **Link**: `/leistungen`

---

## 🔍 BESONDERHEITEN

### 🌑 SECTION DARK (EINZIGARTIG!)
⚠️ **KRITISCH**: Stufe C ist die **EINZIGE Leistungs-Seite** mit `<Section tone="dark">`!

**Auswirkungen**:
- **Background**: Dunkler Hintergrund statt hellem Surface
- **Text-Colors**: `text-white`, `text-slate-100/85`, `text-slate-200/85`
- **Cards**: `surface-light-alpha-05` mit `border-on-dark-subtle`
- **Badges**: `surface-light-alpha-08` mit `text-on-dark-secondary`
- **Zurück-Link**: `text-gray-300 hover:text-white` (statt `text-on-light-primary`)
- **Checkmarks**: `text-gray-300` oder `text-on-dark-secondary` (statt `text-on-light-primary`)
- **Shadows**: Dunklere Schatten wie `rgba(5,10,30,0.75)`

**Begründung**: Enterprise-Ausrichtung, Premium-Positionierung, Security-Fokus rechtfertigt dunkles Design.

### 🎨 Betriebsstufen-Struktur
- ✅ **stageLinks-Array** (3 Cross-Links zu Stufe 0, A, B)
- ✅ **"Zurück zur Übersicht" Link** (mit `text-gray-300` wegen dark tone!)
- ✅ **2× Segment-Sections** ("Einsatzfelder & Outcomes" + "Segment-Governance im Überblick")
- ✅ **5 Sprints** (Sprint 0-4, nicht nur 4 wie bei Fach-Modulen!)
- ✅ **Section tone="dark"** (EINZIGARTIG!)

### 💡 InfoTooltip-Usage
- **Anzahl**: 0 ⚠️
- **Begründung**: Enterprise-Zielgruppe (CTOs, CIOs) benötigt keine Tooltips für Fachbegriffe
- **Alternative**: Ausführliche Beschreibungen statt Tooltips

### 🛠️ AWS-Stack
- **AWS CloudFront**: CDN, Edge Locations, Lambda@Edge
- **AWS S3**: Static Hosting, Bucket Policies, Encryption
- **AWS WAF**: Web Application Firewall, Managed Rules, Custom Rules
- **AWS Shield Advanced**: DDoS Protection, 24/7 DDoS Response Team
- **AWS Lambda@Edge**: Edge Computing, Request/Response Manipulation
- **AWS KMS**: Key Management Service, CMK Rotation, Encryption
- **AWS CloudWatch**: Monitoring, Logs, Alarms, Dashboards
- **AWS GuardDuty**: Threat Detection, Machine Learning
- **AWS Security Hub**: Central Security Management, Compliance Dashboards
- **AWS Config**: Configuration Management, Conformance Packs
- **AWS Secrets Manager**: Secrets Rotation, Encryption
- **AWS CloudTrail**: Audit Logs, Governance, Compliance
- **AWS IAM**: Identity & Access Management, Permission Boundaries, SSO/SCIM

### 📊 Compliance-Standards
- **BAIT**: Bankaufsichtliche Anforderungen an die IT
- **GoBD**: Grundsätze zur ordnungsmäßigen Führung und Aufbewahrung von Büchern
- **BFSG**: Barrierefreiheitsstärkungsgesetz (ab 2025)
- **BITV**: Barrierefreie-Informationstechnik-Verordnung
- **ISO 27001**: Informationssicherheits-Managementsystem
- **DSGVO**: Datenschutz-Grundverordnung
- **OZG**: Onlinezugangsgesetz (Behörden)

### 📈 SLA-Garantien
- **Availability**: 99,9–99,99% Verfügbarkeit
- **Incident Response**: ≤ 15 min
- **Recovery Time**: ≤ 30 min
- **Completion Rate**: ≥ 75%
- **Performance**: INP ≤ 200 ms

### 🔒 Security-Layer
- **Zero Trust Policies**: SSO/SCIM, Adaptive MFA
- **WAF**: Managed Rules, Custom Rules, Bot Management
- **DDoS-Schutz**: Shield Advanced, Layer 3/4/7
- **Encryption**: KMS, CMK Rotation, S3 Encryption
- **Audit-Logs**: CloudTrail, Zentrale Logging
- **Threat Detection**: GuardDuty, Security Hub

### 💼 Enterprise-Fokus
- **Zielgruppe**: CTOs, CIOs, Legal Ops, Compliance-Teams
- **Preis**: Premium-Tier (sehr teuer, höchster Aufwand)
- **Timeline**: 8–12 Wochen (längste Implementierung)
- **Team**: Größtes Team (DevSecOps, Compliance, Legal)
- **Support**: 24/7 Monitoring-Hand-off, On-Call Übergabe

### 🔄 IaC & GitOps
- **Terraform/Terragrunt**: Infrastructure-as-Code
- **GitOps Pipelines**: Automatisierte Deployments
- **Blue/Green**: Zero-Downtime Deployments
- **Canary Releases**: Schrittweise Rollouts
- **Policy-as-Code**: Automatisierte Compliance-Checks

---

## 📊 CONTENT-AUDIT

### ✅ Stärken

1. **Section Dark** – Einzigartiges dunkles Design hebt Enterprise-Positionierung hervor
2. **Umfassender AWS-Stack** – 13 AWS-Services dokumentiert (CloudFront, S3, Lambda@Edge, WAF, Shield, KMS, CloudWatch, GuardDuty, Security Hub, Config, Secrets Manager, CloudTrail, IAM)
3. **6 Compliance-Standards** – BAIT, GoBD, BFSG, BITV, ISO 27001, DSGVO vollständig dokumentiert
4. **SLA-Garantien** – 99,9–99,99% Availability, Incident Response ≤ 15 min, Recovery Time ≤ 30 min
5. **2× Segment-Sections** – "Einsatzfelder & Outcomes" + "Segment-Governance im Überblick"
6. **Enterprise-Zielgruppe** – CTOs, CIOs, Legal Ops, Compliance-Teams klar adressiert
7. **IaC & GitOps** – Terraform/Terragrunt, Blue/Green, Canary Releases dokumentiert

### ⚠️ Schwächen

1. **Keine InfoTooltips** – Enterprise-Zielgruppe braucht evtl. keine Tooltips, aber einige Begriffe (BAIT, GoBD, OZG) könnten erklärt werden
2. **AWS-Pricing fehlt** – Enterprise-Tier = Premium-Preis, aber keine Budget-Range
3. **Team-Größe fehlt** – Wie viele Personen arbeiten in 8-12 Wochen?
4. **Case Studies fehlen** – Keine konkreten Erfolgsbeispiele (aus Vertraulichkeitsgründen?)
5. **SLA-Kosten fehlen** – Was kostet 99,9% vs. 99,99% Availability?

### ❌ Fehlende Elemente

1. **InfoTooltips** – Optional: "BAIT", "GoBD", "OZG", "WORM Backups" könnten erklärt werden
2. **Preis-Indikation** – Enterprise-Budget-Range (z.B. "Ab 50.000 €")
3. **ROI-Kalkulation** – Wann amortisiert sich die Investition?
4. **Vergleich zu Stufe B** – Wann lohnt sich Upgrade von B zu C?
5. **Managed Service Option** – Kann Wolf-Agents den Betrieb übernehmen?

### 🔴 Priorität: NIEDRIG

**Begründung**: Enterprise-Nische, sehr niedriger Traffic, höchster Preis, kleinste Zielgruppe. Wichtig für Vollständigkeit der Skalierungs-Story, aber wenig SEO-relevant.

**Maßnahmen**:
1. **Case Study ergänzen** – Mindestens 1 konkretes Beispiel (anonymisiert, z.B. "Großkanzlei mit BAIT-Compliance")
2. **Preis-Indikation** – Enterprise-Budget-Range kommunizieren
3. **Vergleichstabelle** – Stufe A vs. B vs. C in Tabelle
4. **Managed Service** – Explizit kommunizieren, dass On-Call-Support möglich ist
5. **Optional InfoTooltips** – Für regulatorische Begriffe (BAIT, GoBD, OZG)

---

## 🎯 CONTENT-STRATEGIE

### Primäre Keywords
- `AWS CloudFront` (niedriges Volumen, sehr spezifisch)
- `Enterprise Web Hosting` (niedriges Volumen)
- `Compliance Web Platform` (niedriges Volumen)
- `BAIT Compliance` (Nischen-Keyword)
- `GoBD Compliance` (Nischen-Keyword)

### Sekundäre Keywords
- `Lambda@Edge`
- `AWS WAF`
- `AWS Shield Advanced`
- `Infrastructure-as-Code`
- `GitOps`
- `Zero Trust Policies`
- `SLA 99,99%`

### Zielgruppe
- **Primär**: CTO, CIO, CISO bei Großkanzleien, Behörden, Bildungseinrichtungen mit höchsten Sicherheits-/Compliance-Anforderungen
- **Sekundär**: Legal Ops, Compliance-Manager, IT-Security-Teams

### User Intent
- **Informational**: Was ist BAIT-Compliance? Wie funktioniert AWS CloudFront?
- **Commercial Investigation**: Welche Agentur bietet Enterprise-AWS-Integration für regulierte Branchen?
- **Transactional**: Governance-Workshop sichern, Governance Call buchen

### AIO/GEO/AEO-Status
- **AIO**: ⚠️ Teilweise – Content vorhanden, aber keine dedizierte FAQ-Section
- **GEO**: ❌ Nicht relevant – Enterprise-Plattformen sind nicht lokal gebunden
- **AEO**: ⚠️ Teilweise – Compliance-Standards dokumentiert, aber keine FAQ/HowTo Schema

---

## 📎 VERWANDTE SEITEN

- `/branchen/kanzleien` – Kanzlei-Governance mit BAIT/BORA-Compliance
- `/branchen/schulen-bildung` – Campus & Research Platform
- `/branchen/oeffentliche-einrichtungen` – Bürgerdienste mit BFSG & OZG
- `/leistungen/stufe-0-ftp-classic` – Rapid Response (Einstieg)
- `/leistungen/stufe-a-astro-ftp` – Astro Knowledge Hub (Basis)
- `/leistungen/stufe-b-cloudflare-pages` – Cloudflare Multi-Site (Vorgänger)
- `/leistungen/barrierefreiheit-bfsg` – BFSG-Compliance (Barrierefreiheit)

---

**Dokumentiert am**: 2025-10-31
**Status**: ✅ Vollständig dokumentiert
**Review-Status**: 🟢 Priorität NIEDRIG – Case Study + Preis-Indikation + Vergleichstabelle optional ergänzen
