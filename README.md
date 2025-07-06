# pdf-sortierer

Dieses Projekt automatisiert die Sortierung und Ablage von gescannten PDF-Dateien.  
Neue PDFs im Ordner `gescannt` werden per OCR ausgelesen, nach konfigurierten Schlagwörtern eingeordnet und in die passenden Unterordner des Ordners `Belege` verschoben.  
Anschließend wird ein Hyperlink auf die abgelegte Datei in einer Excel-Datei im Ordner `digitale Buchfuehrung` angelegt.

## Vorbereitung

1. Benötigte Pakete installieren (Tesseract, Poppler und Python‑Abhängigkeiten):
   ```bash
   apt-get update
   apt-get install -y tesseract-ocr poppler-utils
   pip install pytesseract pdf2image watchdog openpyxl
   ```
2. Die Datei `config.json` anpassen. Dort sind die Pfade zu den Dropbox-Ordnern und die Schlagwortzuordnung hinterlegt.

## Nutzung

Das Skript `pdf_sorter.py` überwacht den in der Konfiguration angegebenen Ordner und verarbeitet neue PDF-Dateien automatisch:

```bash
python pdf_sorter.py
```

Beim Erkennen eines neuen PDFs wird der Text per OCR analysiert, die Datei in den passenden Ordner verschoben und in der Excel‑Liste verlinkt.
