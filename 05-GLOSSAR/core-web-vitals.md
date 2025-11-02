# Core Web Vitals

## 📊 META-INFORMATIONEN

- **Term ID**: `core-web-vitals`
- **Begriff (DE)**: Core Web Vitals
- **Begriff (EN)**: Core Web Vitals (CWV)
- **Kategorie**: Performance & Web Vitals
- **Status**: ✅ Implementiert (3× verwendet)
- **Letzte Review**: 2025-10-14

---

## 💡 INFOTOOLTIP-DEFINITION

**Was sind Core Web Vitals?** Die drei wichtigsten Kennzahlen, die Google zur Bewertung der Nutzererfahrung verwendet – wie schnell lädt Ihre Seite (LCP), wie stabil ist sie (CLS), und wie schnell reagiert sie auf Klicks (INP).

---

## 📖 AUSFÜHRLICHE ERKLÄRUNG

Die Core Web Vitals sind Googles Feldmetriken für Ladegeschwindigkeit (LCP), Interaktivität (INP) und Layout-Stabilität (CLS) – entscheidend für die Ranking-Performance und Nutzerzufriedenheit. Sie spiegeln reale Nutzererfahrungen wider und werden im Chrome User Experience Report (CrUX) sowie über eigenes RUM-Tracking gemessen.

Die drei Kern-Metriken sind:

- **LCP (Largest Contentful Paint)** — Ladegeschwindigkeit: Zeit bis zum größten sichtbaren Content-Element (Ziel: ≤ 2,5 Sekunden)
- **INP (Interaction to Next Paint)** — Interaktivität: Zeit bis zur visuellen Reaktion auf Nutzer-Interaktionen (Ziel: ≤ 200 Millisekunden)
- **CLS (Cumulative Layout Shift)** — Layout-Stabilität: Summe unerwarteter Layout-Verschiebungen (Ziel: ≤ 0,1)

Diese Metriken werden als P75-Werte gemessen (75. Perzentil), was bedeutet, dass 75% aller Nutzer:innen mindestens diese Werte erleben sollten. Google nutzt CrUX-Daten für Ranking-Faktoren, aber eigenes RUM-Tracking liefert detailliertere Insights für Optimierungen.

Für Kanzleien, Bildungseinrichtungen und Behörden sind Core Web Vitals geschäftskritisch: Intake-Formulare, Enrollment-Flows und Bürgerdienste funktionieren nur, wenn Performance-Budgets eingehalten werden. Schlechte CWV führen zu Abbrüchen, niedrigerer Conversion und schlechterem Ranking.

### Warum ist es wichtig?

Core Web Vitals sind der Standard für messbare Nutzererfahrung. Sie ermöglichen:

- **Ranking-Relevanz:** Google nutzt CWV als Ranking-Faktor (Page Experience Signal)
- **Conversion-Optimierung:** Schnellere Seiten führen zu höheren Conversions (Lead-to-Call Rate, Completion Rate)
- **Compliance:** BFSG/BITV verlangen berechenbare, stabile Nutzererfahrung
- **Datenbasierte Optimierung:** P75-Werte ermöglichen Performance-Budgets und Alerts

Für Kanzleien bedeutet das: Lead-to-Call Rate +35% bleibt erreichbar, wenn LCP & INP stabil unter Budget bleiben. Für Bildungseinrichtungen: Enrollment-Flows performen auf Mobile (> 60% Nutzung) nur mit stabilen CWV. Für Behörden: Digital Take-up ≥ 70% gelingt nur mit verlässlicher Performance.

### Typische Anwendungsfälle

- **Use Case 1: Kanzlei-Intake-Formulare** — Intake-Formulare, Terminbuchung und Proof-Module müssen < 2,3 s LCP und < 150 ms INP liefern – sonst brechen Mandanten den Kontakt ab. Edge Caching, Bildoptimierung und minimaler JavaScript-Einsatz halten Response Promise ein.
- **Use Case 2: Enrollment-StepFlow** — StepFlow, Kurslisten, Zahlungswidgets brauchen schnelle FCP/LCP und reaktive Eingaben, damit Anmeldungen in 3 Schritten funktionieren. Lazy Loading für Medien und Worker-basierte Validierung sichern Experience.
- **Use Case 3: Behörden-Top-Tasks** — Top-Tasks, Formular-Status und Servicecockpit-Anzeigen müssen auch bei Lastspitzen schnell reagieren, damit Bürgerdienste kompromisslos nutzbar bleiben. Cloudflare Workers / AWS Lambda@Edge verkürzen Server-Antwortzeiten.

---

## 🔗 VERWANDTE BEGRIFFE

- **Siehe auch**: INP, LCP, CLS, TTFB, RUM
- **Unterschied zu**: Synthetische Tests (Lighthouse, PageSpeed Insights) — CWV = Field Data (echte Nutzer), Synthetics = Lab Data (simuliert)
- **Übergeordnet**: Performance-Governance, User Experience (UX)
- **Untergeordnet**: LCP-Budget, INP-Cockpit, CLS-Regression Prevention

---

## 📍 VERWENDUNG AUF DER WEBSITE

### InfoTooltip-Verwendung (3×)

- ✅ `/leistungen/stufe-0-ftp-classic` (Zeile 164)
- ✅ `/downloads/servicecockpit-intake-playbook` (Zeile 49)
- ✅ `/index` (Zeile 93)

### Erwähnungen ohne InfoTooltip

- `/leistungen/analytics-consent` — Core Web Vitals als Teil der Performance-Governance
- `/leistungen/seo-tech` — Technical SEO Services mit Core Web Vitals Optimierung
- `/branchen/kanzleien` — Performance-Budgets für Mandatsmarketing
- `/branchen/schulen-bildung` — Enrollment-Flow Performance
- `/branchen/oeffentliche-einrichtungen` — Bürgerdienste Performance-Monitoring

### Kontext der Verwendungen

**Stufe 0 (FTP Classic):** Core Web Vitals als Basis-Anforderung, auch für einfache Setups.

**Servicecockpit-Playbook:** Kern-KPIs kombiniert mit Core Web Vitals für Lead-to-Call Rate, Completion Rate, Digital Take-up.

**Homepage:** Core Web Vitals als Teil der Performance-Strategie, zusammen mit GitOps und BFSG 2025.

---

## 🛠️ PRAKTISCHE IMPLEMENTIERUNG

### 1. LCP-Budget definieren

**Aufgabe:** Hero-Medien, Above-the-fold Content und Fonts so ausliefern, dass LCP ≤ 2,3 s bleibt – ideal mit Image Optimization, Critical CSS, Edge Caching.

**Schritte:**
- Hero-Images optimieren (WebP, AVIF, responsive srcset)
- Critical CSS inline, Rest defer/async
- Fonts preload (woff2, subset)
- Edge Caching für statische Assets (Cloudflare, AWS CloudFront)

### 2. INP-Cockpit aufsetzen

**Aufgabe:** Event-Handler, Third-Party Scripts und Islands testen; Zielwert < 200 ms, ambitioniert < 150 ms für Intake/StepFlow.

**Schritte:**
- Event-Handler schlank halten (< 50 ms pro Task)
- Third-Party Scripts nach Consent laden (Consent Mode v2)
- Islands mit Partial Hydration (Astro Islands, React Server Components)
- RUM-Tracking für INP-Werte einrichten

### 3. CLS-Regression vermeiden

**Aufgabe:** Layout-Shift Prevention (feste Größen, Skeletons, Reserve-Space) ins Designsystem integrieren und in QA prüfen.

**Schritte:**
- Width/Height-Attribute für alle Images/Videos setzen
- Skeleton Screens für dynamische Inhalte
- Reserve Space für Ads/Widgets
- Font-Display: swap oder optional (verhindert FOIT/FOUT Shifts)

---

## 📚 EXTERNE RESSOURCEN

- **[web.dev – Core Web Vitals](https://web.dev/articles/vitals)** — Offizielle Google-Dokumentation mit Best Practices
- **[Chrome for Developers – CrUX](https://developer.chrome.com/docs/crux/)** — Chrome User Experience Report (Field Data)
- **[HTTP Archive – Core Web Vitals](https://httparchive.org/reports/chrome-ux-report)** — Historische Trends und Benchmark-Daten

---

## 🎯 SEGMENT-PERSPEKTIVEN

### Kanzleien & Boutiquen

**Promise:** Lead-to-Call Rate +35% bleibt erreichbar, wenn LCP & INP stabil unter Budget bleiben.

Intake-Formulare, Terminbuchung und Proof-Module sollten < 2,3 s LCP und < 150 ms INP erreichen. Edge Caching, Bildoptimierung und minimaler JavaScript-Einsatz halten Response Promise ein. Server-Side Tracking statt schwerer Third-Party Widgets verhindert INP-Spitzen.

### Schulen & Campus

**Promise:** Enrollment-Flows performen auf Mobile (> 60% Nutzung) nur mit stabilen CWV.

Enrollment-StepFlow, Update-Listings und Payment-Flows müssen auf Mobile < 180 ms INP liefern (60%+ Mobile-Anteil). Lazy Loading für Medien, Prefetching für StepFlow-Schritte und Worker-basierte Validierung sichern Experience. RUM in Kombination mit Completion Rate zeigt, ob Einbrüche auf Performance zurückgehen.

### Behörden & öffentliche Dienste

**Promise:** Digital Take-up ≥ 70% gelingt nur mit verlässlicher Performance.

Top-Tasks, Formular-Status und Servicecockpit-Dashboards dürfen auch bei Kampagnen keine LCP/INP-Ausreißer haben. Cloudflare Workers / AWS Lambda@Edge verkürzen Server-Antwortzeiten; Caching-Strategien verhindern Lastspitzen. Accessibility + Performance: stabile Layouts und berechenbare Reaktionszeiten sind BFSG/BITV-Relevanz.

---

## 📊 RICHTWERTE (P75)

| Metrik | Gut | Verbesserungswürdig | Schlecht |
|--------|-----|---------------------|----------|
| **LCP** | ≤ 2,5 s | 2,5–4,0 s | > 4,0 s |
| **INP** | ≤ 200 ms | 200–500 ms | > 500 ms |
| **CLS** | ≤ 0,1 | 0,1–0,25 | > 0,25 |

**Ambitionierte Ziele für regulierte Branchen:**
- LCP: ≤ 2,3 s (Kanzleien), ≤ 2,0 s (Bildung/Behörden)
- INP: ≤ 150 ms (Intake/StepFlow), ≤ 180 ms (Mobile)
- CLS: ≤ 0,05 (barrierefreie Seiten)

---

## 📊 SYNONYME & KEYWORDS

**Synonyme:**
- CWV
- Google UX Metriken
- Page Experience Signals

**Keywords:**
- Largest Contentful Paint
- Interaction to Next Paint
- Cumulative Layout Shift
- Field Data
- Chrome UX Report

---

**Wortanzahl:** ~1.100 Wörter
**Review-Status:** ✅ Final
**Quellen-Qualität:** Google web.dev + Chrome Developers
**Segment-Abdeckung:** Vollständig (Kanzlei, Bildung, Behörden)
