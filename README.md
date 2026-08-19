# Callnovo Contact Center Blog

Live at: **[https://callnovo-cc.github.io/blog/](https://callnovo-cc.github.io/blog/)**

Editorial publication covering outsourced customer support, BPO, AI-powered CX, multilingual operations, and contact center economics. Published by [Callnovo Contact Center](https://callnovo.ai/).

## Repository role

This repo (`callnovo-cc/blog`) is a Jekyll project site. It publishes to `/blog/` on the `callnovo-cc.github.io` domain.

Companion repo: `callnovo-cc/callnovo-cc.github.io` — a minimal user-site repo that serves `/robots.txt`, `/sitemap.xml`, and a root redirect at the parent domain root. Do **not** put content there.

## Writing a new article

1. Create `_posts/YYYY-MM-DD-your-slug.md`.
2. Add front matter — the canonical fields the theme + schema honor:

   ```yaml
   ---
   title: "Primary keyword — reader-facing promise"
   description: "One sentence, 140–160 chars, contains primary keyword and states the answer/benefit."
   date: 2026-08-17
   last_modified_at: 2026-08-17
   categories: [insights]              # one of: insights, case-studies, operations, technology
   tags: [tag-1, tag-2, tag-3]         # 3–6, lowercase-hyphenated
   image: /assets/images/article-NN-slug-hero.webp
   image_alt: "Descriptive alt text, ≤ 125 chars."
   author:                             # emits Person JSON-LD instead of Organization
     name: "Vince Lupe"
     url: "https://www.linkedin.com/in/vince-lupe/"
     job_title: "Marketing Specialist"
     same_as:
       - "https://www.linkedin.com/in/vince-lupe/"
   reviewed_by:                        # optional
     name: "Reviewer Name"
     url: "https://..."
   faq:                                # optional — emits FAQPage JSON-LD
     - question: "Real search-query phrasing?"
       answer:   "Self-contained answer, 40–80 words."
   word_count: 1650                    # optional — populates schema.wordCount
   based_on: "https://..."             # optional — for mirrored posts, canonical elsewhere
   ---
   ```

3. Write in Markdown below the front matter.
4. Commit and push:

   ```bash
   git add . && git commit -m "post: your title" && git push
   ```

   GitHub Pages builds and publishes in ~60 seconds.

## Images

**Format:** WebP always. PNG and JPEG only if a specific reason.
**Max width:** 1600px. The theme scales down responsively.
**File size target:** Under 200 KB per image. Compress before commit.
**Filename convention:** `article-NN-slug-figure.webp` — lowercase, hyphenated, no double extensions.

Batch compression via ImageMagick or Pillow:

```bash
convert input.png -resize 1600x -quality 82 output.webp
```

## What's already in place

- **SEO** — `jekyll-seo-tag` emits canonical, Open Graph, Twitter Card, and Organization schema from `_config.yml`. Config includes 10 verified `sameAs` identity URLs.
- **Sitemap** — `jekyll-sitemap` builds `/sitemap.xml` on every push. Root fallback at `callnovo-cc.github.io/sitemap.xml` served by the user-site repo.
- **RSS feed** — `jekyll-feed` builds `/feed.xml`. Limited to 20 latest posts.
- **Structured data** — `_layouts/default.html` emits Article, BreadcrumbList, and (opt-in) FAQPage JSON-LD per post, with Person-author support and `isBasedOn` for mirrored content.
- **Editorial standards page** — `/editorial-standards/` documents E-E-A-T commitments.
- **Redirects** — `jekyll-redirect-from` supports permalink migration via `redirect_from:` in front matter.
- **Pagination** — 10 posts per page via `jekyll-paginate`.

## Local preview

```bash
gem install bundler
bundle install
bundle exec jekyll serve
# → http://localhost:4000/blog/
```

## Folder structure

```
_config.yml                ← site settings (updated 2026-08-19)
_posts/                    ← articles (YYYY-MM-DD-slug.md)
_layouts/                  ← page templates
  default.html               emits site chrome + Article/Breadcrumb/FAQ JSON-LD
  home.html                  homepage
  post.html                  single post
  category.html              individual category archive
assets/
  css/style.css              styling
  images/                    WebP assets under 200 KB each
about.html                 ← /about/
categories.html            ← /categories/  index of all categories
editorial-standards.html   ← /editorial-standards/  E-E-A-T page
404.html                   ← custom 404
index.html                 ← homepage stub → home layout
favicon.ico, favicon.png   ← site icons
```

## Governance

Every article that discusses services, technologies, or operating models connected to Callnovo's work discloses the relationship. AI-assisted tools are used in research, outlining, and editing; editorial responsibility remains with the named author and reviewer. See [Editorial Standards](https://callnovo-cc.github.io/blog/editorial-standards/) for the full policy.
