# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project

`mi-portafolio` is a personal portfolio website built for the **BIOS "Desarrollo de Software Aumentado con IA"** course.

There is no build system, package manager, or framework — and none is planned.

## Constraints

- **HTML and CSS only.** No JavaScript, no frameworks, no build tooling, no package manager. Keep dependencies at zero.
- This is coursework — favor clear, readable, well-structured markup and styles over cleverness.
- **Calm design brief.** No animations, transitions, parallax, carousels, or moving elements. No strong shadows or gradients — keep it static and predictable.
- **Palette: max 4 muted, low-saturation colors** defined as `:root` variables in `base.css`: cream bg `#f4efe6` (never pure white), warm dark gray text `#36352f`, muted blue `#5e7a8a` (headings/links), sage green `#8a9a82` (accents/borders), plus a soft beige surface `#ede7da` for cards.
- **Accessibility:** body font ≥16px (currently ~17px), `line-height: 1.6`, generous spacing between sections, clear heading hierarchy.

## Running

Open the HTML file(s) directly in a browser (e.g. double-click `index.html`), or use a static file server. No build or install step is needed.

## Structure

Single-page site with anchor-linked sections.

```
index.html       # Entry point: header (name + tagline) + nav + #about, #projects, #contact + footer
css/
  base.css       # Reset, :root palette/fonts/spacing variables, base element styles
  layout.css     # Header, nav, section containers, footer, responsive (@media)
  components.css # Reusable pieces: project cards (.projects grid + .project-card), contact list
assets/
  images/        # Photos, decorative images
  icons/         # SVG icons, favicon
```

**CSS load order matters** — stylesheets are linked in `index.html` as
`base.css` → `layout.css` → `components.css` so variables and the cascade resolve
predictably. Define colors/fonts/spacing once via the `:root` custom properties in
`base.css`; reuse them with `var(--…)` rather than hardcoding values.
