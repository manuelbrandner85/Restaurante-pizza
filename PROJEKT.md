# PROJEKT — Ristorante Boulevard, Agrigento

Steckbrief und Übergabe. Wer hier weiterarbeitet, liest zuerst diese Datei.

## Ziel
Gäste in Agrigento — Einheimische wie Tempelbesucher — sollen das Lokal finden,
die Küche einschätzen können und einen Tisch reservieren. Zielhandlung:
Reservierung (Formular oder Anruf).

## Zielgruppe
Drei Gruppen, drei Sprachen: Einheimische (IT), deutschsprachige Reisende (DE),
internationale Gäste (EN). Die Seite erkennt die Browsersprache und ist oben
rechts umschaltbar.

## Design-DNA
```
Haltung:      warm, gedämpft, filmisch
Referenz:     Chiaroscuro — eine Lichtquelle, viel Dunkel drumherum
Farbe:        Nacht #0A0806 · Stein #14100C · Elfenbein #EDE3D0 · Gold #C9963F
              Akzent: Orange #FF9A3C (nur das V in der Wortmarke)
Typografie:   Cinzel (Display) · Cormorant Garamond (Akzent, kursiv) · Barlow (Text)
Raster:       1180 px, ab 1600 px mitwachsend bis 1600 px
Materialität: aufgelegt — Passepartout, Lichtkante, Schatten in drei Stufen
Bildsprache:  Nacht, Bernstein, eine gemeinsame Gradientenkarte über allen Fotos
Motion:       träge einschwingend, lange Wege, keine Bounces
Nicht:        keine Stockfoto-Ästhetik · kein zentrierter Standard-Hero · kein Karussell
```

## Aufbau
- `index.html` — Startseite, enthält CSS und JS vollständig
- `anfahrt.html` — Karte (Google Maps erst nach Klick), Adresse, Entfernungen
- `impressum.html` — Impressum, Datenschutz, Bildnachweis, Haftung
- `bilder/` — WebP, je eine große und eine kleine Fassung (srcset)
- `sitemap.xml`, `robots.txt`, `favicon.png`, `apple-touch-icon.png`

## Mehrsprachigkeit
Alle Texte stehen im Objekt `TEXTE` am Ende jeder HTML-Datei — je ein Block
`de`, `it`, `en` mit identischen Schlüsseln. Ein Element bekommt seinen Text
über `data-t="schluessel"`, Platzhalter über `data-t-ph`, Alternativtexte über
`data-t-alt`, ARIA-Beschriftungen über `data-t-aria`.
Eine vierte Sprache = ein weiterer Block plus ein Knopf im Umschalter.

## Motion-Contract
```
Dauern:  ui 180ms · move 240ms · reveal 520–800ms · Szene 1500ms+
Easing:  cubic-bezier(.2,.7,.2,1)
Regel:   nur transform und opacity animieren
Reduced Motion: Trägheitsscrollen aus, Anheften aus, Inhalte sofort im Endzustand
```

## Entscheidungen
- Trägheitsscrollen nur mit Maus, nie auf Touchgeräten (dort ist das System besser).
- Tempelrolle wird nur ab 900 px Breite angeheftet, darunter Wischen.
- Google Maps lädt erst auf Klick — Datenschutz, siehe impressum.html.
- Bildmaße werden nicht von Hand gepflegt (führte zu verzogenen Bildern).
- Reservierung über zwei gleichwertige Wege: Formular und Telefon.

## Offene Punkte (vor weiterer Verbreitung der Seite)
1. Gerichte und Preise unter „Alla carta" sind erfunden — echte Karte einsetzen.
2. Die vier Speisenbilder sind KI-erzeugt — durch eigene Fotos ersetzen.
3. E-Mail-Adresse im Reservierungsformular ist unbestätigt (`info@boulevard-agrigento.it`).
4. Impressum: Inhaber, P. IVA und Verantwortlicher fehlen (im Text markiert).
5. Öffnungszeiten stammen aus Verzeichnissen, nicht vom Betreiber.

## Bildnachweis
Eingang, Wappen, Speisekarte: Ristorante Boulevard.
Tempio della Concordia bei Nacht — Dreirik (CC0).
Tempio dei Dioscuri, Tempio di Giunone, Panorama — Effems (CC BY-SA 4.0),
Wikimedia Commons. Die Nennung ist Lizenzbedingung und darf nicht entfernt werden.

## Messwerte bei Übergabe
Gedrosselt auf ein Viertel der Rechenleistung, über GitHub Pages:
```
360 px    FCP  944 ms   LCP 1240 ms   CLS 0
1280 px   FCP  808 ms   LCP  808 ms   CLS 0.014
Übertragen bis zur Speisekarte auf dem Handy: ~560 kB
Kein Querscrollen von 320 bis 2560 px · keine Konsolenfehler · alle Verweise 200
```
