---
tags: [preflight, sop]
---

# Mode, Profile & Curve

Part of [[General Preflight]] (step 4). These three settings live in the **Base Characteristics** tool. Capture One **Cultural Heritage (CH)** adds options not in Capture One Pro.

> [!note] 📷 Placeholder — screenshot: Base Characteristics tool with Mode / ICC Profile / Curve set for flat art
> Replace with a current screenshot of our Base Characteristics panel.

---

## Mode

CH adds a **Mode** selector for common workflows:

- **Photography** — all reprographic/photographic work other than scanning film. **← our default.**
- **Film Positive** — reproducing positive films.
- **Film Negative** — reproducing negative films.

The film modes account for the non-linear tone/color of film originals (see [[Imaging Standards by Material Type#Film Negatives]]).

## ICC Profile (Color Profile)

Pick the profile that matches your **light source**, found under the **Cultural Heritage** section of the ICC Profile menu:

- **LED DT Photon** — for the DT Photon, DT Photon XL, and **DT Stellar** (same white-light spectrum). **← our lights.**
- **Flash** — strobes (e.g. Profoto).
- **Tungsten** — 3200K tungsten.

Our standard selection: **Phase One iXG/iXH Flat Art Reproduction — LED DT Photon**.

## Curve

- **Linear Response** — **use for most flat-art reproduction.** Linear through most of the range with slight highlight compression that preserves tone/color in highlights.
- **Linear Scientific** — absolutely linear; tends to clip highlights on anything with gloss or dimensionality. Use only for artwork with no gloss/dimensionality.

> [!tip] Our practice: measure on Scientific, capture on Response
> We set the curve to **Linear Scientific** while *measuring* during preflight, then switch to **Linear Response** for actual capture (step 8 of [[General Preflight]]). This matters for exposure — setting exposure off a white patch under Linear Response overexposes, because Response rolls off highlights. See [[Exposure]].

## Save your defaults

Once set, use the Base Characteristics **⋯ menu → Save As Defaults** to skip these selections next time.

---

## Related
- [[General Preflight]] → next: [[LCC (Lens Cast Calibration)]]
- [[Color Management & Calibration#The Camera — Color Profiling]] · [[Exposure]]

> [!quote] Source
> *DT Digitization Guide — Preflight §7.2–7.4* + lab notes.
