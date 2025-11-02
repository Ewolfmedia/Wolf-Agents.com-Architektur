# Cumulative Layout Shift (CLS)

## 📊 META-INFORMATIONEN

- **Term ID**: `cls`
- **Begriff (DE)**: Cumulative Layout Shift
- **Begriff (EN)**: Cumulative Layout Shift (CLS)
- **Kategorie**: Performance & Web Vitals
- **Status**: ⚠️ Implementiert, aber nicht verwendet (0×)
- **Letzte Review**: 2025-10-25

---

## 💡 INFOTOOLTIP-DEFINITION

**Was ist CLS?** Eine Metrik, die misst, wie stark sich Elemente auf Ihrer Seite unerwartet verschieben – niedrige Werte (≤ 0,1) bedeuten ein stabiles, nutzerfreundliches Layout ohne störende Sprünge.

---

## 📖 AUSFÜHRLICHE ERKLÄRUNG

Cumulative Layout Shift (CLS) misst unvorhergesehene Layout-Verschiebungen. Werte ≤ 0,1 stehen für ruhige, vertrauenswürdige Interfaces. CLS bewertet, wie stark sich sichtbare Elemente unerwartet verschieben. Hohe Werte entstehen durch nachladende Bilder, Fonts oder Ads – und nerven Nutzer:innen massiv.

Typische Ursachen für hohe CLS-Werte:

- **Bilder ohne Dimensionen:** Fehlende `width`/`height`-Attribute
- **Nachladende Fonts:** FOIT/FOUT (Flash of Invisible/Unstyled Text)
- **Dynamische Inhalte:** Ads, Consent-Banner ohne Platzreservierung
- **Animations-Fehler:** CSS-Animationen mit `top`/`left` statt `transform`

Für Kanzleien bedeutet CLS: Mandanten klicken nicht daneben – Intake-Formulare bleiben ruhig. Für Bildungseinrichtungen: Enrollment-StepFlow & Kurslisten bleiben stabil auf Mobile. Für Behörden: Bürgerdienste erfüllen BFSG-Anforderungen ohne Layout-Sprünge.

Die Optimierung erfolgt über Platz reservieren (Bilder, Videos, Ads und eingebettete Widgets mit width/height bzw. aspect-ratio versehen), Fonts & UI-Bausteine optimieren (Font loading mit `font-display`, icon-sprites und UI-Komponenten mit CSS-Reserven oder Skeletons) und RUM-Überwachung (CLS in Real User Monitoring messen und bei Regressionen alarmieren).

### Warum ist es wichtig?

CLS ist entscheidend für Usability und Vertrauen:

- **Usability:** Verhindert Fehlklicks auf Buttons/Formulare
- **Vertrauen:** Ruhige Layouts wirken professionell und seriös
- **SEO:** Bestandteil der Core Web Vitals und damit Ranking-Faktor
- **Accessibility:** Stabile Layouts sind BFSG/BITV-Relevanz für Screenreader und Keyboard-Nutzer

Für regulierte Branchen (Kanzleien, Bildungseinrichtungen, Behörden) ist CLS ≤ 0,1 (ambitioniert ≤ 0,05) unverzichtbar für gute Nutzererfahrung.

### Typische Anwendungsfälle

- **Use Case 1: Kanzlei-Intake-Formulare** — Consent-Banner, Hero-Bilder und FAQ-Module werden mit reservierten Höhen, Skeletons und Preload sauber eingebunden. Mandanten klicken nicht daneben – Intake-Formulare bleiben ruhig.
- **Use Case 2: Enrollment-StepFlow** — Reserven für Medien, Tabellen und Accordion-Inhalte verhindern, dass Eltern/Studierende Buttons verfehlen. Enrollment-StepFlow & Kurslisten bleiben stabil auf Mobile.
- **Use Case 3: Bürgerdienste** — Top-Tasks, Status-Widgets und Formular-Felder benötigen feste Slots, damit Screenreader & Keyboard-Nutzer:innen sicher navigieren. Bürgerdienste erfüllen BFSG-Anforderungen ohne Layout-Sprünge.

---

## 🔗 VERWANDTE BEGRIFFE

- **Siehe auch**: Core Web Vitals, LCP, INP, Skeleton Screens
- **Unterschied zu**: LCP (misst Ladezeit), INP (misst Interaktivität)
- **Übergeordnet**: Performance-Governance, User Experience (UX)
- **Untergeordnet**: Layout Shift Prevention, Font Loading, CSS Reserves

---

## 📍 VERWENDUNG AUF DER WEBSITE

### InfoTooltip-Verwendung (0×)

⚠️ **Nicht verwendet** — Empfehlung: InfoTooltip auf folgenden Seiten hinzufügen:
- `/leistungen/barrierefreiheit` (CLS als Accessibility-Aspekt)
- `/leistungen/redesign-ux-sprints` (Layout-Stabilität)
- `/leistungen/stufe-a-astro-ftp` (CLS-Budget für Komponenten)

### Erwähnungen ohne InfoTooltip

- `/branchen/kanzleien` — CLS-Prävention für Intake-Formulare erwähnt
- `/branchen/schulen-bildung` — Enrollment-StepFlow CLS-Ziele erwähnt
- `/branchen/oeffentliche-einrichtungen` — Bürgerdienste CLS-Monitoring erwähnt

### Kontext der Erwähnungen

CLS wird primär im Performance-Governance-Kontext erwähnt, zusammen mit Core Web Vitals und Layout-Stabilität.

---

## 🛠️ PRAKTISCHE IMPLEMENTIERUNG

### 1. Platz reservieren

**Aufgabe:** Bilder, Videos, Ads und eingebettete Widgets mit width/height bzw. aspect-ratio versehen.

**Schritte:**
- Width/Height-Attribute für alle Images/Videos setzen
- CSS `aspect-ratio` für responsive Elemente nutzen
- Reserve Space für Ads/Widgets (z.B. `min-height` in CSS)
- Skeleton Screens für dynamische Inhalte (Loading States)

### 2. Fonts & UI-Bausteine optimieren

**Aufgabe:** Font loading (`font-display`), icon-sprites und UI-Komponenten mit CSS-Reserven oder Skeletons versehen.

**Schritte:**
- `font-display: swap` oder `optional` für Fonts (verhindert FOIT/FOUT Shifts)
- Icon-Fonts durch SVG-Sprites ersetzen (keine Font-Ladezeit)
- UI-Komponenten mit CSS-Reserven (z.B. Accordion mit `min-height`)
- Consent-Banner mit reservierter Höhe (z.B. `height: 80px` im HTML)

### 3. RUM-Überwachung

**Aufgabe:** CLS in Real User Monitoring (z.B. web-vitals JS + `/rum` endpoint) messen und bei Regressionen alarmieren.

**Schritte:**
- web-vitals Library integrieren (`onCLS` Callback)
- RUM-API für Datenerfassung (`/api/rum` Endpoint)
- Alerts bei P75 CLS > 0,1 (Slack, E-Mail, PagerDuty)
- Servicecockpit-KPIs verknüpfen (Completion Rate, Lead-to-Call Rate)

---

## 📚 EXTERNE RESSOURCEN

- **[web.dev – CLS](https://web.dev/articles/cls)** — Offizielle Google-Dokumentation
- **[Chrome Developers – Optimize CLS](https://web.dev/articles/optimize-cls)** — Best Practices für CLS-Optimierung
- **[HTTP Archive – Core Web Vitals](https://httparchive.org/reports/chrome-ux-report)** — Historische Trends und Benchmark-Daten

---

## 🎯 SEGMENT-PERSPEKTIVEN

### Kanzleien & Boutiquen

**Promise:** Mandanten klicken nicht daneben – Intake-Formulare bleiben ruhig.

Consent-Banner, Hero-Bilder und FAQ-Module werden mit reservierten Höhen, Skeletons und Preload sauber eingebunden. Ruhige Layouts wirken professionell und seriös.

### Schulen & Campus

**Promise:** Enrollment-StepFlow & Kurslisten bleiben stabil auf Mobile.

Reserven für Medien, Tabellen und Accordion-Inhalte verhindern, dass Eltern/Studierende Buttons verfehlen. Mobile-First-Optimierung ist entscheidend für Enrollment-Erfolg.

### Behörden & öffentliche Dienste

**Promise:** Bürgerdienste erfüllen BFSG-Anforderungen ohne Layout-Sprünge.

Top-Tasks, Status-Widgets und Formular-Felder benötigen feste Slots, damit Screenreader & Keyboard-Nutzer:innen sicher navigieren. Accessibility + Performance: stabile Layouts sind BFSG/BITV-Relevanz.

---

## 📊 RICHTWERTE (P75)

| CLS | Bewertung |
|-----|-----------|
| ≤ 0,1 | Gut |
| 0,1–0,25 | Verbesserungswürdig |
| > 0,25 | Schlecht |

**Ambitionierte Ziele für regulierte Branchen:**
- Kanzleien: ≤ 0,05 (Intake-Formulare)
- Bildung: ≤ 0,05 (Mobile Enrollment)
- Behörden: ≤ 0,05 (Barrierefreie Seiten)

---

## 📊 SYNONYME & KEYWORDS

**Synonyme:**
- CLS
- Layout Stability
- Visual Stability

**Keywords:**
- Cumulative Layout Shift
- Layout Shift
- Core Web Vitals
- Skeleton Screens

---

**Wortanzahl:** ~850 Wörter
**Review-Status:** ✅ Final
**Quellen-Qualität:** Google web.dev + Chrome Developers
**Segment-Abdeckung:** Vollständig (Kanzlei, Bildung, Behörden)
**Empfehlung:** InfoTooltip auf 2-3 Seiten hinzufügen (nicht verwendet trotz Implementierung)
