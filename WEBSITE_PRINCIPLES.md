# Website principles and architecture

Playbook for future (AI-assisted) maintenance. Built from the GaryKing.org/mysite instructions
(<https://gking.harvard.edu/mysite/files/ACADEMIC_SITE_PROMPT.md>), with the visual design modeled on the
owner's chosen reference site, <https://gking.harvard.edu/> (so the random "design quest" was skipped;
recorded in `hugo.yaml → params.mysite.design`).

## Stack
- **Hugo extended 0.152.2** (Hugo Blox `blox-tailwind` v0.10.0 needs ≥ 0.148.2), theme vendored in `_vendor/` (committed).
- Tailwind v4 via Blox's `css.TailwindCSS` pipeline → needs `@tailwindcss/cli`, `tailwindcss`, `@tailwindcss/typography` (package.json).
- Project styles: `assets/css/custom.css` only (tokens on `:root`). Always light mode.
- Search: **Pagefind**, built in CI after Hugo; custom modal `layouts/_partials/components/search-modal.html`
  (lazy `import()` via `relURL`, Cmd/Ctrl-K, Esc, arrow keys, Google `site:` fallback). Blox's own search is disabled.
- Deploy: `.github/workflows/deploy.yml` → GitHub Pages. `baseURL` comes from `hugo.yaml` (https), never from the Pages action.

## What Blox still provides
Only `site_head` (meta, Tailwind CSS pipeline, OG tags, canonical) and the head-end hook mechanism.
Everything visible is project-owned: `layouts/baseof.html`, navbar, footer, home, writings, detail, blog,
people, generic page, 404. Hugo Blox uses `layouts/_partials/…` (not `partials/`).

## Content model
- Each item is a bundle: `content/<section>/<slug>/index.md` (+ `featured.jpg`). **Folder name = permanent URL**
  (`permalinks` use `:contentbasename`). Never rename a live folder; use `aliases:` if one must move.
- Publications/talks share front matter: `title, date, authors, publication_types, publication, journal, doi,
  abstract, links[{name,url}], tags, featured, image_credit, award, event, author_notes`.
- `item_info.html` maps an item to its Writings tab and See-Also label (`publication_types` before section).
- **Structure (owner's choice, Nov 2026):** menu = Science · Medicine · Blog · Contact. No C.V. page and no
  People page (both removed at the owner's request, do not re-add them). Short bio = `intro:` in
  `content/_index.md` (hero); long bio = that file's body ("About" section). Full list at `/publication/`
  ("Publications"), linked from Science/Medicine but not the menu.
- **Themes:** `data/themes.yaml` → `science:` and `medicine:` lists of {id, title, summary, papers[slugs]}.
  Rendered by `_partials/themes_page.html` (via `layouts/science/single.html`, `layouts/medicine/single.html`);
  also drive the Publications "Theme" filter and See-Also siblings.

## Automation
- **See Also** (`related_finder.html`): explicit `related_*` → response/edition patterns → siblings (shared
  subcategory, +3) → scoring (+2 title token, +1 shared co-author by surname, +2 shared tag). Threshold 4,
  relaxed to 2. Max 8, title-deduped. No scripts, no generated maps.
- **Thumbnails**: `featured.*` auto-discovered (`thumb.html`, cropped TopLeft 4:3 webp).
  Initial build: real figures for 21 papers (publisher Open Graph images from Springer Nature; first figures
  from PubMed Central), generated typographic tiles (journal/meeting + year, area colour) for the rest.
- **Scholarly metadata** (`scholarly_meta.html`): `citation_*` tags + ScholarlyArticle/Chapter/CreativeWork JSON-LD.
- **Discovery** (`hooks/head-end/mysite.html`): generator meta on every page + homepage `Person` JSON-LD, gated by
  `params.mysite.discovery`. Footer credit gated by `params.mysite.credit`; rendered exactly once (footer).
- `layouts/robots.txt` (allow all, sitemap via `absURL`), `static/llms.txt`.
- **Blog = Substack feed** (`layouts/blog/list.html`): `resources.GetRemote` on `params.substack.url/feed`,
  parsed with `transform.Unmarshal`, merged with any local `content/blog/` posts, sorted by date. Cover images
  are downloaded and resized at build time (never hotlinked). A failed fetch only warns; the page still builds
  with a Substack link. The workflow has a daily `schedule` so new posts appear without a commit.
  `caches.getresource.maxAge: 1h` keeps local builds from serving a stale feed.

## Design rules (keep)
- Navbar: owner's name uppercase bold at left linking home; links right; search = bare magnifier; hamburger right on mobile.
- Hero: text left (name, title, short bio, Science / Medicine pill buttons), lab photo right; stacks photo-on-top ≤ 640px.
- Homepage below hero: About (portrait + long bio), then two cards linking to each theme.
- Science/Medicine: intro, theme chips, then per theme a summary and figure-topped paper cards.
- Publications (`/publication/`): sticky tabs (All/Articles/Books & Chapters/Presentations, only tabs with content), sidebar filters
  (search, area, years), sort, live count, BibTeX export, hash sync. All rows server-rendered; JS only filters.
- Palette: link `#2a6aa3`, primary button `#a04a02`, hero `#ecf2f8`, crimson `#a51c30` for thin accents only,
  bands `#1e1e1e`. Favicon = "VS" on crimson.
- No process/sourcing commentary on rendered pages; owner notes go in `<!-- HTML comments -->`.
- Homepage intro ≠ bio text. Don't paraphrase the owner's words; fix typos only.

## Known owner flags (HTML comments in content)
Search the repo for `OWNER:` to find every open question (draft bio, chapter dates, a CV date mismatch, etc.).
