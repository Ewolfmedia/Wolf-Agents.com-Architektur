# Time to First Byte (TTFB)

## 📊 META-INFORMATIONEN

- **Term ID**: `ttfb`
- **Begriff (DE)**: Time to First Byte
- **Begriff (EN)**: Time to First Byte (TTFB)
- **Kategorie**: Performance & Web Vitals
- **Status**: ✅ Implementiert (1× verwendet)
- **Letzte Review**: 2025-10-25

---

## 💡 INFOTOOLTIP-DEFINITION

**Was ist TTFB?** Die Zeit, die Ihr Server braucht, um auf eine Anfrage zu reagieren – niedrige Werte (unter 200 ms) bedeuten, dass Ihre Seite schnell zu laden beginnt.

---

## 📖 AUSFÜHRLICHE ERKLÄRUNG

Time to First Byte (TTFB) misst, wie schnell der Server das erste Byte liefert – Grundlage für schnelle LCP/INP-Werte. TTFB beschreibt die Dauer zwischen HTTP-Request des Browsers und dem ersten empfangenen Byte der Antwort. Werte unter 200 ms gelten als sehr gut; hohe Werte deuten auf langsame Server, fehlendes Caching oder Netzwerkprobleme hin.

TTFB besteht aus drei Komponenten:

- **Redirect Time:** Zeit für HTTP-Redirects (falls vorhanden)
- **Service Worker Time:** Zeit für Service-Worker-Verarbeitung (falls aktiviert)
- **Backend Time:** Zeit für Server-Verarbeitung und Netzwerk-Latenz

Für Kanzleien bedeutet TTFB: Mandantenformular reagiert sofort – TTFB ≤ 200 ms. Für Bildungseinrichtungen: Enrollment & Campus-Dashboards bleiben weltweit flott. Für Behörden: Bürgerdienste erfüllen BFSG Performance-Vorgaben.

Die Optimierung erfolgt über CDN & Edge (Cloudflare, CloudFront, Fastly oder Netlify Edge nutzen, um Anfragen nah am Nutzer zu bedienen), Origin optimieren (API-Calls cachen, Datenbankabfragen optimieren, Serverless-Kaltstarts reduzieren) und Monitoring einbinden (Server-Logs, RUM und Synthetic Checks kombinieren, Alerts bei TTFB > 400 ms).

### Warum ist es wichtig?

TTFB ist die Grundlage für alle weiteren Performance-Metriken:

- **Basis für gutes LCP:** Ein niedriger TTFB sorgt dafür, dass der Largest Contentful Paint schnell starten kann
- **Ranking-Signal:** Google berücksichtigt Serverantwortzeiten in den PageSpeed-Signalen
- **Verlässliche Infrastruktur:** In Kanzlei-Setups hilft ein schneller TTFB, dass Formulare und Dashboards ohne Verzögerung reagieren
- **Globale Performance:** Geo-lokalisierte Caches halten TTFB niedrig, auch bei internationalen Nutzern

Für regulierte Branchen (Kanzleien, Bildungseinrichtungen, Behörden) ist TTFB ≤ 200 ms unverzichtbar für gute Nutzererfahrung.

### Typische Anwendungsfälle

- **Use Case 1: Kanzlei-Formulare** — CDN-Edge (Cloudflare Pages/Workers) oder Serverless-Funktionen reduzieren Wartezeit für Intake & Dashboards. Mandantenformular reagiert sofort – TTFB ≤ 200 ms.
- **Use Case 2: Campus-Dashboards** — Geo-lokalisierte Caches, HTTP/3 und Connection Reuse halten TTFB niedrig trotz Peaks zu Bewerbungsphasen. Enrollment & Campus-Dashboards bleiben weltweit flott.
- **Use Case 3: Bürgerdienste** — CloudFront/Edge-Worker, Pre-rendering und schlanke APIs verhindern serverseitige Verzögerungen. Bürgerdienste erfüllen BFSG Performance-Vorgaben.

---

## 🔗 VERWANDTE BEGRIFFE

- **Siehe auch**: Core Web Vitals, RUM, LCP, Server-Side Rendering
- **Unterschied zu**: LCP (misst Ladezeit des größten Elements), INP (misst Interaktivität)
- **Übergeordnet**: Performance-Governance, Server Performance
- **Untergeordnet**: CDN, Edge Caching, Origin Optimization

---

## 📍 VERWENDUNG AUF DER WEBSITE

### InfoTooltip-Verwendung (1×)

- ✅ `/index` (Zeile 361)

### Erwähnungen ohne InfoTooltip

- `/leistungen/stufe-b-cloudflare-pages` — TTFB-Optimierung mit Cloudflare Workers
- `/leistungen/stufe-c-aws-cloudfront` — TTFB-Optimierung mit AWS CloudFront
- `/branchen/kanzleien` — Performance-Budgets für Mandatsmarketing
- `/branchen/schulen-bildung` — Globale Enrollment-Performance
- `/branchen/oeffentliche-einrichtungen` — Bürgerdienste Performance-Monitoring

### Kontext der Verwendungen

**Homepage:** TTFB als Teil der Performance-Strategie, zusammen mit RUM und Core Web Vitals.

---

## 🛠️ PRAKTISCHE IMPLEMENTIERUNG

### 1. CDN & Edge aktivieren

**Aufgabe:** Cloudflare, CloudFront, Fastly oder Netlify Edge nutzen, um Anfragen nah am Nutzer zu bedienen.

**Schritte:**
- CDN-Provider auswählen (Cloudflare Pages, AWS CloudFront, Fastly)
- Edge-Locations weltweit aktivieren (200+ PoPs)
- HTTP/3 und Brotli Compression aktivieren
- Cache-Strategien definieren (s-maxage, stale-while-revalidate)

### 2. Origin optimieren

**Aufgabe:** API-Calls cachen, Datenbankabfragen optimieren, Serverless-Kaltstarts reduzieren.

**Schritte:**
- API-Responses cachen (Redis, CloudFlare KV, AWS ElastiCache)
- Datenbankabfragen optimieren (Indexes, Query-Caching)
- Serverless-Kaltstarts reduzieren (Provisioned Concurrency, Keep-Warm)
- Static Site Generation (SSG) statt Server-Side Rendering (SSR)

### 3. Monitoring einbinden

**Aufgabe:** Server-Logs, RUM und Synthetic Checks (Pingdom, SpeedCurve) kombinieren, Alerts bei TTFB > 400 ms.

**Schritte:**
- RUM-Tracking für TTFB-Werte einrichten (web-vitals Library)
- Synthetic Monitoring mit Pingdom, SpeedCurve oder Checkly
- Server-Logs analysieren (NGINX, CloudFront Logs)
- Alerts bei Überschreitung definieren (TTFB > 400 ms = Critical)

---

## 📚 EXTERNE RESSOURCEN

- **[web.dev – TTFB](https://web.dev/articles/ttfb)** — Offizielle Google-Dokumentation
- **[Cloudflare – Performance Guidelines](https://developers.cloudflare.com/fundamentals/performance/)** — Cloudflare-spezifische Optimierungen
- **[AWS – CloudFront Optimization](https://docs.aws.amazon.com/AmazonCloudFront/latest/DeveloperGuide/optimizing-cloudfront.html)** — AWS CloudFront Best Practices

---

## 🎯 SEGMENT-PERSPEKTIVEN

### Kanzleien & Boutiquen

**Promise:** Mandantenformular reagiert sofort – TTFB ≤ 200 ms.

CDN-Edge (Cloudflare Pages/Workers) oder Serverless-Funktionen reduzieren Wartezeit für Intake & Dashboards. Edge-Caching und CDN aktivieren. Response Promise bleibt messbar, auch mit globaler Infrastruktur.

### Schulen & Campus

**Promise:** Enrollment & Campus-Dashboards bleiben weltweit flott.

Geo-lokalisierte Caches, HTTP/3 und Connection Reuse halten TTFB niedrig trotz Peaks zu Bewerbungsphasen. Internationale Kampagnen profitieren von Edge-Locations weltweit.

### Behörden & öffentliche Dienste

**Promise:** Bürgerdienste erfüllen BFSG Performance-Vorgaben.

CloudFront/Edge-Worker, Pre-rendering und schlanke APIs verhindern serverseitige Verzögerungen. Transparente Performance-Nachweise stärken Vertrauen.

---

## 📊 RICHTWERTE

| TTFB | Bewertung |
|------|-----------|
| ≤ 200 ms | Sehr gut |
| 200–400 ms | Gut |
| 400–600 ms | Verbesserungswürdig |
| > 600 ms | Schlecht |

**Ambitionierte Ziele für regulierte Branchen:**
- Kanzleien: ≤ 200 ms (Intake-Formulare)
- Bildung/Behörden: ≤ 250 ms (globale Nutzer)

---

## 📊 SYNONYME & KEYWORDS

**Synonyme:**
- Server Response Time
- TTFB
- Backend Latency

**Keywords:**
- Time to First Byte
- Server Performance
- Core Web Vitals
- CDN Optimization

---

**Wortanzahl:** ~900 Wörter
**Review-Status:** ✅ Final
**Quellen-Qualität:** Google web.dev + Cloudflare + AWS
**Segment-Abdeckung:** Vollständig (Kanzlei, Bildung, Behörden)
