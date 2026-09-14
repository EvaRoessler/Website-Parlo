# Parlo Communications — Projektregeln

Website von Eva Rössler, Parlo Communications, München.
Strategische Kommunikationsberatung. Domain: parlo-communications.de

Diese Datei gilt für **alle** Arbeiten an dieser Website. Bitte vor jeder
Änderung an Seiteninhalten, Überschriften oder Metadaten lesen und einhalten.
Wenn eine Anweisung im Chat diesen Regeln widerspricht, bitte kurz nachfragen.

---

## 1. Überschriften — die wichtigste Regel

Suchmaschinen lesen die Überschriftenstruktur, um zu verstehen, worum es auf
einer Seite geht. Deshalb gilt auf **jeder** Seite, auch auf allen künftigen:

- **Genau eine `<h1>` pro Seite.** Nicht null, nicht zwei.
- **Die `<h1>` enthält das Fokus-Keyword der Seite** (siehe Tabelle in Abschnitt 5).
- **Die `<h1>` muss nicht der optisch größte Text sein.** Sie muss der inhaltlich
  wichtigste sein. Ein großes Zitat oder ein Werbeslogan ist niemals die `<h1>` —
  das wird ein `<h2>` oder ein `<p>` mit eigener CSS-Klasse.
- **Keine Ebene überspringen.** Auf `<h1>` folgt `<h2>`, auf `<h2>` folgt `<h3>`.
  Niemals `<h1>` direkt zu `<h3>`.
- **Überschriften nie für Optik missbrauchen.** Wenn etwas nur größer oder fetter
  aussehen soll, ist das CSS-Arbeit, kein `<h>`-Tag.
- **Jede `<h2>` benennt einen echten Abschnitt** der Seite und beschreibt dessen
  Inhalt in eigenen Worten — keine reinen Schmuckwörter.

### Struktur der Startseite (Soll-Zustand)

```
h1   Strategische Kommunikationsberatung · München        (die kleine Zeile im Hero)
h2   „Die meisten Unternehmen haben etwas zu sagen …"     (das große Zitat)
h2   Mein Angebot
  h3   Strategische Kommunikationsberatung
  h3   Personal Branding & Positionierung
  h3   Interim Communications Lead
h2   Eva Rössler
  h3   Stationen
  h3   Haltung
h2   Die richtige Expertise an passender Stelle           (Netzwerk)
  h3   Marita Schöps
  h3   Michael Kurz
h2   Reden wir                                            (Kontakt)
```

---

## 2. Metadaten — für jede Seite verpflichtend

Jede Seite, auch jede neue Unterseite, bekommt:

| Element | Regel |
|---|---|
| `<title>` | Höchstens **60 Zeichen**. Fokus-Keyword **am Anfang**. Format: `Fokus-Keyword München \| Eva Rössler` |
| `<meta name="description">` | **120 bis 158 Zeichen**. Enthält das Fokus-Keyword und einen Handlungsaufruf. |
| `<link rel="canonical">` | Absolute URL der Seite selbst, immer mit `https://www.` |
| `<html lang="de">` | Auf jeder Seite |
| Open Graph | `og:title`, `og:description`, `og:url`, `og:image`, `og:type`, `og:locale`, `og:site_name` |
| `twitter:card` | `summary_large_image` |

**Niemals** zwei Seiten mit identischem `<title>` oder identischer Description.

**Niemals** `<meta name="robots" content="noindex">` im Live-Betrieb. Falls für
eine Testumgebung nötig: unbedingt vor dem Live-Gang entfernen.

### Startseite — exakte Werte

```html
<title>Strategische Kommunikationsberatung München | Eva Rössler</title>
<meta name="description" content="Strategische Kommunikationsberatung in München: Kommunikationsstrategie, Positionierung und Krisenkommunikation. Jetzt Erstgespräch vereinbaren.">
<link rel="canonical" href="https://www.parlo-communications.de/">
<meta name="robots" content="index, follow, max-image-preview:large">
<meta name="author" content="Eva Rössler">

<meta property="og:type" content="website">
<meta property="og:locale" content="de_DE">
<meta property="og:site_name" content="Parlo Communications">
<meta property="og:url" content="https://www.parlo-communications.de/">
<meta property="og:title" content="Parlo Communications – Kommunikation, die durchdringt">
<meta property="og:description" content="Eva Rössler berät Unternehmen und Führungskräfte strategisch: Kommunikationsstrategie, Personal Branding, Interim Communications Lead.">
<meta property="og:image" content="https://www.parlo-communications.de/img/parlo-communications-og.jpg">
<meta property="og:image:width" content="1200">
<meta property="og:image:height" content="630">
<meta property="og:image:alt" content="Parlo Communications – Eva Rössler, strategische Kommunikationsberatung in München">

<meta name="twitter:card" content="summary_large_image">
```

---

## 3. Strukturierte Daten

Einmal auf der Startseite, im `<head>` oder am Ende des `<body>`:

```html
<script type="application/ld+json">
{
  "@context": "https://schema.org",
  "@type": "ProfessionalService",
  "@id": "https://www.parlo-communications.de/#parlo",
  "name": "Parlo Communications",
  "description": "Strategische Kommunikationsberatung in München für Unternehmen und Führungskräfte.",
  "url": "https://www.parlo-communications.de/",
  "logo": "https://www.parlo-communications.de/img/parlo-communications-logo.svg",
  "image": "https://www.parlo-communications.de/img/eva-roessler-kommunikationsberatung-muenchen.jpg",
  "email": "NOCH EINTRAGEN",
  "founder": {
    "@type": "Person",
    "name": "Eva Rössler",
    "jobTitle": "Kommunikationsberaterin",
    "sameAs": ["https://www.linkedin.com/in/NOCH-EINTRAGEN"]
  },
  "address": {
    "@type": "PostalAddress",
    "addressLocality": "München",
    "addressRegion": "Bayern",
    "addressCountry": "DE"
  },
  "areaServed": [
    { "@type": "City", "name": "München" },
    { "@type": "Country", "name": "Deutschland" }
  ],
  "knowsAbout": [
    "Strategische Kommunikation", "Kommunikationsstrategie", "Krisenkommunikation",
    "Reputationsmanagement", "Personal Branding", "Executive Positioning",
    "Markenpositionierung", "Interne Kommunikation", "Externe Kommunikation",
    "Interim Management Kommunikation"
  ],
  "makesOffer": [
    { "@type": "Offer", "itemOffered": { "@type": "Service",
      "name": "Strategische Kommunikationsberatung",
      "description": "Kommunikationsstrategien, die auf Unternehmensziele einzahlen – von der Medienarbeit bis zur Krisenkommunikation." } },
    { "@type": "Offer", "itemOffered": { "@type": "Service",
      "name": "Personal Branding & Positionierung",
      "description": "Authentische Positionierung von Führungspersönlichkeiten, inklusive Medientraining und Präsentationstraining." } },
    { "@type": "Offer", "itemOffered": { "@type": "Service",
      "name": "Interim Communications Lead",
      "description": "Aufbau von Kommunikationsabteilungen und -prozessen auf Zeit, mit geordneter Übergabe." } }
  ]
}
</script>
```

Bei neuen Unterseiten zusätzlich `BreadcrumbList` ergänzen, sobald es eine
Navigationshierarchie gibt.

---

## 4. Bilder

- **Dateinamen:** nur Kleinbuchstaben, Bindestriche statt Leerzeichen, keine
  Umlaute (ö → oe, ü → ue, ä → ae, ß → ss). Beschreibend, nicht `IMG_4021.jpg`.
- **Alt-Text ist Pflicht** und beschreibt, was zu sehen ist — er wird blinden
  Nutzerinnen vorgelesen. Keywords nur, wo sie inhaltlich stimmen.
- **Rein dekorative Bilder** bekommen `alt=""` (leer), nicht weggelassen. Ein
  Logo, das ein zweites Mal auf derselben Seite auftaucht, ist dekorativ.
- **`width` und `height` immer angeben** — verhindert Layout-Sprünge beim Laden.
- **Erstes sichtbares Bild:** `loading="eager" fetchpriority="high"`.
  **Alle übrigen:** `loading="lazy"`.
- **Format:** WebP mit JPG/PNG als Rückfall.

### Bilder der Startseite

| Bild | Dateiname | Alt-Text |
|---|---|---|
| Logo Header | `parlo-communications-logo.svg` | `Parlo Communications` |
| Hero-Porträt | `eva-roessler-kommunikationsberatung-muenchen.jpg` | `Eva Rössler, Inhaberin von Parlo Communications und Kommunikationsberaterin in München` |
| Porträt „Das bin ich" | `eva-roessler-kommunikationsberaterin-portraet.jpg` | `Eva Rössler, Kommunikationsberaterin mit 15 Jahren Erfahrung in Brand und Corporate Communications` |
| Netzwerk Marita Schöps | `marita-schoeps-transformationsberaterin.jpg` | `Marita Schöps, Transformations- und Changeberaterin im Netzwerk von Parlo Communications` |
| Netzwerk Michael Kurz | `michael-kurz-eventmanager.jpg` | `Michael Kurz, Eventmanager im Netzwerk von Parlo Communications` |
| Logo Footer | `parlo-communications-logo-weiss.svg` | `` (leer, dekorativ) |
| Social-Vorschau | `parlo-communications-og.jpg` | `Parlo Communications – Eva Rössler, strategische Kommunikationsberatung in München` |

Das Social-Vorschaubild (`parlo-communications-og.jpg`) muss noch erstellt
werden: genau 1200 × 630 Pixel, unter 1 MB. Es erscheint, wenn die Seite auf
LinkedIn oder per WhatsApp geteilt wird.

---

## 5. Keyword-Zuordnung — nicht eigenmächtig ändern

Jedes Keyword gehört **genau einer** Seite. Wird ein Begriff aus dieser Tabelle
auf einer anderen Seite als Fokus verwendet, konkurrieren beide Seiten bei Google
gegeneinander und beide verlieren (Keyword-Kannibalisierung).

Ein Begriff darf im **Fließtext** jeder Seite vorkommen. Verboten ist er nur als
Fokus in `<title>`, `<h1>` und `<h2>` fremder Seiten.

| Keyword | Suchvolumen | gehört zu Seite |
|---|---|---|
| strategische kommunikationsberatung | 30 | **Startseite** |
| entwicklung kommunikationsstrategie | 100 | Entwicklung Kommunikationsstrategie |
| externe kommunikation | 150 | Externe Kommunikation |
| kommunikationsstrategie nachhaltigkeit | 100 | Kommunikationsstrategie Nachhaltigkeit |
| pr beratung | 150 | PR-Beratung |
| reputationsmanagement | 800 | Reputationsmanagement |
| personal branding | 400 | Personal Branding |
| linkedin positionierung | 100 | LinkedIn Positionierung |
| präsentationstraining | 300 | Präsentationstraining |
| medientraining für führungskräfte | 30 | Medientraining |
| public speaking | 900 | Public Speaking |
| interne kommunikation | 700 | Interne Kommunikation |
| markenpositionierung | 300 | Markenpositionierung |
| unternehmenspositionierung | 40 | Unternehmenspositionierung |
| markenstrategie beratung | 100 | Markenstrategie Beratung |
| storytelling im business | 210 | Storytelling im Business |
| kommunikationsprozesse im unternehmen | 10 | Kommunikationsprozesse |
| krisenkommunikation unternehmen | 50 | Krisenkommunikation Beratung |
| externe kommunikation verbessern | 100 | Externe Kommunikation (Interim) |

Geplante Seitenstruktur:

```
Startseite
├── Entwicklung Kommunikationsstrategie
│   ├── Externe Kommunikation
│   ├── Kommunikationsstrategie Nachhaltigkeit
│   ├── PR-Beratung
│   └── Reputationsmanagement
├── Personal Branding
│   ├── LinkedIn Positionierung
│   ├── Präsentationstraining
│   ├── Medientraining
│   ├── Public Speaking
│   └── Interne Kommunikation
├── Markenpositionierung
│   ├── Unternehmenspositionierung
│   ├── Markenstrategie Beratung
│   └── Storytelling im Business
└── Interim Communications Lead
    ├── Kommunikationsprozesse
    ├── Krisenkommunikation Beratung
    └── Externe Kommunikation
```

**Beim Anlegen einer neuen Unterseite immer:**

1. Fokus-Keyword aus der Tabelle nehmen, keines erfinden.
2. URL sprechend und kurz: `/kommunikationsstrategie/pr-beratung/`,
   nicht `/seite-7/`. Kleinbuchstaben, Bindestriche, keine Umlaute.
3. `<title>` und Description nach den Regeln aus Abschnitt 2 neu schreiben.
4. Von der Startseite und von der übergeordneten Seite dorthin verlinken —
   im Linktext das Fokus-Keyword verwenden, nicht „hier klicken".
5. Die neue URL in `sitemap.xml` ergänzen.

---

## 6. Sprache und Ton

- Sprache der Website ist Deutsch, Ansprache der Leserinnen und Leser: **Sie**.
- Eva schreibt über sich in der **ersten Person** („Ich baue genau das auf").
- Direkt, klar, ohne Agenturfloskeln. Kurze Sätze. Keine Ausrufezeichen.
- Bestehende Texte nicht eigenmächtig umschreiben. Wenn ein Text aus
  SEO-Gründen geändert werden sollte, vorher vorschlagen und nachfragen.

---

## 7. Technische Pflicht vor dem Live-Gang

- [ ] Eine Domain-Variante festlegen (mit oder ohne `www`), die andere per
      301-Weiterleitung dorthin leiten.
- [ ] `sitemap.xml` und `robots.txt` vorhanden, Sitemap in `robots.txt` verlinkt.
- [ ] Kein `noindex` mehr im Code.
- [ ] Impressum und Datenschutzerklärung vollständig und verlinkt
      (Pflicht, sobald das Kontaktformular Daten entgegennimmt).
- [ ] Kontaktformular sendet tatsächlich und bestätigt dem Absender.
- [ ] Google Search Console eingerichtet, Sitemap eingereicht.
- [ ] Google-Unternehmensprofil angelegt — ohne das bleibt der Ortsbezug
      München wirkungslos.
