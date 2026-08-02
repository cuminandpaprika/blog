# Blog

Hugo static site deployed via GitHub Pages at https://www.jackzheng.co/.

## Stack

- Hugo v0.163.3 (extended) with the LoveIt theme (vendored in `themes/LoveIt`)
- Published to `docs/` (committed to git, served by GitHub Pages)
- See [`LOVEIT.md`](LOVEIT.md) for what the theme already supports (shortcodes, config schema, comment systems, search, etc.) before building something custom. It also has an important note about the theme's nested config schema (`[params.footer]`, `[params.page.share]`, etc.) — a key in the wrong table is silently ignored, not an error.

## Build

Builds must run with `HUGO_ENV=production` (or `--environment production`). The LoveIt theme only enables CDN-hosted vendor assets and fingerprinting in production; a plain dev build instead vendors local copies into `docs/lib/`, which diverges from what's actually committed.

```sh
HUGO_ENV=production hugo   # builds into docs/ — always use this, not plain `hugo`
hugo server                 # local dev server with live reload (dev mode is fine here)
```

A pre-push hook automatically runs the production build before every push. If `docs/` has changed, it amends the HEAD commit to include the rebuild, so the deployed site always stays in sync in a single push.

## Content

Posts live in `content/posts/`. Two conventions:

- **Draft posts** are prefixed with `draft-` (e.g. `draft-my-idea.md`) and have `draft: true` in frontmatter
- **Published posts** have no prefix and `draft: false`

### Frontmatter

Use RFC 3339 dates with a leading-zero timezone offset:

```yaml
date: 2024-01-11T18:15:31+03:00   # correct
date: 2024-01-11T18:15:31+3:00    # wrong — Hugo may parse as zero time (0001-01-01)
```
