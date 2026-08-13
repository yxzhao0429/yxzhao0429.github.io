# AGENTS.md

## Project overview

Static academic homepage for Yu-Xiang Zhao (National Quemoy University). Pure HTML/CSS, no build system, no package manager, no tests, no CI.

## Pages

All four pages exist and are fully hand-written XHTML 1.0 Strict documents:
- `index.html` — biography (English intro, Chinese elsewhere)
- `publications.html` — journal/conference paper tables
- `courses.html` — per-semester teaching tables, oldest semester last
- `students.html` — thesis/project records by academic year

Each page repeats the same boilerplate: `<head>` (Google Fonts Inter + `style.css`), header with logo + nav + hamburger `<button class="nav-toggle">`, footer, a `<button class="scroll-top">`, and an identical inline `<script>` at the bottom of `<body>` (mobile nav toggle + scroll-to-top). Adding a nav item or changing shared markup means editing all four files.

Per-page header conventions (copy, then adjust):
- The logo is the page's own name split into `<span class="color1">…</span><span class="color2">…</span>`, linking back to the page itself.
- The active nav item gets class `current_page_item` (see `index.html:35` for placement). The About item also carries `class="first"` on every page.

## Asset directories

- `images/` — profile photos (`pic.jpg`, `pic2.jpg`, `pic3.jpg`), `favicon/`. Referenced by relative path.
- `courses/` — syllabus PDFs named `<semester>_<CODE>.pdf` (e.g. `1151_GP3.pdf`; semester = `97`…`115`, `1`/`2` term).
- `students/` — thesis/project files named `<year>-<n>[-videoM].(pdf|jpg|mp4)`.

## Conventions

- **Doctype/DOM**: XHTML 1.0 Strict (same as `index.html`). Content is Traditional Chinese; keep `charset=utf-8`. Because it's XHTML, void elements are self-closed (`<br />`) and `&` must be `&amp;`.
- **Section cards**: every section is `.section-card` (fade-in animation). Institution divider cards are bare `<h1>` inside a `.section-card` (e.g. 國立金門大學, 大華技術學院 in both `courses.html` and `students.html`).
- **Tables**: `class="mytable" cellspacing="1" cellpadding="0" border="1"` in `courses.html`; `border="0"` in `students.html`. Header row uses `<th>`. Course semester sections have `<h2 id="courseXXXX">` anchors; syllabus link text is 進度大綱 and opens `target="_blank"`.
- **students.html link text**: master's theses link out to external 論文連結 (`https://hdl.handle.net/...`); undergrad projects use local files labeled 專題成果 (pdf/jpg) and 成果展示`N` (mp4, may also be a YouTube link).
- **Self-citation**: in `publications.html`, the author's own name is marked `<span style="text-decoration: underline;">Y. X. Zhao</span>` (or `趙于翔` in Chinese-authored entries).
- **Body hook**: only `students.html` uses `<body class="page-students">`; `style.css` targets `.page-students .section-card td` to center-align table cells vertically (see `style.css:312`). The other three pages keep a plain `<body>`.
- **Inline styles**: dates and spacing use inline `style=` attributes heavily. Maintain this convention.
- **Responsive**: CSS custom properties with `--max-width: 960px`; breakpoints 768px (hamburger nav) and 480px (smaller fonts). Keep them.

## Template origin

Based on the "astroturfd" Free CSS Templates design (CC Attribution 2.5). Preserve the template comment header at the top of `style.css`.

## Verify changes

No build, tests, or linters. Open `index.html` directly in a browser or run `python -m http.server 8000` in the repo root. Deploy is manual GitHub Pages from `main` (see `README.md`).
