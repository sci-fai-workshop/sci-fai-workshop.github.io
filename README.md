# Sci-fAI: Science for Artificial Intelligence

Workshop website for **Sci-fAI: Science for Artificial Intelligence** — proposed NeurIPS 2026 workshop.

Live URL (once deployed): sci-fai-workshop.github.io


## Structure

```
webpage/
├── index.html          # single-page site (sections: Overview, Speakers, Schedule, CfP, Dates, Organizers, Contact)
├── css/style.css       # all styles (Inter + Source Serif Pro from Google Fonts; Bootstrap 4 navbar only)
├── imgs/               # headshots for speakers & organizers
└── README.md           # this file
```

No build step. Plain static HTML/CSS.

## Local preview

```bash
cd webpage
python3 -m http.server 8765
# open http://localhost:8765
```

## Editing content

All content lives in `index.html` and is organized by `<section>` blocks with matching anchor IDs
(`#overview`, `#speakers`, `#schedule`, `#call`, `#dates`, `#organizers`, `#contact`).

### Add or update a speaker / organizer

Each person is a `.person` div:

```html
<div class="person">
    <a href="HOMEPAGE_URL" target="_blank">
        <img src="imgs/FILENAME.jpg" alt="NAME" />
    </a>
    <h5><a href="HOMEPAGE_URL" target="_blank">NAME</a></h5>
    <div class="affil">AFFILIATION</div>
    <div class="role">ROLE</div>   <!-- organizers only; omit for speakers -->
</div>
```

Photo files live in `imgs/`. They are CSS-cropped to a 130×130 circle, so square sources work best.

### Update dates

Edit the `.important-dates-list` block in `#dates`. Each row is a `.date-item` with
`.date-event` and `.date-value` spans. Use `<span class="date-note">(AoE)</span>` for sublabels.

### Update schedule

Edit rows in the `<table class="schedule-table">` block in `#schedule`.

### Topics / Call for Papers

Each topic tile is a `.contrib-category` block under the `#call` section. Color is set by a class
on the inner `h3` (`t-math`, `t-phys`, `t-cogsci`, `t-neuro`, `t-mi`, `t-pos`).

## Photo credits

| Person | Source |
|---|---|
| Max Welling | amlab.science.uva.nl |
| Andrew Saxe | saxelab.org |
| Eric Schulz | hcai-munich.com |
| Kenji Doya | OIST faculty page |
| Shirley Ho | Simons Foundation |
| Anima Anandkumar | Wikimedia Commons |
| Jaedong Hwang | jd730.github.io |
| Jea Kwon | jeakwon.github.io |
| Dongqi Han | Microsoft Research |
| Li Kevin Wenliang | LinkedIn |
| Rosanne Liu | rosanneliu.com |
| Peter Dayan | Wikimedia Commons |
| SueYeon Chung | personal site |

Replace any of these in `imgs/` if you have higher-resolution lab-supplied versions.

## Deploy to GitHub Pages

1. Create a repo named `scifai26.github.io` (or any name and use Pages).
2. From this directory:
   ```bash
   git init
   git add .
   git commit -m "Initial workshop website"
   git branch -M main
   git remote add origin git@github.com:scifai26/scifai26.github.io.git
   git push -u origin main
   ```
3. In repo **Settings → Pages**, set Source to `main` branch, root.

## Notes

- Important dates are aligned with the [NeurIPS 2026 calendar](https://neurips.cc/Conferences/2026/Dates).
  Workshop submission deadlines beyond the NeurIPS-mandated ones are tentative and should be confirmed
  once the proposal is accepted.
- Contact email: `scifai26@gmail.com` — make sure this address is registered before launch.
- The proposal source lives in the parent directory (`Science4AI.tex`).
