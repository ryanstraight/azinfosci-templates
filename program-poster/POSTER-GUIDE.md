# Program Poster — LLM Style Guide

This document describes the anatomy, CSS classes, and customization patterns for the UA InfoSci program poster template. It is written for LLMs assisting with poster creation and modification.

## Template Type

**Program poster** — a general-purpose 36" x 24" poster for showcasing a research program, initiative, lab, center, or other non-study content. Unlike the conference poster template (which follows Introduction/Methods/Results/Discussion), this template uses **thematic columns** with flexible content.

## Architecture

The poster is a single HTML page rendered by Quarto. The layout is defined entirely in CSS (no JavaScript). Structure:

```
.poster                          ← 36"x24" fixed container
├── .poster-header               ← Blue bar: logo | title | logo
├── .author-bar                  ← Gray bar: name, affiliation, contact
├── .poster-body                 ← 3-column CSS Grid
│   ├── .column                  ← Column 1
│   │   ├── .pillar-header       ← Blue header with title + subtitle
│   │   └── .content-card        ← White card filling remaining height
│   ├── .column.column-center    ← Column 2
│   │   ├── .pillar-header
│   │   └── .content-card
│   └── .column                  ← Column 3
│       ├── .pillar-header
│       └── .content-card
└── .poster-footer               ← Blue bar: left | center | right
```

## Column Structure

Each column is a flex container with two children:

1. **`.pillar-header`** — The colored title bar (rounded top corners)
2. **`.content-card`** — The white content area (rounded bottom corners, no gap between it and the header)

The content-card has `flex: 1` so it fills all remaining vertical space. Elements inside it can use `margin-top: auto` to push themselves to the bottom (e.g., `.definition-box`, `.qr-box`).

### Pillar Header

```html
::: {.pillar-header}
::: {.pillar-title}
Title Text
:::
::: {.pillar-question}
Optional italic subtitle in lighter blue.
:::
:::
```

- `.pillar-title` — 40pt bold white text
- `.pillar-question` — 22pt italic in `$ua-sky-light`
- `.pillar-number` — Optional small caps label above the title (rarely used)

### Content Card

Use Quarto's `::: {.content-card}` div syntax. Everything between the opening and closing `:::` goes inside the card. For raw HTML content (tables, SVGs), use ```` ```{=html} ```` blocks inside the card.

**h3 headers** inside content cards render as styled blue pill bars:

```markdown
### Section Title
```

Produces a centered white-on-blue bar that visually separates content sections within a column.

## Component Library

All components are CSS classes available inside `.content-card`. They can be mixed freely.

### Stat Boxes

Row of metric highlights. Use 2-4 boxes.

```markdown
::: {.stat-boxes}
::: {.stat-box}
**42**

Label
:::
::: {.stat-box}
**N=100**

Label
:::
:::
```

- Number/value goes in `**bold**` (renders at 40pt)
- Label text below (16pt)
- Background: `$ua-red`, text: white

### Big Question

Full-width emphasis callout for a framing question.

```markdown
::: {.big-question}
What assumptions does the current approach make?
:::
```

- Background: `$ua-blue`, text: white, 22pt bold, centered

### Comparison Table

Raw HTML table for side-by-side comparisons. Three columns: icon+label, Column A heading, Column B heading.

```html
<table class="comparison-table">
  <tr>
    <th></th>
    <th>Before</th>
    <th>After</th>
  </tr>
  <tr>
    <td>&#9733;<span class="row-label">Label</span></td>
    <td>Old approach description</td>
    <td>New approach description</td>
  </tr>
</table>
```

- First column: blue background, icon + `.row-label` text
- Second column: light red tint
- Third column: light blue tint, bold text
- Use HTML entities for icons (&#9733; = star, &#9670; = diamond, etc.)

### Concept Callout

Named concept with optional subtitle and description.

```html
<div class="concept-callout">
  <div class="concept-name">Concept Name <span class="concept-subtitle-inline">— optional tagline</span></div>
  <div class="concept-desc">Description of the concept.</div>
</div>
```

- Background: `$ua-blue`
- Name: `$ua-sky-light`, 24pt bold
- Description: white, 17pt

### Definition Box

"What is X?" explainer, typically pushed to the bottom of a column.

```html
<div class="definition-box">
  <div class="def-label">What is your key concept?</div>
  <div class="def-text">A brief definition or explanation.</div>
</div>
```

- Border: `$ua-oasis`
- Background: light oasis tint
- Has `margin-top: auto` — naturally sits at column bottom

### Key Moves

Vertical list of icon + text cards for important points.

```html
<div class="key-moves">
  <div class="key-move move-primary">
    <div class="move-icon">&#9733;</div>
    <div class="move-content">
      <span class="move-title">Point Title:</span> Description text.
    </div>
  </div>
  <!-- Repeat for each point -->
</div>
```

Color variants for `.key-move`:

| Class | Border | Icon Background |
|-------|--------|-----------------|
| `.move-primary` | `$ua-blue` | `$ua-blue` |
| `.move-secondary` | `$ua-red` | `$ua-red` |
| `.move-accent` | `$ua-oasis` | `$ua-oasis` |
| `.move-dark` | `#333` | `#333` |

### Key Insight

Compact single-line accent strip.

```html
<div class="key-insight">
  <div class="insight-icon">&#9888;</div>
  <div class="insight-text">A single important takeaway.</div>
</div>
```

- Red left border, light red background

### Research Area Grid

2-column grid of cards, each with icon + title + detail. Supports SVG icons or HTML entities.

```html
<div class="research-areas">
  <div class="research-area">
    <div class="area-icon">&#9733;</div>
    <div class="area-title">Area Name</div>
    <div class="area-detail">Brief description</div>
  </div>
  <!-- Repeat for each area (2, 4, or 6 recommended) -->
</div>
```

- Border-top colors cycle: blue, red, oasis (repeating)
- For SVG icons, wrap in `<svg>` inside `.area-icon`

### Highlight Box

General emphasis callout with blue tint.

```markdown
::: {.highlight-box}
**Important:** Key information to highlight.
:::
```

### Vision Box

Italic quote-style callout with red left border.

```markdown
::: {.vision-box}
A visionary statement or guiding principle for the program.
:::
```

### Publication Items

For listing research outputs with status badges.

```html
<div class="pub-item">
  <span class="pub-title">Paper title</span>
  <span class="pub-venue">Journal Name</span>
  <span class="pub-status status-published">Published</span>
</div>
```

Status classes: `.status-published`, `.status-accepted`, `.status-review`, `.status-writing`

### QR Box

QR code + label, typically at column bottom.

```markdown
::: {.qr-box}
::: {.qr-content}
**Scan for More**

Description text

[url.arizona.edu]{.qr-url}
:::
::: {.qr-placeholder}
QR CODE
:::
:::
```

Has `margin-top: auto` — sits at column bottom. Replace `.qr-placeholder` with an actual `<img>` tag for the QR image.

## SVG Diagrams

Custom SVG diagrams can be embedded directly in ```` ```{=html} ```` blocks inside content cards. Key considerations:

- Use `viewBox` for responsive sizing: `<svg viewBox="0 0 600 500" style="width: 100%; height: auto;">`
- SVG `<text>` elements inherit the poster font via the CSS rule `.content-card svg text { font-family: ... }`
- Use the UA color palette in SVG fills and strokes (hex values from the color table below)
- For multi-line SVG text, use multiple `<text>` elements with different `y` coordinates
- Test wrapping at 36" scale — SVG text does not wrap automatically

## Color Palette

| Variable | Hex | Usage |
|----------|-----|-------|
| `$ua-blue` | `#0C234B` | Primary: headers, pillar backgrounds, text |
| `$ua-red` | `#AB0520` | Accent: stat boxes, borders, emphasis |
| `$ua-oasis` | `#378DBD` | Secondary: links, definition borders, accent |
| `$ua-sky` | `#81D3EB` | Light accent (low contrast on blue — use sparingly) |
| `$ua-sky-light` | `#B8E4F3` | Safe on blue backgrounds (4.6:1 contrast) |
| `$ua-cool-gray` | `#E2E9EB` | Subtle backgrounds, borders |
| `$ua-warm-gray` | `#F4EDE5` | Warm neutral background |
| `$ua-chili` | `#8B0015` | Darker red variant |
| `$ua-midnight` | `#001C48` | Darker blue variant |
| `$ua-azurite` | `#1E5288` | Medium blue |
| `$ua-bloom` | `#EF4056` | Bright red |
| `$ua-leaf` | `#70B865` | Green accent |
| `$ua-river` | `#007D84` | Teal accent |
| `$ua-mesa` | `#A95C42` | Warm earth tone |
| `$ua-silver` | `#9EABAE` | Muted gray |

## Typography

- **Sans-serif (primary):** `'proxima-nova', Calibri, -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, 'Helvetica Neue', Arial, sans-serif`
- **Serif (accent):** `'garamond-premier-pro', 'Times New Roman', Georgia, serif`
- **Monospace:** `'Fira Code', 'Monaco', 'Consolas', 'Liberation Mono', monospace`

Adobe Fonts (Proxima Nova) load via CDN. If unavailable, the fallback stack applies automatically.

## Size Reference

| Element | Font Size |
|---------|-----------|
| Poster title | 72pt |
| Poster subtitle | 30pt |
| Author bar | 22pt |
| Pillar title | 40pt |
| Pillar subtitle | 22pt |
| h3 section headers | 20pt |
| Body text (content card) | 20pt |
| List items | 18pt |
| Stat box number | 40pt |
| Stat box label | 16pt |
| Footer | 18pt |

## Layout Tips

1. **Content must fit 24" height.** The poster does not scroll or paginate. If content overflows, reduce text or remove components.

2. **Columns are independent flex containers.** Content in one column cannot directly influence the height of elements in another column. Accept that h3 headers across columns may not align perfectly unless content above them is carefully balanced.

3. **Use `margin-top: auto`** on the last element in a column to push it to the bottom (the definition-box and qr-box do this by default).

4. **The middle column** gets the class `column-center` for potential future styling hooks, but currently has no special CSS.

5. **To add a 4th footer field**, add another `<span>` to the footer. All spans use `flex: 1` with text-align rules (first: left, second: center, last: right).

6. **Logo containers**: Use `.no-bg` on `.logo-left` or `.logo-right` to remove the white background box (useful for reverse/transparent logos).

7. **Poster background** is `#EFF1F3` (light gray). Content cards are white. This contrast helps the cards "pop" off the canvas.

## File Structure

```
program-poster/
├── template.qmd                  ← Main poster file
├── infosci-program-poster.scss   ← All styles
├── assets/
│   ├── scss/
│   │   └── _ua-colors.scss       ← Symlink to shared colors (create on setup)
│   ├── infosci-logo-reverse.png  ← White logo for dark header
│   └── ua-logo-white.png         ← UA block logo (white)
├── POSTER-GUIDE.md               ← This file
└── README.md                     ← Human-readable quick start
```

## Customization Patterns

### Changing the number of columns

Edit the `.poster-body` grid in the SCSS and add/remove `.column` divs in the QMD:

- **2 columns:** `grid-template-columns: 1fr 1fr`
- **4 columns:** `grid-template-columns: 1fr 1fr 1fr 1fr`

### Changing poster dimensions

Edit `.poster` in SCSS (`width` and `height`) and the `@page` rule in the print media query. Common sizes:

- 48" x 36" (large conference)
- 36" x 24" (standard, default)
- 42" x 30" (mid-size)

### Rebranding for a different unit

1. Replace logo files in `assets/`
2. Edit `_ua-colors.scss` color variables (or override in the main SCSS)
3. Update footer text in the QMD

### Adding custom components

Define new CSS classes in the SCSS file following the existing pattern:

1. Choose a semantic class name (e.g., `.timeline-box`)
2. Set background, border, padding, font-size, border-radius
3. Use UA color variables for consistency
4. Add the HTML structure in the QMD inside a ```` ```{=html} ```` block
