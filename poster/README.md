# InfoSci Poster Template

UA-branded conference poster (36" × 24" landscape) using HTML/CSS.

## Quick Start

```bash
quarto use template ryanstraight/azinfosci-templates/poster
quarto render template.qmd
```

Open the HTML file in a browser and use **Print → Save as PDF** for the final poster.

## Features

- 36" × 24" landscape format (standard conference size)
- Three-column layout with CSS Grid
- UA brand colors (imported from shared SCSS)
- Section boxes with colored headers
- Stat highlight boxes
- Callout boxes
- QR code placeholder
- Print-optimized CSS

## Customizing Your Poster

### 1. Edit YAML Metadata

Find the `★ EDIT YOUR POSTER INFO HERE ★` section at the top:

```yaml
title: "Your Research Title"
subtitle: "Subtitle or Grant Name"
conference: "Conference Name 2025"

# Use superscript numbers (¹²³) for affiliations
authors: "**First Author**¹, Second Author¹², Third Author²"
affiliations: "¹College of Information Science, UA    ²Department of Computer Science, UA"

contact-email: "author@arizona.edu"
```

### 2. Add Your Logos

Place logo files in an `assets/` folder and update the image paths in the HTML header section:

```html
<img src="assets/your-logo.png" alt="Logo description">
```

Download UA logos from [UA Brand Resources](https://brand.arizona.edu/brand-assets).

### 3. Edit Content Sections

The poster uses standard Quarto markdown. Edit section content directly:

```markdown
## Introduction

Your introduction text here.

- Bullet points work normally
- Add your research question
```

## CSS Classes

### Stat Boxes

Display key metrics prominently:

```markdown
::: {.stat-boxes}
::: {.stat-box}
**94%**

Success Rate
:::

::: {.stat-box}
**N=500**

Sample Size
:::
:::
```

### Callout Box

Highlight important information:

```markdown
::: {.callout-note}
## Research Question
Your key question here.
:::
```

### Conclusions Box

Emphasize key takeaways:

```markdown
::: {.conclusions-box}
**Key Takeaways:**

1. First conclusion
2. Second conclusion
:::
```

### Figure Placeholder

Mark where figures should go:

```markdown
::: {.figure-placeholder}
**INSERT FIGURE HERE**

*Figure 1.* Description
:::
```

Replace with actual figures using standard markdown:

```markdown
![Figure 1. Description](figures/your-chart.png)
```

### QR Code Box

```markdown
::: {.qr-box}
::: {.qr-content}
**Scan for More**

Paper, data, & materials

[yourwebsite.arizona.edu]{.qr-url}
:::
::: {.qr-placeholder}
QR CODE
:::
:::
```

## Column Layout

The poster uses a three-column CSS Grid layout. Content is divided using raw HTML blocks:

```markdown
```{=html}
<div class="column">
```

## Column 1 Content

```{=html}
</div>
<div class="column">
```

## Column 2 Content

```{=html}
</div>
```
```

## Printing to PDF

1. Render the poster: `quarto render template.qmd`
2. Open the HTML file in Chrome or Firefox
3. **Print** (Ctrl+P / Cmd+P)
4. Set paper size to **36" × 24"** (or custom dimensions)
5. Set orientation to **Landscape**
6. Enable **Background graphics** in print options
7. **Save as PDF**

Most print shops accept PDF files at this standard poster size.

## Troubleshooting

**Colors not printing?**

Enable "Background graphics" or "Print backgrounds" in your browser's print dialog.

**Fonts look different in PDF?**

The template uses Arial as a fallback. For exact UA brand fonts (Proxima Nova), ensure Adobe Fonts are loaded or use a browser that supports embedded fonts.

**Content overflowing columns?**

Reduce text or move sections. The poster is designed for concise content.
