# Migration Notes — GitHub Pages Conversion

This document records the conversion of the original WPI-hosted academic website
into a GitHub Pages–ready static site, plus a follow-up cleanup pass.

The site is deployed at **https://andrewctrapp.github.io/**.

---

## 1. Final site map

### Active pages (in the navbar of `index.html`)
- `index.html` — homepage
- `publications.htm`
- `team.htm`
- `joining.htm`
- `platforms-and-software.htm`

### Active deep page (linked from `publications.htm`)
- `randomrhs_2013.htm`

### Other root files kept
- `cv.pdf` — current CV (linked from `index.html`)
- `Tool.mp3` — audio used inline in `index.html`
- `favicon.ico` — root-level fallback; canonical favicon is `img/favicon.ico`
- `MIGRATION_NOTES.md` — this file
- `NEW_IDEAS_x2.txt` — flagged: your personal notes scratchpad. Not referenced
  from any page; safe to delete if it doesn't belong in a public repo.
- `googled7532331f56ef891.html` — empty Google Search Console verifier. Keep if
  you want to re-verify the new site with GSC, otherwise delete.

### Asset folders kept
- `img/` — all referenced images plus the canonical favicon
- `docs/` — preprint PDFs and a couple of dataset files
- `SIP_Instances/` — `.zip` test sets linked from `randomrhs_2013.htm`
- `software/` — open-source code zips linked from `platforms-and-software.htm`

---

## 2. Conversion edits (Phase 1)

### 2.1 Renamed
- `index.htm` → `index.html` (required for GitHub Pages directory index)

### 2.2 Internal navigation
- Every `href="index.htm"` and `href="index.htm#anchor"` → `href="index.html"`
  across all pages.

### 2.3 Favicon
- `href="https://users.wpi.edu/~atrapp/favicon.ico"` → `href="img/favicon.ico"`
  everywhere it appeared.
- Added a new favicon `<link>` to `joining.htm` (it had none).

### 2.4 CV link
- `href="https://users.wpi.edu/~atrapp/cv.pdf"` and the `http://` variant →
  `href="cv.pdf"` everywhere.

### 2.5 Preprint / docs PDFs
- `href="http://users.wpi.edu/~atrapp/docs/<file>.pdf"` → `href="docs/<file>.pdf"`
  everywhere. All referenced PDFs exist locally.

### 2.6 RANDOMRHS-2013 link
- `href="http://users.wpi.edu/~atrapp/randomrhs_2013.htm"` → `href="randomrhs_2013.htm"`
  in `publications.htm`.

### 2.7 Social-preview meta tags in `index.html`
- `og:image` and `og:url` updated from `http://users.wpi.edu/~atrapp/...` to
  `https://andrewctrapp.github.io/...` (active value plus the commented-out
  alternates). Cite-format URL comment also updated.

### 2.8 Misc bug fixes
- `index.html`: `href="refugees.ai"` → `href="https://refugees.ai"` (missing
  protocol meant the browser treated it as a relative path).
- `index.html`: removed dead `<link rel="stylesheet" href="style.css">` — the
  file never existed in the source; page is fully styled by Bootstrap CDN.

---

## 3. Cleanup pass (Phase 2)

Removed to slim the repo from **1.1 GB → 562 MB**:

| Bucket | Items removed |
|---|---|
| Backup `.zip` files at root | `img.zip` (84 MB), `docs.zip` (52 MB), `SIP_Instances.zip` (372 MB), `software.zip`, `Pics.zip`, `css.zip`, `js.zip`, `file_drop.zip` |
| Old CV snapshots | ~47 dated `cv_*.pdf` files (current `cv.pdf` kept) |
| Windows "Copy" duplicates | `joining - Copy.htm`, `img/IMG_3292 - Copy.JPG`, `img/IMG_3293 - Copy.JPG`, `img/IMG_3295 - Copy.JPG` |
| Root files duplicating folder versions | `Dynamic_Annie_4.png` (=img/), `Identifying_Fixations_*.pdf` (=docs/) |
| Unreferenced root media | `1127WPIAsylumTool.wav` |
| Unreferenced folders | `Pics/` (old window/ladder photos), `filedrop/` (empty) |
| 2019 legacy snapshot pages | `index_2019_11_20.htm`, `publications_2019_11_20.htm`, `students_2019_11_20.htm`, `teaching_2019_11_20.htm`, `tools-and-software_2019_11_20.htm` — all contained pre-existing broken refs and were not in any active navigation |
| Retired `x_`-prefixed pages | `x_students.htm`, `x_teaching.htm`, `x_tools-and-software.htm` — not in any active navigation |
| Orphaned framework folders | `css/`, `js/` — only referenced by the deleted 2019 legacy pages; active pages use Bootstrap from a CDN |
| Orphan dataset page | `randomrhs_2012.htm` — not linked from anywhere, and every `SIP_Instances/TPS_*.zip` it referenced never existed in the repo |

---

## 4. Final integrity check

Ran across all 6 active pages (`index.html`, `publications.htm`, `team.htm`,
`joining.htm`, `platforms-and-software.htm`, `randomrhs_2013.htm`):

- All local PDF references resolve. (0 missing)
- All local HTML page references resolve. (0 missing)
- All local image references resolve. (0 missing)
- All 5 navbar pages have `<link rel="icon" href="img/favicon.ico" />`.
- Only "missing" hit is `Favicon_Image_Location` — a placeholder inside an HTML
  comment in `index.html`, not an active reference. Harmless.

---

## 5. Things you may still want to do

1. **Decide on `NEW_IDEAS_x2.txt`** — your personal notes. Probably should not
   be in a public repo. Delete unless you want it visible.
2. **Decide on `googled7532331f56ef891.html`** — re-verify the new site with
   Google Search Console, or delete.
3. **Update Google Analytics** if you want to move from UA-148275737-1 to GA4.
4. **Custom domain** (later, optional) — buy a domain, add a `CNAME` file at the
   repo root containing the domain, configure DNS per GitHub's guide.
