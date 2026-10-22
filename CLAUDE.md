# CLAUDE.md

Personal website for Kurt Hamblin. Repo: `kurt-hamblin/kurt-hamblin.github.io`, served by GitHub Pages. Custom domain: www.kurthamblin.com.

## Goal

Build a small, hand-built Jekyll site from scratch, replacing an older site that used the Hydejack theme. The site should feel like a person wrote it: plain, quiet, easy to read. Reference for layout and tone: https://www.alexlford.com/about (a single column of writing, text-only nav, simple lists, inline photos).

## Stack

- Plain Jekyll, built natively by GitHub Pages. No theme gem.
- One stylesheet: `assets/css/style.css`. Plain CSS, no Sass, no frameworks (no Tailwind, Bootstrap, etc.).
- No JavaScript unless a feature truly needs it. No webpack, no npm, no service worker.
- Only use plugins that GitHub Pages supports out of the box (`jekyll-seo-tag`, `jekyll-sitemap` are fine).
- Layouts: `default.html` (shell with header, nav, footer) and `page.html`. Add more only if needed.

## Site structure

Text-only top nav, in this order:

- **About** (`/`): photo, a few paragraphs in Kurt's voice, current role, contact links.
- **Research** (`/research/`): PhD work at the University of Kansas, written in past tense. Short sections for each project with a link to the paper or repo.
- **Projects** (`/projects/`): personal and code projects. One heading per project, one to three sentences, a link.
- **Personal** (`/personal/`): hobbies and interests as short prose and simple lists, with inline photos.
- **CV**: direct link to the PDF.

Footer: name, email, GitHub, LinkedIn as plain text links. Current year only.

## Design rules

- Light background only. No dark mode, no theme toggle.
- Background: a warm off-white (around `#fbfaf7`). Text: dark gray (around `#222`), not pure black. One muted accent color for links (a dull blue or slate). Visited links can be slightly darker.
- Font: low key and easy to read. Use a system serif stack so nothing loads from the web:
  `font-family: Charter, "Bitstream Charter", "Sitka Text", Cambria, Georgia, serif;`
  Same stack for headings, just bolder. Monospace only for code.
- Body text around 18px, line height around 1.6.
- Single centered column, max width around 40rem (roughly 65 to 75 characters per line). Generous margins.
- Headings plain: no underlines, borders, or icons. Modest size differences.
- Images: full column width or smaller, with a little vertical space around them. Rounded corners at most a couple of pixels, or none.
- Must work on a phone with no horizontal scrolling.

Do not add:

- Hero banners, gradients, cards, grid layouts, shadows, or animations
- Icons or emoji in headings or nav
- "Skills" bars, tag clouds, stats widgets, or GitHub badges
- Stock phrases like "passionate about," "welcome to my corner of the internet," or "let's connect"

## Writing rules

These apply to any text written for the site, and to commit messages.

- No em dashes or en dashes. Use commas, periods, colons, or parentheses.
- Plain language over jargon. Short sentences.
- Past tense for completed work (the PhD is done).
- No overclaiming. Describe what the work did, not how impressive it is.
- Do not invent content. If a fact, date, link, or description is missing, leave a clearly marked `TODO:` and ask Kurt rather than guessing.

## Known facts (confirm before publishing)

- GitHub: https://github.com/kurt-hamblin
- LinkedIn: https://www.linkedin.com/in/kurt-hamblin
- PhD in Physics, University of Kansas. Advisor: Dr. Allison Kirkpatrick.
- B.S. in Physics, UMBC, 2019.
- NASA FINNEST Fellow.
- Research: AGN identification and photometric redshifts with JWST and Chandra data. Projects include AGNBoost (https://github.com/kurt-hamblin/AGNBoost), a Chandra ACIS Extract pipeline for the MEGA survey, and an SED fitting framework.
- Current role and how to describe it: TODO, ask Kurt.
- Contact email: TODO, ask Kurt (the old ku.edu address is likely outdated).

## Files from the old site

The old site lives in a separate repo (`hamblin-ku.github.io`, now under the kurt-hamblin account). Ask Kurt for its local path if you need it. Copy only these into this repo, and nothing from the Hydejack theme:

- `KurtHamblin_CV.pdf`, `KurtHamblin_Resume.pdf` (put in `files/` or the repo root; keep links working)
- Photos still in use, such as the rabbit photos in `assets/img/`
- The Google site verification HTML file
- Text from `index.md`, `research.md`, `projects.md`, and `materials.md` as source material only, rewritten to the rules above

## Custom domain

Do not add a `CNAME` file or set the custom domain until Kurt says the site is ready. Before that happens, Kurt needs to remove the custom domain from the old repo's Pages settings, since GitHub only allows one repo per domain. Then add `CNAME` containing `www.kurthamblin.com` and turn on "Enforce HTTPS" in Pages settings.

## Checking work

- Run `bundle exec jekyll serve` and check every page locally before committing.
- Check pages at phone width.
- Confirm all links work, including the CV PDF.
- Confirm no em or en dashes in any page: search for `—` and `–`.
