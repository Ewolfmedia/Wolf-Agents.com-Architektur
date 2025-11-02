# CLI-first Delivery

## 📊 META-INFORMATIONEN

- **Term ID**: `cli-first`
- **Begriff (DE)**: CLI-first Delivery
- **Begriff (EN)**: CLI-first Delivery
- **Kategorie**: Engineering & Delivery
- **Status**: ✅ Implementiert (5× verwendet)
- **Letzte Review**: 2025-10-25

---

## 💡 INFOTOOLTIP-DEFINITION

**Was ist CLI-first?** Ein Entwicklungsansatz, bei dem alle Prozesse (Build, Test, Deploy) über Kommandozeilen-Skripte laufen – keine manuellen Klicks, sondern nachvollziehbare, versionierte Automatisierung.

---

## 📖 AUSFÜHRLICHE ERKLÄRUNG

CLI-first Delivery bedeutet, dass Builds, Tests, Deployments und Audits über versionierte Kommandozeilen-Skripte laufen – keine manuellen Klickwege. CLI-first Teams steuern Entwicklungs-, Test- und Deployment-Prozesse über Skripte und Tools (z.B. npm, pnpm, make, custom CLIs). Keine manuellen Klickwege, sondern nachvollziehbare Commands, die versioniert werden können.

Die Bausteine von CLI-first sind:

- **Skripte für alle Prozesse:** Build, Tests, Linting, Deployments
- **Secrets-Management:** `.env`-Dateien, Cloud Secrets, Vault-Integration
- **CI/CD-Integration:** GitHub Actions, GitLab CI oder lokale Toolchains

Für Kanzleien bedeutet CLI-first: Release-Logs & Compliance-Nachweise für Mandantenportale jederzeit abrufbar. Für Bildungseinrichtungen: Kampagnen- und Enrollment-Rollouts in Minuten statt Tagen. Für Behörden: OZG-/BFSG-Deployments mit klarer Governance und Auditlog.

Die Implementierung erfolgt über standardisierte Skripte in `package.json` / Makefiles für Build, Lint, Test, Deploy – inklusive Doku und Onboarding. Jeder CLI-Befehl läuft identisch lokal und in GitHub/GitLab Actions, inklusive Secrets-Handling. Logs, Artefakte und Release Notes werden automatisch archiviert (S3, Cloud Storage, Git Tags).

### Warum ist es wichtig?

CLI-first ermöglicht Reproduzierbarkeit, Audit-Trail und Geschwindigkeit:

- **Reproduzierbarkeit:** Jeder Release ist nachvollziehbar und lässt sich wiederholen
- **Audit-Trail:** Commands & Logs liefern Nachweise für Compliance/Revision
- **Geschwindigkeit:** Automatisierte Pipelines sparen Zeit und vermeiden Fehler
- **Lokalität:** Entwickler:innen können lokal testen, was in CI läuft

Für regulierte Branchen (Kanzleien, Bildungseinrichtungen, Behörden) ist CLI-first unverzichtbar, da Deployments nachvollziehbar und auditierbar sein müssen.

### Typische Anwendungsfälle

- **Use Case 1: Kanzlei-Mandantenportale** — Deployments via npm scripts/GitHub Actions dokumentieren jede Änderung – wichtig für BAIT/BORA & Mandatsführung. Release-Historie als Nachweis für Auditor:innen.
- **Use Case 2: Enrollment-Rollouts** — CLI-first Pipelines liefern Previews, Tests und Launches synchron für mehrere Fakultäten/Campus. Kampagnen- und Enrollment-Rollouts in Minuten statt Tagen.
- **Use Case 3: Behörden-Deployments** — CLI- und IaC-basierte Releases sichern Nachvollziehbarkeit, Freigabeprozesse und SLA-konforme Rollbacks. OZG-/BFSG-Deployments mit klarer Governance und Auditlog.

---

## 🔗 VERWANDTE BEGRIFFE

- **Siehe auch**: GitOps, Infrastructure as Code (IaC), DevOps
- **Unterschied zu**: Traditionelle Deployments (manuelle Klicks, UI-basierte Workflows)
- **Übergeordnet**: Continuous Delivery, DevOps-Kultur, Automation
- **Untergeordnet**: npm/pnpm scripts, Makefiles, GitHub Actions, Secrets-Management

---

## 📍 VERWENDUNG AUF DER WEBSITE

### InfoTooltip-Verwendung (5×)

- ✅ `/capabilities` (Zeile 57)
- ✅ `/ueber-mich` (Zeile 146)
- ✅ `/ueber-mich` (Zeile 225)
- ✅ `/ueber-mich` (Zeile 356)

### Erwähnungen ohne InfoTooltip

- `/leistungen/stufe-a-astro-ftp` — CLI-first Workflows für FTP-Deployments
- `/leistungen/stufe-b-cloudflare-pages` — CLI-first für Cloudflare Workers
- `/leistungen/stufe-c-aws-cloudfront` — CLI-first + Terraform für AWS

### Kontext der Verwendungen

**Capabilities-Seite:** CLI-first als Kernkompetenz für Engineering-Workflows.

**Über-Mich-Seite:** Expertise in CLI-first Delivery (4× erwähnt) als zentrale Arbeitsmethode.

**Leistungs-Seiten:** CLI-first als Grundlage für alle Deployment-Stufen (Stufe 0-C).

---

## 🛠️ PRAKTISCHE IMPLEMENTIERUNG

### 1. Skripte standardisieren

**Aufgabe:** `package.json` / Makefiles für Build, Lint, Test, Deploy – inklusive Doku und Onboarding.

**Schritte:**
- `package.json` scripts definieren (build, test, lint, deploy, preview)
- Oder Makefile für polyglotte Projekte (z.B. Astro + Terraform)
- Dokumentation in README.md mit Onboarding-Anleitung
- Conventions für Script-Namen etablieren (z.B. `npm run build:prod`)

### 2. CI/CD koppeln

**Aufgabe:** Jeder CLI-Befehl läuft identisch lokal und in GitHub/GitLab Actions, inklusive Secrets-Handling.

**Schritte:**
- GitHub Actions Workflows mit `npm run build`, `npm run test` etc.
- Secrets via GitHub Secrets oder Vault
- Matrix-Builds für verschiedene Environments (dev, staging, prod)
- Artifacts speichern (Build-Logs, Test-Reports)

### 3. Audit Trails speichern

**Aufgabe:** Logs, Artefakte und Release Notes automatisch archivieren (S3, Cloud Storage, Git Tags).

**Schritte:**
- Build-Logs in S3/GCS/Azure Blob speichern (Retention 3 Jahre)
- Git Tags für Releases mit Semantic Versioning (v1.2.3)
- Release Notes automatisch generieren (Conventional Commits)
- Audit-Reports für Compliance-Teams bereitstellen

---

## 📚 EXTERNE RESSOURCEN

- **[GitHub Actions Best Practices](https://docs.github.com/en/actions/learn-github-actions/best-practices-for-github-actions)** — Offizielle GitHub-Doku
- **[HashiCorp – Infrastructure Automation](https://www.hashicorp.com/resources)** — Terraform, Vault, Nomad
- **[ThoughtWorks Technology Radar – Continuous Delivery](https://www.thoughtworks.com/radar)** — Best Practices für CD

---

## 🎯 SEGMENT-PERSPEKTIVEN

### Kanzleien & Boutiquen

**Promise:** Release-Logs & Compliance-Nachweise für Mandantenportale jederzeit abrufbar.

Deployments via npm scripts/GitHub Actions dokumentieren jede Änderung – wichtig für BAIT/BORA & Mandatsführung. Reproduzierbare Infrastruktur (z.B. Cloudflare Pages, AWS CloudFront) ermöglicht schnelle Rollbacks bei Problemen.

### Schulen & Campus

**Promise:** Kampagnen- und Enrollment-Rollouts in Minuten statt Tagen.

CLI-first Pipelines liefern Previews, Tests und Launches synchron für mehrere Fakultäten/Campus. Mehrsprachige Deployments und internationale Kampagnen profitieren von strukturierten Workflows.

### Behörden & öffentliche Dienste

**Promise:** OZG-/BFSG-Deployments mit klarer Governance und Auditlog.

CLI- und IaC-basierte Releases sichern Nachvollziehbarkeit, Freigabeprozesse und SLA-konforme Rollbacks. Transparente Dokumentation stärkt Vertrauen und erleichtert Audits.

---

## 📊 SYNONYME & KEYWORDS

**Synonyme:**
- CLI-first
- Command-line Delivery
- Script-based Deployments

**Keywords:**
- CLI Delivery
- Automation
- DevOps
- npm scripts
- GitHub Actions

---

**Wortanzahl:** ~900 Wörter
**Review-Status:** ✅ Final
**Quellen-Qualität:** GitHub Docs + HashiCorp + ThoughtWorks
**Segment-Abdeckung:** Vollständig (Kanzlei, Bildung, Behörden)
