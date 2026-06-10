---
tags: [reference, standards]
---

# Imaging Standards by Material Type

These are the capture and output targets we aim for, organized by the **type of original** you're digitizing. When you start a project, identify the material type here first — it tells you the resolution, bit depth, color space, and file format to use, and the workflow pages build on these numbers.

> [!tip] How to use this page
> Find your material below, set your capture to match, then follow the matching workflow in [[Imaging Workflow]]. For *why* these numbers matter, see [[Image Types & File Formats]]. These targets are informed by [FADGI](https://www.digitizationguidelines.gov/guidelines/digitize-technical.html) — see [[Color Management & Calibration#FADGI]].

---

## Bound Items: Archival

Books and other bound objects captured and preserved **as found**, with minimal processing. → workflow: [[Bound Volumes]] · equipment: [[DT Versa]] (unbound, pressed) or [[DT V-Cradle]] (intact)

| Setting | Value |
|---|---|
| Resolution | 400 ppi |
| Bit Depth | 24 bit |
| Color Space | Adobe RGB (1998) |
| File Type | TIFF |
| Sharpening | Standard system sharpening |

- All pages captured at 400 ppi, 24-bit color, tagged Adobe RGB (1998).
- All images in focus with correct light and color settings.
- Covers are always captured unless the project says otherwise.
- Front and back of all pages are captured.
- Foldouts: multiple captures of a single page so every side of every piece is visible.
- Loose/unattached items: captured separately off the book, kept in original order.
- Capture outside the physical page, leaving a border on all sides.
- Deskew with ~1/8"–1/4" border on all sides (depending on item size).
- **Rotation:** handwritten → rotate to match how most pages in the book are oriented; printed text → rotate so text is readable for OCR.

## Bound Items: ScanTailored

Bound objects we want to turn into an **e-book-like** digital copy.

| | Capture | Final Output |
|---|---|---|
| Resolution | 600 ppi B&W, 400 ppi color/grayscale | 600 ppi B&W, 400 ppi color/grayscale |
| Bit Depth | 8 / 24 bit | 1 / 8 / 24 bit |
| Color Space | Grey Gamma 2.2 or Adobe RGB (1998) | Bitmap, Grey Gamma 2.2, or Adobe RGB (1998) |
| File Type | TIFF | TIFF |
| Sharpening | Standard system sharpening | Standard system sharpening |

- Covers: color at 400 ppi unless noted.
- B&W pages and pages with grayscale images: grayscale at 600 ppi.
- Pages with color images/detail: color at 400 ppi.
- Handwriting: color 400 ppi if colored ink; grayscale 600 ppi if gray/black ink.
- Final output: bitmap (B&W only), grayscale (grayscale/fine detail), color (color info).

## Documents

All non-photo, non-postcard, unbound items.

| Setting | Value |
|---|---|
| Resolution | 400 ppi |
| Bit Depth | 24 bit |
| Color Space | Adobe RGB (1998) |
| File Type | TIFF |
| Sharpening | Standard system sharpening |

- 400 ppi, 24-bit color, Adobe RGB (1998), in focus.
- Front and back always captured; capture outside the document for a border.
- Deskew and crop to a 1/8" border.

## Oversized Items

Document-type items too large for the standard capture area — maps, posters, architectural drawings. → workflow: [[Large & Flat Art]]

| Setting | Value |
|---|---|
| Resolution | 300 or 400 ppi (use 400 when possible) |
| Bit Depth | 24 bit |
| Color Space | Adobe RGB (1998) |
| File Type | TIFF |
| Sharpening | Standard system sharpening |

- Minimum 300 ppi (400 preferred), 24-bit color, Adobe RGB (1998).
- Front and back always captured; capture outside the item for a border.
- Deskew and crop to a 1/4" border.

## Photographs

Photographic prints (printed on photo paper). Home-printer prints on regular paper are **documents**. When unsure, treat it as a photograph.

| Setting | Value |
|---|---|
| Resolution | 600 ppi |
| Bit Depth | 48 bit |
| Color Space | Adobe RGB (1998) |
| File Type | TIFF |
| Sharpening | Standard system sharpening |

- 600 ppi, 48-bit color, Adobe RGB (1998), in focus.
- Front and back always captured; capture outside the photo for a border.
- Deskew and crop to a 1/8" border.

## Postcards

Image/graphic on one side, space for note and address on the other.

| Setting | Value |
|---|---|
| Resolution | 600 ppi |
| Bit Depth | 48 bit |
| Color Space | Adobe RGB (1998) |
| File Type | TIFF |
| Sharpening | Standard system sharpening |

- **Always 600 ppi**, even if the front is a drawing — treat like a photograph for resolution.
- 48-bit color, Adobe RGB (1998). Front and back always captured. 1/8" border.

## Scrapbooks

Bound objects with items of various types affixed to pages. → equipment: [[DT V-Cradle]]

| Setting | Value |
|---|---|
| Resolution | 400 ppi (loose photos 600 ppi) |
| Bit Depth | 48 bit |
| Color Space | Adobe RGB (1998) |
| File Type | TIFF |
| Sharpening | Standard system sharpening |

- Pages at 400 ppi, 48-bit color, Adobe RGB (1998). Covers always captured. Front and back of all pages.

## Film: Negatives

Two final files per negative — an **archival master** and a **production master**.

| | Archival Master | Production Master |
|---|---|---|
| Resolution | 5000+ px long side | 5000 px long side |
| Bit Depth | 48 bit color | 16 bit (16-bit grayscale / 48-bit color) |
| Color Space | Adobe RGB (1998) | Grey Gamma 2.2 or Adobe RGB (1998) |
| File Type | TIFF | TIFF |
| Sharpening | None | Standard system sharpening |
| Inversion | Uninverted | Inverted |

- Capture so the cropped image is at least 5000 px on the long side (capture ppi varies with negative size). Capture outside the negative to show the film border where possible.
- **Archival master:** unedited, uninverted, uncropped, 48-bit, Adobe RGB (1998).
- **Production master:** inverted "printed" version — deskewed, cropped just outside the image with a small border, tone/color corrected. B&W negs → 16-bit, Grey Gamma 2.2; color negs → 48-bit, Adobe RGB (1998).
- In Capture One CH, use the **Film Negative** mode (see [[Mode, Profile & Curve]]).

## Film: Positives

| Setting | Value |
|---|---|
| Resolution | 5000 px long side (varies) |
| Bit Depth | 48 bit color |
| Color Space | Adobe RGB (1998) |
| File Type | TIFF |
| Sharpening | Standard system sharpening |

- At least 5000 px on the long side, 48-bit color, Adobe RGB (1998).
- Capture outside the positive for a border; deskew and crop just outside the image; adjust tone/color to match the original.
- In Capture One CH, use the **Film Positive** mode.

---

## Related
- [[Image Types & File Formats]] — what bit depth, ppi, and color space actually mean
- [[Color Management & Calibration]] · [[Common Mistakes]]
- Workflows: [[Bound Volumes]] · [[Large & Flat Art]]

> [!quote] Source
> Material-type standards adapted from *The Digitization Lab Management Guide* (April Martin, 2025). Figures are our own — see placeholders.
