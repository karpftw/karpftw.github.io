---
title: "Colophon"
date: 2026-10-02T00:00:00-05:00
layout: colophon
---

Welcome, refiner. This file documents how hypertext.dev is assembled, transmitted and kept compliant. The work is mysterious and important. Please enjoy each fact equally.

{{< panel code="MDR-01" title="Substrate" >}}
Every word on this site is refined on a single x86-64 workstation running Arch Linux, a rolling release that is never finished and never breaks the same way twice. The desktop is Omarchy, tiled by Hyprland, so no window is ever permitted to overlap another. Management considers this healthy.

Architecture
: x86-64, location undisclosed

Operating system
: Arch Linux, rolling, perpetually up to date

Environment
: Omarchy atop the Hyprland compositor

Terminal palette
: Lumon, loaded at boot

Uptime policy
: Restart only when the kernel insists
{{< /panel >}}

{{< panel code="MDR-02" title="Composition" >}}
Posts are written as plain Markdown, the most durable file format known to computing. Each one starts life with `draft: true` and is previewed on a local loopback at port 1313 before it is cleared for release. Version control is git, so every revision is retained in perpetuity, including the regrettable ones.

Source format
: Markdown with YAML front matter

Drafting
: `hugo new posts/…`, then `hugo server -D`

Version control
: git, single branch, linear history
{{< /panel >}}

{{< panel code="O&D-03" title="Typography" >}}
Three typefaces are in service, all self-hosted, so no font foundry is told when you visit. Each has one job.

<p class="specimen specimen-display" aria-hidden="true">Archivo 0123456789</p>

Display face
: Archivo by Omnibus-Type, drawn at its widest setting and standing in for Manifold Extended, Lumon's corporate face. It sets titles in spaced capitals, headings, the menu and every label.

<p class="specimen specimen-sans" aria-hidden="true">Inter · Refined text</p>

Text face
: Inter by Rasmus Andersson, a neo-grotesque in the spirit of Forma, the face of the Lumon handbook. It sets everything meant to be read at length, at 17 pixels.

<p class="specimen specimen-mono" aria-hidden="true">IBM Plex Mono {}[] 0O 1lI</p>

Data face
: IBM Plex Mono by Mike Abbink and Bold Monday for IBM, the terminal readout. It sets code, dates, tables and fine print.

Licensing
: All three under the SIL Open Font License 1.1
{{< /panel >}}

{{< panel code="O&D-04" title="Chromatics" >}}
The palette is the Lumon theme for Omarchy: navy voids, fluorescent edges and sterile blue-gray surfaces. The lights on this floor are always low; there is no light mode. Every text color has been measured against its background and clears WCAG AA contrast.

{{< swatches >}}
{{< /panel >}}

{{< panel code="O&D-05" title="Sigil" >}}
The wordmark in the corner is set in the display face, then converted to outlines so it never waits on a font. It passes through a globe of eight horizontal lines, each exactly two pixels tall and colored by the same five bands as the bar above it, coolest at the bottom. The globe has no surface. It does not need one.
{{< /panel >}}

{{< panel code="WSD-06" title="Transmission" >}}
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
: About 100 KB compressed for the front page, most of it the four font files
{{< /panel >}}

{{< panel code="WSD-07" title="Surveillance" >}}
None. There are no analytics, no cookies, no tracking pixels, no comment forms and no newsletter pop-ups. Your outie's browsing remains your outie's business. The sole exception: embedded videos are fetched from their own platforms, which keep their own counsel.
{{< /panel >}}

{{< panel code="WSD-08" title="Wellness" >}}
Reading text is set at 17 pixels. Contrast is measured, not estimated. Images carry alternative text, headings follow a sensible order, and any animation on this page halts for visitors who have asked their system for reduced motion. The site reads correctly from 360 pixels wide upward.
{{< /panel >}}

{{< panel code="WSD-09" title="Syndication" >}}
The [RSS feed](/index.xml) carries the latest 30 posts. Subscribe in any feed reader. There is no account to create and no algorithm deciding what you see.
{{< /panel >}}

{{< panel code="ACK-10" title="Acknowledgments" >}}
- [Hugo](https://gohugo.io/), for compiling the archive
- [Omarchy](https://omarchy.org/), for a calm place to work
- The [Lumon theme](https://github.com/OldJobobo/omarchy-lumon-theme) by OldJobobo, for every color
- [Archivo](https://github.com/Omnibus-Type/Archivo), [Inter](https://github.com/rsms/inter) and [IBM Plex](https://github.com/IBM/plex), for the letters
- *Severance*, for the mood. This site is not affiliated with Lumon Industries, which does not exist.
{{< /panel >}}

{{< panel code="LGL-11" title="Terms" >}}
Words and pictures © Ryan Karpowicz. Fonts are used under the SIL Open Font License 1.1; the license texts ship alongside them in `/fonts/`.
{{< /panel >}}

Please enjoy each colophon entry equally.
