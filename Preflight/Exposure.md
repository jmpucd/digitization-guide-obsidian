---
tags: [preflight, sop]
---

# Exposure

Part of [[General Preflight]] (step 7). Goal: consistent, repeatable exposure across the whole project, judged against **known patch values** on your target — not by eye.

---

## Read the patches

1. Add color readouts: click-and-hold the white-balance cursor icon → **Add Color Readout**.
   ![[preflight-add-color-readout.png]]
2. Place readouts on the **mid-tone patches** (our notes use **11, 12, 13**).
   ![[preflight-color-readouts-placed.png]]
3. Prefer **LAB** over RGB (LAB matches the numbers printed on Golden Thread targets and is independent of output color space): **View → LAB Readout → GoldenThread (ICC)**.

## Hit the target value

Compare the readout's top number to the patch's printed value. **The goal: get each readout as close as possible to its patch value without any readout exceeding it** (even in the decimals).
![[preflight-color-readout-compare.png]]

Reference L\* values for the **mid neutral** patch:

| Target | Patch | L\* |
|---|---|---|
| Golden Thread | 15 | 62.3 |
| Device Level | 15 | 62.3 |
| FADGI 19264 | J9 | 62.7 |
| DT NGT2 | F6 | 64.2 |

(These are "batch average" values; your target may differ very slightly.)

## How to adjust

1. **Mainly adjust shutter speed** (for LEDs like DT Photon/Stellar) or strobe power (for strobes). Take another capture and re-measure.
   ![[preflight-exposure-slider.png]]
2. The **Exposure slider** in Capture One can be nudged with **small positive values (< 0.3)** only.
   - **Never** drag it negative — that risks mis-mapping clipped highlight data from a slightly over-exposed frame.
3. When set, right-click the readouts → **Delete All Readouts**.

> [!warning] Don't set exposure off a white patch under Linear Response
> Some guides set exposure on a white patch (e.g. patch 10). That's fine with **Linear Scientific**, but **Linear Response** rolls off highlights — setting exposure off a white patch under Response gives a dramatically over-exposed image. This is why we measure on **Linear Scientific** then switch to **Linear Response** ([[Mode, Profile & Curve]]).

---

## Related
- [[General Preflight]] → back to finalize (step 8)
- [[Mode, Profile & Curve]] · [[White Balance]] · [[Color Management & Calibration]]

> [!quote] Source
> *DT Digitization Guide — Preflight §7.8* + lab notes.
