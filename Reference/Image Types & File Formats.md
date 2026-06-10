---
tags: [reference]
---

# Image Types & File Formats

The vocabulary behind the numbers in [[Imaging Standards by Material Type]]. If you know *what* each setting does, you can make good decisions when a project doesn't fit a standard exactly.

> [!note] 📷 Placeholder — diagram: same image at 8-bit vs 16-bit, sRGB vs Adobe RGB, 200 vs 600 ppi
> Replace with a lab-made comparison figure.

---

## Resolution (PPI)

**PPI = pixels per inch** across the original object — not the file's stored DPI tag. We focus the camera to a target ppi (e.g. 400) so a known length on the object measures the right number of pixels. Higher ppi = more detail but larger files.

- **400 ppi** — bound volumes, documents, oversized items (general reflective capture).
- **600 ppi** — photographs and postcards (fine photographic detail).
- **Film** — set ppi so the cropped frame is ≥ 5000 px on the long side; the ppi number varies with film size.

We verify ppi with the **Capture Resolution Ruler** in Capture One during [[PPI & Focus]].

## Bit Depth

How many tonal steps per channel.

- **8-bit** (24-bit color = 3 × 8) — standard for most reflective material; ~16.7M colors. Smaller files.
- **16-bit** (48-bit color = 3 × 16) — photographs, film, anything where smooth gradients or heavy tonal editing matter. More editing headroom, larger files.

## Color Space (Color Profile)

The set of colors a file can describe. We **tag** files with the right profile so color is interpreted consistently everywhere.

- **Adobe RGB (1998)** — default for almost all color work here; wider gamut than sRGB.
- **Grey Gamma 2.2** — for grayscale outputs (e.g. B&W film production masters, ScanTailor grayscale pages).
- **Bitmap** — pure black/white, 1-bit (ScanTailor B&W-only pages).

Color profiling of the *camera* (vs. tagging the *file*) is covered in [[Color Management & Calibration]].

## File Format: TIFF

**TIFF, uncompressed** is our archival master format across every material type:

- Lossless — no generational quality loss.
- Universally readable and preservation-friendly.
- Holds 8-bit and 16-bit data and embedded color profiles.

Derivative/access formats (JPEG, PDF, e-book outputs from ScanTailor) are made *from* the TIFF masters when a project needs them — the TIFF is always the thing we preserve.

## Master vs. Derivative

- **Archival / production master** — the highest-quality file we keep forever (TIFF). Film keeps two: an uninverted *archival* master and an inverted, corrected *production* master.
- **Derivative / access copy** — smaller files generated for delivery or sharing. Made from masters; never the only copy.

---

## Related
- [[Imaging Standards by Material Type]] — the per-material numbers
- [[Color Management & Calibration]] · [[Common Mistakes]]
- [[General Preflight]] — where these settings get dialed in
