---
title: "Colophon"
date: 2026-10-02T00:00:00-05:00
layout: colophon
---

This page documents how hypertext.dev is written, built and published.

{{< panel code="00" title="Captain on deck" >}}
{{< picard >}}
{{< /panel >}}

{{< panel code="01" title="Substrate" >}}
Every word on this site is written on a single x86-64 workstation running Arch Linux, a rolling release that is never finished and never breaks the same way twice. The desktop is Omarchy, tiled by Hyprland, so no window ever overlaps another.

Architecture
: x86-64

Operating system
: Arch Linux, rolling, perpetually up to date

Environment
: Omarchy atop the Hyprland compositor

Terminal palette
: Lumon, loaded at boot

Uptime policy
: Restart only when the kernel insists
{{< /panel >}}

{{< panel code="02" title="Composition" >}}
Posts are written as plain Markdown, the most durable file format known to computing. Each one starts life with `draft: true` and is previewed on a local loopback at port 1313 before it is published. Version control is git, so every revision is retained in perpetuity, including the regrettable ones.

Source format
: Markdown with YAML front matter

Drafting
: `hugo new posts/…`, then `hugo server -D`

Version control
: git, single branch, linear history
{{< /panel >}}

{{< panel code="03" title="Typography" >}}
Three typefaces are in service, all self-hosted, so no font foundry is told when you visit. Each has one job.

<p class="specimen specimen-display" aria-hidden="true">Archivo 0123456789</p>

Display face
: Archivo by Omnibus-Type, drawn at its widest setting. It sets titles in spaced capitals, headings, the menu, every label and the dates.

<p class="specimen specimen-sans" aria-hidden="true">Instrument Sans · Body text</p>

Text face
: Instrument Sans by Rodrigo Fuenzalida for Instrument, a crisp neo-grotesque. It sets everything meant to be read at length, at 18 pixels.

<p class="specimen specimen-mono" aria-hidden="true">IBM Plex Mono {}[] 0O 1lI</p>

Data face
: IBM Plex Mono by Mike Abbink and Bold Monday for IBM. It sets code, captions and terminal output.

Licensing
: All three under the SIL Open Font License 1.1
{{< /panel >}}

{{< panel code="04" title="Chromatics" >}}
The palette is the Lumon theme for Omarchy: deep navy with cool blue accents. The site is dark only; there is no light mode. Every text color has been measured against its background and clears WCAG AA contrast.

{{< swatches >}}
{{< /panel >}}

{{< panel code="05" title="Wordmark" >}}
The wordmark in the corner is set in the display face, then converted to outlines so it never waits on a font. It passes through a globe of eight horizontal lines, each exactly two pixels tall and colored by the same five bands as the bar above it, darkest at the bottom.
{{< /panel >}}

{{< panel code="06" title="Transmission" >}}
There is no server, no database and no runtime. On every push to the main branch, a GitHub Actions runner compiles the archive with Hugo into flat HTML, and GitHub Pages broadcasts the result. No JavaScript is shipped to your terminal.

1. Markdown
2. Hugo 0.167
3. GitHub Actions
4. GitHub Pages
5. Your terminal
{.pipeline}

Generator
: Hugo, no theme, no Node, no build chain beyond itself

Host
: GitHub Pages, behind a custom domain

Clock
: America/Chicago, which decides what day every post was written

Payload
: About 170 KB for the front page before images, nearly all of it the three font files
{{< /panel >}}

{{< panel code="07" title="Privacy" >}}
None. There are no analytics, no cookies, no tracking pixels, no comment forms and no newsletter pop-ups. What you read here is your own business. The sole exception: embedded videos are fetched from their own platforms, which keep their own counsel.
{{< /panel >}}

{{< panel code="08" title="Accessibility" >}}
Reading text is set at 18 pixels. Contrast is measured, not estimated. Images carry alternative text, headings follow a sensible order, and any animation on this page halts for visitors who have asked their system for reduced motion. The site reads correctly from 360 pixels wide upward.
{{< /panel >}}

{{< panel code="09" title="Syndication" >}}
The [RSS feed](/index.xml) carries the latest 30 posts. Subscribe in any feed reader. There is no account to create and no algorithm deciding what you see.
{{< /panel >}}

{{< panel code="10" title="Acknowledgments" >}}
- [Hugo](https://gohugo.io/), for compiling the archive
- [Omarchy](https://omarchy.org/), for a calm place to work
- The [Lumon theme](https://github.com/OldJobobo/omarchy-lumon-theme) by OldJobobo, for every color
- [Archivo](https://github.com/Omnibus-Type/Archivo), [Instrument Sans](https://github.com/Instrument/instrument-sans) and [IBM Plex](https://github.com/IBM/plex), for the letters
{{< /panel >}}

{{< panel code="11" title="Terms" >}}
Words and pictures © Ryan Karpowicz. Fonts are used under the SIL Open Font License 1.1; the license texts ship alongside them in `/fonts/`.
{{< /panel >}}
