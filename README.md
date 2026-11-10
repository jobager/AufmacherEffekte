# Aufmacher-Effekte

**Ein einzelnes HTML-File, das aus einem beliebigen Foto schnell einen 16:9-Aufmacher für Online-Artikel macht – mit Filtern und passendem Zuschnitt, komplett im Browser und ohne KI-Einheitsbrei.**

Keine Installation, kein Build, kein Server: Die Datei öffnen, ein Bild hineinziehen, Effekt wählen, speichern. Alles läuft lokal – das Bild verlässt den Rechner nicht.

---

## Was es ist

Ein Werkzeug für die tägliche Redaktionsarbeit: In wenigen Klicks entsteht aus einem Pressefoto, Screenshot oder lizenzfreien Bild ein eigenständig gestalteter Aufmacher im Format 1920 × 1080 (16:9). Statt generischer KI-Bilder bekommt man reproduzierbare, handgemachte Looks – und mit speicherbaren Presets einen einheitlichen Stil über viele Artikel hinweg.

Das gesamte Tool steckt in **einer einzigen `.html`-Datei** (reines HTML, CSS und Canvas-JavaScript, ohne Abhängigkeiten außer den Web-Fonts). Damit lässt es sich per Mail verschicken, auf einen USB-Stick legen oder lokal `file://` öffnen.

## Highlights

- **17 Bildeffekte** von Duotone über Dither und Halftone bis Low-Poly und Neon-Noir – jeweils live über Regler und Farbwähler einstellbar.
- **Meta-Effekte:** ein *Slicer*, der das Bild in Zonen mit je eigenem Effekt teilt, und ein *Effekt-Verlauf*, der einen Effekt weich ins Original einblendet.
- **16:9-Format** auf zwei Wegen: interaktiver Zuschnitt oder – für Hochkant-Bilder – ein unscharfer, formatfüllender Hintergrund mit wählbarer Füllfarbe.
- **Farbiger Rahmen** als optionale Außenkante in beliebiger Dicke.
- **Eigene Presets** pro Effekt, dauerhaft im Browser gespeichert.
- **Responsives Layout** (unter 800 px rutschen die Bedienelemente über das Bild) und eine **interaktive Einführungs-Tour**, die die Oberfläche Schritt für Schritt erklärt.
- **Export als PNG** in voller Auflösung.

## Effekte im Überblick

| Effekt | Kurzbeschreibung |
| --- | --- |
| Ohne | Originalbild unbearbeitet |
| Duotone | Zweifarb-Verlauf nach Helligkeit, mit Presets |
| Halftone | Rasterpunktbild (Kreis/Quadrat/Kreuz, s/w, Farbe, Sepia) |
| Dither | Retro-Dithering (Floyd-Steinberg, Atkinson, Bayer, Schwelle; u. a. Game-Boy- und CGA-Palette) |
| Glitch | Digitale Störungen, RGB-Shift, Scanlines |
| ASCII | Umsetzung in Block- oder Textzeichen |
| Riso | Risograph-/Handdruck-Look mit Versatz und Körnung |
| Posterize | Reduzierte Farbstufen (RGB/HSL/Graustufen) |
| Solarize | Teil-Inversion / Sabattier-Effekt |
| Pixelate | Verpixelung (Quadrat, Kreis, Raute) |
| Threshold | Hartes Schwarz/Weiß bzw. Silhouette, auch zweifarbig |
| Blueprint | Kantenerkennung als Blaupause / technische Zeichnung |
| Gradient-Map | Helligkeit auf einen Drei-Stopp-Farbverlauf gemappt |
| Blitzlicht | Schnappschuss-Look mit Vignette, Korn und Datumsstempel |
| Neon-Noir | Dunkle Tönung mit Glow/Bloom und Korn |
| Technik | Industrial-Look aus Raster, Passermarken und Barcode |
| Low-Poly | Triangulation in farbige Dreiecksflächen |

## Bedienung

Die Seitenleiste führt von oben nach unten durch den Arbeitsablauf:

1. **Bild** laden (Drag & Drop oder Dateiauswahl); „Original wiederherstellen" setzt jederzeit zurück.
2. **16:9-Format** herstellen – Zuschnitt oder Unschärfe-Rand.
3. **Effekt** wählen und über die Regler feinjustieren; Einstellungen als Preset sichern.
4. **Meta-Effekte** (Slicer / Effekt-Verlauf) optional darüberlegen.
5. **Rahmen** ergänzen.
6. **Export** als PNG.

## Technik & Datenschutz

- **Rein clientseitig:** Alle Berechnungen laufen im `<canvas>` des Browsers. Es gibt keinen Server, keine Uploads, keine Tracker. Für die Datenschutz-Redaktion relevant: Das Bild bleibt auf dem Rechner.
- **Keine Build-Kette:** kein Node, kein Bundler, keine Laufzeit-Abhängigkeiten. Die einzige externe Ressource sind Google-Web-Fonts (rein kosmetisch; offline wird ein System-Font genutzt).
- **Presets** werden im `localStorage` des Browsers abgelegt – geräte- und browsergebunden.

## Browser & Bildformate

Läuft in aktuellen Chromium-Browsern, Firefox und Safari. Gelesen wird alles, was der Browser selbst dekodiert – in der Praxis **JPEG, PNG, WebP, AVIF, GIF, BMP, SVG und ICO** (bei animierten GIF/WebP das Einzelbild, SVG wird gerastert). **Nicht** unterstützt sind Kamera-RAW, TIFF, PSD und meist HEIC/HEIF – solche Dateien vorher nach JPEG oder PNG exportieren. Gespeichert wird unabhängig vom Eingabeformat immer als PNG.
