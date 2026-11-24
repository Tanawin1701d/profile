# profile: personal academic page

Static personal page for PhD applications. No build step, no dependencies. The
only JavaScript is a short inline block at the bottom of `index.html`, purely
progressive enhancement: it opens a collapsed project when an in-page link
points at it, and expands every project before printing.

```
index.html      all content, edit this
style.css       all styling (pale yellow light theme + dark theme, print aware)
assets/photo.jpg
assets/cv_tanawin_devaveja.pdf   the CV, linked from the sidebar
assets/kathryn-tcad.pdf   the TCAD review manuscript, no longer linked (the paper is linked by DOI)
.nojekyll       tells GitHub Pages to serve the files as-is
```

## Preview locally

```bash
python3 -m http.server 8000     # then open http://localhost:8000
```

## Deploy to GitHub Pages

Live at <https://tanawin1701d.github.io/profile/>, served from the public repo
`Tanawin1701d/profile`, branch `master`, folder `/ (root)`. A push to `master`
rebuilds the site within a minute or so.

Settings → Pages holds that configuration if it ever needs changing. For a
custom domain, add a `CNAME` file containing the domain and point a DNS record
at GitHub Pages.

The repo is public, which GitHub Pages requires on a free account. Anything
committed here is world-readable, including the whole git history, so do not
commit a file you would not publish.

## Updating

- **CV**: `assets/cv_tanawin_devaveja.pdf`, linked first in the sidebar. Build it
  from `phdApp/cv/cv_tanawin.tex` with the phone number replaced by a
  black box, `\colorbox{black}{\texttt{\phantom{...}}}` (the box has no digits
  under it, so the number stays off this public repo), and copy the PDF over this file. Use a
  general CV, not one addressed to a single institution.
- **New project**: copy an existing `<details class="project">` block in `index.html`.
  The `<summary>` holds the title and the one-line `.brief` shown while collapsed;
  everything after it (links, status badge, bullets) appears when expanded. Add
  `open` to the `<details>` tag to have a project start expanded.
- **Date**: the footer line at the bottom of `index.html`.
- **CSS changes**: bump the `?v=` date on the `style.css` link in `index.html`,
  or browsers keep showing the cached old stylesheet. Same for `photo.jpg`.
