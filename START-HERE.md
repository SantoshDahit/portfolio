# Portfolio — Santosh Dahit

Backend engineer portfolio. Two pages, English and Korean, with an in-page
language toggle. No build step, no dependencies.

```
index.html            English portfolio (site root)
portfolio-kr.html     Korean portfolio
santosh-photo.jpg     Photo used in the About section
santosh-avatar.png    Team avatar from kayple.com/about
```

The language toggle lives in the header of each page: `🇰🇷 한국어` on the English
page links to `portfolio-kr.html`, `🇺🇸 English` links back to `index.html`.

---

## Run it locally

Open `index.html` in a browser, or serve the folder:

```bash
python3 -m http.server 8000    # then visit http://localhost:8000
```

A local server is worth using — the pages load Google Fonts over the network,
and `file://` URLs behave differently for some browser features.

---

## Deploy

The site is live on GitHub Pages, served from `main`:

**https://santoshdahit.github.io/portfolio/**

Pushing to `main` redeploys it — usually live within a minute:

```bash
git add -A
git commit -m "Update portfolio"
git push origin main
```

---

## Editing

Both pages are self-contained: all CSS sits in a `<style>` block in `<head>`,
all JS in one `<script>` before `</body>`.

**Keep the two languages in sync.** Any structural change to one page needs the
same change in the other — the design, class names, and section order are
identical by design.

### Design tokens

Colours and fonts are CSS custom properties in `:root`, so a palette change is
a handful of edits at the top of the file:

```css
--bg:     #111111;   /* page background   */
--accent: #7af298;   /* mint accent       */
--ink:    #ffffff;   /* headings          */
--muted:  #b5b5b5;   /* body copy         */
--line:   #3a3b3c;   /* borders           */
```

Type is **Space Grotesk** for display and **Fragment Mono** for the `// section`
eyebrows, tags, and numbers. The Korean page adds **Noto Sans KR** as a fallback
for Hangul.

### Sections

`Hero → Skills → About → Projects → Services → Process → Experience → Contact`

Section IDs match the nav links (`#skills`, `#about`, `#projects`, `#services`,
`#experience`, `#contact`).

### Projects

Project data came from Kayple's portfolio API (`api.homepage.kayple.com/projects`).
Every store and website link on a project card was checked to return HTTP 200 —
if you add one, verify it resolves before committing.

---

## Contact details to update

Search for these if any of them change:

- `santoshdahit454@gmail.com`
- `linkedin.com/in/santosh-dahit`
- `github.com/SantoshDahit`
