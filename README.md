# cv_web: personal academic page

Static personal page for PhD applications. No build step, no dependencies. The
only JavaScript is a short inline block at the bottom of `index.html`, purely
progressive enhancement: it opens a collapsed project when an in-page link
points at it, and expands every project before printing.

```
index.html      all content, edit this
style.css       all styling (always light background, print aware)
assets/photo.jpg
assets/kathryn-tcad.pdf   the TCAD manuscript, linked from the Kathryn project
.nojekyll       tells GitHub Pages to serve the files as-is
```

## Preview locally

```bash
python3 -m http.server 8000     # then open http://localhost:8000
```

## Deploy to GitHub Pages

1. Create a repo named `Tanawin1701d.github.io` (user site, served at
   `https://tanawin1701d.github.io`), or any repo if a project URL is fine.
2. Push these files to the default branch.
3. Repo → Settings → Pages → Source: *Deploy from a branch*, branch `main`, folder `/ (root)`.

For a custom domain, add a `CNAME` file containing the domain and point a DNS
record at GitHub Pages.

## Updating

- **CV**: no CV is published. To add one, drop a PDF in `assets/` and link it
  from the contact block in `index.html`. Use a general CV, not one addressed
  to a single institution.
- **New project**: copy an existing `<details class="project">` block in `index.html`.
  The `<summary>` holds the title and the one-line `.brief` shown while collapsed;
  everything after it (links, status badge, bullets) appears when expanded. Add
  `open` to the `<details>` tag to have a project start expanded.
- **Date**: the footer line at the bottom of `index.html`.
