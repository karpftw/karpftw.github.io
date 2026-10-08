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
- **Archive:** `layouts/section.html` renders `/posts/` as one `.panel` per year holding a `.file-list` table (Type is Link for link posts, else Post; Words is the word count). `layouts/list.html` is separate and still uses the plain `.archive` list styles.
- **About:** `content/about.md` sets `layout: dossier` (`layouts/dossier.html`), a profile panel plus a Notes panel. Its fields come from the `dossier` list in front matter (`redacted: true` draws a redaction bar), and the page body is the Notes panel. The ASCII portrait is a static `<pre>` in `_partials/portrait.html`; it needs `font-variant-ligatures: none` or a monospace with ligatures joins runs like `==` and `--`.
- **Theme references:** explicit nods to BBS, Lumon/Severance and Omarchy belong only on the colophon. Keep the Archive and About copy free of them.
- **404:** `layouts/404.html` is a dropped-connection screen with a pixel "404" SVG. It has the `.handshake` dial-up block and reuses the colophon's `.panel` and `.status-bar` styles. It ships no JavaScript, so it can't echo the requested path. A site-wide `prefers-reduced-motion` rule stops every animation.
- **Images:** `_markup/render-image.html` resolves Markdown images as page-bundle resources first and global `assets/` second. It resizes raster images wider than 1400px and adds width/height and lazy loading. A standalone image becomes a `<figure>`, and its Markdown title becomes the `<figcaption>`. This depends on `wrapStandAloneImageWithinParagraph = false` in `hugo.toml`.
- **Video:** `{{< video src="clip.mp4" caption="..." poster="..." >}}` (from `_shortcodes/video.html`) plays a bundle MP4. Use the built-in `youtube` and `vimeo` shortcodes for embeds.
- **Logo:** the masthead wordmark is an inline SVG in `_partials/logo.html`: HYPERTEXT outlined from Archivo Expanded 700 (so it needs no font load), set through a "globe" of eight 2px horizontal lines whose widths follow an ellipse, in the five top-bar band colors from lightest (top) to darkest. It is drawn in a 194×61 pixel viewBox and the CSS shows it at exactly 194px, so the lines land on whole pixels. The letters are `currentColor` (ink, link-hover on hover).
- **Top bar:** a 38px full-width bar (`body::before` in `style.css`, fixed to the viewport, with a matching 38px `padding-top` on `body` so it covers nothing) of five Lumon blue bands in 8px steps. Its colors are hardcoded and must stay in step with the wordmark's lines. The sticky masthead's `top` and `scroll-padding-top` add the same 38px, so the sidebar never shifts on scroll.
- **Favicon:** `static/favicon.svg` is a 16×16 pixel miniature of the wordmark: a wide H between two pairs of globe lines in the band colors (the middle band is left out). `favicon.ico` (16/32/48) and `apple-touch-icon.png` (180) are nearest-neighbor scale-ups of it, regenerated with `rsvg-convert` and ImageMagick when the SVG changes.
- **Typography:** after Lumon's house style in *Severance*, three self-hosted SIL OFL fonts in `static/fonts/`, preloaded in `_partials/head.html` (Inter italic loads on demand). Lumon's real faces are commercial, so each has a stand-in. Archivo at its widest (`--display`, the `@font-face` pins `font-stretch: 125%`) stands in for Manifold Extended: post and page titles (26px, 500, uppercase, .04em; link posts 20px), `.prose` h2/h3, the menu, and every small label (panel titles, table headers, swatch names, bins, status bar: 12px, 600, uppercase, .12em). It also sets the metadata (dates, pager, footer, file lines, field labels, archive cells) at 13px, 500, .02em, with tabular numerals where digits line up. Inter (`--sans`) stands in for Forma DJR as the reading face at 17px/1.65. IBM Plex Mono 400 (`--mono`) is kept for terminal output: code, captions, the dial-up and MDR screens, the 404 menu keys and the ASCII portrait. Sizes are in px; layout spacing stays in rem (18px root).
- **Site description** (`params.description`) is not shown on the page; it only feeds the meta description fallback in `_partials/head.html`.
- **CSS** goes through Hugo Pipes in `_partials/head.html` (minify + fingerprint + SRI). Colors are CSS variables at the top of `style.css`, taken from the Lumon theme for Omarchy. The site is dark only; there is no light mode. Syntax highlighting emits CSS classes (`markup.highlight.noClasses = false`), styled by the `.chroma` rules in `style.css`.

## Config notes (`hugo.toml`)

- Post permalinks are `/:year/:month/:slug/`. The slug comes from the title, not the folder name. Posts dated in the future are skipped unless you build with `-F`.
- Taxonomies are disabled (`disableKinds = ["taxonomy", "term"]`). There are no tags or categories.
- `markup.goldmark.renderer.unsafe = true`, so posts can contain raw HTML.
- The home page outputs HTML and RSS and is paginated at 15 posts. The section outputs HTML only. The nav menu is defined in `[menus]`.
