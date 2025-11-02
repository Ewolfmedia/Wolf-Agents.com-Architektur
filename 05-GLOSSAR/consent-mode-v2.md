# Consent Mode v2

## 📊 META-INFORMATIONEN

- **Term ID**: `consent-mode-v2`
- **Begriff (DE)**: Consent Mode v2
- **Begriff (EN)**: Google Consent Mode v2
- **Kategorie**: Analytics & Consent
- **Status**: ✅ Implementiert (5× verwendet)
- **Letzte Review**: 2025-10-25

---

## 💡 INFOTOOLTIP-DEFINITION

**Was ist Consent Mode v2?** Googles aktualisiertes Framework für DSGVO-konformes Tracking – sendet je nach Nutzereinwilligung unterschiedlich detaillierte Daten an Google Analytics und Ads. Pflicht seit 2024.

---

## 📖 AUSFÜHRLICHE ERKLÄRUNG

Consent Mode v2 ist Googles Erweiterung des ursprünglichen Consent-Frameworks. Es fügt zwei zusätzliche Signal-Parameter hinzu (`ad_personalization`, `ad_user_data`), die Werbetreibende und Website-Betreiber verpflichten, granulare Einwilligungssignale an Google Analytics und Google Ads zu senden.

Ohne korrekte Implementierung können GA4- und Ads-Daten verloren gehen, Conversions werden modelliert oder gesperrt. Gleichzeitig erhöht Google den Compliance-Druck durch EU-User-Consent-Richtlinien, die ab 2024 strengere Anforderungen stellen.

Die Implementierung erfolgt typischerweise über eine Consent Management Platform (CMP) wie Usercentrics, Cookiebot oder Borlabs Cookie, die die vier Consent-Status (`ad_storage`, `analytics_storage`, `ad_personalization`, `ad_user_data`) verwaltet und an Google Tag Manager (GTM) oder direkt an gtag.js übermittelt.

Server-Side Tracking über Proxies oder Server-Side Tagging (z.B. via Cloudflare Workers oder Google Cloud Platform) reduziert Datenverluste, harmonisiert Consent-Status und verbessert die Datenqualität für Analytics, Ads und Servicecockpit-KPIs.

### Warum ist es wichtig?

Consent Mode v2 stellt sicher, dass Mandatsmarketing, Enrollment-Kampagnen und Bürgerdienste messbar bleiben, ohne Datenschutzanforderungen zu gefährden. Es ermöglicht:

- **Compliance:** DSGVO-konforme Analytics und Ads-Kampagnen
- **Messbarkeit:** Valide KPIs trotz strenger Einwilligungspflichten
- **Vertrauen:** Transparente Dokumentation stärkt Vertrauen und erleichtert Audits
- **Flexibilität:** Modellierte Conversions und Audiences bleiben nutzbar

Für regulierte Branchen (Kanzleien, Bildungseinrichtungen, Behörden) ist Consent Mode v2 unverzichtbar, da Tracking-Maßnahmen ohne korrekte Einwilligungssignale nicht mehr zulässig sind oder stark eingeschränkt werden.

### Typische Anwendungsfälle

- **Use Case 1: Kanzlei-Mandatsmarketing** — Intake-Formulare und Kampagnen-Tracking nutzen Consent Mode v2, um Leads korrekt zu attribuieren und Response Promise zu belegen. Server-Side Tagging hält Daten konsistent.
- **Use Case 2: Enrollment-Kampagnen** — Schulen und Hochschulen setzen Consent Mode v2 + Server-Side Tracking ein, um Anmeldungen nachvollziehbar zu halten, auch bei Remarketing und Stipendien-Kampagnen.
- **Use Case 3: Behörden-Servicecockpit** — Öffentliche Einrichtungen erfassen Completion Rate & Digital Take-up transparent, ohne personenbezogene Daten unzulässig zu verarbeiten.

---

## 🔗 VERWANDTE BEGRIFFE

- **Siehe auch**: RUM (Real User Monitoring), Analytics Dashboard, Server-Side Tracking
- **Unterschied zu**: Consent Mode v1 (fehlten `ad_personalization`, `ad_user_data`)
- **Übergeordnet**: DSGVO-konforme Analytics-Strategie
- **Untergeordnet**: CMP-Integration, GTM-Konfiguration, Consent-Logs

---

## 📍 VERWENDUNG AUF DER WEBSITE

### InfoTooltip-Verwendung (5×)

- ✅ `/capabilities` (Zeile 98)
- ✅ `/leistungen/stufe-a-astro-ftp` (Zeile 170)
- ✅ `/leistungen/stufe-b-cloudflare-pages` (Zeile 104)
- ✅ `/ueber-mich` (Zeile 266)
- ✅ `/ueber-mich` (erwähnt in Kontext, Zeile 119)

### Erwähnungen ohne InfoTooltip

- `/leistungen/analytics-consent` — Vollständiger Artikel über Analytics & Consent-Setup
- `/leistungen/stufe-b-cloudflare-pages` — Server-Side Tracking Kontext (Zeile 168)

### Kontext der Verwendungen

**Capabilities-Seite:** Positionierung als Teil der Analytics-Governance, zusammen mit Core Web Vitals und RUM Monitoring.

**Stufe A (Astro + FTP):** Tracking & Consent Setup mit GA4/Matomo Events, Server-Side Hooks und RUM-Snippets.

**Stufe B (Cloudflare Pages):** Workers & KV/D1 für Servicecockpit-APIs, inklusive Consent Mode v2 & Server-Side Tracking für Intake- und Service-Flows.

**Über-Mich-Seite:** Expertise in Compliance-Themen (BFSG 2025, Consent Mode v2, DSGVO).

---

## 🛠️ PRAKTISCHE IMPLEMENTIERUNG

### 1. CMP & Tagging aktualisieren

**Aufgabe:** CMP (Usercentrics, Borlabs, Cookiebot) muss Consent Mode v2 Signale senden. GTM/Gtag-Konfiguration aktualisieren und testen.

**Schritte:**
- CMP auf Consent Mode v2 konfigurieren (inkl. Region Rules für EU-Nutzer)
- Consent-Events (`default`, `update`) in GTM/Gtag einrichten
- Testen: DevTools → Network → Analytics/Ads Requests prüfen

### 2. Server-Side Tracking vorbereiten

**Aufgabe:** Proxy oder Server-Side Tagging reduziert Datenverluste, harmonisiert Consent-Status (Analytics, Ads, Servicecockpit).

**Schritte:**
- Cloudflare Workers oder GCP Server-Side Tagging einrichten
- Consent-Status an Server-Side Container weitergeben
- Datenverluste durch Ad-Blocker minimieren

### 3. Consent-Logs sichern

**Aufgabe:** Einwilligungen, Widerrufe und Event-Status auditierbar protokollieren – relevant für DSGVO- und BFSG-Nachweise.

**Schritte:**
- Consent-Events in Datenbank (z.B. Cloudflare D1) speichern
- Retention Policy definieren (z.B. 3 Jahre)
- Audit-Reports für Datenschutzbeauftragte bereitstellen

---

## 📚 EXTERNE RESSOURCEN

- **[Google Developers – Consent Mode v2](https://developers.google.com/tag-platform/devguides/consent)** — Offizielle Dokumentation mit Implementierungsbeispielen
- **[Google Ads Support – Consent Mode Anforderungen](https://support.google.com/google-ads/answer/10000067)** — Anforderungen für Google Ads Kampagnen
- **[Usercentrics – Consent Mode v2 Implementierung](https://usercentrics.com/de/knowledge-hub/google-consent-mode-v2/)** — CMP-spezifische Anleitung

---

## 🎯 SEGMENT-PERSPEKTIVEN

### Kanzleien & Boutiquen

**Promise:** Mandatsmarketing bleibt messbar, ohne Datenschutz zu gefährden.

Consent Mode v2 koppelt Mandatsmarketing (GA4/Ads) mit Einwilligungen – wichtig für Response Promise und Kampagnenmessung. Server-Side Tagging (z.B. via Cloudflare Workers oder GCP) hält Daten konsistent und DSGVO-konform. Consent-Logs dienen als Nachweis bei Datenschutz-Anfragen.

### Schulen & Campus

**Promise:** Enrollment-Kampagnen liefern valide KPIs trotz strenger Einwilligungspflichten.

Enrollment-Kampagnen in GA4/Ads laufen nur mit gültigen Consent-Signalen – sonst fallen Remarketing und Lookalikes weg. StepFlow-Events und KPI-Dashboards (Completion Rate) bleiben nutzbar, wenn Consent Mode v2 korrekt integriert ist. Elternkommunikation profitiert von granularen Consent-Kategorien (Analytics, Remarketing, Serviceangebote).

### Behörden & öffentliche Dienste

**Promise:** Servicecockpit & Nutzungsstatistiken bleiben auditierbar.

Auch ohne Werbekampagnen wichtig: Consent Mode v2 steuert Analytics-Events, um BFSG/BITV-Konformität nachzuweisen. Servicecockpit setzt auf anonymisierte, aggregierte Daten – Consent Mode stellt sicher, dass nur zulässige Signale verarbeitet werden. Transparente Dokumentation stärkt Vertrauen und erleichtert Audits.

---

## 📊 SYNONYME & KEYWORDS

**Synonyme:**
- GCM v2
- Google Consent Mode
- Enhanced Consent Mode

**Keywords:**
- Consent Mode
- Server Side Tracking
- DSGVO Analytics
- CMP Integration
- Consent Management

---

**Wortanzahl:** ~1.050 Wörter
**Review-Status:** ✅ Final
**Quellen-Qualität:** Offizielle Google-Dokumentation
**Segment-Abdeckung:** Vollständig (Kanzlei, Bildung, Behörden)
