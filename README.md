# megaconvert

Plugin-based "advanced converter" that works from:
- CLI: `megaconvert convert in.docx out.pdf`
- Python: `from megaconvert import convert_file, convert_bytes`

It tries to support "as many as possible" formats by delegating to external engines when present:

## External tools (optional but recommended)
- LibreOffice (soffice): office formats
- Pandoc: docs/markup conversions
- FFmpeg: audio/video/subtitle conversions
- ImageMagick (magick/convert): image conversions + some PS/PDF routes
- Inkscape: SVG/SVGZ/EPS/PDF vector conversions
- Ghostscript (gs): PS/EPS/PDF, PDF/A via device configs
- Calibre (ebook-convert): epub/mobi/azw3-like ebook conversions (mobi included)
- 7-Zip (7z): archives (zip/rar/7z/tar/gz/bz2/xz/iso, etc.)
- DjVuLibre (ddjvu): djvu -> pdf/images/text
- Tesseract: OCR (image/pdf scan -> text)

## Install
Editable:
pip install -e .
Extras:
pip install -e ".[dev,yaml,xml,toml,ocr]"

## CLI
megaconvert list
megaconvert capabilities
megaconvert supports in.docx pdf
megaconvert convert in.docx out.pdf
megaconvert convert in.mp4 out.mp3 --ff-args "-vn -b:a 192k"
megaconvert convert in.pdf out.pdf --pages "1-3,5"

## Python
from megaconvert import convert_file, convert_bytes, capabilities, supports
convert_file("a.docx", "a.pdf")
ok = supports("docx", "pdf")
caps = capabilities()
