---
tags: [workflow, bound-volumes, sop]
---

# Delete Verso

A bound-volume step between [[Cropping & Straightening]] and [[Export]]: remove the **blank verso (back) pages** so only pages with content are exported.

---

## Steps

1. Select the thumbnail of the **first back page**.
2. **Select → Select by Same → Variant Position → 1**.
3. **Unselect** the first and last page (the covers).
4. Color-tag the rest **Pink**.
5. **Select by Color Tag → Pink** and review every image for any **text or images**.
   - If a page **has** content, **untag** it (remove Pink) and **fix its crop** — it stays.
6. Re-select by Color Tag → Pink, **⌘A** to select all remaining pink thumbnails, right-click → **Delete**.

✅ Then → **[[Export]]** (the export naming/Reset Output Counter step correctly handles any verso pages with text you kept).

---

## Related
- [[Bound Volumes]] · [[Cropping & Straightening]] · [[Export]] · [[Finder Color Tag Guide]]
