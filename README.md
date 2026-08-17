# Callnovo Blog — GitHub Pages Setup

## One-time setup

1. **Create a repo** named `callnovo-blog` (or any name) on GitHub — make it public.
2. Push all these files to the `main` branch.
3. Go to **Settings → Pages → Source**: select `Deploy from a branch` → branch: `main`, folder: `/ (root)`.
4. GitHub will publish to `https://yourusername.github.io/callnovo-blog/` within ~60s.
5. (Optional) Point your custom domain: add a `CNAME` file containing `callnovo.ai` and configure DNS per GitHub's docs.

## Writing a new article — 3 steps

1. Create a file in `_posts/` named: `YYYY-MM-DD-your-slug.md`
2. Add front matter at the top (copy from any existing post):
   ```yaml
   ---
   title: "Your Article Title"
   description: "One sentence for search engines and social previews."
   date: 2026-08-17
   categories: [insights]   # or: case-studies, operations, technology
   ---
   ```
3. Write the article in Markdown below the `---`.
4. `git add . && git commit -m "post: your title" && git push`
   → GitHub builds and publishes in ~60 seconds.

## SEO built in

- `jekyll-seo-tag` auto-generates `<title>`, `<meta description>`, Open Graph tags
- `jekyll-sitemap` generates `/sitemap.xml` automatically — submit to Google Search Console
- `jekyll-feed` generates `/feed.xml` for RSS readers
- Canonical URLs are set automatically
- `robots.txt` allows all crawlers and points to the sitemap

## Folder structure

```
_config.yml          ← site settings
_posts/              ← your articles (YYYY-MM-DD-slug.md)
_layouts/            ← page templates (don't touch unless customizing)
assets/css/style.css ← all styling
index.html           ← homepage (auto-lists posts)
robots.txt           ← crawler instructions
Gemfile              ← for local preview only (optional)
```

## Local preview (optional)

```bash
gem install bundler
bundle install
bundle exec jekyll serve
# → http://localhost:4000
```
