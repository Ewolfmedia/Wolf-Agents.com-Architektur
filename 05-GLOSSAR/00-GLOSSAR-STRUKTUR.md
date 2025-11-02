# Glossar-System: Struktur & Workflow-Dokumentation

**Analysiert:** 2025-10-31
**Status:** ✅ Vollständig recherchiert
**Glossar-Einträge:** 15 (10 aktiv genutzt, 5 ungenutzt)

---

## 📊 SYSTEM-ÜBERSICHT

Das Glossar-System von Wolf-Agents.com basiert auf einer **Astro Content Collection** mit interaktiven **InfoTooltip-Komponenten**, die Fachbegriffe aus SEO, Analytics, Performance, Compliance und DevOps erklären.

### Architektur

```
/src/content/glossar/          → Markdown-Dateien (Content Collection)
/src/components/InfoTooltip.astro  → React-ähnliche Tooltip-Komponente
/src/pages/wissen/glossar/     → Dynamische Glossar-Seiten
/src/content/config.ts:35-66   → Zod-Schema für Glossar-Collection
```

### Workflow: Begriff nachschlagen

1. **Nutzer klickt InfoTooltip** (z.B. auf `/leistungen/analytics-consent`)
2. **Komponente lädt Glossar-Eintrag** via `getEntry('glossar', termId)`
3. **Tooltip/Modal zeigt** `title` + `definitionTooltip`
4. **Link führt zu** `/wissen/glossar/[slug]/` (vollständiger Artikel)

---

## 🔧 INFOTOOLTIP-KOMPONENTE

**Datei:** `/src/components/InfoTooltip.astro` (200 Zeilen)

### Props

| Prop | Typ | Default | Beschreibung |
|------|-----|---------|--------------|
| `termId` | `string` | **Pflicht** | Referenz auf Glossar-Eintrag (Dateiname ohne `.md`) |
| `label` | `string` | `"Mehr erfahren"` | Button-Text für `variant="inline"` |
| `variant` | `'icon' \| 'inline'` | `'icon'` | Icon (ⓘ) oder Text-Button |
| `mode` | `'auto' \| 'popover' \| 'modal'` | `'auto'` | Anzeige-Modus (auto = responsive) |

### Verwendungsbeispiele

```astro
<!-- Standard: Icon-Tooltip -->
<InfoTooltip termId="consent-mode-v2" />

<!-- Inline mit Text -->
<InfoTooltip termId="geo" label="Was ist GEO?" variant="inline" />

<!-- Modal erzwingen -->
<InfoTooltip termId="bfsg-2025" mode="modal" />

<!-- In Fließtext einbetten -->
<span class="inline-flex items-center gap-1">
  RUM Monitoring<InfoTooltip termId="rum" />
</span>
```

### Technische Details

- **Import:** `getEntry('glossar', termId)` (Zeile 13)
- **Fehlerbehandlung:** Wirft Error, wenn termId nicht gefunden
- **Fallback:** Nutzt `definitionTooltip`, falls vorhanden, sonst `definitionPlain`
- **Accessibility:** `aria-label`, `aria-haspopup="dialog"`, `aria-expanded`
- **Link:** Jeder Tooltip hat "Zum Glossar"-Link → `/wissen/glossar/${term.slug}/`

---

## 📋 CONTENT COLLECTION SCHEMA

**Datei:** `/src/content/config.ts:35-66`

### Pflichtfelder (4)

```typescript
title: z.string()             // Anzeigename (z.B. "Consent Mode v2")
category: z.string()          // Kategorie (z.B. "Analytics & Consent")
definitionPlain: z.string()   // Sachliche Kurzdefinition (1-2 Sätze)
definitionTooltip: z.string() // Tooltip-Text (oft mit "Was ist...?")
```

### Optionale Felder (7 Sections)

#### 1. Metadaten
```typescript
lastReview: z.string().optional()  // YYYY-MM-DD Format
owner: z.string().default('Wolf-Agents Content Team')
```

#### 2. Segment-spezifische Value Propositions
```typescript
segments: z.array(z.object({
  segment: z.enum(['kanzlei', 'bildung', 'oeffentlich']),
  promise: z.string(),     // Value Proposition
  summary: z.string(),     // Details
  linkLabel: z.string().optional(),
  linkHref: z.string().optional()
})).optional()
```

#### 3. Praktische Auswirkungen
```typescript
practicalImpact: z.array(z.object({
  title: z.string(),
  description: z.string()
})).optional()
```

#### 4. Externe Quellen
```typescript
sources: z.array(z.object({
  label: z.string(),
  href: z.string()
})).optional()
```

#### 5. SEO Schema
```typescript
schema: z.object({
  type: z.string().default('DefinedTerm'),
  synonyms: z.array(z.string()).optional(),
  keywords: z.array(z.string()).optional()
}).optional()
```

#### 6. Verwandte Begriffe
```typescript
related: z.array(z.string()).optional()
```

### Beispiel-Eintrag (consent-mode-v2.md)

```yaml
---
title: "Consent Mode v2"
category: "Analytics & Consent"
definitionPlain: "Consent Mode v2 erweitert Googles Consent-Framework um zusätzliche Signal-Parameter..."
definitionTooltip: "Was ist Consent Mode v2? Googles aktualisiertes Framework für DSGVO-konformes Tracking..."
lastReview: "2025-10-25"
segments:
  - segment: kanzlei
    promise: "Mandatsmarketing bleibt messbar, ohne Datenschutz zu gefährden."
    summary: "Intake-Formulare und Kampagnen-Tracking nutzen Consent Mode v2..."
practicalImpact:
  - title: "CMP & Tagging aktualisieren"
    description: "CMP (Usercentrics, Borlabs, Cookiebot) muss Consent Mode v2 Signale senden..."
sources:
  - label: "Google Developers – Consent Mode v2"
    href: "https://developers.google.com/tag-platform/devguides/consent"
schema:
  type: "DefinedTerm"
  synonyms: ["GCM v2", "Google Consent Mode"]
  keywords: ["Consent Mode", "Server Side Tracking", "DSGVO Analytics"]
related: ["Core Web Vitals", "INP", "Analytics Dashboard"]
---

## Warum relevant?

[Markdown-Content...]
```

---

## 📈 BESTEHENDE GLOSSAR-EINTRÄGE (15)

### Nach Kategorie

#### Analytics & Consent (1)
1. **consent-mode-v2** — 5× verwendet ✅ HOCH

#### Performance & Web Vitals (6)
2. **rum** — 4× verwendet ✅ HOCH
3. **core-web-vitals** — 3× verwendet ✅ MITTEL
4. **ttfb** — 1× verwendet ✅ NIEDRIG
5. **inp** — 0× verwendet ⚠️ UNGENUTZT
6. **lcp** — 0× verwendet ⚠️ UNGENUTZT
7. **cls** — 0× verwendet ⚠️ UNGENUTZT

#### SEO & Sichtbarkeit (3)
8. **geo** — 7× verwendet ✅ SEHR HOCH
9. **aeo** — 6× verwendet ✅ SEHR HOCH
10. **ai-overviews** — 0× verwendet ⚠️ UNGENUTZT

#### Compliance & Barrierefreiheit (2)
11. **bfsg-2025** — 2× verwendet ✅ MITTEL
12. **wcag-22** — 1× verwendet ✅ NIEDRIG

#### Development & DevOps (3)
13. **gitops** — 3× verwendet ✅ MITTEL
14. **cli-first** — 5× verwendet ✅ HOCH
15. **automation** — 0× verwendet ⚠️ UNGENUTZT

### Usage-Statistik

| termId | Verwendungen | Seiten |
|--------|-------------|---------|
| `geo` | 7× | capabilities (1×), ueber-mich (5×), index (1×) |
| `aeo` | 6× | capabilities (1×), ueber-mich (5×) |
| `consent-mode-v2` | 5× | capabilities, stufe-a, stufe-b, ueber-mich (2×) |
| `cli-first` | 5× | capabilities, ueber-mich (4×) |
| `rum` | 4× | stufe-b, servicecockpit-playbook, bfsg-checklist, index |
| `gitops` | 3× | capabilities, ueber-mich, index |
| `core-web-vitals` | 3× | stufe-0, servicecockpit-playbook, index |
| `bfsg-2025` | 2× | leistungen/index, index |
| `wcag-22` | 1× | capabilities |
| `ttfb` | 1× | index |
| `inp` | 0× | — |
| `lcp` | 0× | — |
| `cls` | 0× | — |
| `ai-overviews` | 0× | — |
| `automation` | 0× | — |

---

## 🔄 WORKFLOW: NEUEN BEGRIFF HINZUFÜGEN

### Schritt 1: Markdown-Datei erstellen

```bash
# Datei in Content Collection anlegen
/src/content/glossar/[begriff-slug].md
```

**Namenskonvention:**
- Kleinbuchstaben
- Bindestriche statt Leerzeichen
- Keine Umlaute (ä → ae, ö → oe, ü → ue)
- Beispiele: `consent-mode-v2`, `core-web-vitals`, `bfsg-2025`

### Schritt 2: Frontmatter ausfüllen

```yaml
---
title: "[Anzeigename]"
category: "[Kategorie]"
definitionPlain: "[1-2 Sätze, sachlich, max. 200 Zeichen]"
definitionTooltip: "[Was ist ...? 1-2 Sätze, max. 150 Zeichen]"
lastReview: "2025-10-31"
segments:
  - segment: kanzlei
    promise: "[Value Proposition]"
    summary: "[Details]"
  - segment: bildung
    promise: "[Value Proposition]"
    summary: "[Details]"
  - segment: oeffentlich
    promise: "[Value Proposition]"
    summary: "[Details]"
practicalImpact:
  - title: "[Maßnahme 1]"
    description: "[Details]"
  - title: "[Maßnahme 2]"
    description: "[Details]"
sources:
  - label: "[Offizielle Quelle]"
    href: "[URL]"
  - label: "[Tutorial/Guide]"
    href: "[URL]"
schema:
  type: "DefinedTerm"
  synonyms: ["[Synonym 1]", "[Synonym 2]"]
  keywords: ["[Keyword 1]", "[Keyword 2]"]
related: ["[Verwandter Begriff 1]", "[Verwandter Begriff 2]"]
---
```

### Schritt 3: Markdown-Content schreiben

```markdown
## Kurz erklärt

[2-3 Absätze: Was ist der Begriff? Warum wichtig?]

## Segment-Perspektive

### Kanzleien & Boutiquen
[Praktische Anwendung für Kanzleien]

### Schulen & Campus
[Praktische Anwendung für Bildungseinrichtungen]

### Behörden & öffentliche Dienste
[Praktische Anwendung für Behörden]

## Implementierungsschritte

1. [Schritt 1]
2. [Schritt 2]
3. [Schritt 3]

## Weiterführende Ressourcen

- [Link zu verwandten Begriffen]
- [Offizielle Dokumentation]
```

### Schritt 4: InfoTooltip einbinden

```astro
<!-- In beliebiger .astro-Datei -->
---
import InfoTooltip from '@/components/InfoTooltip.astro';
---

<p>
  Dies ist ein Text mit <InfoTooltip termId="neuer-begriff" /> Erklärung.
</p>
```

### Schritt 5: Build & Test

```bash
npm run build   # Build prüfen
npm run dev     # Lokal testen
```

**Checkliste:**
- [ ] Glossar-Datei in `/src/content/glossar/` erstellt
- [ ] Alle Pflichtfelder ausgefüllt (title, category, definitionPlain, definitionTooltip)
- [ ] Mindestens 1 Segment ausgefüllt (kanzlei, bildung oder oeffentlich)
- [ ] 2-3 externe Quellen verlinkt
- [ ] Verwandte Begriffe referenziert
- [ ] InfoTooltip auf mindestens 1 Seite eingebunden
- [ ] Build erfolgreich (keine Astro-Fehler)
- [ ] Tooltip funktioniert (Klick öffnet Modal/Popover)
- [ ] Link zu `/wissen/glossar/[slug]/` funktioniert

---

## 📍 KATEGORIEN-SYSTEM

Basierend auf bestehenden Einträgen verwenden wir folgende Kategorien:

1. **Analytics & Consent** — Tracking, Datenschutz, DSGVO
2. **Performance & Web Vitals** — Ladezeiten, Interaktivität, Metriken
3. **SEO & Sichtbarkeit** — Suchmaschinen, KI-Systeme, Auffindbarkeit
4. **Compliance & Barrierefreiheit** — Gesetze, Standards, Zugänglichkeit
5. **Development & DevOps** — Prozesse, Tools, Workflows
6. **Cloud & Infrastructure** — Hosting, CDN, Sicherheit (zukünftig)

**Empfehlung:** Kategorien konsistent halten, neue Kategorien nur bei echtem Bedarf hinzufügen.

---

## 🎯 FEHLENDE BEGRIFFE (Roadmap)

### PRIO 2: Für bestehende Leistungs-Seiten

#### Aus `seo-geo-performance.md`:
- **Entity-Mapping** — Wie Suchmaschinen Entitäten verstehen
- **Crawlbudget** — Effizienz der Suchmaschinen-Indexierung
- **Faceted Navigation** — Filter-Navigationen SEO-konform umsetzen

#### Aus `migration-redirects.md`:
- **GSB** (Government Site Builder) — Behörden-CMS
- **OZG** (Onlinezugangsgesetz) — Digitalisierung öffentlicher Dienste
- **Regex** (Regular Expressions) — Muster für Redirects
- **Hypercare** — Intensiv-Support nach Go-Live

### PRIO 3: AWS-spezifisch (Stufe C)

- **BAIT** (Bankaufsichtliche Anforderungen IT) — Finanzsektor-Compliance
- **GoBD** (Grundsätze ordnungsmäßige Buchführung) — Revisionssicherheit
- **WORM Backups** — Unveränderliche Backups
- **Lambda@Edge** — Serverless Functions am CDN
- **Zero Trust** — Sicherheitsarchitektur

### PRIO 4: Cloudflare-spezifisch (Stufe B)

- **Workers** — Edge Computing Platform
- **KV/D1** — Key-Value & SQL Datenbanken am Edge
- **WAF** (Web Application Firewall) — Angriffserkennung
- **PoP** (Point of Presence) — Edge-Locations

---

## 📊 QUALITÄTS-STANDARDS

### InfoTooltip-Definition (definitionTooltip)
- ✅ Beginnt mit "Was ist ...?" oder "Was sind ...?"
- ✅ 1-2 Sätze, max. 150 Zeichen
- ✅ Einfache Sprache, keine Fachbegriffe (außer im Titel)
- ✅ Vermittelt den Kernnutzen, nicht nur technische Details

### Segment-Perspektiven
- ✅ Alle 3 Segmente ausgefüllt (kanzlei, bildung, oeffentlich)
- ✅ `promise`: Value Proposition in 5-10 Wörtern
- ✅ `summary`: Konkrete Anwendung in 1-2 Sätzen
- ✅ Optional: `linkLabel` + `linkHref` für weiterführende Inhalte

### Quellen
- ✅ Mindestens 2 externe Quellen
- ✅ Bevorzugt: Offizielle Dokumentation, Standards, Spezifikationen
- ✅ Links aktuell und erreichbar

### Markdown-Content
- ✅ Strukturiert mit H2/H3-Überschriften
- ✅ 300-400 Wörter (ausführlich, aber prägnant)
- ✅ Segment-spezifische Sections
- ✅ Praktische Implementierungsschritte
- ✅ Interne Verlinkungen zu verwandten Begriffen

---

## 📏 WORTANZAHL-RICHTWERTE

| Element | Ziel | Max |
|---------|------|-----|
| `definitionTooltip` | 100-120 Zeichen | 150 |
| `definitionPlain` | 150-180 Zeichen | 200 |
| Segment `promise` | 40-60 Zeichen | 80 |
| Segment `summary` | 100-150 Zeichen | 200 |
| Markdown Body | 300-400 Wörter | 600 |
| **Gesamt pro Begriff** | **350-450 Wörter** | **700** |

---

## 🔗 VERWANDTE DOKUMENTATIONEN

- `/Wolf-Agents.com-Architektur/00-DOKUMENTATIONS-PROTOKOLL.md` — Standards
- `/Wolf-Agents.com-Architektur/04-LEISTUNGEN/` — Leistungs-Seiten mit InfoTooltips
- `/Wolf-Agents.com-Architektur/02-BRANCHEN/` — Branchen-Seiten (Segment-Kontext)
- `/src/components/InfoTooltip.astro` — Komponenten-Code
- `/src/content/config.ts` — Content Collection Schema

---

**Struktur-Dokumentation abgeschlossen:** 2025-10-31
**Wortanzahl:** ~1.950 Wörter
**Status:** ✅ Vollständig, bereit für Begriff-Dokumentationen
