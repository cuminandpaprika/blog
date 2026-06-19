# Blog

Hugo static site deployed via GitHub Pages at https://www.jackzheng.co/.

## Stack

- Hugo v0.122.0 with the LoveIt theme
- Published to `docs/` (committed to git, served by GitHub Pages)

## Build

```sh
hugo          # builds into docs/
hugo server   # local dev server with live reload
```

A pre-push hook automatically runs `hugo` before every push. If `docs/` has changed, it amends the HEAD commit to include the rebuild, so the deployed site always stays in sync in a single push.

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
