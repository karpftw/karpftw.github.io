# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## What this is

hypertext.dev: a Hugo blog with no theme, no Node, no Go modules, and no Sass. All templates live in `layouts/` and all styling lives in `assets/css/style.css`. Pushing to `main` builds and deploys to GitHub Pages through `.github/workflows/hugo.yaml`, which pins `HUGO_VERSION` (currently 0.167.0) and sets `TZ=America/Chicago`. The time zone affects post dates and therefore permalinks.

## Commands

```sh
hugo server -D                          # local preview with drafts at http://localhost:1313
hugo build --gc --minify                # production build into public/ (same as CI minus baseURL/cacheDir)
hugo new posts/my-post.md               # plain post (archetypes/posts.md; draft: true)
hugo new posts/my-post/index.md         # page bundle, for posts with images/video alongside
```

There are no tests or linters. A successful `hugo build` with no warnings is the check. `public/` and `.hugo_build.lock` are build output and are gitignored.

## Architecture

- **Templates** use Hugo's newer layout naming: `layouts/baseof.html`, `home.html`, `section.html` (the `/posts/` archive, grouped by year), `list.html`, `page.html`, plus `_partials/`, `_shortcodes/`, and `_markup/`. Use the underscore-prefixed directories, not the old `partials/` and `shortcodes/` names.
- **`_partials/post.html`** renders a post on both the home page and the single-post page. When a post's front matter includes `link:`, it becomes a *link post*: the title links to the external URL and a pixel-arrow SVG after it links to the permalink.
- **`page.html`** branches on `.Section`. Posts get the post partial and prev/next navigation. Other pages, such as `content/about.md`, get a plain article.
- **Colophon:** `content/colophon.md` sets `layout: colophon`, rendered by `layouts/colophon.html` (decorative BBS/Severance chrome) with its text in `panel` and `swatches` shortcodes. Its CSS is scoped to `.colophon-page`, because `.colophon` is already the site footer's class. The swatch hex labels are hardcoded and must be kept in step with the color variables.
- **Images:** `_markup/render-image.html` resolves Markdown images as page-bundle resources first and global `assets/` second. It resizes raster images wider than 1400px and adds width/height and lazy loading. A standalone image becomes a `<figure>`, and its Markdown title becomes the `<figcaption>`. This depends on `wrapStandAloneImageWithinParagraph = false` in `hugo.toml`.
- **Video:** `{{< video src="clip.mp4" caption="..." poster="..." >}}` (from `_shortcodes/video.html`) plays a bundle MP4. Use the built-in `youtube` and `vimeo` shortcodes for embeds.
- **Logo:** the masthead wordmark is an inline SVG in `_partials/logo.html`, drawn on a 97×19 pixel grid in the style of the Omarchy logo. It uses `currentColor`, and the CSS shows it at exactly 2× (194px) so the pixels stay crisp.
- **Typography:** two self-hosted SIL OFL fonts in `static/fonts/`, preloaded in `_partials/head.html`. Jersey 10 (`--pixel`) is a pixel face for the tagline, menu, titles, headings, dates, pager and footer; keep it at multiples of 10px (20px, 30px, 40px) or its strokes go uneven. Regular post titles are 40px so they stand apart from link posts, whose titles are 30px and underlined. Fira Code (`--mono`) is the body and code face.
- **CSS** goes through Hugo Pipes in `_partials/head.html` (minify + fingerprint + SRI). Colors are CSS variables at the top of `style.css`, taken from the Lumon theme for Omarchy. The site is dark only; there is no light mode. Syntax highlighting emits CSS classes (`markup.highlight.noClasses = false`), styled by the `.chroma` rules in `style.css`.

## Config notes (`hugo.toml`)

- Post permalinks are `/:year/:month/:slug/`. The slug comes from the title, not the folder name. Posts dated in the future are skipped unless you build with `-F`.
- Taxonomies are disabled (`disableKinds = ["taxonomy", "term"]`). There are no tags or categories.
- `markup.goldmark.renderer.unsafe = true`, so posts can contain raw HTML.
- The home page outputs HTML and RSS and is paginated at 15 posts. The section outputs HTML only. The nav menu is defined in `[menus]`.
