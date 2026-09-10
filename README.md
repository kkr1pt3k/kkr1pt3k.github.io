# kkr1pt3k.github.io

Personal portfolio for **Emmanuel Owusu Asante** — served at <https://kkr1pt3k.github.io>.

Plain static site: no build step, no framework. GitHub Pages serves `index.html`
directly (`.nojekyll` disables Jekyll processing).

## Structure

```
.
├── index.html              # single page
├── .nojekyll
├── assets/
│   ├── css/styles.css
│   ├── js/main.js          # nav, active-section, image lightbox
│   ├── img/                # LightCSPNet figures
│   ├── emmanuel-asante-resume.pdf   # ADD THIS
│   └── headshot.jpg                 # optional, ADD THIS
```

## Status

Email, LinkedIn, graduation year, and the résumé PDF are all filled in.
Still worth a personal pass:

- Hero + About prose — tweak to your voice (marked with `EDIT:` comments in `index.html`)
- `assets/resume/resume.html` → the "Experience" entry for iZen AI Academy needs
  a real title and dates; re-export the PDF afterwards (see below)
- Optional: add `assets/headshot.jpg` and wire it into the header

## Regenerating the résumé PDF

`assets/emmanuel-asante-resume.pdf` is produced from `assets/resume/resume.html`:

```bash
chrome --headless --disable-gpu --no-pdf-header-footer \
  --print-to-pdf=assets/emmanuel-asante-resume.pdf \
  "file://$PWD/assets/resume/resume.html"
```

(or just open `resume.html` in a browser and Print → Save as PDF)

## Local preview

```bash
python -m http.server 8000
# open http://localhost:8000
```

## Deploy

Push to `main` on `kkr1pt3k/kkr1pt3k.github.io`, then in the repo:
**Settings → Pages → Build and deployment → Source: Deploy from a branch → `main` / `root`.**
Live within a minute or two at `https://kkr1pt3k.github.io`.

## Image credits

- `assets/img/lightcspnet-*` — from
  [kkr1pt3k/LightCSPNet-Cloud-Segmentation](https://github.com/kkr1pt3k/LightCSPNet-Cloud-Segmentation) (MIT).
- `assets/img/spinal-*` — aggregate result plots (ROC, coefficient magnitudes) from the
  EAI 6010 project; contain no patient-level data.
