# Largest Contentful Paint (LCP)

## 📊 META-INFORMATIONEN

- **Term ID**: `lcp`
- **Begriff (DE)**: Largest Contentful Paint
- **Begriff (EN)**: Largest Contentful Paint (LCP)
- **Kategorie**: Performance & Web Vitals
- **Status**: ⚠️ Implementiert, aber nicht verwendet (0×)
- **Letzte Review**: 2025-10-25

---

## 💡 INFOTOOLTIP-DEFINITION

**Was ist LCP?** Eine Metrik, die misst, wie schnell das größte sichtbare Element Ihrer Seite (z.B. Hero-Bild oder Überschrift) lädt – Werte unter 2,5 Sekunden sorgen für einen guten ersten Eindruck.

---

## 📖 AUSFÜHRLICHE ERKLÄRUNG

Largest Contentful Paint (LCP) misst, wie schnell das größte sichtbare Element (Hero, Bild, Überschrift) geladen ist. Google empfiehlt ≤ 2,5 s. LCP beschreibt, wie lange es dauert, bis das größte sichtbare Element – häufig ein Hero-Bild oder Überschrift – geladen und gerendert ist. Google empfiehlt P75-Werte ≤ 2,5 Sekunden.

Die häufigsten LCP-Elemente sind:

- **Hero-Images:** Große Bilder im Above-the-fold-Bereich
- **Textblöcke:** Überschriften oder Paragraphen (wenn kein großes Bild vorhanden)
- **Video-Thumbnails:** Poster-Bilder von Videos
- **Hintergrundbilder:** CSS-Hintergrundbilder mit `url()`

Für Kanzleien bedeutet LCP: Hero & Proof erscheinen ≤ 2,3 s – Mandanten vertrauen schneller. Für Bildungseinrichtungen: Anmelde-Seiten laden schnell auf mobilen Geräten (>60% Nutzung). Für Behörden: Bürgerdienste sind ohne Verzögerung erreichbar (BFSG-Konformität).

Die Optimierung erfolgt über Hero Assets optimieren (Responsive Images, AVIF/WebP, `fetchpriority`, `loading=lazy` für Non-critical Graphics), Critical Rendering Path verkürzen (Critical CSS inline, restliches CSS/JS deferred; Fonts mit `preload` + `font-display`) und TTFB & CDN prüfen (Origin-Performance, Edge Caching und HTTP/3 aktivieren).

### Warum ist es wichtig?

LCP ist der entscheidende Faktor für den ersten Eindruck einer Website:

- **First Impression:** Besucher:innen sehen schnell die Kernbotschaft
- **Ranking-Signal:** Schlechter LCP kann SEO-Rankings drücken
- **Mandantenreisen:** Gerade bei Kanzlei-Seiten entscheidet die Startsekunde über Vertrauen
- **Conversion-Optimierung:** Schneller LCP führt zu höheren Conversions

Für regulierte Branchen (Kanzleien, Bildungseinrichtungen, Behörden) ist LCP ≤ 2,5 s (ambitioniert ≤ 2,3 s) unverzichtbar für gute Nutzererfahrung.

### Typische Anwendungsfälle

- **Use Case 1: Kanzlei-Hero-Bilder** — Optimierte Hero-Bilder, Preload-Fonts und Edge-Caching sichern die erste Impression. Hero & Proof erscheinen ≤ 2,3 s – Mandanten vertrauen schneller.
- **Use Case 2: Enrollment-Landingpages** — Responsive Bilder, Critical CSS und CDN reduzieren Wartezeiten für Eltern/Studierende. Anmelde-Seiten laden schnell auf mobilen Geräten (>60% Nutzung).
- **Use Case 3: Bürgerdienste-Startseiten** — Static-first Aufbau, regionale CDNs und Server-Tuning halten TTFB & LCP niedrig. Bürgerdienste sind ohne Verzögerung erreichbar (BFSG-Konformität).

---

## 🔗 VERWANDTE BEGRIFFE

- **Siehe auch**: Core Web Vitals, INP, TTFB, Image Optimization
- **Unterschied zu**: FCP (First Contentful Paint) — LCP misst größtes Element, FCP erstes Element
- **Übergeordnet**: Performance-Governance, User Experience (UX)
- **Untergeordnet**: Hero Asset Optimization, Critical CSS, Edge Caching

---

## 📍 VERWENDUNG AUF DER WEBSITE

### InfoTooltip-Verwendung (0×)

⚠️ **Nicht verwendet** — Empfehlung: InfoTooltip auf folgenden Seiten hinzufügen:
- `/leistungen/redesign-ux-sprints` (Hero-Optimierung)
- `/leistungen/stufe-0-ftp-classic` (LCP-Budget auch für einfache Setups)
- `/leistungen/stufe-a-astro-ftp` (LCP-Optimierung mit Astro)

### Erwähnungen ohne InfoTooltip

- `/branchen/kanzleien` — LCP-Budget für Hero-Bilder erwähnt
- `/branchen/schulen-bildung` — Enrollment-Landingpages LCP-Ziele erwähnt
- `/branchen/oeffentliche-einrichtungen` — Bürgerdienste LCP-Monitoring erwähnt

### Kontext der Erwähnungen

LCP wird primär im Performance-Governance-Kontext erwähnt, zusammen mit Core Web Vitals und Hero-Optimierung.

---

## 🛠️ PRAKTISCHE IMPLEMENTIERUNG

### 1. Hero Assets optimieren

**Aufgabe:** Responsive Images, AVIF/WebP, `fetchpriority`, `loading=lazy` für Non-critical Graphics.

**Schritte:**
- Hero-Images in AVIF/WebP konvertieren (mit PNG/JPEG Fallback)
- Responsive Images mit `srcset` und `sizes`
- `fetchpriority="high"` für LCP-Element setzen
- `loading="lazy"` für Below-the-fold Images

### 2. Critical Rendering Path verkürzen

**Aufgabe:** Critical CSS inline, restliches CSS/JS deferred; Fonts mit `preload` + `font-display`.

**Schritte:**
- Critical CSS inline in `<head>` einbinden
- Non-critical CSS mit `media="print" onload="this.media='all'"`
- JavaScript mit `defer` oder `async` laden
- Fonts preload mit `<link rel="preload" as="font">`
- `font-display: swap` oder `optional` für Fonts

### 3. TTFB & CDN prüfen

**Aufgabe:** Origin-Performance, Edge Caching (Cloudflare/AWS) und HTTP/3 aktivieren.

**Schritte:**
- CDN einrichten (Cloudflare Pages, AWS CloudFront, Fastly)
- Edge-Locations weltweit aktivieren
- HTTP/3 und Brotli Compression aktivieren
- Cache-Strategien definieren (s-maxage, stale-while-revalidate)

---

## 📚 EXTERNE RESSOURCEN

- **[web.dev – LCP](https://web.dev/articles/lcp)** — Offizielle Google-Dokumentation
- **[Chrome Developers – Optimize LCP](https://web.dev/articles/optimize-lcp)** — Best Practices für LCP-Optimierung
- **[SpeedCurve – LCP Research](https://www.speedcurve.com/blog/web-vitals-user-experience/)** — Forschung zu LCP und Nutzererfahrung

---

## 🎯 SEGMENT-PERSPEKTIVEN

### Kanzleien & Boutiquen

**Promise:** Hero & Proof erscheinen ≤ 2,3 s – Mandanten vertrauen schneller.

Optimierte Hero-Bilder, Preload-Fonts und Edge-Caching sichern die erste Impression. Gerade bei Kanzlei-Seiten entscheidet die Startsekunde über Vertrauen.

### Schulen & Campus

**Promise:** Anmelde-Seiten laden schnell auf mobilen Geräten (>60% Nutzung).

Responsive Bilder, Critical CSS und CDN reduzieren Wartezeiten für Eltern/Studierende. Mobile-First-Optimierung ist entscheidend für Enrollment-Erfolg.

### Behörden & öffentliche Dienste

**Promise:** Bürgerdienste sind ohne Verzögerung erreichbar (BFSG-Konformität).

Static-first Aufbau, regionale CDNs und Server-Tuning halten TTFB & LCP niedrig. Accessibility + Performance: schnelle Ladezeiten sind BFSG/BITV-Relevanz.

---

## 📊 RICHTWERTE (P75)

| LCP | Bewertung |
|-----|-----------|
| ≤ 2,5 s | Gut |
| 2,5–4,0 s | Verbesserungswürdig |
| > 4,0 s | Schlecht |

**Ambitionierte Ziele für regulierte Branchen:**
- Kanzleien: ≤ 2,3 s (Hero & Proof)
- Bildung: ≤ 2,0 s (Mobile Enrollment)
- Behörden: ≤ 2,0 s (Bürgerdienste)

---

## 📊 SYNONYME & KEYWORDS

**Synonyme:**
- LCP
- Largest Contentful Paint
- Hero Load Time

**Keywords:**
- Largest Contentful Paint
- Core Web Vitals
- Page Speed
- Hero Optimization

---

**Wortanzahl:** ~850 Wörter
**Review-Status:** ✅ Final
**Quellen-Qualität:** Google web.dev + Chrome Developers
**Segment-Abdeckung:** Vollständig (Kanzlei, Bildung, Behörden)
**Empfehlung:** InfoTooltip auf 2-3 Seiten hinzufügen (nicht verwendet trotz Implementierung)
