# ArystoTech Productivity Suite

Freeware desktop utility apps built with Python and PySide6.

## Overview

This repository ships one bundle app plus six standalone desktop tools:

- `PySuperApp`: one shell that includes all six tools
- `PyBulkRenamer`: bulk file renaming with preview
- `PyImageSquisher`: single-image and batch image compression
- `PyImageConverter`: single-image and batch image conversion
- `PyJson2CsvConverter`: JSON to CSV conversion
- `PyJsonXmlFormatter`: JSON/XML formatting and minification
- `PyLogExtractor`: log filtering and extraction

## Apps

### PySuperApp

Bundle all six workflows into one desktop app with Home, per-tool tabs, and About screens.

Launcher:

```bash
python PySuperApp.py
```

### PyBulkRenamer

Rename files with live preview before applying changes.

Highlights:

- prefix, suffix, and find/replace rules
- conflict detection before rename
- safer two-phase rename flow

Launcher:

```bash
python PyBulkRenamer.py
```

### PyImageSquisher

Compress images without overwriting the originals.

Highlights:

- single-image or bulk queue workflow
- JPEG, PNG, and WEBP output
- max-width and quality controls

Launcher:

```bash
python PyImageSquisher.py
```

### PyImageConverter

Convert images across supported formats with single and bulk workflows.

Highlights:

- drag-and-drop batch conversion
- SVG rendering support
- format-aware export settings and optimization

Launcher:

```bash
python PyImageConverter.py
```

### PyJson2CsvConverter

Convert JSON files or pasted JSON into flat CSV output.

Highlights:

- nested structure detection
- dot-notation flattening
- configurable CSV delimiters

Launcher:

```bash
python PyJson2CsvConverter.py
```

### PyJsonXmlFormatter

Format and minify JSON or XML, then inspect the result in a searchable output window.

Highlights:

- auto-detect JSON vs XML
- pretty-print and minify actions
- searchable modal output view

Launcher:

```bash
python PyJsonXmlFormatter.py
```

Compatibility note:

- `PyJsonBeautifier.py` remains in the repo as a compatibility launcher for the renamed formatter

### PyLogExtractor

Extract matching lines from large logs or text files.

Highlights:

- plain-text or regex search
- case-sensitive or case-insensitive matching
- line-by-line processing for large files

Launcher:

```bash
python PyLogExtractor.py
```

## Freeware Model

All app features are available by default with no activation step.

This is part of ArystoTech Software's give-back, pay-it-forward idea: ship useful tools for free, then let people support the work only if they find it valuable.

Optional support links in the apps point to:

- [buymeacoffee.com/arystotech](https://buymeacoffee.com/arystotech)
- [arystotech.com/productivity_suite](https://arystotech.com/productivity_suite)

## Run From Source

Install dependencies:

```bash
pip install PySide6 Pillow cryptography
```

Run the bundle or any standalone launcher shown above.

## Build

Use the provided packaging script:

```bat
compile_all.bat
```
