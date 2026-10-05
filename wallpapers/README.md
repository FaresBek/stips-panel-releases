# STIPS wallpaper gallery

STIPS Panel 1.9.0 and newer read `catalog.json` from this folder (Settings → Appearance → Background → Gallery).
The panel downloads the catalog and the thumbnails when the gallery opens, and a full image only when it is chosen.

## Adding a wallpaper

1. Add a 1920×1200 JPEG to `full/` and a 400×250 JPEG thumbnail with the same file name to `thumbs/`.
2. Add an entry to `catalog.json`:
   - `id`: unique, lowercase, used as the file name on the panel
   - `name`: label shown in the gallery
   - `tone`: `light` or `dark` (used by the gallery filter)
   - `muted`: `true` for low-colour designs
   - `thumb`, `image`: paths relative to this folder
   - `width`, `height`, `bytes`, `sha256`: of the full image; the panel rejects a download whose size or hash differs
3. Commit to `main`. Panels see the new wallpaper the next time the gallery opens.

Landscape images are cropped to fill portrait and square (4") screens, so keep the subject near the centre.
