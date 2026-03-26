# PyFreeApps — ArystoTech Free Desktop Utilities

A collection of **100% offline, privacy-first desktop utilities** built with Python and PySide6. All tools are available as standalone `.exe` applications and are also bundled together in a single all-in-one launcher: **PySuperFreeApps**.

Developed by **ArystoTech Software** · [arystotech.com/free](http://arystotech.com/free)

---

## Overview

| App | Purpose | Accent Color |
|---|---|---|
| [PyBulkRenamer](#pybulkrenamer) | Batch file renaming with live preview | Amber |
| [PyImageSquisher](#pyimagesquisher) | Image compression, resizing, and format conversion | Red |
| [PyJson2CsvConverter](#pyjson2csvconverter) | JSON to CSV conversion with smart auto-detection | Green |
| [PyJsonBeautifier](#pyjsonbeautifier) | JSON formatter, minifier, and validator | Purple |
| [PyLogExtractor](#pylogextractor) | Log file search and line extraction | Cyan |
| [PySuperFreeApps](#pysuperfreeapps) | All-in-one tabbed launcher for all tools above | Indigo |

---

## PyBulkRenamer

**Batch rename files safely with live conflict detection.**

### Purpose
Allows users to apply rename rules (prefix, suffix, find/replace) to all files inside a selected folder. A live preview table shows every proposed change before anything is committed, and conflicts are caught before any file is touched.

### Features
- **Select Folder** — browse and load all files from any local directory
- **Rename Rules** — apply any combination of:
  - Prefix added to the beginning of each filename
  - Suffix added before the file extension
  - Find & Replace text within filenames
- **Live Preview Table** — shows Original Name vs. New Name side-by-side; updates in real time as rules change
- **Conflict Detection** — highlights in red any target name that duplicates another proposed name or already exists in the folder; the Apply button is disabled until all conflicts are resolved
- **Safe Two-Phase Rename** — files are first renamed to temporary names, then to their final names, preventing partial-rename failures from corrupting the folder
- **Automatic Rollback** — if any rename fails mid-operation, completed renames are reversed to restore original filenames
- **100% Offline** — no uploads, no network calls

### Requirements
- Python 3.x, PySide6

---

## PyImageSquisher

**Compress and convert entire image folders in seconds.**

### Purpose
Processes a folder of images and writes compressed/converted copies to a separate output folder. Useful for reducing disk usage, preparing images for web publishing, or batch-converting formats without touching the originals.

### Features
- **Input / Output Folder Selection** — source and destination folders are kept separate; defaults the output to a `Squished/` subfolder inside the input
- **Output Format** — choose between JPEG, PNG, or WebP
- **Max Width (px)** — down-scales images that exceed a specified pixel width while preserving aspect ratio using high-quality LANCZOS resampling
- **Quality Slider** — adjustable 10–100% quality for JPEG and WebP; PNG is always lossless
- **Smart JPEG Handling** — transparently converts RGBA/palette images to RGB with a white background to prevent JPEG encoding errors
- **Processing Log** — real-time per-file log showing output file size and estimated space savings
- **Space Savings Summary** — reports total MB saved across the batch
- **100% Offline** — images never leave the machine

### Requirements
- Python 3.x, PySide6, Pillow

---

## PyJson2CsvConverter

**Convert JSON data to CSV with deep flattening and smart auto-detection.**

### Purpose
Turns complex or nested JSON files into clean, flat CSV files suitable for spreadsheets, databases, or data analysis pipelines. Works from a file on disk or from JSON pasted directly into the app.

### Features
- **Two Input Modes** (tabbed):
  - *File to File* — browse for a `.json` file and specify a `.csv` output path
  - *Paste Data to File* — paste raw JSON text directly into the editor and save the result
- **Smart Array Auto-Detection** — automatically finds the most suitable array in the JSON structure (prefers arrays of objects, chooses the largest candidate); logs the detected path
- **Deep Flattening** — nested objects are flattened using dot-notation keys (e.g., `address.city`); simple arrays are joined as comma-separated strings; complex arrays are serialized as JSON strings
- **Configurable CSV Delimiter** — choose Comma (`,`), Semicolon (`;`), or Pipe (`|`)
- **Auto Output Path** — suggests a CSV filename based on the input JSON filename
- **Status Log** — shows conversion steps, row and column counts, and any errors
- **Clear Error Reporting** — JSON syntax errors include line and column numbers
- **100% Offline**

### Requirements
- Python 3.x, PySide6

---

## PyJsonBeautifier

**Format, minify, and validate JSON entirely offline.**

### Purpose
A quick-access JSON editor for developers and API workers who need to clean up messy JSON responses, strip whitespace for transmission, or validate payloads without sending sensitive data to an online tool.

### Features
- **Split-Pane Editor** — raw JSON on the left, formatted output on the right; panes are resizable via a draggable splitter
- **Beautify** — pretty-prints JSON with 4-space indentation and Unicode characters preserved
- **Minify** — strips all whitespace to produce the most compact valid JSON string
- **Validator** — both Beautify and Minify validate the input first; errors are shown in red in the output pane with the failing line and column number in the status bar
- **Copy Output** — copies the right-pane result to the clipboard with one click
- **Clear** — resets both panes and the status message
- **100% Offline** — API keys and payloads stay on the local machine

### Requirements
- Python 3.x, PySide6

---

## PyLogExtractor

**Search large log files safely without loading them into memory.**

### Purpose
Scans arbitrarily large log or text files line by line and writes only the matching lines to a new output file. Designed for server logs, application logs, and any structured text file where only a subset of lines is relevant.

### Features
- **Input / Output File Selection** — browse for any `.log` or `.txt` file; output path defaults to `<input>_extracted.txt`
- **Plain Text Search** — simple substring match
- **Regex Search** — full Python `re` module regex support with syntax validation before execution
- **Case Sensitivity Toggle** — optionally match case exactly
- **Memory-Safe Processing** — reads the source file line by line; never loads the entire file into RAM, making it safe for multi-gigabyte logs
- **Progress Reporting** — logs a progress message every 100,000 lines scanned
- **Result Summary** — reports total lines scanned and total matching lines found
- **Source Protection** — prevents selecting the same file as both input and output
- **100% Offline**

### Requirements
- Python 3.x, PySide6

---

## PySuperFreeApps

**All-in-one tabbed launcher that bundles every tool above into a single window.**

### Purpose
Provides a unified desktop experience where all five utilities are accessible via tabs without needing to open separate executables. Includes a home/landing tab and an About tab.

### Tabs
| Tab | Description |
|---|---|
| Home | Landing page with app overview and navigation cards |
| Bulk Renamer | Full PyBulkRenamer interface |
| Image Squisher | Full PyImageSquisher interface |
| JSON → CSV | Full PyJson2CsvConverter interface |
| JSON Beautifier | Full PyJsonBeautifier interface |
| Log Extractor | Full PyLogExtractor interface |
| About | Credits and links |

All features from each individual app are available within the combined launcher. The window resizes to 1400×920 to comfortably accommodate all tool UIs.

### Requirements
- Python 3.x, PySide6, Pillow

---

## Common Design Principles

All apps share the following qualities:

- **100% Offline / Private** — no data is ever sent to a server or external service
- **Modern Dark Theme** — consistent Fusion-style dark UI with card-based layout, rounded corners, and per-app accent colors
- **Standalone Executables** — each app is compiled with PyInstaller into a single `.exe` with no external dependencies required at runtime
- **Non-destructive Defaults** — operations never overwrite source files; outputs always go to a separate destination
- **Live Status Feedback** — every app has a summary label and/or log viewer that communicates progress and results clearly

---

## Tech Stack

| Component | Technology |
|---|---|
| Language | Python 3 |
| UI Framework | PySide6 (Qt 6) |
| Image Processing | Pillow (PIL) |
| Packaging | PyInstaller |
| Styling | Qt Stylesheet (QSS) |

---

## Getting Started

### Run from source

```bash
pip install PySide6 Pillow
python PySuperFreeApps.py   # all-in-one launcher
# or run individual apps:
python PyBulkRenamer.py
python PyImageSquisher.py
python PyJson2CsvConverter.py
python PyJsonBeautifier.py
python PyLogExtractor.py
```

### Run compiled executables

Pre-built `.exe` files are located in the `dist/` directory and require no Python installation.

---

## Support

- Website: [arystotech.com/free](http://arystotech.com/free)
- Buy us a coffee: [buymeacoffee.com/arystotech](https://buymeacoffee.com/arystotech)
