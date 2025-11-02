# Interaction to Next Paint (INP)

## 📊 META-INFORMATIONEN

- **Term ID**: `inp`
- **Begriff (DE)**: Interaction to Next Paint
- **Begriff (EN)**: Interaction to Next Paint (INP)
- **Kategorie**: Performance & Web Vitals
- **Status**: ⚠️ Implementiert, aber nicht verwendet (0×)
- **Letzte Review**: 2025-10-25

---

## 💡 INFOTOOLTIP-DEFINITION

**Was ist INP?** Eine Google-Metrik, die misst, wie schnell Ihre Website auf Klicks, Taps und Tastatureingaben reagiert – Werte unter 200 ms bedeuten eine flüssige, responsive Bedienung.

---

## 📖 AUSFÜHRLICHE ERKLÄRUNG

Interaction to Next Paint (INP) misst, wie lange es dauert, bis nach einer Interaktion der nächste Frame gerendert wird – Google ersetzt damit FID als Core Web Vital. INP betrachtet die langsamste Interaktion auf einer Seite. Werte über 200 ms deuten auf blockierende Hauptthread-Aufgaben oder überlastete Rendering-Pipelines hin.

Typische Ursachen für schlechte INP-Werte:

- **Lange JavaScript-Tasks:** Tasks > 50 ms blockieren den Main Thread
- **Unoptimierte Event-Handler:** Schwere Berechnungen in Click/Input-Handlern
- **Layout-Thrashing:** Mehrfaches Lesen/Schreiben im DOM verursacht Reflows
- **Rendering schwerer Komponenten:** Charts, Maps direkt im Main Thread

Für Kanzleien bedeutet INP: Intake & Mandatsformulare reagieren in ≤ 150 ms. Für Bildungseinrichtungen: Enrollment-StepFlow bleibt auf Mobile unter 180 ms. Für Behörden: Bürgerdienste mit INP ≤ 200 ms erfüllen BFSG & Digital Take-up Ziele.

Die Optimierung erfolgt über JS-Last reduzieren (Event-Handler schlank halten, Third-Party Skripte nach Consent laden, schwere Aufgaben in Worker auslagern), UI-Komponenten prüfen (interaktive Module auditieren, Partials hydrieren und Skeletons/Streaming nutzen) und RUM + Alerts einrichten (web-vitals + `/api/rum` nutzen, Alerts bei INP > 200 ms triggern).

### Warum ist es wichtig?

INP ist seit März 2024 offizieller Core Web Vital (ersetzt FID) und misst die gesamte Interaktivität einer Seite:

- **Ranking-Relevanz:** Google nutzt INP als Ranking-Faktor (Page Experience Signal)
- **Conversion-Optimierung:** Schnelle Reaktionen führen zu höheren Conversions (Lead-to-Call Rate, Completion Rate)
- **Compliance:** BFSG/BITV verlangen berechenbare, responsive Nutzererfahrung
- **Datenbasierte Optimierung:** P75-Werte ermöglichen Performance-Budgets und Alerts

Für regulierte Branchen (Kanzleien, Bildungseinrichtungen, Behörden) ist INP ≤ 200 ms (ambitioniert ≤ 150 ms) unverzichtbar für gute Nutzererfahrung.

### Typische Anwendungsfälle

- **Use Case 1: Kanzlei-Intake-Formulare** — JS-Overhead, Drittskripte und Form-Validierung werden optimiert, damit Response Promise < 1 h glaubwürdig bleibt. Intake & Mandatsformulare reagieren in ≤ 150 ms.
- **Use Case 2: Enrollment-StepFlow** — Progressive Validierung, Lightweight Islands und RUM-Tracking sichern zufriedene Eltern/Studierende. Enrollment-StepFlow bleibt auf Mobile unter 180 ms.
- **Use Case 3: Bürgerdienste** — Edge-Caching, Workers und barrierefreie Komponenten halten den Main Thread frei, auch bei Spitzen. Bürgerdienste mit INP ≤ 200 ms erfüllen BFSG & Digital Take-up Ziele.

---

## 🔗 VERWANDTE BEGRIFFE

- **Siehe auch**: Core Web Vitals, CLS, LCP, TTFB
- **Unterschied zu**: FID (First Input Delay) — INP misst alle Interaktionen, FID nur die erste
- **Übergeordnet**: Performance-Governance, User Experience (UX)
- **Untergeordnet**: Event-Handler Optimization, Web Workers, Partial Hydration

---

## 📍 VERWENDUNG AUF DER WEBSITE

### InfoTooltip-Verwendung (0×)

⚠️ **Nicht verwendet** — Empfehlung: InfoTooltip auf folgenden Seiten hinzufügen:
- `/leistungen/analytics-consent` (Performance-Governance-Kontext)
- `/leistungen/stufe-a-astro-ftp` (INP-Budget für Formulare)
- `/leistungen/stufe-b-cloudflare-pages` (Workers für Interaktivität)

### Erwähnungen ohne InfoTooltip

- `/branchen/kanzleien` — INP-Budget für Mandatsformulare erwähnt
- `/branchen/schulen-bildung` — Enrollment-StepFlow INP-Ziele erwähnt
- `/branchen/oeffentliche-einrichtungen` — Bürgerdienste INP-Monitoring erwähnt

### Kontext der Erwähnungen

INP wird primär im Performance-Governance-Kontext erwähnt, zusammen mit Core Web Vitals und RUM Monitoring.

---

## 🛠️ PRAKTISCHE IMPLEMENTIERUNG

### 1. JS-Last reduzieren

**Aufgabe:** Event-Handler schlank halten, Third-Party Skripte nach Consent laden, schwere Aufgaben in Worker auslagern.

**Schritte:**
- Event-Handler aufsplitten (`requestIdleCallback`/`setTimeout`)
- Third-Party Scripts nach Consent laden (Consent Mode v2)
- Web Worker für CPU-intensive Tasks (z.B. Form-Validierung, Datenverarbeitung)
- Hardwarebeschleunigte Animationen, CSS-Transitions statt JS-Animationen

### 2. UI-Komponenten prüfen

**Aufgabe:** Interaktive Module (Formulare, Karten, Tabellen) auditieren, Partials hydrieren und Skeletons/Streaming nutzen.

**Schritte:**
- Interaktive Komponenten identifizieren (Formulare, Accordions, Tabs)
- Partial Hydration (Astro Islands, React Server Components)
- Skeleton Screens für dynamische Inhalte
- Lazy-Loading für schwere Komponenten (Charts, Maps)

### 3. RUM + Alerts einrichten

**Aufgabe:** web-vitals + `/api/rum` nutzen, Alerts bei INP > 200 ms triggern und mit Servicecockpit KPIs verknüpfen.

**Schritte:**
- web-vitals Library integrieren (`onINP` Callback)
- RUM-API für Datenerfassung (`/api/rum` Endpoint)
- Alerts bei P75 INP > 200 ms (Slack, E-Mail, PagerDuty)
- Servicecockpit-KPIs verknüpfen (Completion Rate, Lead-to-Call Rate)

---

## 📚 EXTERNE RESSOURCEN

- **[web.dev – INP](https://web.dev/articles/inp)** — Offizielle Google-Dokumentation
- **[Chrome Developers – Optimize INP](https://web.dev/articles/optimize-inp)** — Best Practices für INP-Optimierung
- **[HTTP Archive – Core Web Vitals](https://httparchive.org/reports/chrome-ux-report)** — Historische Trends und Benchmark-Daten

---

## 🎯 SEGMENT-PERSPEKTIVEN

### Kanzleien & Boutiquen

**Promise:** Intake & Mandatsformulare reagieren in ≤ 150 ms.

JS-Overhead, Drittskripte und Form-Validierung werden optimiert, damit Response Promise < 1 h glaubwürdig bleibt. Event-Handler schlank halten, Server-Side Tracking statt schwerer Third-Party Widgets.

### Schulen & Campus

**Promise:** Enrollment-StepFlow bleibt auf Mobile unter 180 ms.

Progressive Validierung, Lightweight Islands und RUM-Tracking sichern zufriedene Eltern/Studierende. Lazy Loading für Medien, Prefetching für StepFlow-Schritte.

### Behörden & öffentliche Dienste

**Promise:** Bürgerdienste mit INP ≤ 200 ms erfüllen BFSG & Digital Take-up Ziele.

Edge-Caching, Workers und barrierefreie Komponenten halten den Main Thread frei, auch bei Spitzen. Accessibility + Performance: stabile Layouts und berechenbare Reaktionszeiten sind BFSG/BITV-Relevanz.

---

## 📊 RICHTWERTE (P75)

| INP | Bewertung |
|-----|-----------|
| ≤ 200 ms | Gut |
| 200–500 ms | Verbesserungswürdig |
| > 500 ms | Schlecht |

**Ambitionierte Ziele für regulierte Branchen:**
- Kanzleien: ≤ 150 ms (Intake-Formulare)
- Bildung: ≤ 180 ms (Mobile Enrollment)
- Behörden: ≤ 200 ms (Bürgerdienste)

---

## 📊 SYNONYME & KEYWORDS

**Synonyme:**
- INP
- Interaction Responsiveness
- Core Web Vital Interactivity

**Keywords:**
- Interaction to Next Paint
- INP Core Web Vital
- Event Handler Optimization
- Web Workers

---

**Wortanzahl:** ~900 Wörter
**Review-Status:** ✅ Final
**Quellen-Qualität:** Google web.dev + Chrome Developers
**Segment-Abdeckung:** Vollständig (Kanzlei, Bildung, Behörden)
**Empfehlung:** InfoTooltip auf 2-3 Seiten hinzufügen (nicht verwendet trotz Implementierung)
