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
Four typefaces are in service, all self-hosted, so no font foundry is told when you visit. Two more are borrowed from your own machine when it already has them.

<p class="specimen specimen-geometric" aria-hidden="true">Hypertext · 0123456789</p>

Title face
: Futura by Paul Renner, where your system has it installed, as Apple devices do. Elsewhere, Jost by Owen Earl, a free face drawn in Futura's image. It sets post titles, dates, the menu, the pager and the footer.

<p class="specimen specimen-sans" aria-hidden="true">Refined text · 0123456789</p>

Text face
: Verdana by Matthew Carter, where installed, as on Windows and Apple devices. Elsewhere, DejaVu Sans, a descendant of Bitstream Vera, trimmed to Latin characters to keep it light. It sets the body of every post and page, at 16 pixels with generous leading.

<p class="specimen specimen-pixel" aria-hidden="true">Jersey 10 · 0123456789</p>

Display face
: Jersey 10 by The Soft Type Project. A bitmap-born face rendered only at 20, 30 and 40 pixels, multiples of its 10-pixel grid, so that every stroke lands on a whole screen pixel. It sets page titles, headings and file listings.

<p class="specimen specimen-mono" aria-hidden="true">Fira Code -> 0O 1lI {}[] !=</p>

Code face
: Fira Code by Nikita Prokopov and contributors. A monospaced face built for terminals, kept for code and the remaining fine print.

Licensing
: Jersey 10, Jost and Fira Code under the SIL Open Font License 1.1; DejaVu Sans under the Bitstream Vera license. Futura and Verdana are never shipped.
{{< /panel >}}

{{< panel code="O&D-04" title="Chromatics" >}}
The palette is the Lumon theme for Omarchy: navy voids, fluorescent edges and sterile blue-gray surfaces. The lights on this floor are always low; there is no light mode. Every text color has been measured against its background and clears WCAG AA contrast.

{{< swatches >}}
{{< /panel >}}

{{< panel code="O&D-05" title="Sigil" >}}
The wordmark in the corner is not a font. It is hand-plotted on a 97 × 19 grid, one cell at a time, and shipped as inline SVG at exactly twice its native size so no pixel is ever split. Its letterforms follow the Omarchy wordmark; the p, e, t and x were drafted from scratch to match. The p and r descend below the baseline by design, following review.
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
: About 105 KB compressed for the front page, most of it the four fonts
{{< /panel >}}

{{< panel code="WSD-07" title="Surveillance" >}}
None. There are no analytics, no cookies, no tracking pixels, no comment forms and no newsletter pop-ups. Your outie's browsing remains your outie's business. The sole exception: embedded videos are fetched from their own platforms, which keep their own counsel.
{{< /panel >}}

{{< panel code="WSD-08" title="Wellness" >}}
Text is set at no less than 16 pixels. Contrast is measured, not estimated. Images carry alternative text, headings follow a sensible order, and any animation on this page halts for visitors who have asked their system for reduced motion. The site reads correctly from 360 pixels wide upward.
{{< /panel >}}

{{< panel code="WSD-09" title="Syndication" >}}
The [RSS feed](/index.xml) carries the latest 30 posts. Subscribe in any feed reader. There is no account to create and no algorithm deciding what you see.
{{< /panel >}}

{{< panel code="ACK-10" title="Acknowledgments" >}}
- [Hugo](https://gohugo.io/), for compiling the archive
- [Omarchy](https://omarchy.org/), for the wordmark's inspiration and a calm place to work
- The [Lumon theme](https://github.com/OldJobobo/omarchy-lumon-theme) by OldJobobo, for every color
- [Jersey 10](https://github.com/scfried/soft-type-jersey), [Jost](https://github.com/indestructible-type/Jost), [DejaVu Sans](https://dejavu-fonts.github.io/) and [Fira Code](https://github.com/tonsky/FiraCode), for the letters
- *Severance*, for the mood. This site is not affiliated with Lumon Industries, which does not exist.
{{< /panel >}}

{{< panel code="LGL-11" title="Terms" >}}
Words and pictures © Ryan Karpowicz. Fonts are used under the SIL Open Font License 1.1 and the Bitstream Vera license; the license texts ship alongside them in `/fonts/`.
{{< /panel >}}

Please enjoy each colophon entry equally.
