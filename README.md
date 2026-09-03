# Callnovo Contact Center Blog

Live at: **[https://callnovo-cc.github.io/blog/](https://callnovo-cc.github.io/blog/)**

Editorial publication covering customer support outsourcing, BPO delivery, AI-powered customer support, multilingual operations, compliance, ecommerce support, and contact center operations. Published by [Callnovo Contact Center](https://callnovo.ai/).

## Repository role

This repository, `callnovo-cc/blog`, is the Jekyll GitHub Pages project site for the Callnovo Contact Center Blog. It publishes to:

```text
https://callnovo-cc.github.io/blog/
```

The companion repository, `callnovo-cc/callnovo-cc.github.io`, is the minimal user-site repository at the parent domain root. It serves the root redirect and root-level technical files such as `robots.txt` and `sitemap.xml`.

Do **not** publish blog articles, layouts, assets, or category content in the companion user-site repository. All Callnovo Blog content belongs here.

## What this site does

The blog is the durable, first-published canonical editorial destination for Callnovo Contact Center content. It supports:

- Buyer-side analysis of customer service outsourcing, BPO pricing, AI customer support, multilingual CX, data security, ecommerce support, and contact center operations.
- Long-form Jekyll Markdown posts with canonical URLs.
- Article, BreadcrumbList, and optional FAQPage structured data.
- Person-author support, author parity controls, and commercial-context disclosure.
- A homepage with a featured article, latest-article feed, raw-topic chips, and curated editorial pathways.
- A category system with seven curated decision hubs and an auto-generated raw-topic index.
- Editorial Standards, About, and custom 404 recovery pages.
- Canonical, Open Graph, Twitter Card, sitemap, RSS feed, and redirect support.

## Repository structure

```text
_config.yml                ← Site configuration, plugins, identity, and global defaults
_posts/                    ← Published articles: YYYY-MM-DD-slug.md
_layouts/
  default.html             ← Shared document head, metadata, site chrome, and structured-data controls
  home.html                ← Homepage featured article, latest feed, and curated decision pathways
  post.html                ← Single-post layout, visible topic chips, CTA, and related articles
  category.html            ← Future-ready individual category archive layout
assets/
  css/style.css            ← Site styles
  images/                  ← WebP visual assets
about.html                 ← /about/ publication identity and disclosure page
categories.html            ← /categories/ curated decision hubs plus auto-generated raw-topic index
editorial-standards.html   ← /editorial-standards/ methodology, disclosure, and update policy
404.html                   ← Custom not-found recovery page
index.html                 ← Homepage metadata and home-layout assignment
README.md                  ← This repository guide
```

## Site architecture

### Homepage

`index.html` supplies homepage-specific metadata. `_layouts/home.html` renders:

- The newest post as the featured article.
- A latest-articles feed that excludes the featured post.
- Raw category chips linked to stable `#topic-…` anchors on `/categories/`.
- Seven curated decision pathways that link to the matching editorial hub anchors.

### Posts

Each post uses `_layouts/post.html`, which renders:

- Publication and update dates.
- Visible category chips.
- Front-matter title as the H1.
- Article description as the visible deck.
- The post body.
- Callnovo CTA and publication note.
- Related articles where available.

### Categories

`categories.html` is the primary category-discovery page. It contains two complementary systems:

1. **Curated decision hubs** for broader buyer questions:
   - AI-Powered Customer Support
   - Customer Service Outsourcing
   - BPO Pricing and Commercial Models
   - Compliance, Security, and Governance
   - Multilingual Customer Support
   - Ecommerce and Amazon Customer Support
   - Contact Center Operations

2. **All Topics**, an auto-generated index based on raw front-matter categories.

Raw category chips use this stable target pattern:

```liquid
{{ '/categories/' | relative_url }}#topic-{{ category | slugify }}
```

Curated homepage and recovery links use explicit hub anchors, such as:

```text
/categories/#ai-powered-customer-support
/categories/#customer-service-outsourcing
/categories/#compliance-security-and-governance
```

Do not treat raw category anchors and curated hub anchors as interchangeable. They serve different discovery purposes.

## Writing a new article

### 1. Create the post file

Create a new file in `_posts/`:

```text
_posts/YYYY-MM-DD-your-slug.md
```

Example:

```text
_posts/2026-09-03-ai-customer-support-governance.md
```

The date and slug must match the intended canonical URL:

```text
https://callnovo-cc.github.io/blog/YYYY/MM/DD/your-slug/
```

### 2. Use the active Article Draft Template

The repository README is a technical guide, not the full publishing specification. Before drafting or adapting a post, use the current:

```text
Callnovo Contact Center - GitHub Pages - Article Draft Template
```

The active template governs author controls, category selection, Article/FAQ structured data, images, citations, delivery preview, and pre-commit verification.

### 3. Add complete front matter

Use this as the baseline:

```yaml
---
title: "Primary keyword — reader-facing promise"
description: "One sentence of approximately 140–160 characters that answers the search intent and includes the primary keyword naturally."
slug: "post-slug-lowercase-hyphenated"
date: YYYY-MM-DD
last_modified_at: YYYY-MM-DD

# REQUIRED: Select 3–5 controlled categories.
# Categories drive visible topic chips, /categories/ placement,
# curated-hub eligibility, breadcrumb topic links, and internal discovery.
# Never use generic publishing labels such as insights, blog, general, or news.
categories:
  - primary-topic
  - supporting-topic
  - supporting-topic
  - optional-supporting-topic
  - optional-supporting-topic

# OPTIONAL: Use 3–6 granular article-specific concepts.
# Tags are SEO descriptors, not site-navigation categories.
tags:
  - primary-tag
  - secondary-tag
  - tertiary-tag

author:
  name: "Vince Lupe"
  role: "Marketing Specialist, Callnovo Contact Center"
  url: "https://www.linkedin.com/in/vince-lupe/"
  same_as:
    - "https://www.linkedin.com/in/vince-lupe/"

reviewed_by:
  name: "Reviewer Name"
  role: "Reviewer Title, Callnovo Contact Center"
  url: "https://www.linkedin.com/in/reviewer-handle/"

image: /assets/images/post-slug-hero.webp
image_alt: "Descriptive alt text, 125 characters or fewer."
image_caption: "Hero caption."
image_credit: "Illustration: Callnovo"

canonical_url: "https://callnovo-cc.github.io/blog/YYYY/MM/DD/post-slug/"
redirect_from:
  - /blog/YYYY/MM/DD/post-slug/

faq: true
breadcrumbs: true
article_type: "Article"
reading_time_minutes: 8
word_count: 1650
excerpt_separator: "<!--more-->"
twitter_creator: "@callnovocc"
sponsored: false
ai_assisted: true
disclaimer: "informational"
---
```

Delete the entire `reviewed_by` block when no reviewer is provided. Do not leave placeholders in published files.

## Category governance

Categories are site-navigation architecture. Tags are granular topic descriptors.

### Controlled category vocabulary

**Core service and operating topics**

```text
ai
automation
bpo
contact-center
customer-support
outsourcing
```

**Commercial, buyer, and governance topics**

```text
compliance
data-security
pricing
vendor-evaluation
```

**Industry, audience, and market topics**

```text
amazon
ecommerce
multilingual
saas
small-business
```

### Category rules

- Select **3–5** lowercase, hyphenated categories.
- Select one primary topic and two to four genuinely relevant supporting categories.
- Every category must create a useful reader-discovery path.
- Use the controlled vocabulary exactly as written.
- Do not create synonyms, plural variations, or unreviewed new categories when an approved category fits.
- Do not use generic labels such as `insights`, `blog`, `general`, or `news`.
- A new category is allowed only for a durable new topic cluster; it must later be reviewed before it becomes part of a curated hub.

### Category examples

```text
AI customer-support operating model:
ai, automation, customer-support, contact-center

AI customer-support outsourcing governance:
ai, outsourcing, bpo, compliance, customer-support

BPO compliance and data-security checklist:
bpo, compliance, data-security, customer-support

BPO pricing article:
bpo, pricing, outsourcing, customer-support

Amazon seller customer support:
ecommerce, amazon, outsourcing, customer-support

Multilingual customer support:
ai, multilingual, customer-support, contact-center

SaaS support outsourcing:
saas, outsourcing, customer-support, bpo

Customer-service outsourcing transition:
outsourcing, bpo, customer-support, contact-center
```

## Author and schema controls

Unless a documented exception is separately approved, posts must use:

```yaml
author:
  name: "Vince Lupe"
  role: "Marketing Specialist, Callnovo Contact Center"
  url: "https://www.linkedin.com/in/vince-lupe/"
  same_as:
    - "https://www.linkedin.com/in/vince-lupe/"
```

The same author identity must match across:

- YAML front matter.
- Manually authored Article JSON-LD.
- Any visible author attribution.
- Any other page-level metadata field that identifies the author.

Do not use internal drafting identities, placeholders, unapproved role variants, or blank author URLs in published content.

## Structured data

`_layouts/default.html` provides shared metadata and structured-data controls. Post-level Article JSON-LD belongs immediately after the closing YAML fence and before visible article content.

Every Article schema must reflect the visible page, including:

- Exact title/headline.
- Accurate description.
- Canonical image URL.
- `datePublished` and `dateModified`.
- Canonical WebPage `@id`.
- Matching Person author identity.
- Callnovo Contact Center publisher identity.

Include FAQPage JSON-LD only when the visible article contains a matching FAQ section.

Do not publish malformed JSON-LD. After structured-data changes, validate the live page through Google Rich Results Test or Schema Markup Validator.

## Images and media

### File standards

- Use **WebP** by default.
- Use PNG or JPEG only where a specific exception is documented.
- Maximum source width: 1600px.
- Preferred hero dimensions: 1200×630.
- File size target: under 200 KB where practical.
- Use lowercase, hyphenated filenames.
- Do not use double extensions.

Examples:

```text
post-slug-hero.webp
post-slug-figure-01.webp
```

### Hero image requirements

Hero markup must retain:

```html
.article-hero
loading="eager"
fetchpriority="high"
width="1200"
height="630"
```

Hero alt text must be descriptive and 125 characters or fewer. Include the primary keyword only where natural.

### Inline figure requirements

Every inline figure must include:

- Descriptive alt text.
- An italic caption where planned.
- `loading="lazy"`.
- Verified intrinsic width and height.
- A GitHub Pages-ready asset path.

### Asset verification

Before an asset is used in a post, it must be Vince Lupe-verified and have its intended GitHub Pages permalink established in the source planning record. Do not treat an unverified or not-yet-uploaded asset as publish-ready.

### Compression example

ImageMagick example:

```bash
convert input.png -resize 1600x -quality 82 output.webp
```

## Markdown and content rules

- The front-matter title supplies the H1. Start visible article content at H2.
- Use H2 for primary sections and H3 only beneath an H2. Do not skip heading levels.
- Keep the approved draft’s facts, citations, cross-links, buyer stage, keyword angle, and CTA intact during adaptation.
- Use descriptive anchor text. Never use “click here,” “learn more,” or bare URLs as anchor text.
- Include tables, lists, figures, and checklists only where the source draft calls for a comparison, framework, sequence, criteria, or decision aid.
- Do not add boilerplate merely to fill a section.

## Links and citations

- Execute the approved cross-link plan from the Unified Article Brief Template.
- Link to Callnovo services or products only where relevant to the reader and approved in the source draft.
- Link to sibling GitHub Pages posts only after their canonical URLs are confirmed live.
- Keep factual claims, quotations, statistics, and third-party attribution connected to genuine clickable source URLs.
- Every in-text citation must have an alphabetized APA 7th-edition References entry.
- Every References entry must appear in the body and be a genuine clickable hyperlink.
- Apply `target="_blank"` only when deliberate new-tab behavior is appropriate.
- Every deliberate `target="_blank"` link must include `rel="noopener"`.

## Local preview

Install dependencies and serve the project locally:

```bash
gem install bundler
bundle install
bundle exec jekyll serve
```

Then open:

```text
http://localhost:4000/blog/
```

Local preview is useful for Markdown, Liquid, page hierarchy, image paths, and layout checks. It does not replace live GitHub Pages verification.

## Publishing workflow

1. Re-read the approved Combined Draft Template directly before adaptation.
2. Create the post in `_posts/YYYY-MM-DD-slug.md`.
3. Complete every front-matter field and remove unused optional blocks.
4. Add Article JSON-LD and matching FAQPage JSON-LD where applicable.
5. Verify image paths, image attributes, citations, references, links, and category selection.
6. Commit and push:

   ```bash
   git add .
   git commit -m "post: descriptive title"
   git push
   ```

7. Wait for GitHub Pages to complete its build.
8. Fetch the live URL directly. A successful commit is not proof of successful publication.
9. Confirm the live title, meta description, canonical URL, H1, image sources, internal links, and structured data.
10. Use the confirmed GitHub Pages canonical URL in downstream publication formats.

## Publish verification checklist

After every production commit:

1. Confirm GitHub Pages build completion and absence of Liquid or Jekyll errors.
2. Fetch the live page directly, preferably in a private/incognito browser window as a cache check.
3. Verify:
   - Rendered title and meta description.
   - Canonical URL.
   - Visible H1 and heading hierarchy.
   - Open Graph and Twitter metadata where relevant.
   - Article, FAQPage, and BreadcrumbList JSON-LD where applicable.
   - Hero and inline image sources, alt text, and dimensions.
   - Internal article links and category links.
4. Confirm category chips resolve to the raw-topic pattern:

   ```text
   /categories/#topic-category-name
   ```

5. Confirm editorial pathway links resolve to the appropriate curated hub anchor.
6. Run Rich Results Test or Schema Markup Validator when structured data changed.
7. Do not mark downstream assets ready until the canonical GitHub Pages URL is live and verified.

## What is already in place

- **SEO metadata** — canonical, Open Graph, Twitter Card, and global identity metadata are handled through site configuration and the shared default layout.
- **Structured data** — shared layout controls support Article, BreadcrumbList, and opt-in FAQPage JSON-LD, plus Person-author and canonical-reference patterns.
- **Sitemap** — Jekyll sitemap output is generated during GitHub Pages builds; root fallback is maintained by the companion user-site repository.
- **RSS feed** — Jekyll feed output is available at `/feed.xml`.
- **Redirect support** — `jekyll-redirect-from` supports migration through `redirect_from:` front matter.
- **Editorial standards** — `/editorial-standards/` documents methodology, sourcing, commercial disclosure, updates, and corrections.
- **About page** — `/about/` describes publication scope, publisher relationship, and proper use of editorial content.
- **Category directory** — `/categories/` provides curated decision hubs and an auto-generated raw-topic index.
- **404 recovery** — `/404.html` provides homepage, category, topic, contact, and recent-article recovery paths.

## Governance

Every article discussing services, technologies, or operating models connected to Callnovo’s work must disclose the relationship clearly.

AI-assisted tools may support research, outlining, drafting, and editing. Editorial responsibility remains with the named author and reviewer where applicable.

Use the [Editorial Standards](https://callnovo-cc.github.io/blog/editorial-standards/) page as the public policy reference for sourcing, corrections, commercial context, and editorial methodology.
