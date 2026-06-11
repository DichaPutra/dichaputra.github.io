# Dicha Putra Arwindra Web Profile & Blog (dichaputra.sbs)

Welcome! This document outlines the project purpose, stack, key conventions, and crucial guidelines for AI assistants or human developers modifying this codebase.

## 1. Project Purpose
This project is the source code for the personal portfolio website and blog of **Dicha Putra Arwindra (SobatS)**, hosted at [dichaputra.sbs](https://dichaputra.sbs/). The site is styled as a retro gaming player interface, gamifying his professional trajectory (Backend Developer / System Analyst), technology stack, multi-asset investment portfolio, and personal projects.

---

## 2. Tech Stack
The project is built entirely on static, zero-dependency web technologies:
* **Frontend Structure**: HTML5 (`index.html` files).
* **Styling**: Custom CSS3 utilizing CSS Custom Properties (CSS variables) for theme colors.
* **Typography**: Google Fonts ("Press Start 2P" for headings, "Space Mono" for body copy).
* **Assets**: Raw SVGs for social media links, custom pixel art `.png` files, and local `.mp4` video assets.
* **SEO & Metadata**: JSON-LD Structured Data Schema, Open Graph (OG) meta tags, canonical links, and custom robots/sitemap.

---

## 3. Key Conventions
* **Retro 8-Bit Gaming Theme**: The site features a Stardew Valley-inspired visual aesthetic. All design elements must strictly follow the custom color palette and pixel boundaries.
* **Pixel Styling Rules**:
  * Borders are styled using `var(--pixel-border) solid var(--soil)`.
  * Box shadows include inset highlights to mimic pixelated 3D boxes:
    ```css
    box-shadow:
      inset -3px -3px 0 var(--bark),
      inset 3px 3px 0 var(--parchment),
      4px 4px 0 var(--shadow);
    ```
  * Heavy use of pixelated rendering (`image-rendering: pixelated;`) for images.
  * A global CRT-scanline overlay is set up via the `.screen-overlay` div.
* **Inline styles**: Currently, each HTML page contains its own `<style>` tag containing variables and structural layouts. Do not attempt to load complex build scripts or Tailwind CSS unless explicitly instructed.

---

## 4. Instructions for AI Assistants (Before Modifying Code)

> [!IMPORTANT]
> Read these rules carefully before suggesting edits to this codebase.

1. **Maintain the Pixel Aesthetic**:
   * Do not use standard modern components, standard flat colors, or generic browser controls.
   * If adding new sections, cards, or buttons, wrap them in the `.pixel-box` container pattern.
   * Use only the pre-defined CSS variables in the `:root` palette (e.g. `--soil`, `--cream`, `--gold`, `--leaf`, `--heart`).

2. **Manual Sync Required (No SSG/Build Step)**:
   * There is no static site generator or templating framework. 
   * If you edit global layout blocks like **the navigation bar (`<nav>`)**, **the footer (`<footer>`)**, or **the global CSS color variables**, you **must** replicate those changes manually across:
     * Root [index.html](file:///home/arwindra23/dichaputra-sbs/index.html)
     * Blog Home [blog/index.html](file:///home/arwindra23/dichaputra-sbs/blog/index.html)
     * Individual blog posts (e.g., [blog/pengalaman-bri-backend-dev.html](file:///home/arwindra23/dichaputra-sbs/blog/pengalaman-bri-backend-dev.html))

3. **Avoid Adding External JS Libraries**:
   * The pages run with minimal JavaScript. Keep enhancements lightweight, write plain Vanilla JS, and avoid importing heavy frameworks or third-party dependencies unless requested.

4. **Verify CSS Duplication**:
   * Keep an eye out for duplicate rules (e.g., redundant definitions of `.hero-intro` or duplicate styling classes). Clean up duplicate CSS definitions as you work on those sections.
