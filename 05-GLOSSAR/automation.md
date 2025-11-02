# Automation

## 📊 META-INFORMATIONEN

- **Term ID**: `automation`
- **Begriff (DE)**: Automation / Automationen
- **Begriff (EN)**: Automation
- **Kategorie**: Operations & Delivery
- **Status**: ⚠️ Implementiert, aber nicht verwendet (0×)
- **Letzte Review**: 2025-10-25

---

## 💡 INFOTOOLTIP-DEFINITION

**Was sind Automationen?** Workflows und Skripte, die wiederkehrende Aufgaben automatisch erledigen – von Formular-Nachfass bis CRM-Updates – und so Zeit sparen und Fehler reduzieren.

---

## 📖 AUSFÜHRLICHE ERKLÄRUNG

Automationen (Workflows, Skripte, Integrationen) übernehmen wiederkehrende Aufgaben – von Intake-Nachfass bis Formularrouting – und sichern konsistente KPIs. Automationen sind Skripte, API-Flows oder Plattform-Workflows, die wiederkehrende Aufgaben zuverlässig ausführen. Im Kontext unserer Projekte bedeuten sie: weniger manuelle Nacharbeit, konsistente Daten und nachvollziehbare Prozesse.

Praxisbeispiele für Automationen:

- **Mandanten-Nachfass:** Intake-Formular abgeschlossen? Automation verschickt per Resend oder Twilio Follow-up-E-Mails und SMS, dokumentiert dies im CRM und erinnert das Team, wenn keine Reaktion erfolgt
- **Content-Generation:** Python-Skripte erzeugen strukturierte Produkttexte inklusive SEO-Metadaten oder aktualisieren zentrale FAQ-Bausteine
- **Formular-Weiterleitungen:** Cloudflare Workers verarbeiten Uploads, reichern sie mit Metadaten an und speichern sie revisionssicher in DMS oder Storage-Systemen

Für Kanzleien bedeutet Automation: Response Promise einhalten, ohne Personenstunden zu verbrennen. Für Bildungseinrichtungen: Enrollment Journeys bleiben in 3 Schritten, auch bei Spitzen. Für Behörden: Bürgerdienste dokumentieren jeden Schritt auditierbar.

Die Implementierung erfolgt über Workflow-Kandidaten priorisieren (manuelle Schritte identifizieren und nach Impact vs. Aufwand bewerten), Toolchain festlegen (Serverless, iPaaS, CRM-Automationen oder eigene Scripts) und Governance & Logging sichern (jede Automation dokumentiert Input, Output, Fehlerstatus).

### Warum ist es wichtig?

Automationen sind das Bindeglied zwischen Website/WebApp und Backoffice-Prozessen:

- **Zeit sparen:** Wiederkehrende Aufgaben laufen automatisch (Nachfass, Datenpflege, Rückmeldungen)
- **Fehler reduzieren:** Automatisierte Prozesse sind konsistenter als manuelle Schritte
- **KPIs steigern:** Lead-to-Call-Rate, Completion Rate und Digital Take-up steigen nachhaltig
- **Compliance:** Auditierbare Prozesse (Input, Output, Fehlerstatus dokumentiert)

Für regulierte Branchen (Kanzleien, Bildungseinrichtungen, Behörden) sind Automationen unverzichtbar für skalierbare, compliance-konforme Prozesse.

### Typische Anwendungsfälle

- **Use Case 1: Kanzlei-Intake-Nachfass** — Intake-Follow-ups, CRM-Syncs und Mandats-Statusmeldungen laufen automatisch – dokumentiert im Servicecockpit. Response Promise einhalten, ohne Personenstunden zu verbrennen.
- **Use Case 2: Enrollment-Workflows** — Formularrouting, Wartelisten, Payment-Status und Elternkommunikation laufen über Workers/Zapier/Make – KPIs landen im Dashboard. Enrollment Journeys bleiben in 3 Schritten, auch bei Spitzen.
- **Use Case 3: Behörden-Servicecockpit** — Servicecockpit, Formular-Weiterleitungen, Reminder für Dokumente oder Fristen automatisieren OZG-/BFSG-konforme Prozesse. Bürgerdienste dokumentieren jeden Schritt auditierbar.

---

## 🔗 VERWANDTE BEGRIFFE

- **Siehe auch**: GitOps, Consent Mode v2, Servicecockpit, CLI-first Delivery
- **Unterschied zu**: Manuelle Prozesse, Ad-hoc-Skripte (Automationen = versioniert, dokumentiert, auditierbar)
- **Übergeordnet**: Operations, DevOps, Business Process Automation
- **Untergeordnet**: Serverless Functions, iPaaS (Zapier, Make), CRM-Automationen, Cron Jobs

---

## 📍 VERWENDUNG AUF DER WEBSITE

### InfoTooltip-Verwendung (0×)

⚠️ **Nicht verwendet** — Empfehlung: InfoTooltip auf folgenden Seiten hinzufügen:
- `/leistungen/analytics-consent` (Intake-Automationen)
- `/leistungen/stufe-b-cloudflare-pages` (Workers für Automationen)
- `/leistungen/stufe-c-aws-cloudfront` (Lambda für Automationen)

### Erwähnungen ohne InfoTooltip

- `/leistungen/analytics-consent` — Automationen für Intake & Consent erwähnt
- `/branchen/kanzleien` — Mandanten-Nachfass-Automationen erwähnt
- `/branchen/schulen-bildung` — Enrollment-Workflows erwähnt
- `/branchen/oeffentliche-einrichtungen` — Behörden-Automationen erwähnt

### Kontext der Erwähnungen

Automationen werden primär im Operations-Kontext erwähnt, als Bindeglied zwischen Frontend und Backend-Prozessen.

---

## 🛠️ PRAKTISCHE IMPLEMENTIERUNG

### 1. Workflow-Kandidaten priorisieren

**Aufgabe:** Manuelle Schritte identifizieren (Nachfass, Datenpflege, Rückmeldungen) und Automations-Chancen nach Impact vs. Aufwand bewerten.

**Schritte:**
- Manuelle Prozesse dokumentieren (Intake, CRM-Sync, Follow-up, Reporting)
- Impact vs. Aufwand bewerten (High Impact, Low Effort = Priorität 1)
- Quick Wins identifizieren (z.B. E-Mail-Nachfass nach Formular-Submit)
- Roadmap erstellen (Q1: 3 Automationen, Q2: 5 Automationen)

### 2. Toolchain festlegen

**Aufgabe:** Serverless (Workers, Lambda), iPaaS (Make/Zapier), CRM-Automationen oder eigens entwickelte Scripts zielgerichtet einsetzen.

**Schritte:**
- **Serverless:** Cloudflare Workers, AWS Lambda für API-Integration
- **iPaaS:** Zapier, Make (ehem. Integromat) für No-Code-Workflows
- **CRM:** HubSpot, Salesforce, Pipedrive für CRM-Automationen
- **Custom Scripts:** Python, Node.js für komplexe Logik (versioniert in Git)

### 3. Governance & Logging sichern

**Aufgabe:** Jede Automation dokumentiert Input, Output, Fehlerstatus – inkl. SLA, Owner und Eskalationspfad.

**Schritte:**
- Automation-Documentation (Confluence, Notion): Input, Output, Trigger, SLA
- Logging-Infrastructure (CloudWatch, Datadog, Sentry): Fehler-Tracking
- Alerting bei Failures (Slack, E-Mail, PagerDuty)
- Review-Zyklen definieren (monatlich Automation-Health-Check)

---

## 📚 EXTERNE RESSOURCEN

- **[Zapier State of Business Automation](https://zapier.com/blog/automation-report/)** — Studie zu Automation-Trends
- **[Cloudflare Workers Use Cases](https://developers.cloudflare.com/workers/examples/)** — Praxisbeispiele für Serverless Automations
- **[AWS Step Functions + Lambda Best Practices](https://docs.aws.amazon.com/step-functions/latest/dg/best-practices.html)** — AWS-spezifische Best Practices

---

## 🎯 SEGMENT-PERSPEKTIVEN

### Kanzleien & Boutiquen

**Promise:** Response Promise einhalten, ohne Personenstunden zu verbrennen.

Intake-Follow-ups, CRM-Syncs und Mandats-Statusmeldungen laufen automatisch – dokumentiert im Servicecockpit. Mehr-Augen-Prinzip und Audit-Trail für kritische Prozesse.

### Schulen & Campus

**Promise:** Enrollment Journeys bleiben in 3 Schritten, auch bei Spitzen.

Formularrouting, Wartelisten, Payment-Status und Elternkommunikation laufen über Workers/Zapier/Make – KPIs landen im Dashboard. Mehrsprachige Automationen für internationale Kampagnen.

### Behörden & öffentliche Dienste

**Promise:** Bürgerdienste dokumentieren jeden Schritt auditierbar.

Servicecockpit, Formular-Weiterleitungen, Reminder für Dokumente oder Fristen automatisieren OZG-/BFSG-konforme Prozesse. Transparente Dokumentation stärkt Vertrauen.

---

## 🔄 AUTOMATION-TYPEN

### Event-driven Automations
Trigger: Formular-Submit, API-Call, Zeitplan (Cron)
Beispiel: Intake-Formular → E-Mail-Nachfass nach 24h

### Scheduled Automations
Trigger: Zeitplan (täglich, wöchentlich, monatlich)
Beispiel: Monats-Report-Generation, Backup-Jobs

### Integration Automations
Trigger: Datenänderung in System A → Update in System B
Beispiel: CRM-Kontakt erstellt → E-Mail-Tool-Sync

---

## 📊 SYNONYME & KEYWORDS

**Synonyme:**
- Workflow Automation
- Process Automation
- Business Process Automation (BPA)

**Keywords:**
- Automation
- Workflow
- Serverless Integration
- iPaaS
- CRM Automation

---

**Wortanzahl:** ~950 Wörter
**Review-Status:** ✅ Final
**Quellen-Qualität:** Zapier Report + Cloudflare Docs + AWS Best Practices
**Segment-Abdeckung:** Vollständig (Kanzlei, Bildung, Behörden)
**Empfehlung:** InfoTooltip auf 2-3 Seiten hinzufügen (nicht verwendet trotz Implementierung)
