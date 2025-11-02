# KONTAKT - Content & Struktur-Architektur

**Dokumentiert am:** 2025-11-01
**Status:** IST-Zustand (keine Optimierungsvorschläge)

---

## 📊 1. HEADER & META-INFORMATIONEN

| Attribut | Wert |
|----------|------|
| **URL** | https://www.wolf-agents.com/kontakt |
| **Datei** | `/src/pages/kontakt.astro` |
| **Title Tag** | "Kontakt & Intake – Wolf-Agents" |
| **Meta Description** | "Kontaktieren Sie Wolf-Agents für Kanzlei-, Bildungs- und Behördenprojekte. Persönliche Betreuung. Mo–Sa 8–20 Uhr erreichbar." |
| **Canonical URL** | https://www.wolf-agents.com/kontakt |
| **Noindex** | Nein |
| **Geschätzte Zeichenanzahl** | ~7.200 Zeichen (ohne Code/HTML) |
| **Geschätzte Wortanzahl** | ~1.020 Wörter |
| **Geschätzte Lesedauer** | 5-6 Minuten |
| **Anzahl Sections** | 2 Hauptbereiche (Hero, Contact-Form-Section) |
| **Anzahl H1** | 1 (im Hero: "Kontakt") |
| **Anzahl H2** | 2 (Kostenloses Beratungsgespräch, Kontaktinformationen) |
| **Anzahl H3** | 3 (Was Sie erwarten können, E-Mail/Telefon/Adresse, Kostenlose Erstberatung) |

---

## 🔗 2. VERLINKUNGSSTRUKTUR

### Interne Links (ausgehend)

**Navigation:**
- Logo-Link: `/`
- Branchen-Dropdown: `/branchen/kanzleien`, etc.
- Leistungen-Dropdown: `/leistungen` + Unterseiten
- Wissen-Dropdown: `/wissen`, `/wissen/glossar`, `/code-statt-cms`
- CTA-Button: `/kontakt`

**Hero (Section 1):**
- CTA Primary: `#contact-form` → "Kontakt aufnehmen" (Anchor-Link)
- CTA Tertiary: `mailto:info@wolf-agents.com` → "Oder an info@wolf-agents.com schreiben"

**Contact-Form-Section (Section 2):**
- Datenschutz-Link: `/datenschutz` (in Consent-Checkbox-Label)
- Call-to-Action-Buttons: `tel:+4915146533415`, `mailto:info@wolf-agents.com`

**Footer:**
- Branchen, Leistungen, Wissen, Kontakt, Impressum, Datenschutz (Standard-Links)

### Externe Links
- `mailto:info@wolf-agents.com` (3×)
- `tel:+4915146533415` (2×)
- Cloudflare Turnstile Script: `https://challenges.cloudflare.com/turnstile/v0/api.js`

### Backlinks (intern)
Diese Seite wird verlinkt von:
- Navigation: "Kontakt" (alle Seiten)
- Footer: "Kontakt" (alle Seiten)
- Alle CTA-Sections: "Kontakt aufnehmen", "Migration planen", "Gespräch starten", etc.

**Gesamtanzahl interne Links:** ~18-24 (inkl. Navigation, Footer, Anchor-Link, Datenschutz-Link)

---

## 🏗️ 3. LAYOUT & SEMANTISCHE STRUKTUR

---

### SECTION 1: HERO (Dark Grid)

**Komponente:** `<Hero />`
**Layout-Pattern:** Full-viewport Hero mit Dark Grid Background
**Hintergrund:** `var(--surface-dark)` (#04060D) mit Grid-Pattern + Glow-Effekt

```
HERO#hero (Full Height: 100vh/100dvh, tone: dark-grid)
│
├── Badge: "Mo–Sa 8–20 Uhr erreichbar"
├── H1: "Kontakt"
├── Subtitle: "Digitale Projekte für Kanzleien, Bildung & öffentliche Dienste – wir sind Mo–Sa von 8–20 Uhr erreichbar..."
│
└── CTA-Group (2 CTAs: Primary + Tertiary)
    ├── Primary: "Kontakt aufnehmen" → #contact-form (Anchor-Link)
    └── Tertiary: "Oder an info@wolf-agents.com schreiben" → mailto:info@wolf-agents.com
```

**Note:** `showSecondaryCta={false}` → Kein Secondary-CTA

---

### SECTION 2: CONTACT-FORM-SECTION (Light)

**Komponente:** `<Section tone="light" />`
**Layout-Pattern:** 2-Column Grid (Desktop: lg:grid-cols-2)
**Hintergrund:** `var(--surface-light)` (#F9FAFB)

```
SECTION#contact-form-section (tone: light, standard padding)
│
└── Container (max-w-4xl mx-auto)
    │
    └── Grid (lg:grid-cols-2, gap-12)
        │
        ├── LEFT-COLUMN: Contact Form
        │   │
        │   ├── H2: "Kostenloses Beratungsgespräch"
        │   │   Font: Inter SemiBold, 24px
        │   │   Farbe: var(--text-primary-on-light)
        │   │   Margin-bottom: mb-2 (8px)
        │   │
        │   ├── Intro-Paragraph
        │   │   Text: "Wir melden uns zeitnah telefonisch oder per E-Mail..."
        │   │   Font: Inter Regular, 14px
        │   │   Margin-bottom: mb-4 (16px)
        │   │
        │   ├── ContentBoxDark: "Was Sie erwarten können"
        │   │   Heading: "Was Sie erwarten können" (H3)
        │   │   │
        │   │   └── List (3 Items mit Checkmark-Icons)
        │   │       ├── "Persönlicher Ansprechpartner für Ihr Projekt"
        │   │       ├── "Transparente Prozesse und klare Kommunikation"
        │   │       └── "Erreichbarkeit Mo–Sa 8–20 Uhr"
        │   │
        │   ├── Maintenance-Notice (conditional, falls formLocked=true)
        │   │   Background: bg-amber-50
        │   │   Border: border-amber-200
        │   │   Text: "Wartungsarbeiten am Kontaktformular" + Maintenance-Message + Fallback
        │   │   Role: status (aria-live)
        │   │
        │   ├── Form-Lock-Overlay (conditional, falls formLocked=true)
        │   │   Position: absolute, z-20
        │   │   Background: rgba(249, 250, 251, 0.85) + backdrop-blur
        │   │   Icon: Warning-Triangle (Amber-colored)
        │   │   Text: "Formular derzeit nicht verfügbar"
        │   │
        │   └── <form id="contact-form"> (method="POST", novalidate)
        │       Class: blur-[1px] + pointer-events-none (falls formLocked=true)
        │       │
        │       ├── Honeypot-Field (hidden)
        │       │   Name: "company", tabindex="-1", autocomplete="off"
        │       │
        │       ├── Field 1: Name (required)
        │       │   Label: "Name *"
        │       │   Input: type="text", placeholder="Ihr vollständiger Name"
        │       │   Class: form-input
        │       │   Border-Gradient: input-border-gradient
        │       │
        │       ├── Field 2: E-Mail (required)
        │       │   Label: "E-Mail-Adresse *"
        │       │   Input: type="email", placeholder="ihre.email@beispiel.de"
        │       │   Validation: emailPattern (/^[^\s@]+@[^\s@]+\.[^\s@]+$/)
        │       │
        │       ├── Field 3: Telefon (optional)
        │       │   Label: "Telefon (optional)"
        │       │   Input: type="tel", placeholder="+49 123 456789"
        │       │
        │       ├── Field 4: Segment / Organisationstyp (required)
        │       │   Label: "Ihr Segment / Organisationstyp"
        │       │   Select: 9 Options (Kanzlei, Steuerberatung, WP, Notariat, Schule, Behörde, Versicherung, Industrie, Andere)
        │       │   Chevron-Icon: select-chevron (custom-styled)
        │       │
        │       ├── Field 5: Projekt (required)
        │       │   Label: "Ihr Projekt"
        │       │   Select: 9 Options (Neue Website, Redesign, Serviceportal, Digitale Anmeldung, SEO, GEO, Migration, Beratung, noch unklar)
        │       │
        │       ├── Field 6: Nachricht (required)
        │       │   Label: "Ihre Nachricht *"
        │       │   Textarea: rows="5", placeholder="Beschreiben Sie kurz Ihr Projekt..."
        │       │
        │       ├── Field 7: Cloudflare Turnstile (CAPTCHA)
        │       │   Class: cf-turnstile
        │       │   Data-Attributes: data-turnstile-action="kontaktformular", data-turnstile-theme="light"
        │       │   Script: https://challenges.cloudflare.com/turnstile/v0/api.js
        │       │   Render: Via JavaScript (mountTurnstile-Funktion)
        │       │
        │       ├── Consent-Checkbox (required)
        │       │   Input: type="checkbox", id="privacy", name="consent"
        │       │   Label: "Ich bestätige, die Datenschutzerklärung gelesen zu haben..." + Link → /datenschutz
        │       │
        │       ├── Form-Status-Box (hidden by default)
        │       │   ID: form-status
        │       │   Role: status/alert (dynamisch)
        │       │   Classes: success/error/info (dynamisch via JavaScript)
        │       │   Content: Success/Error-Messages + Optional-Link (Confirm-URL)
        │       │
        │       ├── Submit-Button (Button-Komponente)
        │       │   Text: "Audit/Erstgespräch anfragen"
        │       │   Variant: "primary"
        │       │   Size: "lg"
        │       │   fullWidth: true
        │       │   Icon: Envelope (SVG-Path), iconPosition: "right"
        │       │
        │       └── Footnote
        │           Text: "Hinweis: Wir bestätigen Ihre Anfrage innerhalb von 60 Minuten..."
        │           Font: 12px, text-on-light-muted
        │
        └── RIGHT-COLUMN: Kontakt-Informationen
            │
            ├── H2: "Kontaktinformationen"
            │   Font: Inter SemiBold, 24px
            │   Margin-bottom: mb-4 (16px)
            │
            ├── CTA-Buttons-Row (sm:flex-row, gap-3)
            │   │
            │   ├── Call-Button
            │   │   Text: "Jetzt anrufen"
            │   │   Href: tel:+4915146533415
            │   │   Background: bg-slate-800
            │   │   Icon: Phone (SVG)
            │   │
            │   └── Email-Button
            │       Text: "E-Mail schreiben"
            │       Href: mailto:info@wolf-agents.com
            │       Border: border-slate-700
            │       Icon: Envelope (SVG)
            │
            ├── Contact-Info-Box (rounded-lg, border, p-6)
            │   Background: var(--surface-light)
            │   │
            │   ├── E-Mail-Row
            │   │   Icon: Envelope (SVG, w-6 h-6)
            │   │   H3: "E-Mail"
            │   │   Link: info@wolf-agents.com → mailto:info@wolf-agents.com
            │   │
            │   ├── Telefon-Row
            │   │   Icon: Phone (SVG)
            │   │   H3: "Telefon"
            │   │   Link: +49 151 46533415 → tel:+4915146533415
            │   │
            │   └── Adresse-Row
            │       Icon: Location-Pin (SVG)
            │       H3: "Adresse"
            │       Text: "Eduard Wolf Grafik & Design, Vorderhainberg 21, 94496 Ortenburg, Bayern, Deutschland"
            │
            └── ContentBoxDark: "Kostenlose Erstberatung"
                Heading: "Kostenlose Erstberatung" (H3)
                │
                ├── Paragraph
                │   Text: "In einem unverbindlichen 30-minütigen Gespräch analysieren wir Ihre aktuelle Website..."
                │
                └── List (4 Items mit Circle-Checkmark-Icons)
                    ├── "Website-Performance Analyse"
                    ├── "SEO-Quick-Check"
                    ├── "Conversion-Optimierung Tipps"
                    └── "Technische Empfehlungen"
```

**Abstände:**
- Outer Padding: Standard (nicht explizit angegeben, vermutlich py-24 md:py-32)
- Container: max-w-4xl, mx-auto
- Grid-Gap: gap-12 (48px)
- Form-Fields-Gap: space-y-6 (24px)

---

## 🎨 4. DESIGN-SYSTEM-DETAILS

### Farbnutzung (Hauptfarben)

| Element | CSS-Variable | Hex/rgba-Wert | Verwendung |
|---------|--------------|---------------|------------|
| **Hero (Dark Grid)** | `--surface-dark` | #04060D | Section-Hintergrund |
| **Form-Section (Light)** | `--surface-light` | #F9FAFB | Section-Hintergrund |
| Form-Input-Border | `--border-on-light-subtle` | rgba(15,23,42,0.18) | Input-Borders |
| Maintenance-Notice-BG | — | bg-amber-50 (#FFF7ED) | Maintenance-Notice-Background |
| Maintenance-Notice-Border | — | border-amber-200 (#FED7AA) | Maintenance-Notice-Border |
| Success-Status-BG | — | bg-amber-50 | Form-Status Success |
| Success-Status-Border | — | border-amber-300 | Form-Status Success |
| Error-Status-BG | — | bg-red-50 | Form-Status Error |
| Error-Status-Border | — | border-red-100 | Form-Status Error |
| Checkmark-Icon (Emerald) | — | text-emerald-400 (#34D399) | Success-Icons |

### Typografie-Details

**Font-Family:** Inter (Weights: Regular 400, Medium 500, SemiBold 600, Bold 700)

**Font-Sizes:**
- H1 (Hero): 48px @ Mobile → 72px @ Desktop
- H2 (Section): 24px (1.5rem)
- H3 (ContentBox-Headings): 18px
- Body (Regular): 14px
- Form-Labels: 14px (font-semibold)
- Footnote: 12px

### Spacing-System

- **Section-Padding:** Standard (vermutlich py-24 md:py-32)
- **Form-Fields-Gap:** space-y-6 (24px)
- **Grid-Gap:** gap-12 (48px)

### Border-Radius

- **Medium:** rounded-xl (12px) — Buttons, Call-to-Action
- **Large:** rounded-2xl (16px) — Maintenance-Notice, Form-Status
- **XL:** rounded-3xl (24px) — ContentBoxDark

---

## 📱 5. RESPONSIVE BREAKPOINTS

| Breakpoint | Screen-Width | Grid-Cols | Form-Layout |
|------------|--------------|-----------|-------------|
| **Mobile** | <640px | 1 | Vertikal gestapelt (Form + Kontakt-Info) |
| **Tablet** | 640-1023px | 1 | Vertikal gestapelt (sm:flex-row für CTA-Buttons) |
| **Desktop** | ≥1024px | 2 | 2-Spalten (lg:grid-cols-2) |

### Hauptänderungen

**Mobile:** Form + Kontakt-Info vertikal gestapelt, CTA-Buttons vertikal

**Desktop:** Form links, Kontakt-Info rechts, CTA-Buttons horizontal

---

## 🧩 6. KOMPONENTEN-BIBLIOTHEK

### Genutzte Astro-Components

| Komponente | Datei | Props/Features |
|------------|-------|----------------|
| `<Hero />` | `/src/components/Hero.astro` | 2 CTAs (Primary + Tertiary), showSecondaryCta={false} |
| `<Section />` | `/src/components/Section.astro` | tone="light", id="contact-form-section" |
| `<ContentBoxDark />` | `/src/components/ContentBoxDark.astro` | heading, headingLevel="h3", class="mb-6" |
| `<Button />` | `/src/components/Button.astro` | type="submit", variant="primary", size="lg", fullWidth={true}, icon, iconPosition="right" |

### Native HTML-Components + Custom-Features

- **`<form>`:** method="POST", novalidate, data-form-disabled, data-maintenance-message
- **Honeypot-Field:** Hidden input "company" (Anti-Spam)
- **Cloudflare Turnstile:** CAPTCHA-Integration via `<div class="cf-turnstile">`
- **Custom-Validation:** JavaScript email-pattern, consent-checkbox-validation
- **Form-Lock-System:** ENV-Variable `PUBLIC_CONTACT_FORM_LOCKED` → blur + overlay

---

## 🔍 7. SEO & STRUKTURIERTE DATEN

### Schema.org Markup

**Typ: ContactPage + Organization**
```json
{
  "@context": "https://schema.org",
  "@type": "ContactPage",
  "name": "Kontakt - Wolf-Agents",
  "description": "Kontaktseite für Website-Services von Wolf-Agents",
  "mainEntity": {
    "@type": "Organization",
    "name": "Eduard Wolf Grafik & Design",
    "email": "info@wolf-agents.com",
    "address": {
      "@type": "PostalAddress",
      "streetAddress": "Vorderhainberg 21",
      "addressLocality": "Ortenburg",
      "addressRegion": "Bayern",
      "postalCode": "94496",
      "addressCountry": "DE"
    }
  }
}
```

**Zusammenfassung:**
- ContactPage-Schema für SEO-Visibility
- Organization-Schema mit E-Mail + Postadresse

### Open Graph / Twitter Card

**Annahme** (basierend auf Base-Layout-Standard):
- og:title: "Kontakt & Intake – Wolf-Agents"
- og:description: "Kontaktieren Sie Wolf-Agents für Kanzlei-, Bildungs- und Behördenprojekte..."
- og:type: website

---

## ♿ 8. BARRIEREFREIHEIT (WCAG 2.2)

### Kontrast-Ratios

**Text-on-Light:** #0F172A auf #F9FAFB ≈ **18.9:1** (AAA)

**Icons (Emerald):** #34D399 auf #04060D ≈ **10.3:1** (AAA)

### Semantische HTML-Struktur

- **Korrekte Tags:** `<form>`, `<fieldset>`, `<label>`, `<input>`, `<textarea>`, `<select>`
- **Labels:** Alle Form-Felder haben `<label for="id">`
- **Required-Fields:** `required`-Attribute + `*` in Label-Text
- **Aria-Attributes:** `role="status"` (Form-Status, Maintenance-Notice), `aria-live="polite/assertive"`, `aria-hidden="true"` (Icons)

### Interaktive Elemente

- **Focus-Rings:** Standard (vermutlich via global.css) + Custom für Form-Status-Confirm-Link
- **Touch-Targets:** Min. 44×44px (Buttons, Inputs)
- **Keyboard-Navigation:** Form-Felder via Tab, Submit via Enter
- **Error-Handling:** `setCustomValidity()` + `reportValidity()` für Custom-Validation-Messages

### Validation & Feedback

- **Email-Validation:** Pattern `/^[^\s@]+@[^\s@]+\.[^\s@]+$/`
- **Consent-Validation:** Required-Checkbox, Custom-Message "Bitte bestätigen Sie die Datenschutzerklärung..."
- **Turnstile-Validation:** Required-Token, Error-Message "Bitte bestätigen Sie die Sicherheitsabfrage..."
- **Success/Error-Messages:** Visuelle + Screen-Reader-freundliche Feedback (role="status/alert", aria-live)

---

## 📝 9. CONTENT-STRATEGIE & TARGETING

### Hauptthema

Kontaktformular für unverbindliche Erstberatung. Fokus auf persönliche Betreuung, schnelle Response (<1 h), klare Kommunikation.

### Primäre Keywords

- Kontakt Wolf-Agents
- Erstberatung Website
- Kanzlei Website Kontakt
- Behörden Digitalisierung Kontakt

### Sekundäre Keywords (LSI)

- Kostenloses Beratungsgespräch
- Response Promise
- Intake-Flow
- Mo–Sa 8–20 Uhr erreichbar

### Zielgruppe

**Primär:** Entscheider in Kanzleien, Bildungseinrichtungen, Behörden (35-65 Jahre), die Erstberatung suchen

**Sekundär:** Externe Berater, Agenturen

### User Intent

**Primär:** Transactional (Formular ausfüllen, Erstgespräch buchen)

**Sekundär:** Informational (Kontakt-Informationen abrufen)

### AIO/GEO/AEO-Status

**AIO:**
- Frage: "Wie erreiche ich Wolf-Agents?" → Kontakt-Info-Box (E-Mail, Telefon, Adresse)

**GEO:**
- ✅ ContactPage-Schema + Organization-Schema mit Postadresse

**AEO:**
- ⚠️ Begrenzt (Kontakt-Seite ist transaktional, wenig SEO-Potenzial)

---

## 🔎 10. CONTENT-AUDIT-NOTIZEN

### Stärken

- ✅ **Form-Lock-System:** Wartungs-Overlay + Maintenance-Message (ENV-gesteuert)
- ✅ **Turnstile-Integration:** Cloudflare CAPTCHA für Spam-Schutz
- ✅ **Custom-Validation:** JavaScript-gestützte Validierung (Email-Pattern, Consent-Required)
- ✅ **Success/Error-Animations:** Custom-CSS-Animations (confirmPulse, noteGlow)
- ✅ **Honeypot-Field:** Anti-Spam-Mechanismus (hidden "company"-Field)
- ✅ **Schema.org:** ContactPage + Organization mit Postadresse
- ✅ **Accessibility:** Labels, Required-Attributes, Aria-Live-Regions

### Altlasten / Schwächen

- ⚠️ **API-Endpoint unklar:** Form sendet an `/api/contact` → Backend-Dokumentation fehlt
- ⚠️ **Turnstile-Sitekey ENV-Variable:** `PUBLIC_TURNSTILE_SITE_KEY` → Muss konfiguriert sein
- ⚠️ **Maintenance-Nachrichten ENV-gesteuert:** Könnte für Non-Tech-User komplex sein

### Fehlende Elemente

- ❌ **Live-Chat:** Keine Chat-Integration (z.B. Tawk.to, Intercom)
- ❌ **Kalender-Integration:** Keine direkte Terminbuchung (z.B. Calendly)
- ❌ **Social-Media-Links:** Keine LinkedIn, Twitter-Links

### Content-Refresh-Priorität

**🟢 Niedrig**

**Begründung:** Formular ist funktional und gut strukturiert. Verbesserung möglich durch Kalender-Integration (Q2 2026).

---

## ⚡ 11. PERFORMANCE & TECHNISCHE DETAILS

### Core Web Vitals (Zielwerte)

- **LCP:** < 2.3 s (Hero H1)
- **INP:** < 200 ms (Form-Inputs, Submit-Button)
- **CLS:** < 0.1 (Form statisch, keine dynamischen Layouts)

### Lazy Loading

- **Images:** Keine Images (nur SVG-Icons inline)
- **Scripts:** 2 Scripts (Turnstile-API async/defer, Form-Validation-Script type="module")

### Mobile Optimierung

- **Responsive:** Ja (Tailwind-Breakpoints)
- **Touch-Targets:** Min. 44×44px (Form-Inputs, Buttons)
- **Viewport-Meta:** Standard in Base-Layout

### JavaScript-Features

**Form-Validation:**
- Email-Pattern-Validation (`/^[^\s@]+@[^\s@]+\.[^\s@]+$/`)
- Consent-Checkbox-Required-Validation
- Turnstile-Token-Required-Validation
- Custom-Validity-Messages (`setCustomValidity()`)

**Turnstile-Integration:**
- Render: `window.turnstile.render(container, { sitekey, action, theme })`
- Reset: `window.turnstile.reset()` nach Submit

**Form-Submission:**
- Fetch-API: POST `/api/contact` mit JSON-Payload
- Response-Handling: 202 (Success) → reset + status-message, 422 (Validation-Error) → error-messages
- Status-Messages: Dynamic-Classes (successClasses, errorClasses, infoClasses)

**Custom-Animations:**
- `confirmPulse`: Box-Shadow-Animation für Success-Status (2.4s, 2 Iterations)
- `noteGlow`: Background-Position + Color-Animation für Status-Note (2.4s, infinite)

---

## 📊 12. CONTENT-METRIKEN

### Textmenge

- **Gesamtzeichen:** ~7.200 Zeichen
- **Gesamtwörter:** ~1.020 Wörter
- **Lesedauer:** 5-6 Minuten

### Link-Dichte

- **Interne Links:** 18-24 (Navigation, Footer, Anchor-Link, Datenschutz-Link)
- **Externe Links:** 5 (3× mailto:, 2× tel:, 1× Turnstile-Script)
- **CTAs:** 4 (Hero ×2, Form-Section ×2)
- **Anchor-Links:** 1 (#contact-form)

### Content-Verteilung

- **Dark Sections:** 50% (1 von 2: Hero)
- **Light Sections:** 50% (1 von 2: Contact-Form-Section)

### Interaktive Elemente

- **Buttons/CTAs:** 4 (Hero ×2, Call-Button, Email-Button, Submit-Button via Button-Komponente)
- **Form-Fields:** 7 (Name, Email, Telefon, Segment, Projekt, Nachricht, Turnstile) + 1 Consent-Checkbox + 1 Honeypot
- **ContentBoxes:** 2 (Was Sie erwarten können, Kostenlose Erstberatung)
- **Custom-Overlays:** 1 (Form-Lock-Overlay, conditional)
- **Status-Box:** 1 (Form-Status, hidden by default)

### Form-Metriken

**Felder:**
- Required: 6 (Name, Email, Segment, Projekt, Nachricht, Consent, Turnstile)
- Optional: 1 (Telefon)
- Honeypot: 1 (Company, hidden)

**Validation-Messages:**
- NAME_REQUIRED: "Bitte nennen Sie uns Ihren vollständigen Namen."
- EMAIL_INVALID: "Bitte verwenden Sie eine gültige E-Mail-Adresse."
- MESSAGE_TOO_SHORT: "Bitte beschreiben Sie Ihr Anliegen etwas ausführlicher."
- CONSENT_REQUIRED: "Bitte bestätigen Sie die Datenschutzerklärung."
- HONEYPOT_TRIGGERED: "Die Anfrage konnte nicht verarbeitet werden."

---

**ENDE DER DOKUMENTATION**

Dokumentiert am 2025-11-01 von Claude (Sonnet 4.5) nach Protokoll `/Wolf-Agents.com-Architektur/00-DOKUMENTATIONS-PROTOKOLL.md`.
