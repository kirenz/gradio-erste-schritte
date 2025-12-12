# Erste Schritte mit Gradio

![Python Version](https://img.shields.io/badge/python-3.11-blue.svg)
![uv](https://img.shields.io/badge/uv-managed-430f8e.svg?style=flat&logo=python&logoColor=white)
![Gradio Version](https://img.shields.io/badge/gradio-6.1.0-orange.svg)
![License](https://img.shields.io/badge/license-MIT-green.svg)

Dieses Repository enthält kleine Gradio-Apps, die unterschiedliche Wege zeigen, wie man Python-Funktionen als Weboberfläche bereitstellt – von der einfachen `gr.Interface`-Variante bis zum frei gestaltbaren `gr.Blocks`-Layout.

[Gradio](https://www.gradio.app/) ist ein Python-Framework, mit dem sich interaktive Webanwendungen für Machine Learning und Data Science ohne Frontend-Kenntnisse erstellen lassen. Die Beispiele in diesem Repository zeigen sowohl die Grundlagen als auch fortgeschrittene Techniken.

## Inhaltsverzeichnis

- [Voraussetzungen](#voraussetzungen)
- [Setup](#setup)
- [Überblick über die Beispiele](#überblick-über-die-beispiele)
- [Gemini konfigurieren](#gemini-konfigurieren)
- [Anwendungen starten](#anwendungen-starten)
- [Was Sie erwarten können](#was-sie-erwarten-können)
- [Troubleshooting](#troubleshooting)
- [Weiterführende Ressourcen](#weiterführende-ressourcen)
- [Lizenz](#lizenz)

## Voraussetzungen

- [uv](https://github.com/astral-sh/uv) ist installiert (verwaltet Abhängigkeiten und virtuelle Umgebung).


## Setup

1. Repository klonen oder herunterladen.

    ```bash
    git clone https://github.com/kirenz/gradio-erste-schritte.git
    ```
    

2. Ins Projekt wechseln:
   ```bash
   cd gradio-erste-schritte
   ```
3. Abhängigkeiten installieren (legt auch die virtuelle Umgebung an):
   ```bash
   uv sync
   ```
4. Den Ordner im Code-Editor öffnen, z. B. mit VS Code.

## Überblick über die Beispiele

### 1. Hello World Beispiele

- **`hello_gradio.py`** – minimaler Einstieg mit `gr.Interface`
  - Zeigt die einfachste Art, eine Python-Funktion als Web-App bereitzustellen
  - Nimmt einen Namen entgegen und gibt eine Begrüßung zurück
  - Ideal für schnelle Prototypen

- **`hello_gradio_blocks.py`** – gleiche Logik, aber mit manuell aufgebautem Blocks-Layout
  - Demonstriert das `gr.Blocks` API für mehr Kontrolle über Layout und Events
  - Ermöglicht individuellere Gestaltung der Benutzeroberfläche
  - Nutzt explizite Event-Handler

### 2. Komponenten-Beispiele

- **`gradio_components.py`** – zeigt mehrere Eingabe- und Ausgabekomponenten in einem Interface
  - Demonstriert Textbox, Dropdown und Slider
  - Kombiniert mehrere Eingaben zu einer Ausgabe
  - Nutzt die einfache Interface-API

- **`gradio_components_blocks.py`** – dasselbe Szenario, frei arrangiert mit Rows und Buttons
  - Zeigt Custom-Layout mit `gr.Row()` für nebeneinander angeordnete Komponenten
  - Trennt Input- und Output-Bereiche visuell
  - Demonstriert manuelle Event-Verkettung

## Anwendungen starten

Alle Beispiele lassen sich direkt über uv starten. Die folgenden Befehle immer aus dem Projektordner heraus ausführen; uv sorgt automatisch für die richtige Umgebung.

>[!WARNING] 
>Immer nur eine Gradio-App gleichzeitig laufen lassen. Um eine laufende App zu beenden, ins Terminal wechseln und `Strg + C` (macOS/Linux) bzw. `Ctrl + C` (Windows) drücken. Erst danach den nächsten `uv run`-Befehl ausführen.


Hello World mit Interface

```bash
uv run hello_gradio.py
```

Hello World mit Blocks

```bash
uv run hello_gradio_blocks.py
```

Komponenten-Demo mit Interface

```bash
uv run gradio_components.py
```

Komponenten-Demo mit Blocks

```bash
uv run gradio_components_blocks.py
```


## Hinweise zu Nutzung von Gradio

Nach dem Start einer Gradio-App:

1. **Lokaler Server**: Gradio startet automatisch einen lokalen Webserver (standardmäßig auf Port 7860)
2. **Browser-Zugriff**: Die URL wird im Terminal angezeigt (z.B. `http://127.0.0.1:7860`)
3. **Automatisches Öffnen**: In den meisten Fällen öffnet sich automatisch ein Browser-Tab
4. **Interaktive UI**: Sie sehen eine webbasierte Benutzeroberfläche mit den definierten Komponenten
5. **Live-Reload**: Änderungen am Python-Code erfordern einen Neustart der App

### Unterschiede zwischen Interface und Blocks

- **`gr.Interface`**: 
  - Schneller Einstieg mit minimaler Konfiguration
  - Automatisches Layout
  - Begrenzte Anpassungsmöglichkeiten
  - Ideal für einfache Ein-/Ausgabe-Szenarien

- **`gr.Blocks`**: 
  - Vollständige Kontrolle über Layout und Design
  - Manuelle Event-Verkettung erforderlich
  - Komplexere Anwendungen möglich
  - Nutzen von Rows, Columns und Custom-Layouts

## Troubleshooting

### Port bereits in Verwendung

**Problem**: `OSError: [Errno 48] Address already in use`

**Lösung**: 
- Eine andere Gradio-App läuft noch. Beenden Sie diese mit `Strg/Ctrl + C`
- Oder starten Sie auf einem anderen Port:
  ```python
  demo.launch(server_port=7861)
  ```

### Python-Version

**Problem**: Falsche Python-Version wird verwendet

**Lösung**:
- `uv` verwaltet automatisch die korrekte Python-Version (3.11)
- Bei Problemen: `uv sync` erneut ausführen

### Abhängigkeiten nicht gefunden

**Problem**: `ModuleNotFoundError`

**Lösung**:
```bash
uv sync
```

## Weiterführende Ressourcen

- [Offizielle Gradio-Dokumentation](https://www.gradio.app/docs/)
- [Gradio Guides und Tutorials](https://www.gradio.app/guides/)
- [uv Package Manager](https://github.com/astral-sh/uv)

