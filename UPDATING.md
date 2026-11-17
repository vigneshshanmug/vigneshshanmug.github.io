# Updating your website

Everything on the site is plain text files in this repository. You can edit them directly on GitHub
(open a file → pencil icon → **Commit changes**). Every commit to `main` rebuilds and republishes the
site automatically in about two minutes, check the **Actions** tab to watch it.


---

## Add a paper

1. Go to `content/publication/` and click **Add file → Create new file**.
2. Name it `your-short-slug/index.md` (lowercase words with hyphens, e.g. `il13-hodgkin-lymphoma-2027/index.md`).
   **The folder name becomes the permanent web address, never rename it after it is live.**
3. Paste and fill in:

```yaml
---
title: "Paper Title"
date: 2027-03-15
authors:
  - "Vignesh Shanmugam"
  - "Co-Author Name"
publication_types: ["journal_article"]   # or book_chapter, report, data, software, patent
publication: "Journal Name, 12(3), 45–67"
journal: "Journal Name"
doi: "10.xxxx/xxxxx"
abstract: "Paste the abstract here."
links:
  - name: "Publisher's Version"
    url: "https://doi.org/10.xxxx/xxxxx"
tags: ["spatial-genomics", "lymphoma-biology", "Hodgkin lymphoma"]
featured: true          # optional: prefer this paper in the homepage research-area lists
---
```

4. **Thumbnail:** upload an image named `featured.jpg` (or `featured.png`) into the same folder.
   Without one, the page simply shows no image. A figure from the paper works well.
   If the image is from the publisher, add `image_credit: "Figure from Journal Name"`.
5. **PDF:** upload it to `static/files/` and add a link with `url: "files/your-paper.pdf"` (no leading slash).

Every paper appears on the full Publications list automatically. To **feature** it on the Science or
Medicine page, add its folder name under a theme in `data/themes.yaml` (see below). Topic tags
(e.g. `"Hodgkin lymphoma"`, `"myeloid neoplasms"`) improve the automatic **See Also** links.

## Edit the Science and Medicine pages

- The opening paragraphs: `content/science/index.md` and `content/medicine/index.md`.
- The themes (title, summary, which papers are featured and in what order): `data/themes.yaml`.
  Add, remove or reorder themes and papers there; a paper is listed by its folder name in `content/publication/`.

## Add a presentation

Same as a paper, but in `content/talk/your-slug/index.md`:

```yaml
---
title: "Talk Title"
date: 2027-12-07
authors: ["Shanmugam V", "Co-Author A"]
publication_types: ["presentation"]
event: "67th ASH Annual Meeting & Exposition"
publication: "67th ASH Annual Meeting & Exposition"
award: "Oral presentation"     # optional; shows as a small label
tags: ["lymphoma-biology"]
---
```

## Blog (Substack)

Just publish on Substack as usual. The site's **Blog** page reads your Substack feed every time the site
rebuilds, automatically once a day, and on every commit, and lists your latest posts (title, date,
subtitle, cover image), each linking to Substack. A post's cover image and subtitle on Substack become
its thumbnail and summary here.

- Want a new post to show up immediately? GitHub → **Actions** → "Deploy Hugo site to Pages" → **Run workflow**.
- Change the Substack address or number of posts shown: `hugo.yaml` → `params.substack`.
- Optional: a post that should live on this site instead of Substack can go in
  `content/blog/<slug>/index.md` (title, date, summary, text); it is listed alongside the Substack posts.

## Edit your short and long bio

Both are in `content/_index.md`: the short bio (top of the homepage) is the `intro:` field; the long bio
("About" section) is the text below the front matter. Photos: `assets/images/hero-lab.jpg` (top) and
`assets/images/portrait.jpg` (About). Replace the files, keeping the same names.

## Edit your name, title, institutions, or email

`hugo.yaml` → `params.owner`. These feed the navbar, homepage, footer, and search-engine metadata.

## Change the menu

`hugo.yaml` → `menu.main` (currently Science · Medicine · Blog · Contact). The full Publications list is linked from the Science and Medicine pages rather than the menu.

## Rename a button or label

`i18n/en.yaml` (e.g. change "Publications" or "Download citations (BibTeX)").

## Footer credit and invisible marker

`hugo.yaml` → `params.mysite.credit` (the small "Created using GaryKing.org/mysite" line) and
`params.mysite.discovery` (hidden generator tag + search-engine metadata). Set either to `false` to remove it.

## Preview changes on your own computer (optional)

```bash
npm ci                 # once
hugo server -D         # then open http://localhost:1313/vigneshshan.github.io/
```
Search works only on the published site (or after `hugo && npx pagefind --site public`).
