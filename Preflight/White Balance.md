---
tags: [preflight, sop]
---

# White Balance

Part of [[General Preflight]] (step 6). Setting white balance correctly is as important as setting exposure. Do it with the **color target** under the glass (remove the LCC board first and re-capture the target).

---

## Steps

1. In the **White Balance** tool (or the Cursor Tools), select the **dropper** (white-balance picker). Make sure Mode reads **Custom**.
   ![[preflight-white-balance-dropper.png]]
2. Zoom into the target and **click the correct neutral patch** (see the patch table below). Click only inside the designated patch.
   ![[preflight-white-balance-patch.png]]
3. Press **`v`** to put the cursor tool away (prevents accidental misclicks).

## Which patch to click

| Target | White-balance patch |
|---|---|
| ISA **Golden Thread** | Patch **15** |
| ISA **Device Level** | Patch **17** |
| ISA **FADGI 19264** | Patch **J9** |
| **DT NGT2** | Patch **F6** |

> Our lab notes also reference clicking the mid-tone patch **14** on our target — confirm against the patch your target actually uses.

## How to know it worked

- Using **RGB** values: the three channels should read the **same, ±2** after clicking.
- Using **LAB** values: **a\*** (magenta) and **b\*** (yellow) should drop to a fraction of a point.

> [!tip] Save it as a preset
> You can save a white balance as a camera hardware preset via the white-balance picker in the **Camera** tool → **Set** → a Custom slot. We reuse presets like `No_Glass_400PPI` across sessions — see [[Large & Flat Art]].

---

## Related
- [[General Preflight]] → next: [[Exposure]]
- [[Color Management & Calibration]]

> [!quote] Source
> *DT Digitization Guide — Preflight §7.7* + lab notes.
