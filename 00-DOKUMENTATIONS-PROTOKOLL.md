# DOKUMENTATIONS-PROTOKOLL

**Version:** 1.0
**Erstellt am:** 2025-10-30
**Zweck:** Definiert Standards für die Dokumentation aller Unterseiten von Wolf-Agents.com

---

## 🎯 ZIELSETZUNG

Diese Dokumentation dient dazu, jede Unterseite der Website in **strukturierter, textbasierter Form** abzubilden, um:

1. **Content-Optimierung** mit externen LLMs durchzuführen (SEO/AIO/GEO/AEO)
2. **Architektur-Analyse** zu ermöglichen (Wie sind Seiten aufgebaut? Welche Patterns werden genutzt?)
3. **Strategische Planung** zu unterstützen (Welche Seiten erweitern? Welche Branchen hinzufügen?)
4. **Konsistenz** über alle Dokumentationen hinweg sicherzustellen

**WICHTIG:** Wir dokumentieren den **IST-Zustand**, nicht den Soll-Zustand! Keine prägenden Optimierungsvorschläge, die LLMs in eine bestimmte Richtung drängen könnten.

---

## 📋 TEMPLATE-STRUKTUR

Jede Seiten-Dokumentation folgt diesem Aufbau:

### 1. Header & Meta-Informationen
- Seitentitel (H1)
- Dokumentations-Datum
- Status (IST-Zustand)

**Tabelle mit:**
- URL
- Datei (Pfad zur Astro-Komponente)
- Title Tag
- Meta Description
- Canonical URL
- Noindex (Ja/Nein)
- Geschätzte Zeichenanzahl (ohne Code/HTML)
- Geschätzte Wortanzahl
- Geschätzte Lesedauer
- Anzahl Sections
- Anzahl H1, H2, H3

### 2. Verlinkungsstruktur
- **Interne Links (ausgehend):** Alle Links, die VON dieser Seite ausgehen
- **Externe Links:** Falls vorhanden
- **Gesamtanzahl interne Links:** Schätzung
- **Backlinks (optional):** Welche Seiten verlinken AUF diese Seite?

### 3. Layout & Semantische Struktur

**Für jede Section:**

#### Section-Header
- **Komponente:** Name der Astro-Komponente (z.B. `<Hero />`, `<Section tone="dark" />`)
- **Layout-Pattern:** Beschreibender Name (z.B. "Hero Dark Grid", "3-Column Card Grid")
- **Hintergrund:** Genaue Farbe (CSS-Variable + Hex-Code)

#### Hintergrund-Details (falls relevant)
- Gitter-Pattern (ja/nein, Grid-Größe)
- Glow-Effekt (Position, Farbe, Opacity)
- Gradient (falls vorhanden)

#### Semantik & Content (Code-Block-Format)
```
SECTION#id (Attribute: tone, glow, grid, padding-classes)
│
├── Badge (falls vorhanden)
│   Text: "[Exakter Text]"
│   Farbe: CSS-Variable + Hex-Code
│   Background: CSS-Variable + rgba
│   Font: Font-Family, Font-Size (px + rem), Font-Weight
│   Padding: Tailwind-Class (px-X py-Y) + Pixel-Werte
│   Border-radius: Tailwind-Class + Pixel
│   [Weitere Styling-Details]
│
├── H1/H2/H3 (Headline)
│   Text: "[Exakter Headline-Text]"
│   Font: Font-Family, Font-Size @ Mobile/Tablet/Desktop (px + rem)
│   Farbe: CSS-Variable + Hex-Code/rgba
│   Line-height: Wert (tight/snug/normal/relaxed)
│   Letter-spacing: Wert (em)
│   Text-shadow: Falls vorhanden (Werte)
│   Max-width: Tailwind-Class + Pixel
│   Margin-bottom: Tailwind-Class (mb-X) + Pixel
│
├── Paragraph (Intro/Description)
│   Text: "[Exakter Text - bei sehr langen Texten: erste 100 Wörter + '...']"
│   Font: Font-Family, Font-Size @ Mobile/Desktop
│   Farbe: CSS-Variable + rgba/Hex
│   Line-height: Wert
│   Max-width: Falls gesetzt
│   Margin-top/bottom: Tailwind-Classes + Pixel
│   │
│   └── Inline-Elemente (falls vorhanden)
│       - <InfoTooltip termId="xyz" /> → Tooltip-Link
│       - <strong> → Fettgedruckte Begriffe
│       - <a href="/link"> → Inline-Links
│
├── Grid/Flex-Layout (falls Cards/Elemente)
│   Display: grid/flex
│   Grid-cols: Anzahl @ Mobile/Tablet/Desktop
│   Gap: Tailwind-Class (gap-X) + Pixel
│   Items-align/justify: Werte
│   │
│   ├── Card 1 (falls wiederholende Elemente)
│   │   Background: CSS-Variable + Hex/rgba
│   │   Border: Dicke + Farbe
│   │   Border-radius: Pixel
│   │   Padding: Tailwind + Pixel
│   │   Shadow: CSS-Variable oder exakte Werte
│   │   Hover-Effekt: transform + shadow-Änderung
│   │   Transition: Werte
│   │   │
│   │   ├── Icon/Image (falls vorhanden)
│   │   │   Size: Pixel × Pixel
│   │   │   Source: Pfad oder SVG-inline
│   │   │   Alt-Text: "[Text]"
│   │   │
│   │   ├── H3 (Card-Title)
│   │   │   Text: "[Exakter Text]"
│   │   │   [Font-Details wie oben]
│   │   │
│   │   ├── Description
│   │   │   Text: "[Exakter Text]"
│   │   │   [Font-Details]
│   │   │
│   │   └── CTA-Link/Button
│   │       Text: "[Button-Text]"
│   │       Href: /link
│   │       [Button-Styling-Details]
│   │
│   ├── Card 2
│   │   [Struktur wie Card 1]
│   │
│   └── Card N
│       ...
│
└── Details/Summary (falls Accordion)
    Summary: "[Text]"
    Icon: Plus/Minus (Rotation bei open)
    Hidden-Content: "[Text bei expanded]"
    [Styling-Details]
```

#### Abstände & Layout (Zusammenfassung)
- Outer Padding: py-X @ Mobile, py-Y @ Tablet, py-Z @ Desktop
- Container max-width: Tailwind-Class + Pixel
- Inner Padding (falls Card): p-X
- Grid-Gap: gap-X + Pixel
- Margin-bottom (zwischen Sections): mb-X

---

### 4. Design-System-Details

**Farbnutzung (Tabelle pro Section):**

| Element | CSS-Variable | Hex/rgba-Wert | Verwendung |
|---------|--------------|---------------|------------|
| Background | `--surface-dark` | #04060D | Section-Hintergrund |
| H2-Text | `#FFFFFF` | #FFFFFF | Headline |
| Body-Text | `--text-secondary-on-dark` | rgba(249,250,251,0.72) | Paragraphen |
| Border | `--border-on-dark-subtle` | rgba(255,255,255,0.18) | Card-Borders |

**Typografie-Details:**
- Font-Family: Inter (Weights: Regular/Medium/SemiBold/Bold)
- Font-Sizes: Mobile → Tablet → Desktop (mit px + rem)
- Line-Heights: tight (1.15), snug (1.25), normal (1.5), relaxed (1.75)
- Letter-Spacing: -0.02em (Headlines), 0 (Body), 0.18em-0.3em (Uppercase-Labels)

**Spacing-System:**
- Section-Padding: py-20/28/32 (80px/112px/128px)
- Container-Padding: px-6/12 (24px/48px)
- Gaps: gap-4/6/8 (16px/24px/32px)

**Border-Radius:**
- Small: 8px (rounded-lg)
- Medium: 12px (rounded-xl)
- Large: 20px (rounded-[20px])
- XL: 24px (rounded-3xl)
- Full: 9999px (rounded-full)

---

### 5. Responsive Breakpoints

**Tabelle:**

| Breakpoint | Screen-Width | Grid-Cols | Font-Size H2 | Padding |
|------------|--------------|-----------|--------------|---------|
| Mobile | <640px | 1 | 1.875rem (30px) | px-6 py-20 |
| Tablet | 640-1023px | 2 | 2.25rem (36px) | px-8 py-28 |
| Desktop | ≥1024px | 3-4 | 2.25-3.75rem (36-60px) | px-12 py-32 |

**Hauptänderungen:**
- Grid-Layout: 1-col @ Mobile → 2-col @ Tablet → 3-4-col @ Desktop
- Font-Sizes: Skalierung (z.B. H1: 36px → 48px → 72px)
- Padding: Zunehmendes Padding mit Bildschirmgröße

---

### 6. Komponenten-Bibliothek

**Genutzte Astro-Components:**

| Komponente | Datei | Props (Key-Value-Paare) |
|------------|-------|-------------------------|
| `<Hero />` | `/src/components/Hero.astro` | title, subtitle, ctaText, ctaHref, variant, badge, ... |
| `<Section />` | `/src/components/Section.astro` | tone="light/dark", glow="center/top/none", grid={true/false} |
| `<CardGroup />` | `/src/components/CardGroup.astro` | title, intro, mobilePattern="accordion", columns={3}, items=[...] |
| `<InfoTooltip />` | `/src/components/InfoTooltip.astro` | termId="xyz", mode="auto/modal" |

**Für jede genutzte Komponente:**
- Vollständige Props-Liste dokumentieren
- Beispiel-Code-Snippet (falls komplex)

---

### 7. SEO & Strukturierte Daten

**Schema.org Markup:**
- Typ (z.B. FAQPage, Article, Organization)
- Vollständiger JSON-LD-Code (falls nicht zu lang)
- Zusammenfassung der strukturierten Daten

**Open Graph / Twitter Card:**
- og:title, og:description, og:image
- twitter:card, twitter:title

---

### 8. Barrierefreiheit (WCAG 2.2)

**Kontrast-Ratios:**
- Text-on-Dark: Farbe auf Hintergrund = Ratio (z.B. 19:1 AAA)
- Text-on-Light: Farbe auf Hintergrund = Ratio

**Semantische HTML-Struktur:**
- Korrekte Tags: `<nav>`, `<main>`, `<section>`, `<article>`, `<aside>`, `<footer>`
- H1-H3-Hierarchie: Korrekt/inkorrekt

**Interaktive Elemente:**
- Focus-Rings: Vorhanden/Custom
- Button vs. Link: Korrekte Semantik
- ARIA-Attribute: Auflistung (falls vorhanden)

**Reduced Motion:**
- Unterstützung: Ja/Nein (via `@media (prefers-reduced-motion)`)

---

### 9. Content-Strategie & Targeting

**Hauptthema der Seite:**
- Worum geht es? (1-2 Sätze)

**Primäre Keywords:**
- Keyword 1
- Keyword 2
- Keyword 3

**Sekundäre Keywords (LSI):**
- LSI-Keyword 1
- LSI-Keyword 2

**Zielgruppe:**
- Beschreibung (z.B. "Geschäftsführer kleiner Kanzleien, 40-65 Jahre")

**User Intent:**
- Primär: Informational / Transactional / Navigational
- Sekundär: [Falls relevant]

**AIO/GEO/AEO-Status:**
- **AIO:** Welche Frage beantwortet diese Seite?
- **GEO:** Strukturierte Daten vorhanden? Schema.org-Typ?
- **AEO:** Featured-Snippet-Potenzial? Listicles? Konkrete Metriken?

---

### 10. Content-Audit-Notizen

**Stärken:**
- ✅ Was funktioniert gut? (z.B. "Klare H1-H2-Hierarchie")
- ✅ Positive Aspekte

**Altlasten / Schwächen:**
- ⚠️ Zu spezifische Formulierungen?
- ⚠️ Veraltete Inhalte?
- ⚠️ Inkonsistenzen?

**Fehlende Elemente:**
- ❌ Was fehlt? (z.B. Testimonials, CTAs, Videos)

**Content-Refresh-Priorität:**
- 🔴 Hoch / 🟡 Mittel / 🟢 Niedrig
- Begründung: Warum ist diese Seite wichtig/unwichtig für SEO?

---

### 11. Performance & Technische Details (optional)

**Core Web Vitals (Zielwerte):**
- LCP: < X s
- INP: < X ms
- CLS: < X

**Lazy Loading:**
- Images: Ja/Nein
- Scripts: defer/async

**Mobile Optimierung:**
- Responsive: Ja/Nein
- Touch-Targets: Min. 44px × 44px

---

### 12. Content-Metriken

**Textmenge:**
- Gesamtzeichen: ~X
- Gesamtwörter: ~X
- Lesedauer: X-Y Minuten

**Link-Dichte:**
- Interne Links: X
- Externe Links: X
- CTAs: X

**Content-Verteilung:**
- Dark Sections: X%
- Light Sections: X%

**Interaktive Elemente:**
- Buttons: X
- Collapsibles: X
- Tooltips: X
- Carousels/Sliders: X

---

## 📐 QUALITÄTSSTANDARDS

### 1. Genauigkeit
- ✅ **Exakte Texte:** Alle H1-H3-Headlines und wichtige Paragraphen wortgetreu übernehmen
- ✅ **Präzise Farben:** CSS-Variablen UND Hex/rgba-Werte angeben
- ✅ **Korrekte Maße:** Pixel UND Tailwind-Classes dokumentieren

### 2. Vollständigkeit
- ✅ Alle Sections erfassen (keine überspringen)
- ✅ Alle wichtigen Props von Komponenten dokumentieren
- ✅ Links vollständig auflisten (inkl. Glossar-Tooltips)

### 3. Lesbarkeit
- ✅ Code-Block-Format für Struktur-Bäume nutzen
- ✅ Tabellen für Vergleiche und Metriken
- ✅ Emojis für Section-Header (📊, 🏗️, 🎨, 🔗, etc.)

### 4. Konsistenz
- ✅ Immer gleiches Template nutzen
- ✅ Gleiche Terminologie (z.B. "Section" statt "Bereich", "Component" statt "Komponente")
- ✅ Einheitliche Formatierung (Bold für Überschriften, Code für CSS-Variablen)

---

## 🚫 WAS NICHT DOKUMENTIERT WIRD

### Auslassen:
- ❌ **Detaillierter Code:** Kein vollständiger Astro/HTML/CSS-Code (nur Struktur)
- ❌ **Implementierungs-Details:** Wie JavaScript funktioniert (nur "Was macht es?")
- ❌ **Versionsverlauf:** Keine Git-History oder Changelog
- ❌ **Server-Konfiguration:** Keine Deployment-Details

### Reduzieren:
- ⚠️ Sehr lange Texte: Erste 100-200 Wörter + "..." (falls Paragraph > 500 Wörter)
- ⚠️ Wiederholende Elemente: "Card 2-10 folgen gleicher Struktur wie Card 1"

---

## 🔄 AKTUALISIERUNGS-WORKFLOW

### Wann aktualisieren?
1. Nach größerem Content-Refresh einer Seite
2. Nach Design-System-Änderungen (neue Farben, Fonts)
3. Nach strukturellen Änderungen (neue Sections, Komponenten)

### Wie aktualisieren?
1. Datum im Header ändern
2. Betroffene Sections neu dokumentieren
3. **Changelog am Ende hinzufügen** (optional):
   ```
   ## 📝 ÄNDERUNGSHISTORIE

   **2025-11-15:**
   - Hero-Headline geändert von "..." zu "..."
   - Section 3: Neue Branch-Card "Handwerksbetriebe" hinzugefügt
   ```

---

## 💡 TIPPS FÜR EFFIZIENTE DOKUMENTATION

### 1. Komponenten-Hierarchie verstehen
- Lese zuerst die `.astro`-Datei der Seite
- Identifiziere alle verwendeten Components
- Dokumentiere von außen nach innen (Sections → Cards → Inline-Elemente)

### 2. Design-Tokens nutzen
- Immer CSS-Variablen MIT konkreten Werten dokumentieren
- Beispiel: `--surface-dark` (#04060D) statt nur `--surface-dark`
- Hilft bei Farb-Audits und Konsistenz-Checks

### 3. Metriken schätzen
- Zeichenanzahl: Kopiere Text in Word/Google Docs → Zeichen zählen
- Wortanzahl: Ähnlich
- Lesedauer: ~200 Wörter/Minute (Faustregel)
- Links: Browser-DevTools → `document.querySelectorAll('a').length`

### 4. Screenshots NICHT einbetten
- Nur textbasiert (wie vereinbart)
- Farben und Layout-Beschreibungen reichen für LLM-Arbeit

---

## 📂 DATEINAMEN-KONVENTION

### Format:
```
[seitenname].md
```

### Beispiele:
- `startseite.md`
- `kontakt.md`
- `ueber-mich.md`
- `kanzleien.md` (Branch-Seite)
- `stufe-0-ftp-classic.md` (Leistungs-Seite)
- `core-web-vitals.md` (Glossar-Seite)

### Ordner-Zuordnung:
- `01-CORE-PAGES/`: Startseite, Kontakt, Über Mich, Datenschutz, Impressum
- `02-BRANCHEN/`: Alle Branch-Seiten
- `03-LEISTUNGEN/`: Alle Service-Seiten
- `04-WISSEN/blog/`: Blog-Artikel
- `04-WISSEN/glossar/`: Glossar-Begriffe

---

## ✅ CHECKLISTE VOR ABSCHLUSS

Bevor eine Dokumentation als "fertig" gilt:

- [ ] Alle 12 Haupt-Sections ausgefüllt
- [ ] Metriken berechnet (Zeichen, Wörter, Lesedauer, Links)
- [ ] Mindestens 3 Farb-Details pro Section dokumentiert
- [ ] Alle H1-H3-Headlines wortgetreu übernommen
- [ ] Komponenten-Props vollständig aufgelistet
- [ ] Responsive Breakpoints dokumentiert
- [ ] Content-Audit-Notizen hinzugefügt (Stärken/Schwächen)
- [ ] Verlinkungsstruktur vollständig

---

## 🎓 BEISPIEL-REFERENZ

**Vollständiges Beispiel:** Siehe `/01-CORE-PAGES/startseite.md`

Diese Datei dient als Muster für alle zukünftigen Dokumentationen. Bei Unsicherheiten über Format oder Detail-Level: Startseite als Referenz nutzen.

---

## 📞 SUPPORT & FRAGEN

Bei Unklarheiten oder Inkonsistenzen:
1. Prüfe `startseite.md` als Referenz
2. Halte Dich an dieses Protokoll
3. Im Zweifel: Lieber zu detailliert als zu oberflächlich

---

**ENDE DES DOKUMENTATIONS-PROTOKOLLS**

Dieses Protokoll ist verbindlich für alle Seiten-Dokumentationen im `/Wolf-Agents.com-Architektur/`-Ordner.
