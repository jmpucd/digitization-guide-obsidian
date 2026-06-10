---
tags: [pipeline, tooling]
---

# Archiving & Delivery (`archive-project`)

`archive-project` pushes a **finished project** from a local archive queue to long-term **CentOS** archives, **verifying integrity with MD5 at every hop**, logs it in a **Google Sheet**, and (planned) shares it on **Box**.

> [!info] Status: core flow built (a few config details to confirm); Box sharing planned. Source: `archive-tool` (`archive-tool-brief.md`).

---

## Before you run it

The project must be **consolidated into one folder** in an archive queue, and that queue folder must contain a **`.archive-source`** marker file (prevents accidental archiving of the wrong directory). Multi-machine assembly is **out of scope** — bring the files together first.

## What it does

`archive-project` (run interactively; `--yes` to skip confirmation):

1. **Pick source** — scans configured `archive_queue_paths`, skips unmounted drives, shows a picker (`[Internal] MC-247_water_rights_maps`).
2. **Pick destination** — SSHes to CentOS, lists collections under the archives root; drill into `*-Collections` to a numbered subfolder, or `+ new collection` (validated against e.g. `MC-450` format).
3. **Confirm** — shows resolved source / Synology staging / CentOS paths.
4. **Transfer with integrity checks:**
   - Compute an **MD5 manifest** (`manifest.md5`) of every file (excludes `@eaDir`, `.DS_Store`, `Thumbs.db`, `*.tmp`, etc.), plus a checksum **of the manifest itself**.
   - rsync **laptop → Synology staging** (resumable: `--partial --append-verify`).
   - **Verify on Synology** (`md5sum -c`); abort on any mismatch.
   - rsync **Synology → CentOS** — run *from the Synology* to avoid the campus firewall; staging copy is kept as a backup.
   - **Verify on CentOS** (`md5sum -c`); abort on any mismatch.
5. **Log to Google Sheet** — append a row: project ID, name, source machine/path, Synology path, CentOS path, status `archived, not shared`, date, manifest checksum, and Box columns.

## Collections

Prefix-numbered (`D-XXX`, `MC-XXX`, `O-XXX`) and named (`HarrisonCollection`, `Maps`, `Serials`, …). Parent folders end in `-Collections`. New collections must match `^<prefix>-\d+$`.

## Box sharing — planned

A CentOS **poller** (~every 2 min) will read the Sheet and act on it — **no webhooks**, the Sheet *is* the control surface:

- **Share:** rows with **Share on Box = true**, empty **Shared date**, status `archived, not shared` → `rclone` the project to Box, set collaborators from **Share with**, write back Box path + `shared`.
- **Unshare:** **Share on Box = false** with a Box path (or status `remove`) → remove collaborators (leave files by default), clear Box path/date, status back to `archived, not shared`.
- **Errors** write `error: <reason>` and halt that row (no auto-retry).

## To confirm (from the design brief)

CentOS archives root path · Tailscale stability across machines · SSH key distribution · Google service account · full collection prefix list · auto-`mkdir` vs manual for new collections · Box unshare behavior · rclone Box config · symlink handling.

## Where it fits

Takes over after a session is **checked in as done** in [[Session Handoff (digi)]] and staged into an archive queue. It's the last stage of the [[Processing Pipeline Overview]].

---

## Related
- [[Processing Pipeline Overview]] · [[Session Handoff (digi)]] · [[File & Folder Naming]]
