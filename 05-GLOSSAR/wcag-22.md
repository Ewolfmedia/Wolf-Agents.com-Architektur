# WCAG 2.2

## 📊 META-INFORMATIONEN

- **Term ID**: `wcag-22`
- **Begriff (DE)**: WCAG 2.2
- **Begriff (EN)**: Web Content Accessibility Guidelines 2.2
- **Kategorie**: Compliance & Barrierefreiheit
- **Status**: ✅ Implementiert (1× verwendet)
- **Letzte Review**: 2025-10-25

---

## 💡 INFOTOOLTIP-DEFINITION

**Was ist WCAG 2.2?** Der internationale Standard für barrierefreie Websites – definiert technische Anforderungen, damit Menschen mit Behinderungen Ihre Website problemlos nutzen können. Level AA ist Pflicht für Behörden und empfohlen für alle.

---

## 📖 AUSFÜHRLICHE ERKLÄRUNG

Die Web Content Accessibility Guidelines 2.2 definieren technische Anforderungen für barrierefreie Webangebote – Level AA ist Pflicht für öffentliche Stellen und empfohlen für Kanzleien & Bildung. WCAG 2.2 erweitert die WCAG 2.1 um zusätzliche Erfolgskriterien (z.B. Fokus-Indikatoren, Dragging-Alternativen). Level AA ist die Zielstufe für öffentliche Stellen und empfehlener Standard für professionelle Dienstleister.

Die WCAG 2.2 basiert auf vier Prinzipien (POUR):

- **Perceivable (Wahrnehmbar):** Inhalte müssen für alle Nutzer:innen wahrnehmbar sein (z.B. Alternativtexte für Bilder)
- **Operable (Bedienbar):** Alle Funktionen müssen bedienbar sein (z.B. Tastaturbedienbarkeit)
- **Understandable (Verständlich):** Inhalte und Bedienung müssen verständlich sein (z.B. klare Fehlermeldungen)
- **Robust (Robust):** Inhalte müssen mit verschiedenen Technologien kompatibel sein (z.B. Screenreader)

Für Kanzleien bedeutet WCAG 2.2: Mandanten mit Hilfstechnologien bedienen – Risiko von Abmahnungen senken. Für Bildungseinrichtungen: Enrollment, Lerninhalte und Campus-Services barrierefrei zugänglich. Für Behörden: BFSG/BITV-Konformität sicherstellen – Audit & Monitoring bestehen.

Die Umsetzung erfolgt über Audits & Maßnahmenpläne (WCAG 2.2 AA Audit durchführen, Findings priorisieren, Verantwortliche & Fristen definieren), Komponentenbibliothek härten (Buttons, Accordions, Dialoge, Tabellen mit ARIA-Pattern, Fokus-Styling und Tastaturtests absichern) und Redaktion & QA schulen (Checklisten, Snippets und Tools bereitstellen).

### Warum ist es wichtig?

WCAG 2.2 ist der globale Standard für digitale Barrierefreiheit und in vielen Ländern gesetzlich vorgeschrieben:

- **Rechtssicherheit:** Ab 2025 gelten strengere Barrierefreiheits-Gesetze (BFSG) – WCAG 2.2 AA erfüllt die technische Grundlage
- **Bessere Nutzbarkeit:** Mandanten mit Screenreadern, Seh- oder Motorikeinschränkungen können Formulare und Inhalte problemlos nutzen
- **Höhere Conversion:** Barrierefreie Websites haben bessere Completion Rates
- **Reputationseffekt:** Erhöht Vertrauen und minimiert Abmahnrisiken

Für regulierte Branchen (Kanzleien, Bildungseinrichtungen, Behörden) ist WCAG 2.2 AA-Konformität unverzichtbar.

### Typische Anwendungsfälle

- **Use Case 1: Kanzlei-Formulare** — Formulare, Intake-Flows und Wissensbereiche erfüllen WCAG 2.2 AA (Fokus, Kontrast, Tastatur, Fehlerhilfe). Mandanten mit Screenreadern können Intake-Formulare problemlos ausfüllen.
- **Use Case 2: Enrollment-Prozesse** — StepFlow, Kurslisten, Medien und Download-Portale orientieren sich an WCAG und Landesvorgaben. Enrollment, Lerninhalte und Campus-Services barrierefrei zugänglich.
- **Use Case 3: Bürgerdienste** — Bürgerdienste, Top Tasks, PDF-Alternative und Feedbackmechanismen erfüllen WCAG 2.2 AA. BFSG/BITV-Konformität sicherstellen – Audit & Monitoring bestehen.

---

## 🔗 VERWANDTE BEGRIFFE

- **Siehe auch**: BFSG 2025, Barrierefreiheit, Accessibility Audit, ARIA-Pattern
- **Unterschied zu**: WCAG 2.1 (Vorgängerversion), BITV (deutsche Umsetzung für Behörden)
- **Übergeordnet**: Web Accessibility Initiative (WAI), W3C Standards
- **Untergeordnet**: Erfolgskriterien (SC 2.4.11, SC 2.1.1, SC 3.3.7), ARIA-Pattern

---

## 📍 VERWENDUNG AUF DER WEBSITE

### InfoTooltip-Verwendung (1×)

- ✅ `/capabilities` (Zeile 104)

### Erwähnungen ohne InfoTooltip

- `/leistungen/barrierefreiheit` — Vollständiger Artikel über Barrierefreiheit & WCAG 2.2
- `/downloads/bfsg-bitv-checklist` — WCAG 2.2 Checkliste
- `/branchen/kanzleien` — WCAG-Compliance für Mandantenportale
- `/branchen/schulen-bildung` — Enrollment-Accessibility
- `/branchen/oeffentliche-einrichtungen` — BITV + WCAG für Bürgerdienste

### Kontext der Verwendungen

**Capabilities-Seite:** WCAG 2.2 als Teil der Barrierefreiheits-Expertise, zusammen mit BFSG 2025.

---

## 🛠️ PRAKTISCHE IMPLEMENTIERUNG

### 1. Audit & Maßnahmenplan

**Aufgabe:** WCAG 2.2 AA Audit durchführen, Findings priorisieren, Verantwortliche & Fristen definieren.

**Schritte:**
- Accessibility-Audit mit axe, WAVE oder BITV-Test durchführen
- Findings nach Priorität sortieren (Critical, High, Medium, Low)
- Maßnahmenplan mit Verantwortlichen erstellen (Confluence, Jira, Notion)
- Accessibility-Erklärung veröffentlichen

### 2. Komponentenbibliothek härten

**Aufgabe:** Buttons, Accordions, Dialoge, Tabellen mit ARIA-Pattern, Fokus-Styling und Tastaturtests absichern.

**Schritte:**
- ARIA-Pattern für interaktive Komponenten (Accordion, Modal, Tabs)
- Fokus-Indikatoren deutlich sichtbar machen (SC 2.4.11)
- Tastaturbedienbarkeit sicherstellen (SC 2.1.1/2.1.2)
- Screenreader-Tests (NVDA, JAWS, VoiceOver)

### 3. Redaktion & QA schulen

**Aufgabe:** Checklisten, Snippets und Tools (axe, WAVE) bereitstellen; Feedback-Kanal für Barrieren eröffnen.

**Schritte:**
- Content-Checklisten (Alt-Texte, Überschriften-Hierarchie, Link-Texte)
- Snippets für barrierefreie Patterns (HTML, CSS, ARIA)
- Tools in Browser-Extensions integrieren (axe DevTools, WAVE)
- Feedback-Formular für Barriere-Meldungen einrichten

---

## 📚 EXTERNE RESSOURCEN

- **[W3C WCAG 2.2 Quick Reference](https://www.w3.org/WAI/WCAG22/quickref/)** — Offizielle W3C-Dokumentation (deutsch/englisch)
- **[BFIT-Bund Leitfaden](https://www.bfit-bund.de/)** — Barrierefreiheit in der IT des Bundes
- **[BITV-Test Kriterien](https://www.bitvtest.de/bitv-test/das-testverfahren-im-ueberblick.html)** — BITV-Test für Behörden

---

## 🎯 SEGMENT-PERSPEKTIVEN

### Kanzleien & Boutiquen

**Promise:** Mandanten mit Hilfstechnologien bedienen – Risiko von Abmahnungen senken.

Formulare, Intake-Flows und Wissensbereiche erfüllen WCAG 2.2 AA (Fokus, Kontrast, Tastatur, Fehlerhilfe). Erhöht Vertrauen und minimiert Abmahnrisiken. Response Promise bleibt messbar, auch mit barrierefreien Komponenten.

### Schulen & Campus

**Promise:** Enrollment, Lerninhalte und Campus-Services barrierefrei zugänglich.

StepFlow, Kurslisten, Medien und Download-Portale orientieren sich an WCAG und Landesvorgaben. Barrierefreie Enrollment-Prozesse sichern zufriedene Eltern/Studierende.

### Behörden & öffentliche Dienste

**Promise:** BFSG/BITV-Konformität sicherstellen – Audit & Monitoring bestehen.

Bürgerdienste, Top Tasks, PDF-Alternative und Feedbackmechanismen erfüllen WCAG 2.2 AA. Transparente Dokumentation stärkt Vertrauen und erleichtert Audits.

---

## 📊 WCAG 2.2 KERNTHEMEN

### Fokus-Indikatoren (SC 2.4.11)
Fokus-Ring muss deutlich sichtbar sein (mindestens 2px Outline, Kontrast 3:1).

### Tastaturbedienbarkeit (SC 2.1.1/2.1.2)
Jede Funktion ohne Maus steuerbar, keine Tastaturfallen.

### Darstellung von Fehlern (SC 3.3.7)
Eingabefehler klar erklären und Korrektur anbieten (z.B. "E-Mail-Adresse ungültig").

---

## 📊 SYNONYME & KEYWORDS

**Synonyme:**
- Web Content Accessibility Guidelines 2.2
- WCAG AA
- Accessibility Standard

**Keywords:**
- WCAG
- Accessibility Standard
- Barrierefreiheit
- ARIA Pattern
- Level AA

---

**Wortanzahl:** ~950 Wörter
**Review-Status:** ✅ Final
**Quellen-Qualität:** W3C + BFIT-Bund + BITV-Test
**Segment-Abdeckung:** Vollständig (Kanzlei, Bildung, Behörden)
