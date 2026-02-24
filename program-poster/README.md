# InfoSci Program Poster Template

UA-branded general-purpose poster (36" x 24" landscape) for research programs, labs, initiatives, and other non-study content.

**Different from the conference poster template.** The conference poster uses a rigid Introduction/Methods/Results/Discussion flow. This template uses flexible thematic columns with a component library you can mix and match.

## Quick Start

```bash
quarto use template ryanstraight/azinfosci-templates/program-poster
quarto render template.qmd
```

Open the HTML in a browser. Use **Print > Save as PDF** for the final poster.

## When to Use This Template

- Research program overviews
- Lab or center showcases
- Initiative or grant summaries
- Departmental displays
- Hallway or permanent installation posters
- Any poster that isn't presenting a single study's results

For conference research posters (with Methods, Results, Discussion), use the `poster/` template instead.

## Structure

The poster has three thematic columns. Each column has:

1. **Pillar Header** — colored title bar with a name and optional subtitle
2. **Content Card** — white card that fills the remaining height

You decide what goes in each column. The SCSS provides a library of reusable components (stat boxes, comparison tables, key-move cards, definition boxes, QR boxes, etc.).

## Customizing

### 1. Edit YAML Metadata

```yaml
title: "Your Program Title"
subtitle: "A tagline or framing statement"
author-line-1: "<strong>Your Name</strong>, Ph.D. — Your Title"
author-line-2: "College of Information Science &bull; University of Arizona"
```

### 2. Add Your Logos

Place logo files in `assets/`:

| File | Purpose |
|------|---------|
| `assets/infosci-logo-reverse.png` | White logo for dark header (left) |
| `assets/ua-logo-white.png` | UA block logo (right) |

Download from [UA Brand Resources](https://brand.arizona.edu/brand-assets) (requires NetID).

### 3. Edit Column Content

Each column is wrapped in Quarto div syntax:

```markdown
::: {.pillar-header}
::: {.pillar-title}
Column Name
:::
::: {.pillar-question}
Guiding question or subtitle.
:::
:::

::: {.content-card}
Your content here.
:::
```

### 4. Use Components

See **POSTER-GUIDE.md** for the full component library with code examples:

- Stat boxes
- Comparison tables
- Concept callouts
- Definition boxes
- Key-move cards
- Research area grids
- Publication lists
- QR code boxes
- Vision boxes
- SVG diagrams

## Printing to PDF

1. Render: `quarto render template.qmd`
2. Open HTML in Chrome or Firefox
3. Print (Ctrl+P)
4. Paper size: **36" x 24"** (custom)
5. Orientation: **Landscape**
6. Enable **Background graphics**
7. Save as PDF

## Using with an LLM

This template ships with **POSTER-GUIDE.md**, a detailed style guide written specifically for LLM assistants. When working with Claude, ChatGPT, or similar:

1. Share the POSTER-GUIDE.md with your LLM
2. Describe what your poster is about
3. The LLM can generate properly-structured content using the documented CSS classes and HTML patterns

## Troubleshooting

**Content overflows the poster?**
The poster is exactly 24" tall. Reduce text or remove components until everything fits.

**Colors not printing?**
Enable "Background graphics" in your browser's print dialog.

**Fonts look different?**
The template uses Proxima Nova via Adobe Fonts (internet required). Falls back to system fonts.

**Columns not equal width?**
The CSS Grid enforces `1fr 1fr 1fr`. If content appears uneven, it's a visual effect of different content heights, not actual width differences.
