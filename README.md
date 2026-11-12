# Offline SVG to PNG Scaling Converter

**German version below / Deutsche Fassung unten**

---

# 🇬🇧 English

**A simple, fully offline tool to scale, position and convert SVG graphics into high-resolution PNG images — directly in your browser. No installation, no uploads, no external services.**

**Simply explained:** This tool lets you open an SVG graphic, adjust its size and position, choose a background and save the result as a high-quality- and high-resolution-PNG-image.

**Technical overview:** A lightweight, client-side HTML application using JavaScript, the HTML5 Canvas API and browser-native image rendering to rasterize SVG files into configurable PNG output without requiring a backend or external dependencies.


## 1. About the Project

### What is this project?

The Offline SVG to PNG Scaling Converter is a browser-based utility for converting SVG vector graphics into PNG raster images.

It allows users to scale, position and align SVG graphics on a freely configurable canvas and convert it to an high-resolution-PNG-Image.
Different canvas formats, background options and output dimensions make it suitable for a variety of use cases.

The entire application runs locally in the browser. No files need to be uploaded to a server, and no external services are required.

### Why was this project created?

SVG files are resolution-independent vector graphics.
They can be scaled without losing quality.

However, many online converters export SVG files at a very low pixel resolution, resulting in blurry or pixelated PNG images that are often unsuitable for further use.
However, many applications, platforms and workflows require PNG files instead.

A simple conversion is often not enough. Users may also need to:

- Scale a graphic without changing its proportions.
- Position it precisely on a larger canvas.
- Center or align it.
- Place it on a white, transparent or image-based background.
- Prepare it for specific formats such as A4, 16:9 or 9:16.
- Export it at a defined pixel resolution.

That was the main reason I decided to create this tool.

This project brings these functions together in one small, easy-to-use tool.

This project and its README were created with assistance from ChatGPT and GitHub Copilot.


### Which problem does it solve?

Instead of using complex graphics software for simple conversion and layout tasks, users can perform the entire workflow directly in their browser.

**The main idea:** Convert a SVG, scale, position and export it as a high-resolution-PNG — without installing software or uploading sensitive graphics to external websites.

---

## 2. Features

| Feature | Description |
|---|---|
| Offline operation | Runs locally in the browser |
| SVG import | Load SVG files from your computer |
| PNG export | Save the result as a PNG file |
| Background options | Transparent, white or custom image |
| Custom canvas | Define individual width and height |
| Preset formats | A4, 16:9, 9:16 and 3:4 to use as a reference |
| SVG scaling | Scale graphics from 1× to 100× |
| Position control | Adjust X and Y coordinates |
| Alignment | Left, center, right, top and bottom |
| Aspect ratio | Option to lock the canvas proportions |
| Live preview | See changes immediately |
| Language selection | German and English |
| Appearance | System, light and dark mode |
| Reset | Restore the default editing settings |

---

## 3. How It Works

### For users

You select an SVG file, choose the desired canvas format to use as a reference, adjust the graphic and export the result as a PNG.

### Technical implementation

The application consists of a single HTML file containing HTML, CSS and JavaScript.

The processing pipeline works as follows:

1. The SVG file is read locally using the browser's `FileReader` API.
2. The SVG source is converted into a Blob.
3. A temporary object URL is created.
4. The browser loads the SVG as an image.
5. The SVG is rendered onto an HTML5 Canvas element.
6. Background, dimensions, scaling, positioning and alignment are applied during rendering.
7. The Canvas content is exported using the `toDataURL("image/png")` method.

The rendering process is handled entirely on the client side.

**No server-side processing, external API calls or third-party JavaScript libraries are required.**

---

## 4. Getting Started

### Requirements

- A modern web browser.
- An SVG file to convert.
- No installation required.
- No additional software or libraries required.


### Installation

There is no conventional installation process.

Simply download the HTML or clone the repository:

```bash
git clone https://github.com/BergSchweizer/svg-to-png-scaling-converter.git
```

Open the `svgconverter.html` file in your favorite browser.

### Offline usage

The application is designed to work offline.

Once the HTML file is available locally, you can open it without an internet connection.

Your SVG files and background images are processed locally in your browser.

---

## 5. User Guide – Step by Step

### Step 1 – Open an SVG file

Under **SVG File**, select the SVG graphic you want to convert.

The graphic will automatically appear in the preview area.

The original dimensions of the SVG are used as the initial canvas dimensions when the original format is selected.

To remove the loaded graphic, click the `X` button next to the file selection.

### Step 2 – Choose a background

Under **Background**, you can select one of three options:

- **Transparent:** Creates a transparent background for the PNG.
- **White:** Creates a solid white background.
- **Image:** Uses a custom image as the background.

To use your own background:

1. Select an image using the file selector.
2. Choose `Image` from the background mode dropdown.
3. The image will be displayed across the entire canvas.

Supported image formats depend on your browser. Common formats such as PNG and JPEG are supported.

Use the `X` button to remove the background image.

### Step 3 – Choose a canvas format

Under **Template / Aspect Ratio**, select a format to use as a reference.

Available reference:

| Format | Canvas dimensions |
|---|---:|
| Original | SVG dimensions |
| A4 Portrait | 2480 × 3508 px |
| A4 Landscape | 3508 × 2480 px |
| 16:9 Landscape | 1920 × 1080 px |
| 9:16 Portrait | 1080 × 1920 px |
| 3:4 Portrait | 1440 × 1920 px |
| 3:4 Landscape | 1920 × 1440 px |

You can also enter your own width and height in pixels.

The **Lock Aspect Ratio** option helps preserve the canvas proportions when changing its width.

### Step 4 – Adjust the SVG layer

This is where you control the appearance and placement of your graphic.

#### Scaling

Use the scaling slider to increase the size of the SVG.

Available range: 1× to 100×.

When using the Original template, the canvas dimensions are adjusted according to the selected scaling factor.

#### Position X

Controls the horizontal offset of the SVG graphic.

- Negative values move it to the left.
- Positive values move it to the right.
- Zero means no additional horizontal offset.

You can use either the slider or the numeric input.

#### Position Y

Controls the vertical offset.

- Negative values move it upwards.
- Positive values move it downwards.
- Zero means no additional vertical offset.

Again, both the slider and numeric input are available.

#### Horizontal alignment

Choose between:

- Left
- Center
- Right

#### Vertical alignment

Choose between:

- Top
- Center
- Bottom

The alignment settings determine the reference position of the graphic within the canvas. Additional X and Y offsets are applied on top of that alignment.

### Step 5 – Preview your result

The preview area on the right displays the current canvas.

Changes to the settings are rendered immediately.

The status display shows the current canvas dimensions in pixels.

This allows you to adjust the composition before exporting.

### Step 6 – Save your PNG

Click **Save** to export the current canvas as an untitled-PNG file directly into your download path.

The default filename is:

```text
preview.png
```

The image is generated directly from the Canvas element.

You can also right-click the preview and select **Save image as**, depending on your browser.
This allows you to customize the file name and saving location.

---

## 6. Additional Settings

### Language

The application supports:

- German
- English

Select your preferred language under Settings.

The interface labels, descriptions and accessibility labels are translated accordingly.

### Appearance

Three appearance modes are available:

- **System:** Automatically follows your operating system's color preference.
- **Light:** Uses a light interface.
- **Dark:** Uses a dark interface.

When System is selected, the application also reacts to changes in the operating system's color scheme.

### Mouse wheel controls

You can use the mouse wheel while hovering over supported controls to change their values.

This works with:

- Sliders
- Numeric inputs
- Dropdown menus

It allows faster adjustments without having to drag sliders or repeatedly click dropdown arrows.

### Reset settings

Click **Reset Settings** to restore the default editing configuration.

This resets:

- Scaling
- X and Y position
- Horizontal and vertical alignment
- Canvas template
- Original canvas dimensions, if an SVG is loaded

The currently loaded SVG and background image are not automatically removed.

---

## 7. Technical Architecture

### Technologies

| Technology | Purpose |
|---|---|
| HTML5 | Application structure |
| CSS3 | Layout, styling and themes |
| JavaScript | Application logic and rendering |
| HTML5 Canvas API | Image composition and PNG export |
| FileReader API | Local SVG file reading |
| Blob API | SVG data handling |
| URL.createObjectURL() | Temporary image URLs |
| Image API | Browser-native image loading |

### Rendering engine

The core rendering functionality is implemented in the `render()` function.

It performs the following operations:

1. Sets the canvas dimensions.
2. Clears the previous canvas content.
3. Draws the selected background.
4. Calculates the SVG dimensions based on the scaling factor.
5. Calculates the SVG position based on offsets and alignment.
6. Draws the SVG onto the canvas.
7. Updates the displayed canvas dimensions.

### SVG dimension detection

The application uses `parseSvgDimensions()` to determine the dimensions of an SVG file.

It first attempts to read the `viewBox` attribute.

If this is unavailable, it falls back to the SVG's `width` and `height` attributes.

The resulting dimensions are used to determine the initial canvas size and aspect ratio.

### Project structure

The current implementation consists of one self-contained file:

```text
svg-to-png-scaling-converter/
│
├── svgconverter.html
├── README.md
└── LICENSE
```

HTML, CSS, JavaScript and the translation dictionaries are contained in the HTML file.

This keeps the project lightweight and easy to distribute.

---

## 8. Privacy and Security

Privacy is one of the main design principles of this application.

- No file uploads to external servers.
- No cloud processing.
- No external APIs.
- No third-party JavaScript dependencies.
- No account or registration required.

SVG files and background images are processed locally in the browser.

**Important:** Offline operation does not automatically mean that every SVG file is harmless. Only open files from sources you trust. The application is not a dedicated SVG security scanner.

---

## 9. Current Limitations

The current version focuses on straightforward SVG-to-PNG conversion.

Some limitations:

- PNG is the available export format.
- There is no batch conversion functionality.
- There is no drag-and-drop interface.
- The canvas is intended for desktop browser use.
- The background image is scaled to fill the entire canvas.
- There is no project file format for saving and reopening editing sessions.

---

## 10. Project Status

This project is an independently developed utility created with assistance from AI-based development tools, including ChatGPT and GitHub Copilot.

It is intended as a practical, lightweight tool rather than a full graphics editing suite.

Contributions, suggestions and feedback are welcome.

---

## 11. License

This project is licensed under the MIT License. You are free to use, modify, distribute, and integrate this software into other projects, including for commercial purposes, subject to the terms of the license.

See the LICENSE file for details.

---

# 🇩🇪 Deutsche Version

## 1. Über das Projekt

### Was ist dieses Programm?

Der Offline SVG to PNG Scaling Converter ist ein browserbasiertes Werkzeug, mit dem sich SVG-Grafiken skalieren, positionieren und in hochauflösende PNG-Bilder umwandeln lassen.

Einfach gesagt: Du lädst eine SVG-Datei, passt Größe und Position an, bestimmst den Hintergrund und speicherst das Ergebnis als hochauflösende PNG.

Technisch handelt es sich um eine eigenständige HTML-Anwendung, die SVG-Dateien mithilfe von JavaScript und der HTML5 Canvas API clientseitig rasterisiert – vollständig lokal und ohne Serververarbeitung.

### Wie ist das Projekt entstanden?

SVG ist ein Vektorformat. Grafiken lassen sich damit ohne Qualitätsverlust beliebig vergrößern oder verkleinern.

Viele Online-Konverter wandeln SVG-Dateien lediglich in einer sehr geringen Pixelauflösung um. Das Ergebnis sind häufig stark verpixelte PNG-Bilder (Pixel-Art-Effekt), die für eine weitere Verwendung kaum oder gar nicht brauchbar sind.

In der Praxis werden jedoch häufig PNG-Dateien benötigt, beispielsweise für Webseiten, Präsentationen, Dokumente, Grafiken oder Social-Media-Inhalte.

Eine einfache Konvertierung reicht dabei nicht immer aus. Häufig muss die Grafik zusätzlich:

- Auf eine bestimmte Größe gebracht werden.
- Auf einer größeren Fläche positioniert werden.
- Horizontal oder vertikal ausgerichtet werden.
- Auf einem transparenten, weißen oder individuellen Hintergrund liegen.
- In ein festgelegtes Seitenverhältnis gebracht werden.
- Mit einer definierten Pixelauflösung exportiert werden.

Genau aus diesem praktischen Bedarf heraus ist dieses Projekt entstanden.

Das Ziel war, ein unkompliziertes Werkzeug zu schaffen, das diese Aufgaben in einer einzigen Anwendung zusammenführt.

Die Entwicklung erfolgte eigenständig und mit Unterstützung von KI-basierten Entwicklungswerkzeugen, insbesondere ChatGPT und GitHub Copilot.

### Welches Problem löst es?

Statt für einfache Konvertierungs- und Layoutaufgaben ein umfangreiches Grafikprogramm zu öffnen oder einen Online-Konverter zu verwenden, lassen sich alle notwendigen Arbeitsschritte direkt im Browser erledigen.

**Die Grundidee:** SVG laden, Größe und Position einstellen, Hintergrund auswählen und als PNG speichern – ohne Installation, ohne Upload und ohne externe Dienste.

---

## 2. Funktionen im Überblick

| Funktion | Beschreibung |
|---|---|
| Offline-Betrieb | Funktioniert lokal im Browser |
| SVG importieren | SVG-Dateien vom eigenen Rechner laden |
| PNG exportieren | Ergebnis als PNG speichern |
| Hintergrund | Transparent, weiß oder eigenes Bild |
| Freie Canvas-Größe | Breite und Höhe selbst festlegen |
| Formatvorlagen | A4, 16:9, 9:16 und 3:4 als Refernz |
| Skalierung | SVG von 1× bis 100× vergrößern |
| Positionierung | X- und Y-Position einstellen |
| Ausrichtung | Links, zentriert, rechts, oben und unten |
| Seitenverhältnis | Option zur Beibehaltung der Canvas-Proportionen |
| Live-Vorschau | Änderungen sofort sichtbar |
| Sprache | Deutsch und Englisch |
| Darstellung | System, Hell und Dunkel |
| Zurücksetzen | Bearbeitungseinstellungen zurücksetzen |

---

## 3. Wie funktioniert das Programm?

### Für Einsteiger

Das Programm zeichnet die ausgewählte SVG-Grafik auf eine digitale Zeichenfläche. Diese Zeichenfläche kann individuell gestaltet und anschließend als PNG-Bild gespeichert werden.

### Technischer Ablauf

Die Anwendung besteht aus einer einzelnen HTML-Datei mit integriertem HTML, CSS und JavaScript.

Die Verarbeitung erfolgt in mehreren Schritten:

1. Die SVG-Datei wird über die browserinterne `FileReader` API lokal eingelesen.
2. Der SVG-Quelltext wird in ein `Blob`-Objekt umgewandelt.
3. Über `URL.createObjectURL()` wird eine temporäre Objekt-URL erzeugt.
4. Der Browser lädt die SVG-Datei als Bild.
5. Die Grafik wird auf ein HTML5-Canvas gerendert.
6. Hintergrund, Skalierung, Positionierung und Ausrichtung werden angewendet.
7. Das Canvas wird über `toDataURL("image/png")` als PNG exportiert.

Die gesamte Verarbeitung findet clientseitig statt.

Es werden weder ein Backend noch externe APIs oder zusätzliche JavaScript-Bibliotheken benötigt.

---

## 4. Voraussetzungen und Start

### Voraussetzungen

- Ein aktueller Webbrowser.
- Eine SVG-Datei.
- Keine Installation notwendig.
- Keine zusätzlichen Bibliotheken notwendig.

### Installation

Das Projekt kann direkt über GitHub heruntergeladen oder geklont werden:

```bash
git clone https://github.com/BergSchweizer/svg-to-png-scaling-converter.git
```

Anschließend die Datei `svgconverter.html` im Browser öffnen.

Alternativ kann die HTML-Datei direkt heruntergeladen und lokal geöffnet werden.

### Offline-Betrieb

Die Anwendung ist für den lokalen Offline-Betrieb ausgelegt.

Nach dem Herunterladen der HTML-Datei ist keine Internetverbindung mehr erforderlich.

SVG-Dateien und Hintergrundbilder werden ausschließlich im Browser verarbeitet.

---

## 5. Bedienungsanleitung – Schritt für Schritt

### Schritt 1 – SVG-Datei laden

Im Bereich **SVG-Datei** die gewünschte Grafik auswählen.

Die Grafik erscheint anschließend automatisch in der Vorschau.

Wenn die Vorlage auf **Original** steht, werden zunächst die ursprünglichen Abmessungen der SVG-Grafik als Canvas-Größe verwendet.

Über die Schaltfläche `X` kann die geladene SVG-Datei wieder entfernt werden.

### Schritt 2 – Hintergrund festlegen

Im Bereich **Hintergrund** stehen drei Optionen zur Verfügung:

- **Transparent:** Die PNG-Datei erhält einen transparenten Hintergrund.
- **Weiß:** Die Zeichenfläche wird mit Weiß gefüllt.
- **Bild:** Ein eigenes Bild wird als Hintergrund verwendet.

So funktioniert es:

1. Über die Dateiauswahl ein Hintergrundbild laden.
2. Im Dropdown-Menü die Option `Bild` auswählen.
3. Das Bild wird über die gesamte Zeichenfläche gelegt.

Gängige Bildformate wie PNG und JPEG werden unterstützt, abhängig von den Möglichkeiten des Browsers.

Über `X` lässt sich das Hintergrundbild wieder entfernen.

### Schritt 3 – Vorlage und Seitenverhältnis auswählen

Im Bereich **Vorlage / Seitenverhältnis** kann das gewünschte Referenzformat zur ausgewählt werden.

| Vorlage | Abmessungen |
|---|---:|
| Original | SVG-Abmessungen |
| DIN A4 Hochformat | 2480 × 3508 px |
| DIN A4 Querformat | 3508 × 2480 px |
| 16:9 Querformat | 1920 × 1080 px |
| 9:16 Hochformat | 1080 × 1920 px |
| 3:4 Hochformat | 1440 × 1920 px |
| 3:4 Querformat | 1920 × 1440 px |

Alternativ können Breite und Höhe manuell in Pixeln eingetragen werden.

Mit **Seitenverhältnis sperren** lässt sich beim Ändern der Breite das bisherige Verhältnis der Zeichenfläche beibehalten.

### Schritt 4 – SVG-Ebene bearbeiten

Hier werden Größe und Position der Grafik eingestellt.

#### Skalierung

Mit dem Skalierungsregler wird die SVG-Grafik vergrößert.

Der Wertebereich reicht von 1× bis 100×.

Bei Verwendung der Vorlage **Original** wird auch die Größe der Zeichenfläche entsprechend dem Skalierungsfaktor angepasst.

#### Position X

Steuert die horizontale Position der SVG-Grafik.

- Negative Werte verschieben die Grafik nach links.
- Positive Werte verschieben sie nach rechts.
- Null bedeutet keine zusätzliche horizontale Verschiebung.

Die Einstellung ist sowohl über den Schieberegler als auch über das Zahlenfeld möglich.

#### Position Y

Steuert die vertikale Position.

- Negative Werte verschieben die Grafik nach oben.
- Positive Werte verschieben sie nach unten.
- Null bedeutet keine zusätzliche vertikale Verschiebung.

Auch hier stehen Schieberegler und Zahlenfeld zur Verfügung.

#### Horizontale Ausrichtung

Es stehen drei Möglichkeiten zur Verfügung:

- Links
- Zentriert
- Rechts

#### Vertikale Ausrichtung

Hier kann zwischen folgenden Optionen gewählt werden:

- Oben
- Zentriert
- Unten

Die Ausrichtung legt die Position innerhalb der Zeichenfläche fest. Zusätzliche X- und Y-Verschiebungen werden anschließend darauf angewendet.

### Schritt 5 – Vorschau kontrollieren

Auf der rechten Seite befindet sich die Vorschau.

Alle Änderungen werden unmittelbar dargestellt.

Die Statusanzeige zeigt die aktuelle Größe der Zeichenfläche in Pixeln an.

Dadurch kann die Grafik vor dem Export kontrolliert und angepasst werden.

### Schritt 6 – PNG speichern

Mit **Speichern** wird die aktuelle Zeichenfläche als PNG-Datei exportiert und Heruntergeladen.

Der voreingestellte Dateiname lautet:

```text
preview.png
```

Alternativ kann – abhängig vom Browser – über einen Rechtsklick auf die Vorschau die Option **Grafik speichern unter** verwendet werden.
Auf diese Weise können kann der Dateiname und der Speicherort individuell festlegen.

---

## 6. Weitere Einstellungen

### Sprache

Die Benutzeroberfläche unterstützt Deutsch und Englisch.

Die Sprache lässt sich unter **Einstellungen → Sprache** umstellen.

Beschriftungen, Platzhalter und Accessibility-Labels werden entsprechend übersetzt.

### Darstellung

Es gibt drei Darstellungsmodi:

- **System:** Übernimmt automatisch die Farbeinstellung des Betriebssystems.
- **Hell:** Helles Erscheinungsbild.
- **Dunkel:** Dunkles Erscheinungsbild.

Im Systemmodus reagiert die Anwendung auch auf Änderungen der systemweiten Darstellung.

### Mausrad-Steuerung

Bei ausgewählten Bedienelementen kann das Mausrad verwendet werden, um Werte zu verändern.

Das funktioniert bei:

- Schiebereglern
- Zahlenfeldern
- Dropdown-Menüs

Dadurch können Einstellungen schneller vorgenommen werden, ohne jeden Regler manuell ziehen zu müssen.

### Einstellungen zurücksetzen

Über **Einstellungen zurücksetzen** wird die Bearbeitungskonfiguration auf die Standardwerte zurückgesetzt.

Dabei werden folgende Einstellungen zurückgesetzt:

- Skalierung
- X- und Y-Position
- Horizontale und vertikale Ausrichtung
- Vorlage
- Ursprüngliche Canvas-Abmessungen, sofern eine SVG geladen ist

Die geladene SVG-Datei und das Hintergrundbild bleiben erhalten.

---

## 7. Technischer Aufbau

### Verwendete Technologien

| Technologie | Aufgabe |
|---|---|
| HTML5 | Struktur der Anwendung |
| CSS3 | Gestaltung, Layout und Themes |
| JavaScript | Programmlogik und Steuerung |
| HTML5 Canvas API | Bildkomposition und PNG-Export |
| FileReader API | Lokales Einlesen von SVG-Dateien |
| Blob API | Verarbeitung der SVG-Daten |
| URL.createObjectURL() | Erzeugung temporärer Objekt-URLs |
| Image API | Laden und Darstellen der Grafiken |

### Rendering Engine

Die zentrale Bildverarbeitung erfolgt über die Funktion `render()`.

Sie übernimmt folgende Aufgaben:

1. Festlegen der Canvas-Abmessungen.
2. Löschen des bisherigen Canvas-Inhalts.
3. Zeichnen des ausgewählten Hintergrunds.
4. Berechnen der SVG-Abmessungen anhand des Skalierungsfaktors.
5. Berechnen der Position anhand der X-/Y-Werte und Ausrichtung.
6. Zeichnen der SVG-Grafik auf das Canvas.
7. Aktualisieren der Statusanzeige.

### Ermittlung der SVG-Abmessungen

Die Funktion `parseSvgDimensions()` ermittelt die Abmessungen einer SVG-Datei.

Zunächst wird versucht, die Werte aus dem `viewBox`-Attribut auszulesen.

Falls dieses nicht vorhanden ist, werden ersatzweise die Attribute `width` und `height` ausgewertet.

Die ermittelten Werte dienen als Grundlage für die initiale Canvas-Größe und das Seitenverhältnis.

### Projektstruktur

Die aktuelle Version besteht aus einer einzigen eigenständigen HTML-Datei:

```text
svg-to-png-scaling-converter/
│
├── svgconverter.html
├── README.md
└── LICENSE
```

HTML, CSS, JavaScript und die Sprachdefinitionen befinden sich gemeinsam in dieser Datei.

Dadurch bleibt das Projekt kompakt, portabel und einfach weiterzugeben.

---

## 8. Datenschutz und Sicherheit

Ein wesentlicher Bestandteil des Projekts ist die lokale Verarbeitung der Dateien.

- Keine Datei-Uploads auf externe Server.
- Keine Cloud-Verarbeitung.
- Keine externen APIs.
- Keine externen JavaScript-Bibliotheken.
- Keine Registrierung oder Benutzerkonten.

SVG-Dateien und Hintergrundbilder werden direkt im Browser verarbeitet.

**Wichtiger Hinweis:** Lokaler Offline-Betrieb bedeutet nicht automatisch, dass jede SVG-Datei ungefährlich ist. Öffne nur Dateien aus vertrauenswürdigen Quellen. Das Programm ist kein spezieller SVG-Sicherheitsprüfer.

---

## 9. Aktuelle Einschränkungen

Die aktuelle Version konzentriert sich auf die grundlegende Konvertierung und Positionierung von SVG-Grafiken.

Folgende Funktionen sind derzeit nicht implementiert:

- Export in andere Formate als PNG.
- Stapelverarbeitung mehrerer SVG-Dateien.
- Drag-and-drop.
- Ein spezielles mobiles Bedienkonzept.
- Speichern und Wiederöffnen von Bearbeitungsprojekten.
- Individuelle Anpassung der Hintergrundbild-Positionierung.

Das Hintergrundbild wird aktuell auf die gesamte Canvas-Fläche skaliert.

---

## 10. Projektstatus und Entwicklung

Dieses Projekt ist ein eigenständig entwickeltes Werkzeug, dessen Umsetzung durch KI-basierte Entwicklungswerkzeuge unterstützt wurde, insbesondere durch ChatGPT und GitHub Copilot.

Das Ziel ist eine praktische, schlanke und leicht zugängliche Anwendung für alltägliche Grafikaufgaben.

Verbesserungsvorschläge, Fehlerberichte und Beiträge zur Weiterentwicklung sind willkommen.

---

## 11. Lizenz

Dieses Projekt unterliegt der MIT-Lizenz. Es steht Ihnen frei, diese Software zu nutzen, zu ändern, zu verbreiten und in andere Projekte zu integrieren, auch für kommerzielle Zwecke, sofern Sie die Bedingungen der Lizenz einhalten.

Einzelheiten finden Sie in der Datei „LICENSE“.
