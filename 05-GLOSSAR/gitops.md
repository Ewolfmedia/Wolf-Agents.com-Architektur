# GitOps

## 📊 META-INFORMATIONEN

- **Term ID**: `gitops`
- **Begriff (DE)**: GitOps
- **Begriff (EN)**: GitOps
- **Kategorie**: Engineering & Delivery
- **Status**: ✅ Implementiert (3× verwendet)
- **Letzte Review**: 2025-10-25

---

## 💡 INFOTOOLTIP-DEFINITION

**Was ist GitOps?** Ein Deployment-Modell, bei dem Git die einzige Wahrheitsquelle ist – jede Änderung läuft über Pull Requests mit Review, und Deployments erfolgen automatisch. Ideal für Transparenz und Compliance.

---

## 📖 AUSFÜHRLICHE ERKLÄRUNG

GitOps steuert Infrastruktur- und Code-Deployments vollständig über Git. Pull Requests, Reviews und automatisierte Controller synchronisieren den gewünschten Zustand. GitOps nutzt Git als "Source of Truth" für Applikations- und Infrastrukturzustände. Pipeline- oder Controller-Tools (z.B. ArgoCD, Flux) überwachen das Repo und synchronisieren es mit der Produktionsumgebung.

Die Kernprinzipien von GitOps sind:

- **Deklarativ:** Der gewünschte Zustand wird in Git deklariert (Infrastructure as Code, Kubernetes Manifests, etc.)
- **Versioniert:** Alle Änderungen sind nachvollziehbar via Git-History
- **Automatisiert:** Controller/Pipelines synchronisieren automatisch
- **Kontinuierlich:** Abweichungen werden automatisch korrigiert (Self-Healing)

Für Kanzleien bedeutet GitOps: Compliance-konforme Releases für Mandantenportale mit Audit-Trail. Für Bildungseinrichtungen: Mehrere Campus-Deployments synchronisieren ohne Chaos. Für Behörden: OZG-/BFSG-Rollouts mit Revisionssicherheit.

Die Implementierung erfolgt über strukturierte Repositories (Application + Infrastructure Repos) mit klaren Branching-Strategien (main, release, hotfix) und CODEOWNERS. Automation wird über GitHub/GitLab Actions, ArgoCD oder Flux aufgesetzt, die Deployments aus Pull Requests triggern. Policies, Secrets-Management, Observability und Incident-Rollback-Prozesse werden dokumentiert.

### Warum ist es wichtig?

GitOps ermöglicht Transparenz, Sicherheit und Rollback-Fähigkeit für Deployments:

- **Transparenz:** Jeder Deployment-Schritt ist per Commit/PR dokumentiert
- **Sicherheit:** Reviews & Branch-Policies verhindern unkontrollierte Änderungen
- **Rollback-Fähigkeit:** Vorherige Zustände lassen sich per Git revert wiederherstellen
- **Compliance:** Release-Historie als Nachweis für Auditor:innen

Für regulierte Branchen (Kanzleien, Bildungseinrichtungen, Behörden) ist GitOps unverzichtbar, da Deployments nachvollziehbar und auditierbar sein müssen.

### Typische Anwendungsfälle

- **Use Case 1: Kanzlei-Mandantenportale** — Branch-Policies, Reviews und ArgoCD/Actions dokumentieren jeden Schritt – hilfreich für BAIT/BORA-Audits. Mehr-Augen-Prinzip bei kritischen Updates (z.B. Datenschutztexte, Formulare).
- **Use Case 2: Campus-Deployments** — GitOps orchestriert Parallelreleases (Landingpages, Apps) für verschiedene Fakultäten inkl. Previews und Rollbacks. Mehrere Campus-Deployments synchronisieren ohne Chaos.
- **Use Case 3: Behörden-Rollouts** — Infrastructure-as-Code plus GitOps Controller sichern, dass Produktionsumgebungen exakt den genehmigten PRs entsprechen. OZG-/BFSG-Rollouts mit Revisionssicherheit.

---

## 🔗 VERWANDTE BEGRIFFE

- **Siehe auch**: CLI-first Delivery, Infrastructure as Code (IaC), DevOps
- **Unterschied zu**: Traditionelle Deployments (manuelle Klicks, keine Versionierung)
- **Übergeordnet**: Continuous Delivery, DevOps-Kultur
- **Untergeordnet**: ArgoCD, Flux, GitHub Actions, Branch-Policies

---

## 📍 VERWENDUNG AUF DER WEBSITE

### InfoTooltip-Verwendung (3×)

- ✅ `/capabilities` (Zeile 66)
- ✅ `/ueber-mich` (Zeile 234)
- ✅ `/index` (Zeile 106)

### Erwähnungen ohne InfoTooltip

- `/leistungen/stufe-a-astro-ftp` — GitOps-basierte Deployments mit GitHub Actions
- `/leistungen/stufe-b-cloudflare-pages` — GitOps für Cloudflare Pages Deployments
- `/leistungen/stufe-c-aws-cloudfront` — GitOps + Terraform für AWS-Infrastruktur

### Kontext der Verwendungen

**Capabilities-Seite:** GitOps als Kernkompetenz für Delivery-Workflows.

**Über-Mich-Seite:** Expertise in GitOps und CLI-first Delivery.

**Homepage:** GitOps als Teil der Engineering-Strategie, zusammen mit Core Web Vitals und BFSG 2025.

---

## 🛠️ PRAKTISCHE IMPLEMENTIERUNG

### 1. Repositories strukturieren

**Aufgabe:** Application + Infrastructure Repos mit klaren Branching-Strategien (main, release, hotfix) und CODEOWNERS definieren.

**Schritte:**
- Separate Repos für Application Code und Infrastructure (Terraform, Kubernetes Manifests)
- Branching-Strategie definieren (Git Flow, GitHub Flow, Trunk-Based Development)
- CODEOWNERS-Datei für Reviews erstellen (z.B. Backend-Team für API-Changes)
- Branch-Protection Rules aktivieren (z.B. "main" protected, requires review)

### 2. Automation aufsetzen

**Aufgabe:** GitHub/GitLab Actions, ArgoCD oder Flux nutzen, um Deployments aus Pull Requests zu triggern und zu synchronisieren.

**Schritte:**
- CI/CD-Pipelines in GitHub/GitLab Actions konfigurieren
- ArgoCD/Flux für Kubernetes-Deployments einrichten (Auto-Sync, Self-Healing)
- Preview-Environments für Pull Requests erstellen
- Deployment-Notifications in Slack/Teams integrieren

### 3. Compliance & Monitoring

**Aufgabe:** Policies, Secrets-Management, Observability (status dashboards) und Incident-Rollback-Prozesse dokumentieren.

**Schritte:**
- Policy-as-Code mit Open Policy Agent (OPA) oder Kyverno
- Secrets-Management mit GitHub Secrets, Vault oder AWS Secrets Manager
- Status-Dashboards für Deployment-Health (ArgoCD UI, Grafana)
- Rollback-Playbook dokumentieren (Git revert, Canary Rollback)

---

## 📚 EXTERNE RESSOURCEN

- **[WeaveWorks – GitOps Principles](https://www.weave.works/technologies/gitops/)** — Originale GitOps-Definition von Weaveworks
- **[ArgoCD Documentation](https://argo-cd.readthedocs.io/)** — Kubernetes-native GitOps-Tool
- **[CNCF GitOps WG](https://opengitops.dev/)** — OpenGitOps Spezifikation der CNCF

---

## 🎯 SEGMENT-PERSPEKTIVEN

### Kanzleien & Boutiquen

**Promise:** Compliance-konforme Releases für Mandantenportale mit Audit-Trail.

Release-Historie als Nachweis für Auditor:innen. Mehr-Augen-Prinzip bei kritischen Updates (z.B. Datenschutztexte, Formulare). Reproduzierbare Infrastruktur (z.B. Cloudflare Pages, AWS CloudFront).

### Schulen & Campus

**Promise:** Mehrere Campus-Deployments synchronisieren ohne Chaos.

GitOps orchestriert Parallelreleases (Landingpages, Apps) für verschiedene Fakultäten inkl. Previews und Rollbacks. Mehrsprachige Deployments und internationale Kampagnen profitieren von strukturierten Workflows.

### Behörden & öffentliche Dienste

**Promise:** OZG-/BFSG-Rollouts mit Revisionssicherheit.

Infrastructure-as-Code plus GitOps Controller sichern, dass Produktionsumgebungen exakt den genehmigten PRs entsprechen. Transparente Dokumentation stärkt Vertrauen und erleichtert Audits.

---

## 📊 SYNONYME & KEYWORDS

**Synonyme:**
- Git-based Operations
- GitOps Delivery
- Declarative Deployments

**Keywords:**
- GitOps
- Continuous Delivery
- Infrastructure as Code
- ArgoCD
- Kubernetes

---

**Wortanzahl:** ~900 Wörter
**Review-Status:** ✅ Final
**Quellen-Qualität:** Weaveworks + ArgoCD + CNCF
**Segment-Abdeckung:** Vollständig (Kanzlei, Bildung, Behörden)
