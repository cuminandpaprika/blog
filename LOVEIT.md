# LoveIt theme reference

What the vendored [LoveIt](https://github.com/dillonzq/LoveIt) theme (`themes/LoveIt`, v0.3.1) does out of the box, so features get reused instead of reinvented. Demo site: https://hugoloveit.com/. Ground truth for everything below is the theme's own default config at `themes/LoveIt/hugo.toml` and its templates in `themes/LoveIt/layouts/`, not just the docs site (which can drift from the vendored version).

**⚠️ Config schema is nested, not flat.** LoveIt 0.3.x reads config from *nested* tables — `[params.footer]`, `[params.page.share]`, `[params.page.comment.*]`, `[params.page.seo.publisher]`, `[params.verification]`, `[params.home.profile]` / `[params.home.posts]` — unlike older LoveIt/LeaveIt versions which used flat top-level `[params]` keys (`since`, `icp`, `license`, `socialShare`, `home_paginate`, etc). A key in the wrong place is **silently ignored** — Hugo/Go templates don't error on unknown params, they just read `nil` and fall back to the theme's own default (see `themes/LoveIt/hugo.toml` for every default). This bit us once already (2026-08-02): footer copyright year, license text, and social-share on/off were all set in dead flat keys and had no effect. **When adding any new LoveIt param to `config.toml`, grep `themes/LoveIt/layouts/` for the exact key path first** rather than trusting memory or older blog posts about the theme.

## Config structure (current, as used in this repo's `config.toml`)

| Area | Key |
|---|---|
| Theme (auto/light/dark) | `params.defaultTheme` |
| Author | `params.author.{name,email,link}` |
| Header | `params.header.{desktopMode,mobileMode}`, `params.header.title.{name,logo,pre,post,typeit}` |
| Footer | `params.footer.{enable,custom,hugo,copyright,author,since,icp,license}` |
| Home profile | `params.home.profile.{enable,avatarURL,gravatarEmail,title,subtitle,typeit,social,disclaimer}` |
| Home posts list | `params.home.posts.{enable,paginate}` |
| App/PWA icons | `params.app.{title,noFavicon,svgFavicon,themeColor,iconColor,tileColor}` |
| Site SEO image (JSON-LD) | `params.seo.{image,thumbnailUrl}` |
| OG/Twitter Card image | top-level `params.images` (array) or per-page front matter `images` |
| Search-engine verification | `params.verification.{google,bing,yandex,pinterest,baidu}` |
| Analytics | `params.analytics.{google.id,google.respectDoNotTrack,fathom.id,fathom.server,plausible.dataDomain,yandexMetrica.id}` — note: this repo currently uses the legacy root-level `googleAnalytics = "G-..."` key instead, which Hugo still aliases into `Site.Config.Services.GoogleAnalytics.ID` and the theme's analytics partial falls back to that, so it works, but `params.analytics.google.id` is the current idiomatic spot |
| Social icons (home page) | `params.social.<Network> = "handle"` — up to 84 networks, see full list in `themes/LoveIt/hugo.toml` |
| Cookie consent banner | `params.cookieconsent.{enable,content.message,content.dismiss,content.link}` |
| CDN swap for vendor libs | `params.cdn.data = "jsdelivr.yml"` (or a custom yaml under `assets/data/cdn/`) |
| Compatibility shims | `params.compatibility.{polyfill,objectFit}` |
| Per-page/site-wide defaults for pages | everything under `params.page.*` below |

### `params.page.*` (defaults for every post; can be overridden per-post in front matter)

- `hiddenFromHomePage`, `hiddenFromSearch`, `twemoji`, `lightgallery`, `ruby`, `fraction`, `fontawesome`, `linkToMarkdown`, `rssFullText`
- `toc.{enable,keepStatic,auto}`
- `code.{copy,maxShownLines}`, `code.render.{goat,mermaid}`
- `math.{enable,inlineLeftDelimiter,inlineRightDelimiter,blockLeftDelimiter,blockRightDelimiter,copyTex,mhchem}` (KaTeX)
- `mapbox.{accessToken,lightStyle,darkStyle,navigation,geolocate,scale,fullscreen}`
- `share.{enable,X,Threads,Facebook,Linkedin,Whatsapp,Pinterest,Tumblr,HackerNews,Reddit,VK,Buffer,Xing,Line,Instapaper,Pocket,Flipboard,Weibo,Blogger,Baidu,Odnoklassniki,Evernote,Skype,Trello,Diaspora,Mix,Telegram}`
- `comment.enable` (master switch — nothing shows unless this is `true`), then per-system: `comment.disqus`, `comment.gitalk`, `comment.valine`, `comment.facebook`, `comment.telegram`, `comment.commento`, `comment.utterances`, `comment.giscus`, `comment.waline`
- `library.{css,js}` — inject extra CSS/JS by key name, file resolved from `assets/` or a full URL
- `seo.{images,publisher.{name,logoUrl}}`

## Front matter fields (see `themes/LoveIt/archetypes/default.md`)

```
title, subtitle, date, lastmod, draft, author, authorLink, description, license, images
tags, categories
featuredImage, featuredImagePreview
hiddenFromHomePage, hiddenFromSearch
twemoji, lightgallery, ruby, fraction, fontawesome, linkToMarkdown, rssFullText
toc: { enable, auto, keepStatic }
code: { copy, maxShownLines }
math: { enable, ... }
mapbox: { ... }
share: { enable, ... }
comment: { enable, ... }
library: { css: {...}, js: {...} }
seo: { images, ... }
```

Content summary priority: manual `<!--more-->` split → front matter `summary` → `description` → auto first-70-words (`summaryLength` to customize).

Local resources (images, audio) resolve in priority order: page bundle resources → `assets/` → `static/`.

## Built-in shortcodes

**Standard Hugo:** `figure`, `gist`, `highlight`, `instagram`, `param`, `ref`/`relref`, `x` (tweet embed), `vimeo`, `youtube`

**LoveIt extended** (`themes/LoveIt/layouts/shortcodes/`, also mirrored in this repo's `layouts/shortcodes/` for a few fixed-up ones):
- `style` — scoped custom CSS for a block of content, SASS nesting supported
- `link` — richer alternative to markdown links (works inside code blocks, custom class/rel)
- `image` — lazysizes + lightGallery-powered image with responsive `src_s`/`src_l` variants and captions
- `admonition` — 12 callout types: note, abstract, info, tip, success, question, warning, failure, danger, bug, example, quote. `{{< admonition type=tip title="..." open=false >}}...{{< /admonition >}}`
- `mermaid` — diagrams
- `echarts` — interactive charts (Apache ECharts)
- `mapbox` — interactive maps (Mapbox GL JS)
- `music` — APlayer/MetingJS embedded player
- `bilibili` — Bilibili video embed
- `typeit` — animated typing effect
- `script` — inject JS guaranteed to run after third-party libs load
- `raw` — raw HTML passthrough (skip markdown escaping, e.g. for LaTeX)
- `person` — h-card microformat link to a person's site

**Extended markdown syntax** (no shortcode needed, just inline syntax): Font Awesome icons, ruby annotation, fraction notation.

## Comment systems supported

Disqus, Gitalk, Valine, Facebook Comments, Telegram Comments, Commento, utterances, giscus, Waline — configured under `params.page.comment.*`, gated by the `comment.enable` master switch. None are currently turned on in this blog.

## Search

Built-in client-side search via Lunr.js (no backend) or Algolia (cloud). Config: `params.search.{enable,type,contentLength,placeholder,maxResultLength,snippetLength,highlightTag,absoluteURL,algolia.*}`. Not currently enabled here — worth considering before hand-rolling any search feature.

## Other built-in capabilities worth knowing about before building something custom

- Light/dark mode toggle, TypeIt typing animation, self-expanding TOC — all free, just config flags.
- Multilingual/i18n out of the box (23+ languages) if this blog ever goes multi-language.
- Lazy-loaded images (lazysizes), one-click copy-to-clipboard on code blocks, syntax highlighting — automatic.
- RSS per section/list/home, sitemap, robots.txt, JSON-LD SEO schema — all generated by the theme already; don't hand-roll.
- CDN mode for every vendor JS/CSS library via `params.cdn` + a data file, for swapping in your own mirrors.

## Where to look when in doubt

`themes/LoveIt/hugo.toml` is the theme's own default config — it is the single most reliable "what does this key do and what's its default" reference, more so than the public docs site (which documents the latest theme version; this repo is pinned to v0.3.1). Grep `themes/LoveIt/layouts/` for `.Site.Params.<path>` to confirm a key is actually read before relying on it.
