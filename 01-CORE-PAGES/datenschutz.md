# DATENSCHUTZ – PAGE DOKUMENTATION
**Stand:** 2025-11-01
**Datei:** `/src/pages/datenschutz.astro` (246 Zeilen inkl. Styles)
**URL-Slug:** `/datenschutz`
**Page-Typ:** Privacy Policy (Pflichtseite nach Art. 13/14 DSGVO)

---

## 1. PAGE-ÜBERBLICK & ZWECK

### Was ist diese Page?
Datenschutzerklärung (Privacy Policy) für Wolf-Agents – rechtliche Pflichtseite nach EU-Datenschutz-Grundverordnung (DSGVO, Art. 13/14). Die Page erläutert transparent, welche personenbezogenen Daten beim Besuch der Website und bei Kontaktaufnahme verarbeitet werden, welche Drittdienste eingebunden sind (Cloudflare, ZeroBounce, AWS), welche Rechte Besucher haben und wie sie diese geltend machen können.

**Primäre Funktion:** DSGVO-Compliance (Informationspflicht nach Art. 13 DSGVO).

### Primäre Ziele
1. **DSGVO-Compliance:** Erfüllung der Informationspflicht (Art. 13/14 DSGVO)
2. **Transparenz:** Offenlegung aller Datenverarbeitungen (Hosting, Formulare, Email-Versand)
3. **Rechtsgrundlagen:** Benennung der DSGVO-Artikel für jede Verarbeitung (Art. 6 Abs. 1 lit. b/c/f)
4. **Drittland-Übermittlungen:** Erklärung zu USA-Dienstleistern (Cloudflare, AWS) + EU-Standardvertragsklauseln
5. **Betroffenenrechte:** Aufklärung über Auskunft, Berichtigung, Löschung, Widerspruch (Art. 15-21 DSGVO)

### User Journey & Conversion Funnel
1. **Entry:** Footer-Link "Datenschutz" (auf allen Pages vorhanden, gesetzlich vorgeschrieben)
2. **Hero:** Titel "Datenschutzerklärung" + Badge "Datenschutz" → signalisiert Legal Page
3. **ContentBoxDark:** Verantwortliche Stelle (Eduard Wolf, Kontaktdaten) → DSGVO Art. 13 Abs. 1 lit. a
4. **Legal-Card:** 8 Sections mit vollständiger DSGVO-Information (Hosting, Cookies, Kontakt, Rechte)
5. **CTAs:** Primary (Kontakt aufnehmen) + Secondary (Impressum anzeigen) → Cross-Linking
6. **Exit:** Zurück zu Footer-Navigation oder Kontakt-Page

**Besonderheit:** Page ist **nicht conversion-orientiert** → rein informational/legal

### SEO & Indexierung
```astro
noindex={true}
```
→ Page wird **nicht von Suchmaschinen indexiert** (Standard für Legal Pages)
→ Verhindert direkte Landung via Google ("Datenschutz Wolf-Agents")
→ Kein SEO-Wert notwendig (Pflichtseite, keine Traffic-Quelle)

---

## 2. TECHNISCHE ARCHITEKTUR

### Framework & Komponenten
- **Framework:** Astro (Static Site Generation)
- **Layout:** `Base.astro` (Standard-Layout für alle statischen Pages)
- **Components:**
  - `Nav.astro` (Header-Navigation mit `variant="transparent"`)
  - `Hero.astro` (Full-Viewport Dark-Grid Hero mit `align="left"`)
  - `Section.astro` (1 Section, tone="light", **class="-mt-20"**)
  - `ContentBoxDark.astro` (Verantwortliche Stelle)
  - `Footer.astro` (Standard-Footer mit Legal-Links)

**Component-Konsistenz:** Identische Struktur wie Impressum-Page (Hero + ContentBoxDark + Legal-Card)

### Styling & Theming

**Hero-Konfiguration:**
```astro
<Hero
  align="left"              <!-- Linksbündiger Text (konsistent mit Impressum) -->
  variant="dark-grid"
  minHeightStyle="min-height:100vh;min-height:100dvh;"
/>
```

**Section-Konfiguration:**
```astro
<Section tone="light" class="-mt-20">
```
→ **Negative Margin (-mt-20)** → Section überlappt Hero (Glaskarten-Effekt)

**Custom CSS (Scoped Styles):**
```css
/* Legal Card (identisch zu Impressum, mit minimalen Anpassungen) */
.legal-card {
  position: relative;
  padding: 2.75rem 2.5rem;
  border-radius: 2.25rem;
  background: rgba(255, 255, 255, 0.95);
  border: 1px solid rgba(226, 232, 240, 0.8);
  box-shadow: 0 32px 120px -60px rgba(15, 23, 42, 0.7);
}

/* Blur-Orbs (leicht veränderte Positionierung vs. Impressum) */
.legal-card::before {
  top: -100px;     /* Impressum: -90px */
  right: -110px;   /* Impressum: -120px */
  width: 240px;    /* Impressum: 220px */
  height: 240px;   /* Impressum: 220px */
}

.legal-card::after {
  bottom: -150px;  /* Impressum: -130px */
  left: -110px;    /* Impressum: -90px */
  width: 220px;    /* Impressum: 200px */
  height: 220px;   /* Impressum: 200px */
}

/* H3-Styling (neu, nicht in Impressum) */
.legal-prose h3 {
  font-size: clamp(1.1rem, 1.9vw, 1.35rem);  /* Responsive: 17.6px → 21.6px */
  margin-top: 1.6rem;
  margin-bottom: 0.6rem;
  font-weight: 600;
  color: #1f2937;  /* Gray-800 (leicht heller als H2) */
}

/* Link-Styling (mit Border-Bottom) */
.legal-prose a {
  color: #334155;
  font-weight: 600;
  border-bottom: 1px solid rgba(51, 65, 85, 0.12);  /* Subtile Unterstreichung */
  transition: all 0.2s ease;
}

.legal-prose a:hover {
  border-bottom-color: rgba(15, 23, 42, 0.3);  /* Dunkler on Hover */
  color: #0f172a;
}
```

**Unterschiede zu Impressum:**
- H3-Styling vorhanden (Datenschutz hat Subsections 4.1–4.6)
- Link-Border-Bottom (visueller Unterschied)
- Blur-Orb-Positionen leicht verschoben

---

## 3. CONTENT-AUDIT

### Hero (variant="dark-grid", align="left", Full Viewport)

```astro
<Hero
  title="Datenschutzerklärung"
  subtitle="Wir erläutern transparent, welche personenbezogenen Daten wir beim Besuch dieser Website verarbeiten, welche Rechte Sie haben und wie Sie uns erreichen."
  badge="Datenschutz"
  ctaText="Kontakt aufnehmen"
  ctaHref="/kontakt"
  secondaryCtaText="Impressum anzeigen"
  secondaryCtaHref="/impressum"
  align="left"
  variant="dark-grid"
  minHeightStyle="min-height:100vh;min-height:100dvh;"
/>
```

**Title-Strategie:** "Datenschutzerklärung" (formal, eindeutig)

**Subtitle-Strategie:**
- **Transparenz:** "erläutern transparent" (Trust Building)
- **Scope:** "beim Besuch dieser Website" (nicht generell, sondern website-spezifisch)
- **Rechte:** "welche Rechte Sie haben" (empowering)
- **Kontakt:** "wie Sie uns erreichen" (niedrigschwellig)

**Badge-Element:** "Datenschutz" (kategorisiert Page als Privacy Content)

**CTA-Hierarchie:**
1. **Primary CTA:** "Kontakt aufnehmen" → `/kontakt` (für DSGVO-Anfragen, Auskunft, Löschung)
2. **Secondary CTA:** "Impressum anzeigen" → `/impressum` (Cross-Link zu komplementärer Legal Page)

---

### ContentBoxDark: Datenschutz-Kontakt

```astro
<ContentBoxDark heading="Datenschutz-Kontakt" badge="Verantwortliche Stelle">
  <p class="text-sm text-slate-200/80 leading-relaxed">
    <strong class="text-white">Eduard Wolf Grafik &amp; Design</strong><br>
    Eduard Wolf<br>
    Vorderhainberg&nbsp;21<br>
    94496 Ortenburg, Deutschland
  </p>
  <p class="mt-3 text-sm text-slate-200/80">
    Telefon: <a href="tel:+4915146533415" class="text-white hover:text-slate-100">+49&nbsp;151&nbsp;46533415</a><br>
    E-Mail: <a href="mailto:info@wolf-agents.com" class="text-white hover:text-slate-100">info@wolf-agents.com</a>
  </p>
</ContentBoxDark>
```

**DSGVO-Kontext:** Art. 13 Abs. 1 lit. a DSGVO (Name und Kontaktdaten des Verantwortlichen)
→ Muss zu Beginn der Datenschutzerklärung genannt werden (Quick Access)

---

### Legal-Card: Datenschutz-Abschnitte (8 H2-Sections)

**Layout:** Custom `.legal-card` div mit `.legal-prose` article

---

#### Section 1: Verantwortliche Stelle

```markdown
## 1. Verantwortliche Stelle

Eduard Wolf Grafik & Design
Eduard Wolf
Vorderhainberg 21
94496 Ortenburg, Deutschland

Telefon: +49 151 46533415
E-Mail: info@wolf-agents.com
```

**DSGVO-Artikel:** Art. 13 Abs. 1 lit. a DSGVO
**Content:** Identisch zu ContentBoxDark (Redundanz gewollt für DSGVO-Compliance)

---

#### Section 2: Hosting & Server-Logfiles

```markdown
## 2. Hosting & Server-Logfiles

Unsere Website wird über Cloudflare Pages, Cloudflare Workers und verbundene Dienste der Cloudflare, Inc., 101 Townsend St, San Francisco, CA 94107, USA bereitgestellt. Ohne aktivierte Data Localization Suite erfolgt die Verarbeitung auf der globalen Cloudflare-Infrastruktur; mit Cloudflare besteht ein Auftragsverarbeitungsvertrag einschließlich EU-Standardvertragsklauseln. Details zur regionalen Verarbeitung finden Sie in Abschnitt 5.

Bei jedem Aufruf werden durch Cloudflare automatisiert Logdaten (u. a. IP-Adresse, Datum und Uhrzeit, angeforderte Ressource, Referrer, übertragene Datenmenge sowie Browser- und Betriebssysteminformationen) verarbeitet, um die Website bereitzustellen, Angriffe abzuwehren und Fehler zu analysieren. Rechtsgrundlage ist Art. 6 Abs. 1 lit. f DSGVO (berechtigtes Interesse an einer sicheren und stabilen Website). Logdaten werden maximal 30 Tage gespeichert und anschließend gelöscht oder anonymisiert, sofern keine längere Aufbewahrung zu Beweiszwecken erforderlich ist.

Alle Verbindungen werden transportverschlüsselt (TLS/HTTPS), um übermittelte Inhalte vor unbefugtem Zugriff zu schützen.
```

**DSGVO-Artikel:**
- Art. 6 Abs. 1 lit. f DSGVO (berechtigtes Interesse)
- Art. 44 ff. DSGVO (Drittlandübermittlung)

**Technische Details:**
- **Cloudflare-Dienste:** Pages (Static Hosting), Workers (Serverless Functions), KV (Key-Value Store), Turnstile (Bot Protection)
- **Cloudflare-Adresse:** 101 Townsend St, San Francisco, CA 94107, USA
- **Data Localization:** Optional (EU-Rechenzentren), sonst global
- **Auftragsverarbeitung:** AV-Vertrag + EU-Standardvertragsklauseln (Art. 46 Abs. 2 lit. c DSGVO)

**Logdaten:**
- IP-Adresse
- Datum/Uhrzeit
- Angeforderte Ressource (URL)
- Referrer (woher kam der Besucher?)
- Übertragene Datenmenge
- Browser/OS-Informationen (User-Agent)

**Speicherdauer:** Max. 30 Tage → dann Löschung oder Anonymisierung

**TLS/HTTPS:** Transportverschlüsselung (Standard für alle Cloudflare-Seiten)

---

#### Section 3: Keine Tracking-Cookies, kein Profiling

```markdown
## 3. Keine Tracking-Cookies, kein Profiling

Wir setzen keine Statistik- oder Marketing-Dienste ein und speichern keine Tracking-Cookies. Zur Absicherung unseres Kontaktformulars binden wir Cloudflare Turnstile ein. Turnstile prüft clientseitig technische Signale (IP-Adresse, User-Agent, Referrer sowie Interaktions- und Timing-Daten) und stellt uns serverseitig ein prüfbares Token bereit. Turnstile setzt keine Tracking-Cookies und dient nicht Werbe- oder Profiling-Zwecken. Rechtsgrundlage ist Art. 6 Abs. 1 lit. f DSGVO (berechtigtes Interesse an der Sicherung unserer Formulare und Infrastruktur); weitere Informationen finden Sie in Abschnitt 4.2.
```

**DSGVO-Artikel:** Art. 6 Abs. 1 lit. f DSGVO (berechtigtes Interesse)

**Content-Strategie:**
- **Positiv-Messaging:** "keine Tracking-Cookies, kein Profiling" (Trust Building)
- **Turnstile-Erklärung:** Bot-Protection, aber **keine Cookies, kein Profiling**
- **Transparenz:** "prüft clientseitig technische Signale" (IP, User-Agent, Referrer, Interaktions-/Timing-Daten)
- **Server-Token:** Turnstile sendet Token an Server (nicht Besucher-Tracking, sondern Bot-Detection)

**Unterscheidung zu Google Analytics/Facebook Pixel:**
→ Wolf-Agents nutzt **keine Analytics-Dienste** → keine Cookie-Banner notwendig (DSGVO-freundlich)

---

#### Section 4: Kontaktaufnahme (6 H3-Subsections)

##### 4.1 Kontaktformular

```markdown
### 4.1 Kontaktformular

Wenn Sie uns über das Formular kontaktieren, verarbeiten wir die von Ihnen übermittelten Pflicht- und freiwilligen Angaben (Name, E-Mail-Adresse, Nachricht sowie optional Kanzlei, Telefonnummer oder Projektdetails) zur Bearbeitung Ihres Anliegens bzw. zur Anbahnung eines Vertrags. Rechtsgrundlagen sind Art. 6 Abs. 1 lit. b DSGVO sowie Art. 6 Abs. 1 lit. f DSGVO (berechtigtes Interesse an effizienter Kommunikation).

Wir verwenden ein Double-Opt-In-Verfahren: Nach Absenden der Anfrage erhalten Sie eine Bestätigungs-E-Mail. Bis zur Bestätigung speichern wir das zugehörige Token pseudonymisiert in einem Cloudflare Workers KV-Speicher (Binding „CONTACT_DOI") mit einer Speicherdauer von 48 Stunden.
```

**DSGVO-Artikel:**
- Art. 6 Abs. 1 lit. b DSGVO (Vertragsanbahnung)
- Art. 6 Abs. 1 lit. f DSGVO (berechtigtes Interesse)

**Verarbeitete Daten:**
- **Pflicht:** Name, E-Mail, Nachricht
- **Optional:** Kanzlei, Telefon, Projektdetails

**Double Opt-In:**
- **Mechanik:** Form-Submit → E-Mail mit Bestätigungslink → Click → Lead bestätigt
- **Token-Speicher:** Cloudflare Workers KV (Binding `CONTACT_DOI`)
- **Speicherdauer:** 48 Stunden (automatische Löschung via TTL)
- **Pseudonymisierung:** Token ist nicht direkt Person zuordenbar

---

##### 4.2 Bot- und Spam-Schutz (Cloudflare Turnstile)

```markdown
### 4.2 Bot- und Spam-Schutz (Cloudflare Turnstile)

Zum Schutz vor automatisierten Formular-Missbräuchen setzen wir „Turnstile" von Cloudflare (Cloudflare, Inc., 101 Townsend St, San Francisco, CA 94107, USA) ein. Turnstile analysiert ausschließlich technische Signale (z. B. IP-Adresse, User-Agent, Interaktions- und Timing-Daten), erstellt daraus ein Prüf-Token und übermittelt dieses an unsere Server. Turnstile setzt keine Tracking-Cookies und wird nicht für Werbezwecke eingesetzt. Rechtsgrundlage ist Art. 6 Abs. 1 lit. f DSGVO (berechtigtes Interesse an der Absicherung unserer Systeme). Cloudflare verarbeitet die Daten als Auftragsverarbeiter; internationale Übermittlungen sind über EU-Standardvertragsklauseln abgesichert.

Weiterführende Informationen erhalten Sie unter https://developers.cloudflare.com/turnstile/ sowie im Trust Hub von Cloudflare unter https://www.cloudflare.com/trust-hub/privacy-and-data-protection/.
```

**DSGVO-Artikel:** Art. 6 Abs. 1 lit. f DSGVO (berechtigtes Interesse)

**Turnstile-Mechanik:**
1. **Client-seitig:** JavaScript analysiert technische Signale (IP, User-Agent, Interaktions-Daten, Timing)
2. **Token-Erstellung:** Turnstile erstellt Challenge-Token (nicht tracking, nur Bot-Detection)
3. **Server-Validierung:** Token wird an Wolf-Agents-Server gesendet → Cloudflare API validiert Token
4. **Keine Cookies:** Turnstile nutzt keine Cookies (DSGVO-freundlich)

**Links:**
- Turnstile Docs: https://developers.cloudflare.com/turnstile/
- Cloudflare Trust Hub: https://www.cloudflare.com/trust-hub/privacy-and-data-protection/

---

##### 4.3 Serverseitiges Rate-Limiting (Cloudflare Workers KV)

```markdown
### 4.3 Serverseitiges Rate-Limiting (Cloudflare Workers KV)

Zur Abwehr massenhafter Formularanfragen speichern wir kurzzeitige Zähler pro IP-Adresse und Zeitfenster (typischerweise 60 Sekunden) in Cloudflare Workers KV. Die Einträge werden nach Ablauf der jeweiligen TTL automatisch gelöscht; eine weitergehende Profilbildung findet nicht statt. Rechtsgrundlage ist Art. 6 Abs. 1 lit. f DSGVO (berechtigtes Interesse an der Aufrechterhaltung der Verfügbarkeit). Technische Details zum TTL-Mechanismus sind unter https://developers.cloudflare.com/workers/runtime-apis/kv/#ttl beschrieben.
```

**DSGVO-Artikel:** Art. 6 Abs. 1 lit. f DSGVO (berechtigtes Interesse)

**Rate-Limiting-Mechanik:**
1. **IP-basiert:** Jede IP-Adresse hat Zähler (z. B. max. 3 Form-Submits pro 60s)
2. **Cloudflare Workers KV:** Key-Value-Store für kurzlebige Daten
3. **TTL (Time to Live):** 60 Sekunden → automatische Löschung nach Ablauf
4. **Keine Profilbildung:** Daten werden nicht aggregiert/analysiert

**Link:** https://developers.cloudflare.com/workers/runtime-apis/kv/#ttl

---

##### 4.4 Validierung von E-Mail-Adressen (ZeroBounce)

```markdown
### 4.4 Validierung von E-Mail-Adressen (ZeroBounce)

Zur Vermeidung fehlerhafter oder missbräuchlicher Kontaktaufnahmen prüfen wir eingegebene E-Mail-Adressen automatisiert über ZeroBounce (ZeroBounce Ltd., 44 Broadway, London E15 1XH, UK). Hierbei werden die E-Mail-Adresse und ggf. technische Metadaten wie die IP-Adresse an den EU-Endpoint des Dienstes übermittelt. Rechtsgrundlage ist Art. 6 Abs. 1 lit. f DSGVO (Schutz unserer Infrastruktur und Reputation). ZeroBounce agiert als Auftragsverarbeiter; es bestehen ein Auftragsverarbeitungsvertrag sowie EU-Standardvertragsklauseln. Informationen: https://www.zerobounce.net/privacy-policy.html und https://www.zerobounce.net/dpa/.
```

**DSGVO-Artikel:** Art. 6 Abs. 1 lit. f DSGVO (berechtigtes Interesse)

**ZeroBounce-Details:**
- **Anbieter:** ZeroBounce Ltd., 44 Broadway, London E15 1XH, UK
- **Funktion:** Email-Validierung (Syntax-Check, Domain-Check, Mailbox-Verification)
- **Übermittlung:** E-Mail-Adresse + IP-Adresse (Metadaten)
- **EU-Endpoint:** Verarbeitung in EU-Rechenzentren
- **Auftragsverarbeitung:** AV-Vertrag + EU-Standardvertragsklauseln

**Links:**
- Privacy Policy: https://www.zerobounce.net/privacy-policy.html
- DPA (Data Processing Agreement): https://www.zerobounce.net/dpa/

---

##### 4.5 E-Mail-Versand und Archivierung (AWS SES, WorkMail, Mail Manager)

```markdown
### 4.5 E-Mail-Versand und Archivierung (AWS SES, WorkMail, Mail Manager)

Nach erfolgreicher Prüfung versenden wir Ihre Nachricht über Amazon Simple Email Service (Amazon Web Services EMEA SARL, 38 Avenue John F. Kennedy, L-1855 Luxemburg) in der Region eu-west-1 (Irland). Unsere Postfächer betreiben wir mit Amazon WorkMail; zur Beweissicherung und zur Erfüllung gesetzlicher Pflichten werden ein- und ausgehende Nachrichten in AWS Mail Manager (EU-Region) archiviert. Rechtsgrundlagen sind Art. 6 Abs. 1 lit. b DSGVO (Kommunikation und Vertragsvorbereitung) sowie Art. 6 Abs. 1 lit. c DSGVO (gesetzliche Aufbewahrungspflichten von bis zu zehn Jahren).

AWS handelt als Auftragsverarbeiter; maßgeblich sind das AWS Data Processing Addendum und die EU-Standardvertragsklauseln. Weitere Informationen: https://aws.amazon.com/compliance/gdpr-center/, https://aws.amazon.com/artifact/, https://aws.amazon.com/messaging/aws-mail-manager/ sowie https://docs.aws.amazon.com/workmail/latest/adminguide/journaling.html.
```

**DSGVO-Artikel:**
- Art. 6 Abs. 1 lit. b DSGVO (Vertragsanbahnung/Kommunikation)
- Art. 6 Abs. 1 lit. c DSGVO (gesetzliche Aufbewahrungspflichten)

**AWS-Details:**
- **Anbieter:** Amazon Web Services EMEA SARL, 38 Avenue John F. Kennedy, L-1855 Luxemburg
- **SES (Simple Email Service):** Email-Versand (Region: eu-west-1 = Irland)
- **WorkMail:** Postfach-Hosting (EU-Region)
- **Mail Manager:** Email-Archivierung (EU-Region)

**Aufbewahrungspflichten:**
- **Handelsrecht (HGB):** 6 Jahre (§ 257 HGB)
- **Steuerrecht (AO):** 10 Jahre (§ 147 AO)
→ Längste Pflicht: **10 Jahre** (gilt für Rechnungen, Verträge)

**Auftragsverarbeitung:** AWS Data Processing Addendum (DPA) + EU-Standardvertragsklauseln

**Links:**
- GDPR Center: https://aws.amazon.com/compliance/gdpr-center/
- AWS Artifact (Compliance-Docs): https://aws.amazon.com/artifact/
- Mail Manager: https://aws.amazon.com/messaging/aws-mail-manager/
- WorkMail Journaling: https://docs.aws.amazon.com/workmail/latest/adminguide/journaling.html

---

##### 4.6 Alternative Kontaktwege

```markdown
### 4.6 Alternative Kontaktwege

Bei einer Kontaktaufnahme per E-Mail oder Telefon verarbeiten wir die von Ihnen bereitgestellten Kommunikationsdaten auf denselben Rechtsgrundlagen und zu den oben genannten Zwecken. Eine längere Aufbewahrung erfolgt nur, wenn gesetzliche Pflichten dies verlangen oder Sie an weiterführender Kommunikation interessiert sind.
```

**DSGVO-Artikel:** Art. 6 Abs. 1 lit. b/f DSGVO (wie 4.1)

**Content-Strategie:** Catch-all für Telefon/Email (nicht nur Formular)

---

#### Section 5: Cloudflare – Ort der Verarbeitung

```markdown
## 5. Cloudflare – Ort der Verarbeitung

Die Bereitstellung unserer Website (Cloudflare Pages, Workers, Workers KV, Turnstile) erfolgt auf der globalen Infrastruktur von Cloudflare. Sofern wir Cloudflare Regional Services bzw. die Data Localization Suite für die EU aktivieren, findet die Verarbeitung in EU-Rechenzentren statt; andernfalls kann eine Verarbeitung auch außerhalb der EU erfolgen. In allen Fällen bestehen ein Auftragsverarbeitungsvertrag und EU-Standardvertragsklauseln. Details: https://developers.cloudflare.com/data-localization/.
```

**DSGVO-Artikel:** Art. 44 ff. DSGVO (Drittlandübermittlung)

**Cloudflare Data Localization:**
- **Regional Services:** EU-Rechenzentren (optional, kostenpflichtig)
- **Data Localization Suite:** Zusätzliche Garantien für EU-Datenresidenz
- **Global Infrastructure:** Ohne Regional Services → Verarbeitung auch in USA möglich

**Absicherung:** AV-Vertrag + EU-Standardvertragsklauseln (Art. 46 Abs. 2 lit. c DSGVO)

**Link:** https://developers.cloudflare.com/data-localization/

---

#### Section 6: Empfänger

```markdown
## 6. Empfänger

Empfänger im Sinne der DSGVO sind ausschließlich die genannten Auftragsverarbeiter (Cloudflare, ZeroBounce, Amazon Web Services) sowie interne Stellen, die Ihre Anfrage bearbeiten. Eine weitergehende Weitergabe erfolgt nur, wenn wir gesetzlich dazu verpflichtet sind oder Sie ausdrücklich eingewilligt haben.
```

**DSGVO-Artikel:** Art. 13 Abs. 1 lit. e DSGVO (Empfänger der Daten)

**Empfänger-Liste:**
1. **Cloudflare** (Hosting, Workers, Turnstile)
2. **ZeroBounce** (Email-Validierung)
3. **Amazon Web Services** (Email-Versand, WorkMail, Mail Manager)
4. **Interne Stellen** (Eduard Wolf, ggf. Mitarbeiter für Anfragen-Bearbeitung)

**Keine Weitergabe** außer:
- Gesetzliche Verpflichtung (z. B. Strafverfolgungsbehörden mit Beschluss)
- Ausdrückliche Einwilligung (z. B. Weiterleitung an Partner-Kanzlei nach Zustimmung)

---

#### Section 7: Speicherdauer

```markdown
## 7. Speicherdauer

Kontaktanfragen speichern wir nach Abschluss der Kommunikation maximal 24 Monate, sofern keine gesetzlichen Aufbewahrungspflichten entgegenstehen. Daten aus dem Double-Opt-In-Verfahren werden nach 48 Stunden automatisch gelöscht, Einträge aus dem Rate-Limiting nach Ablauf der jeweiligen TTL. Archivierte E-Mails werden gemäß den handels- und steuerrechtlichen Vorgaben bis zu zehn Jahren vorgehalten. Logdaten (vgl. Abschnitt 2) werden nach spätestens 30 Tagen gelöscht oder anonymisiert.
```

**DSGVO-Artikel:** Art. 13 Abs. 2 lit. a DSGVO (Speicherdauer)

**Speicherfristen:**
| Datentyp                  | Speicherdauer             | Rechtsgrundlage              |
|---------------------------|---------------------------|------------------------------|
| Kontaktanfragen           | Max. 24 Monate            | Art. 6 Abs. 1 lit. b/f DSGVO |
| DOI-Tokens                | 48 Stunden (TTL)          | Art. 6 Abs. 1 lit. f DSGVO   |
| Rate-Limiting-Zähler      | 60 Sekunden (TTL)         | Art. 6 Abs. 1 lit. f DSGVO   |
| Archivierte E-Mails       | Bis zu 10 Jahre           | Art. 6 Abs. 1 lit. c DSGVO   |
| Logdaten (Cloudflare)     | Max. 30 Tage              | Art. 6 Abs. 1 lit. f DSGVO   |

**Ausnahmen:** Gesetzliche Aufbewahrungspflichten (HGB, AO) verlängern Speicherdauer

---

#### Section 8: Ihre Rechte

```markdown
## 8. Ihre Rechte

Sie haben jederzeit das Recht auf Auskunft nach Art. 15 DSGVO, Berichtigung nach Art. 16 DSGVO, Löschung nach Art. 17 DSGVO, Einschränkung der Verarbeitung nach Art. 18 DSGVO, Widerspruch nach Art. 21 DSGVO sowie das Recht auf Datenübertragbarkeit nach Art. 20 DSGVO. Einwilligungen können Sie jederzeit mit Wirkung für die Zukunft widerrufen. Zudem besteht ein Beschwerderecht bei der zuständigen Aufsichtsbehörde, insbesondere in dem Mitgliedstaat Ihres üblichen Aufenthaltsortes oder des mutmaßlichen Verstoßes.

Kopien der mit unseren Auftragsverarbeitern geschlossenen Standardvertragsklauseln und Auftragsverarbeitungsverträge stellen wir auf Anfrage zur Verfügung. Bitte richten Sie entsprechende Anfragen an die oben genannten Kontaktdaten.
```

**DSGVO-Artikel:**
- Art. 15 DSGVO (Auskunft)
- Art. 16 DSGVO (Berichtigung)
- Art. 17 DSGVO (Löschung/"Recht auf Vergessenwerden")
- Art. 18 DSGVO (Einschränkung der Verarbeitung)
- Art. 20 DSGVO (Datenübertragbarkeit)
- Art. 21 DSGVO (Widerspruch)
- Art. 77 DSGVO (Beschwerderecht bei Aufsichtsbehörde)

**Betroffenenrechte:**
1. **Auskunft:** Welche Daten werden verarbeitet? (Art. 15 DSGVO)
2. **Berichtigung:** Falsche Daten korrigieren (Art. 16 DSGVO)
3. **Löschung:** "Recht auf Vergessenwerden" (Art. 17 DSGVO)
4. **Einschränkung:** Verarbeitung einfrieren (Art. 18 DSGVO)
5. **Datenübertragbarkeit:** Daten in maschinenlesbarem Format erhalten (Art. 20 DSGVO)
6. **Widerspruch:** Verarbeitung widersprechen (Art. 21 DSGVO)

**Einwilligung-Widerruf:** "mit Wirkung für die Zukunft" (ex nunc, nicht ex tunc)

**Aufsichtsbehörde (Deutschland):**
- Bundes: Bundesbeauftragte für den Datenschutz und die Informationsfreiheit (BfDI)
- Landesebene: Bayerisches Landesamt für Datenschutzaufsicht (BayLDA, für Wolf-Agents zuständig)

**Kopien von SCCs/AVVs:** Auf Anfrage → Transparenz-Verpflichtung (Art. 13 Abs. 2 lit. f DSGVO)

---

#### Footer: Stand-Angabe

```markdown
Stand: Oktober 2025
```

**Content-Strategie:** Zeitstempel zeigt Aktualität (1 Monat nach Impressum "September 2025")

---

## 4. BARRIEREFREIHEIT (WCAG 2.2 Level AA)

### Compliance-Status: ✅ Level AA Compliant

**Identisch zu Impressum:**
- Tastaturnavigation ✅
- Semantische HTML-Struktur (H1 → H2 → H3) ✅
- Farbkontrast ≥ 4.5:1 ✅
- Link-Unterscheidung (Color + Weight + Border-Bottom) ✅

**Zusätzlich:**
- H3-Hierarchie (4.1–4.6) korrekt implementiert ✅
- Externe Links haben `rel="nofollow noopener"` + `target="_blank"` ✅

---

## 5. SEO & STRUKTURIERTE DATEN

### Meta-Tags
```astro
<Base
  title="Datenschutz - Wolf-Agents"
  description="Datenschutzerklärung von Eduard Wolf Grafik & Design, Wolf-Agents Website-Services für Kanzleien nach DSGVO."
  noindex={true}
>
```

**Title:** 28 Zeichen (konsistent mit Impressum)
**Description:** 117 Zeichen (Keywords: Datenschutz, Eduard Wolf, Wolf-Agents, Kanzleien, DSGVO)
**noindex:** true (verhindert Indexierung)

### Strukturierte Daten
**Aktuell:** Keine Schema.org-Integration
**Empfohlen:** `Organization` Schema (identisch zu Impressum-Empfehlung)

### Interne Verlinkung
**Hero CTAs:**
1. `/kontakt` (Primary)
2. `/impressum` (Secondary)

**Legal-Card Links (extern):**
3. https://developers.cloudflare.com/turnstile/
4. https://www.cloudflare.com/trust-hub/privacy-and-data-protection/
5. https://developers.cloudflare.com/workers/runtime-apis/kv/#ttl
6. https://www.zerobounce.net/privacy-policy.html
7. https://www.zerobounce.net/dpa/
8. https://aws.amazon.com/compliance/gdpr-center/
9. https://aws.amazon.com/artifact/
10. https://aws.amazon.com/messaging/aws-mail-manager/
11. https://docs.aws.amazon.com/workmail/latest/adminguide/journaling.html
12. https://developers.cloudflare.com/data-localization/

**Gesamt:** 2 interne + 10 externe Links (alle mit `rel="nofollow noopener" target="_blank"`)

---

## 6. PERFORMANCE & CORE WEB VITALS

**Erwartete Metriken:** Identisch zu Impressum
- LCP: ~1.4s ✅
- INP: ~90ms ✅
- CLS: ~0.05 ✅

**Optimierungen:** Identisch zu Impressum (SSG, Dark-Grid Hero, Scoped Styles, inline SVG)

---

## 7. KOMPONENTEN-INTERAKTIONEN

**Identisch zu Impressum:**
- Hero (align="left")
- ContentBoxDark (Verantwortliche Stelle)
- Section (negative Margin -mt-20)
- Legal-Card (Scoped Styles mit Blur-Orbs)

**Unterschied:** H3-Styling für Subsections (4.1–4.6)

---

## 8. CONTENT-STRATEGIE

### Messaging-Architektur
**Primäre Value Propositions:**
1. **Transparenz:** "Wir erläutern transparent" (Hero-Subtitle)
2. **Keine Tracking-Cookies:** Trust Building (Section 3)
3. **DSGVO-Compliance:** Alle Rechtsgrundlagen benannt (Art. 6 Abs. 1 lit. b/c/f)
4. **EU-Datenschutz:** ZeroBounce (UK), AWS (Luxemburg/Irland) → EU-Rechenzentren
5. **Betroffenenrechte:** Auskunft, Löschung, Widerspruch (Section 8)

### Tonalität
**Tone:** Formal, transparent, rechtskonform (aber verständlicher als typische Datenschutzerklärungen)

**Zielgruppen:**
1. **Legal Professionals (Kanzleien):** Erwarten präzise DSGVO-Artikel-Angaben
2. **Behörden:** Prüfen Compliance bei Auftragsvergabe
3. **End Users:** Wollen verstehen, was mit ihren Daten passiert

---

## 9. TECHNISCHE IMPLEMENTIERUNGS-DETAILS

**Identisch zu Impressum:**
- Datei-Struktur (Imports)
- Scoped Styles (`.legal-card`, `.legal-prose`)
- Non-Breaking Spaces (`&nbsp;`)

**Zusätzlich:** H3-Styling für Subsections

---

## 10. TESTING & QA

**Funktionale Tests:** Identisch zu Impressum (Phone/Email Links, Hero CTAs)

**Content-Tests:**
**Test Case: Externe Link-Attribute**
```gherkin
Given Legal-Card enthält 10 externe Links
When Besucher klickt externen Link
Then Link öffnet in neuem Tab (target="_blank")
And Link hat rel="nofollow noopener" (Security + SEO)
```

**Accessibility-Tests:** Identisch zu Impressum

---

## 11. DEPLOYMENT & MAINTENANCE

**Build-Output:**
```
dist/
  datenschutz/
    index.html  (246 Zeilen → ~30KB minified HTML inkl. Scoped Styles)
```

**Caching:** Identisch zu Impressum (7 Tage Edge, 24h Browser)

**Content-Updates:**
**Häufige Updates:**
- **Stand-Angabe:** Bei DSGVO-Änderungen (aktuell "Oktober 2025")
- **Drittdienste:** Bei Austausch von Cloudflare/ZeroBounce/AWS
- **Speicherfristen:** Bei Änderung der internen Policies

---

## 12. ZUSAMMENFASSUNG & NÄCHSTE SCHRITTE

### Stärken dieser Page
1. **DSGVO-Compliance:** Alle Pflichtangaben vorhanden (Art. 13/14 DSGVO)
2. **Transparenz:** Keine Tracking-Cookies, kein Profiling → Trust Building
3. **EU-Fokus:** ZeroBounce (UK), AWS (Luxemburg/Irland) → EU-Rechenzentren
4. **Technische Tiefe:** Double Opt-In, Rate-Limiting, Turnstile detailliert erklärt
5. **Betroffenenrechte:** Art. 15-21 DSGVO vollständig aufgelistet
6. **Externe Links:** Alle mit `rel="nofollow noopener"` → Security + SEO

### Verbesserungspotenziale
1. **Schema.org:** Aktuell kein `Organization` Schema → sollte ergänzt werden
2. **Stand-Angabe:** "Oktober 2025" → bei Content-Änderungen aktualisieren
3. **Cloudflare Regional Services:** Aktuell nicht klar, ob aktiviert → sollte spezifiziert werden

### Nächste Schritte
**Phase 1: Schema-Integration (Woche 1):**
- [ ] Implementiere `Organization` Schema (identisch zu Impressum-Empfehlung)

**Phase 2: Content-Review (jährlich):**
- [ ] Prüfe Aktualität der Drittdienste (Cloudflare, ZeroBounce, AWS)
- [ ] Update Stand-Angabe (aktuell "Oktober 2025")
- [ ] Prüfe, ob Cloudflare Regional Services aktiviert → Text entsprechend anpassen

---

**Ende der Dokumentation.**
**Batch 7 (11/11 Pages) ist vollständig abgeschlossen!**
Alle 54 Pages (Batches 1-7) sind dokumentiert. 🎉
