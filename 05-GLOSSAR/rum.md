# Real User Monitoring (RUM)

## 📊 META-INFORMATIONEN

- **Term ID**: `rum`
- **Begriff (DE)**: Real User Monitoring
- **Begriff (EN)**: Real User Monitoring (RUM)
- **Kategorie**: Performance & Web Vitals
- **Status**: ✅ Implementiert (4× verwendet)
- **Letzte Review**: 2025-10-25

---

## 💡 INFOTOOLTIP-DEFINITION

**Was ist RUM?** Real User Monitoring sammelt Performance-Daten von echten Website-Besuchern – zeigt Ihnen, wie schnell Ihre Seite wirklich lädt und wo Nutzer Probleme haben.

---

## 📖 AUSFÜHRLICHE ERKLÄRUNG

Real User Monitoring (RUM) misst Core Web Vitals, Fehler und Events direkt bei echten Nutzer:innen – unverzichtbar für Performance-Governance. Im Gegensatz zu synthetischen Tests (Lighthouse, PageSpeed Insights) zeigt RUM, wie sich eine Website in der Praxis verhält: mit echten Geräten, Verbindungstypen, Browsern und Nutzerinteraktionen.

RUM sammelt Daten zu Largest Contentful Paint (LCP), Interaction to Next Paint (INP), Cumulative Layout Shift (CLS), Time to First Byte (TTFB) und weiteren Metriken. Diese Daten werden typischerweise an eine RUM-API gesendet und in Dashboards visualisiert, die Performance-Regressionen erkennen und Alerts auslösen.

Für Kanzleien, Bildungseinrichtungen und Behörden ist RUM besonders wichtig, da Mandatsaufnahme, Enrollment-Flows und Bürgerdienste nur dann funktionieren, wenn Performance-Probleme frühzeitig erkannt werden. RUM-Daten fließen direkt in Servicecockpit-KPIs ein und ermöglichen datenbasierte Optimierungen.

Die Implementierung erfolgt über JavaScript-Libraries wie `web-vitals` von Google, die Performance-Metriken im Browser erfassen und an eine API senden. Cloudflare Workers, AWS Lambda oder eigene APIs dienen als Datenerfassung und speichern die Metriken in Datenbanken (D1, DynamoDB, PostgreSQL).

### Warum ist es wichtig?

RUM liefert die Grundlage für Performance-Governance und Service-Level-Agreements (SLAs). Es ermöglicht:

- **Echte Daten:** Synthetische Tests simulieren nur Standard-Szenarien, RUM zeigt die Realität
- **Segmentierung:** Unterschiede zwischen Desktop, Tablet, Mobile, Regionen und Kampagnen
- **Nachweise:** Dokumentierte Performance-Verbesserungen für Audits und Mandanten
- **Alerts:** Automatische Benachrichtigungen bei Performance-Regressionen

Für Kanzleien bedeutet RUM, dass Intake-Formulare auf Mobile genauso schnell reagieren wie auf Desktop. Für Bildungseinrichtungen zeigt RUM, ob bestimmte Kampagnen oder Länder schlechtere INP/LCP-Werte haben. Für Behörden dokumentiert RUM, dass BFSG/Service-Level (z.B. Completion Rate, Performance) eingehalten werden.

### Typische Anwendungsfälle

- **Use Case 1: Kanzlei Lead-to-Call KPIs** — RUM zeigt, ob Intake-Formulare auf Mobile langsamer reagieren und Mandanten abspringen. P75-Metriken für Mandantenreisen (Kontaktformular, Intake) werden dauerhaft beobachtet.
- **Use Case 2: Enrollment-Flow Optimierung** — RUM deckt auf, ob bestimmte Kampagnen oder Länder schlechtere INP/LCP-Werte haben. Progressive Validierung und Lightweight Islands halten den Main Thread frei.
- **Use Case 3: Bürgerdienste überwachen** — RUM-Dashboards dokumentieren, dass BFSG/Service-Level (z.B. Completion Rate, Performance) eingehalten werden. Edge-Caching und Workers halten den Main Thread frei, auch bei Spitzen.

---

## 🔗 VERWANDTE BEGRIFFE

- **Siehe auch**: Core Web Vitals, INP, LCP, CLS, TTFB
- **Unterschied zu**: Synthetische Tests (Lighthouse, PageSpeed Insights) — RUM = echte Nutzer, Synthetics = simulierte Szenarien
- **Übergeordnet**: Performance-Governance, Servicecockpit-KPIs
- **Untergeordnet**: web-vitals Library, RUM-API, Performance-Dashboards

---

## 📍 VERWENDUNG AUF DER WEBSITE

### InfoTooltip-Verwendung (4×)

- ✅ `/leistungen/stufe-b-cloudflare-pages` (Zeile 168)
- ✅ `/downloads/servicecockpit-intake-playbook` (Zeile 147)
- ✅ `/downloads/bfsg-bitv-checklist` (Zeile 272)
- ✅ `/index` (Zeile 354)

### Erwähnungen ohne InfoTooltip

- `/leistungen/analytics-consent` — RUM-Snippets als Teil des Tracking-Setups
- `/leistungen/stufe-a-astro-ftp` — RUM-Snippets und KPI-Dokumentation (Zeile 170)

### Kontext der Verwendungen

**Stufe B (Cloudflare Pages):** RUM Monitoring für Intake- und Service-Flows, kombiniert mit Consent Mode v2 und Error-Tracking.

**Servicecockpit-Playbook:** Kombination von Formular- und CRM-Daten mit RUM und Analytics für Kern-KPIs (Lead-to-Call Rate, Completion Rate, Digital Take-up).

**BFSG-Checklist:** WCAG-Checks mit RUM-Daten, Jour-fixe-Protokollen und Servicecockpit-Alerts für Barrierefreiheits-Audits.

**Homepage:** RUM als Teil der Performance-Governance-Strategie, zusammen mit Core Web Vitals und TTFB.

---

## 🛠️ PRAKTISCHE IMPLEMENTIERUNG

### 1. Sampling & Privacy definieren

**Aufgabe:** Sampling-Rate (z.B. 5%) und DSGVO-konforme Speicherung (anonymisierte IDs, Consent Mode) festlegen.

**Schritte:**
- Sampling-Rate definieren (100% = alle Nutzer, 5% = repräsentative Stichprobe)
- Anonymisierte Session-IDs verwenden (keine IP-Adressen speichern)
- Consent Mode v2 integrieren (nur mit Einwilligung tracken)

### 2. Dashboards & Alerts

**Aufgabe:** Servicecockpit-Visuals mit P75-Werten, Segmentierung (Gerät/Standort) und Alerts bei Regressionen.

**Schritte:**
- Looker Studio, PowerBI oder Notion-Dashboards einrichten
- P75-Werte für LCP, INP, CLS, TTFB visualisieren
- Alerts bei Überschreitung definieren (z.B. INP > 200 ms)

### 3. Feedback Loop

**Aufgabe:** RUM-Daten in Sprint-Retros & Jour-fixe integrieren – Maßnahmen mit Performance-Auswirkung tracken.

**Schritte:**
- RUM-Dashboards in wöchentliche Meetings einbinden
- Performance-Regressionen mit Code-Changes korrelieren
- A/B-Tests mit RUM-Daten validieren

---

## 📚 EXTERNE RESSOURCEN

- **[web.dev – Measure Web Vitals in JavaScript](https://web.dev/articles/vitals#measure_web_vitals_in_javascript)** — Offizielle Google-Anleitung für web-vitals Library
- **[Cloudflare – Analytics API](https://developers.cloudflare.com/analytics/graphql-api/)** — Cloudflare-spezifische RUM-Implementierung
- **[Calibre – RUM Guide](https://calibreapp.com/docs/features/real-user-monitoring)** — Kommerzielle RUM-Lösung mit ausführlichem Guide

---

## 🎯 SEGMENT-PERSPEKTIVEN

### Kanzleien & Boutiquen

**Promise:** Lead-to-Call KPIs mit echten Performance-Daten verknüpfen.

RUM zeigt, ob Intake-Formulare auf Mobile langsamer reagieren und Mandanten abspringen. Regelmäßige Kontrolle der P75-Metriken für Mandantenreisen (Kontaktformular, Intake) ermöglicht datenbasierte Optimierungen. Segmentierung zwischen Desktop-, Tablet- und Mobile-Benutzern deckt Schwachstellen auf.

### Schulen & Campus

**Promise:** Enrollment-Flow Optimierungen anhand realer Geräte/Regionen steuern.

RUM deckt auf, ob bestimmte Kampagnen oder Länder schlechtere INP/LCP-Werte haben. Progressive Validierung, Lightweight Islands und RUM-Tracking sichern zufriedene Eltern/Studierende. Mehrsprachigkeit und internationale Kampagnen profitieren von regionaler Segmentierung.

### Behörden & öffentliche Dienste

**Promise:** Bürgerdienste überwachen und Compliance-Nachweise liefern.

RUM-Dashboards dokumentieren, dass BFSG/Service-Level (z.B. Completion Rate, Performance) eingehalten werden. Edge-Caching, Workers und barrierefreie Komponenten halten den Main Thread frei, auch bei Spitzen. Auditor:innen können dokumentierte Performance-Verbesserungen nachvollziehen.

---

## 📊 SYNONYME & KEYWORDS

**Synonyme:**
- RUM
- Field Monitoring
- Real User Metrics

**Keywords:**
- Real User Monitoring
- Web Vitals
- Performance Analytics
- Field Data
- P75 Metriken

---

**Wortanzahl:** ~1.000 Wörter
**Review-Status:** ✅ Final
**Quellen-Qualität:** Google web.dev + Cloudflare Docs
**Segment-Abdeckung:** Vollständig (Kanzlei, Bildung, Behörden)
