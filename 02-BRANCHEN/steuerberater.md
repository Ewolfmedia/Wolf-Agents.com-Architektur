# STEUERBERATER & LOHNSTEUERHILFE - Content & Struktur-Architektur

**Dokumentiert am:** 2025-10-30
**Status:** IST-Zustand (keine Optimierungsvorschläge)

---

## 📊 META-INFORMATIONEN

| Attribut | Wert |
|----------|------|
| **URL** | https://www.wolf-agents.com/branchen/steuerberater |
| **Datei** | `/src/pages/branchen/[slug].astro` (Dynamic Route) |
| **Content-Datei** | `/src/content/branchen/steuerberater.json` |
| **Title Tag** | "Steuerberater & Lohnsteuerhilfe – Branchenlösung \| Wolf-Agents" |
| **Meta Description** | "Wir kombinieren GEO-Sichtbarkeit, Mandantenportale und Automationen, damit Steuerkanzleien Anfragen priorisieren und Backoffice-Zeit sparen." |
| **Canonical URL** | https://www.wolf-agents.com/branchen/steuerberater |
| **Noindex** | Nein |
| **Geschätzte Zeichenanzahl** | ~10.900 Zeichen (ohne Code/HTML) |
| **Geschätzte Wortanzahl** | ~1.520 Wörter |
| **Geschätzte Lesedauer** | 6-8 Minuten |
| **Anzahl Sections** | 10 Hauptbereiche (OHNE StepFlow in Path-Section) |
| **Anzahl H1** | 1 |
| **Anzahl H2** | 8 |
| **Anzahl H3** | 14+ |

---

## 🔗 VERLINKUNGSSTRUKTUR

### Interne Links (ausgehend)
- Navigation: `/`, `/branchen/`, `/leistungen/`, `/wissen/`
- Hero CTA: `/kontakt`, `/leistungen`
- Path Section Task-Links: `#onboarding`, `#mandantenservice`, `#pakete`
- Solution InfoTooltips: `/wissen/glossar/automation`, `/wissen/glossar/aeo`, `/wissen/glossar/consent-mode-v2`
- Glossary-Links: `/wissen/glossar/geo`, `/wissen/glossar/consent-mode-v2`, `/wissen/glossar/rum`, `/wissen/glossar/gitops`
- CTA: `/kontakt`, `/wissen#guides`
- More Branches: 3 Sibling-Links
- Footer: ~20 Links

**Gesamtanzahl interne Links:** ~40-45

### Externe Links
Keine

---

## 🏗️ LAYOUT & SEMANTISCHE STRUKTUR

**WICHTIG:** Diese Seite nutzt die **identische Struktur** wie `/branchen/kanzleien` (siehe `kanzleien.md` für vollständige Layout-Details).

**UNTERSCHIED zu Kanzleien:** Diese Seite hat **KEINEN StepFlow** in der Path-Section. Alle 3 Task-Articles werden ohne eingebetteten Flow dargestellt.

---

### KEY CONTENT-UNTERSCHIEDE ZU KANZLEIEN

#### Hero
- **Badge:** "Segment · Steuer"
- **H1:** "Skalierbare Content- & Beratungsstrecken für Steuerteams"
- **Subtitle:** "Wir kombinieren GEO-Sichtbarkeit, Mandantenportale und Automationen, damit Steuerkanzleien Anfragen priorisieren und Backoffice-Zeit sparen."

#### Top Tasks (3 Cards)
1. **Mandanten-Onboarding starten**
   - Description: "Geführte Aufnahme inkl. Beleg-Upload, Vollmacht und Risikoprofil."
   - Audience: "Neumandate"
   - Link: #onboarding

2. **Fristen & To-dos veröffentlichen**
   - Description: "Automatisierte Erinnerungen, FAQ und Dokumente für Bestandsmandanten."
   - Audience: "Bestandsmandanten"
   - Link: #mandantenservice

3. **Paket & Preise vergleichen**
   - Description: "Transparente Leistungsmodelle inkl. ROI-Rechner für Unternehmer:innen."
   - Audience: "Unternehmen"
   - Link: #pakete

#### Path Section (3 Task-Articles, OHNE StepFlow)
**Struktur:** Gleich wie Kanzleien, aber **KEINE StepFlow-Embed-Card** bei index 0.

Alle 3 Articles haben nur:
- Header-Row (H3 + Description + Badge)
- Kein verschachtelter 4-Schritt-Flow

#### Pains (3 Cards)
1. **Telefon & E-Mail blockieren das Team**
   - "Wiederkehrende Fragen zu Belegen, Fristen und Formularen erzeugen hohen manuellen Aufwand und lange Reaktionszeiten."

2. **Fehlende GEO-Präsenz für lokale Keywords**
   - "Kanzleien ohne strukturierte Local-Strategie verlieren Sichtbarkeit gegenüber Portalen und Vergleichsseiten."

3. **Mandanten erwarten digitale Self-Services**
   - "Upload, Terminbuchung und Status-Tracking fehlen oder sind nur über externe Portale verfügbar."

#### Solutions (3 Cards)
1. **Mandantenportal mit Automationen**
   - Summary: "Upload, Checklisten, Vollmachten und Status-E-Mails laufen automatisiert – inklusive DATEV-Schnittstelle."
   - InfoTooltip: termId="automation"
   - Proof: "E-Mail-Aufkommen −35 %"

2. **Local SEO & GEO Cluster**
   - Summary: "Standort- und Leistungscluster mit Bewertungsstrategie sichern Sichtbarkeit in Google Maps & AI Overviews."
   - InfoTooltip: termId="aeo"
   - Proof: "+4 neue Local Pack Rankings"

3. **Servicecockpit mit KPIs**
   - Summary: "Consent Mode v2 + Server-Side Tracking zeigen, welche Services Abschlüsse liefern und wo Funnel abbrechen."
   - InfoTooltip: termId="consent-mode-v2"
   - Proof: "Digital Take-up +28 %"

#### WebApps (3 Cards)
1. **Mandanten-Onboarding**
   - Description: "Interaktiver Fragebogen mit Branchenlogik, benötigten Dokumenten und Freigabe-Workflow."
   - Outcome: "Klar priorisierte Mandate schon vor dem Erstgespräch."
   - Tech-Stack: "Astro", "Cloudflare Workers", "D1"

2. **Fristen- & Newsletter-Automation**
   - Description: "Segmentierte Reminder und White-Label Newsletter basierend auf Rechtsform & Leistungen."
   - Outcome: "Weniger Nachfragen, bessere Mandantenbindung."
   - Tech-Stack: "Resend", "Cloudflare KV", "Segment"

3. **ROI- & Paket-Rechner**
   - Description: "Vergleicht Leistungspakete, zeigt ROI und Einsparpotenziale für Unternehmer:innen."
   - Outcome: "Schnellere Kaufentscheidung und höhere Upsell-Quote."
   - Tech-Stack: "React Island", "Astro", "Cloudflare Pages"

#### KPIs (3 Cards)
1. **Telefonaufwand:** "−30 %"
2. **Newsletter-Abos:** "+4×"
3. **Digital Take-up:** "+28 %"

#### FAQ (3 Items)
1. **"Wie integrieren Sie DATEV oder andere Kanzlei-Tools?"**
   - Answer: "Wir nutzen DATEVconnect / DUO, binden bestehende Portale über SSO ein oder entwickeln sichere APIs via Cloudflare Workers. Uploads werden verschlüsselt übertragen und revisionssicher archiviert."
   - AI-Snippet: "DATEVconnect / DUO, SSO und Workers ermöglichen sichere Automationen."

2. **"Welche Laufzeit hat ein Standardprojekt?"**
   - Answer: "Für eine Steuerkanzlei rechnen wir mit 6–8 Wochen: 2 Wochen Strategie & Content, 3 Wochen Implementierung, 1–2 Wochen QA und Go-Live."
   - AI-Snippet: "Steuerkanzlei-Projekte brauchen 6–8 Wochen bis zum Go-Live."

3. **"Wie unterstützen Sie interne Teams nach dem Launch?"**
   - Answer: "Wir liefern Video-Handovers, dokumentierte Deployments und optionale Retainer für Content, GEO und Automationen. Monitoring & KPI-Dashboards laufen weiterhin im Servicecockpit."
   - AI-Snippet: "Video-Handovers, Deploy-Doku und Retainer sichern Betrieb nach Launch."

#### Glossary-Links (4 Badges)
- "geo"
- "consent mode v2"
- "rum"
- "gitops"

#### CTA-Section
- **Headline:** "Backoffice entlasten & Mandanten priorisieren"
- **Subline:** "Wir automatisieren Intake, Fristen und Reporting – DSGVO-konform und mandantenfreundlich."
- **Primary CTA:** "Kostenlosen Workflow-Check buchen" → /kontakt
- **Secondary CTA:** "Mandantenportal-Demo ansehen" → /wissen#guides

---

## 🔍 SEO & STRUKTURIERTE DATEN

### Schema.org Markup

**Typ:** AccountingService + ProfessionalService

**JSON-LD:**
```json
{
  "@context": "https://schema.org",
  "@type": ["AccountingService", "ProfessionalService"],
  "name": "Steuerberater & Lohnsteuerhilfe",
  "url": "https://www.wolf-agents.com/branchen/steuerberater",
  "audience": ["Unternehmen", "Privatmandanten"],
  "areaServed": ["DE", "AT", "CH"],
  "serviceType": "Skalierbare Content- & Beratungsstrecken für Steuerteams"
}
```

**Unterschied zu Kanzleien:** Schema-Typ ist `AccountingService` statt `LegalService`.

---

## 🎯 CONTENT-STRATEGIE & TARGETING

### Hauptthema

Skalierbare Beratungsstrecken für Steuerkanzleien: Mandantenportale, Fristen-Automation und ROI-Rechner reduzieren Telefonaufwand um 30% und erhöhen Digital Take-up um 28%. Fokus auf DATEV-Integration, GEO-Sichtbarkeit und Self-Service-Portale.

### Primäre Keywords

- Websites für Steuerberater
- Steuerberater Website
- Mandantenportal Steuerkanzlei
- Digitalisierung Steuerkanzlei
- DATEV-Integration
- Steuerkanzlei Webentwicklung

### Sekundäre Keywords (LSI)

- Mandanten-Onboarding
- Fristen-Automation
- ROI-Rechner
- Local SEO für Steuerberater
- Consent Mode v2
- Server-Side Tracking
- Digital Take-up
- Rechtsform-Segmentierung
- White-Label Newsletter

### Zielgruppe

**Primär:**
- Geschäftsführende Steuerberater in kleinen bis mittelgroßen Kanzleien
- Alter: 35-60 Jahre
- DACH-Region
- Pain: Telefonflut, fehlende Self-Services, schlechte GEO-Sichtbarkeit

**Sekundär:**
- Backoffice-Teams in Steuerkanzleien
- IT-Verantwortliche

### User Intent

**Primär:** Informational
- "Wie digitalisiere ich Mandanten-Onboarding?"
- "DATEV-Integration für Website"
- "Wie reduziere ich Telefonaufwand?"

**Sekundär:** Transactional
- "Workflow-Check buchen" CTA

### AIO/GEO/AEO-Status

**AIO:**
- ✅ FAQ mit 3 Fragen + AI-Snippets
- ✅ "DATEV-Integration" direkt in FAQ beantwortet

**GEO:**
- ✅ AccountingService Schema
- ✅ Local SEO & GEO Cluster als Solution
- ✅ +4 neue Local Pack Rankings als Proof

**AEO:**
- ✅ Konkrete Metriken: −30% Telefonaufwand, +4× Newsletter-Abos, +28% Digital Take-up
- ✅ Projekt-Laufzeit: 6–8 Wochen (direkt in FAQ)
- ⚠️ Kein StepFlow (im Gegensatz zu Kanzleien) – weniger visuelle Journey-Darstellung

---

## 📝 CONTENT-AUDIT-NOTIZEN

### Stärken

- ✅ **DATEV-Integration prominent:** FAQ beantwortet Hauptfrage sofort
- ✅ **Konkrete Laufzeit:** 6–8 Wochen direkt kommuniziert (transparenter als Kanzleien)
- ✅ **ROI-Rechner als WebApp:** Conversion-Tool für Unternehmer:innen
- ✅ **Newsletter-Automation:** 4× mehr Abos zeigt Skalierbarkeit
- ✅ **Rechtsform-Segmentierung:** Branchenlogik im Onboarding erwähnt
- ✅ **Consent Mode v2 + Server-Side Tracking:** Aktuelle Privacy-Anforderungen adressiert

### Altlasten / Schwächen

- ⚠️ **Kein StepFlow:** Im Gegensatz zu Kanzleien fehlt visuelle Journey (könnte User-Verständnis schmälern)
- ⚠️ **"Segment · Steuer" Badge:** Wieder unklar, was "Segment" bedeutet
- ⚠️ **Keine Testimonials:** Keine Referenzkunden
- ⚠️ **"Mandantenportal-Demo ansehen" CTA:** Link führt zu `/wissen#guides` (generisch, kein spezifisches Mandantenportal-Demo)
- ⚠️ **Pain "Fehlende GEO-Präsenz":** Etwas generisch formuliert, könnte spezifischer sein ("Steuerportale wie Steuertipps.de dominieren Suchergebnisse")

### Fehlende Elemente

- ❌ **StepFlow:** Keine visuelle 3-4-Schritt-Journey wie bei Kanzleien
- ❌ **Social Proof:** Keine Logos, Testimonials, Case Studies
- ❌ **Preistransparenz:** ROI-Rechner wird erwähnt, aber keine Beispiel-Pakete
- ❌ **DATEV-Logo/Zertifikat:** Könnte Vertrauen stärken
- ❌ **Screenshot/Video:** Keine visuelle Darstellung des Mandantenportals

### Content-Refresh-Priorität

**Priorität:** 🔴 **HÖCHSTE**

**Begründung:**
1. **Haupt-Zielgruppe #2:** Steuerberater sind zweite Hauptzielgruppe nach Kanzleien
2. **DATEV-Integration:** Killer-Feature für deutsche Steuerkanzleien – sollte prominenter visualisiert werden
3. **Fehlender StepFlow:** Schwächt User-Engagement im Vergleich zu Kanzleien-Seite
4. **SEO-Potenzial:** "DATEV-Integration", "Mandantenportal Steuerkanzlei" haben hohes Suchvolumen

**Empfohlene Maßnahmen (für externes LLM):**
- StepFlow für Mandanten-Onboarding hinzufügen (z.B. 3 Schritte)
- DATEV-Integration visuell hervorheben (Screenshot, Diagramm)
- Testimonials von Steuerkanzleien ergänzen
- ROI-Rechner-Beispiel zeigen (z.B. "Kanzlei mit 500 Mandanten spart 12h/Woche")

---

## 📊 CONTENT-METRIKEN

### Textmenge

- **Gesamtzeichen:** ~10.900
- **Gesamtwörter:** ~1.520
- **Lesedauer:** 6-8 Minuten

### Link-Dichte

- **Interne Links:** ~40-45
- **CTAs:** 4
- **InfoTooltips:** 3 (automation, aeo, consent-mode-v2)
- **Glossary-Links:** 4

### Content-Verteilung

- **Dark Sections:** 40% (Hero, Path, Solutions, WebApps, FAQ)
- **Light Sections:** 60% (Tasks, Pains, KPI, Glossary, CTA, More Branches)

**UNTERSCHIED zu Kanzleien:**
- **Path-Section kürzer:** Keine StepFlow-Embed-Card (~200 Zeilen weniger Content)
- **FAQ kürzer:** 3 statt 3 Items (gleich), aber Antworten kompakter

---

**ENDE DER DOKUMENTATION**

**Letzte Aktualisierung:** 2025-10-30
**Nächste Review:** Nach StepFlow-Hinzufügung oder DATEV-Visualisierung
