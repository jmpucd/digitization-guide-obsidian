---
tags: [pipeline, tooling]
---

# Session Handoff (`digi`)

`digi` moves a **Capture One session** between the capture station, the Synology **queue**, and the edit workstations — so a session is always in exactly one place, everyone can see who has it, and two people never edit it at once. Color tags, ratings, and crops travel inside the `.cosessiondb`.

> [!info] Status: built. Source: `digitization-tasks-helper`. Full SOP: `docs/SOP-capture-one-handoff.md`.

---

## The three states

A session is always in **one** of these:

1. **Capturing** — on the capture station's internal drive only.
2. **Parked** — on the Synology only, no lock file → **available**.
3. **Checked out** — on the Synology **and** one edit mini's TB SSD; a lock file on the Synology names the holder.

| Location | Role |
|---|---|
| Capture station `~/Pictures/capture_sessions/` | Where fresh captures land |
| Synology `<share>/capture_sessions/` | **Canonical queue** — source of truth when nobody's editing |
| Edit mini `/Volumes/<TB-SSD>/capture_sessions/` | Fast local working copy while editing |

## The commands

| Command | What it does |
|---|---|
| `digi park` | Capture done → copy session to the Synology queue, remove local copy |
| `digi checkout` | Pull an available session to this Mac's SSD, **write a lock** |
| `digi checkin` | Push edits back to the Synology, record **stage + note**, **release lock** |
| `digi queue` | List all sessions and who holds each |
| `digi status` | What's on this Mac, what's elsewhere, count available |
| `digi log` | Audit trail (park/checkout/checkin/force-unlock) |
| `digi doctor` | Verify tools/paths are configured |
| `digi force-unlock <session>` | Admin: clear a **stale** lock (requires a reason) |

## Typical loop

1. **Capture station, capture done:** close the session in Capture One → `digi park` → pick session + your name → it lands in the queue as **available**.
2. **Edit mini:** `digi checkout` → pick an available session + your name → open it in Capture One **from the SSD path it reports** (never from the Synology share).
3. **When done/pausing:** close the session → `digi checkin` → choose stage (**crop / qa-qc / done / other**) + a one-line note → lock releases, session is **available** again.

## Safety rules

> [!warning] Do not skip
> - **Always close the Capture One session** before `park` or `checkin` (an in-progress DB write copies in an inconsistent state).
> - **Never edit a session directly off the Synology share** — always `checkout` to a local SSD first.
> - **Never manually delete the Synology copy** — it's the source of truth.
> - **Never `force-unlock`** without confirming the holder isn't actively working.

## Where it fits

Replaces the manual SSD shuttle described in [[Page Splitting#Move to the cropping workstation]]. After a session is checked in as **done**, it's staged for [[Archiving & Delivery (archive-tool)]].

---

## Related
- [[Processing Pipeline Overview]] · [[Archiving & Delivery (archive-tool)]] · [[Finder Color Tag Guide]]
