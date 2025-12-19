# InfoSci Presentation Template

UA-branded Revealjs slides for conferences, lectures, and talks.

## Quick Start

```bash
quarto use template ryanstraight/azinfosci-templates/presentation
quarto add jmbuhr/quarto-qrcode
quarto render presentation.qmd
```

## Features

- 1920x1080 widescreen format
- UA brand colors and typography
- "Follow Along" QR code slide
- Section divider slides (blue/red)
- Quote boxes, emphasis boxes, concept comparisons
- Speaker notes
- APA citations

## Required Files

After scaffolding, your directory should contain:

```
your-project/
├── presentation.qmd      # Main slides file
├── infosci-theme.scss    # UA styling
├── references.bib        # Bibliography
├── _extensions/          # QR code extension (after quarto add)
└── assets/
    ├── infosci-logo.png       # ⚠ Add from UA Brand
    ├── infosci-logo-reverse.png  # ⚠ Add from UA Brand
    └── apa.csl
```

## YAML Options

### Essential (edit these)

```yaml
subtitle: |
    **Your Presentation Title**<br />
    Event or Conference Name

author:
  - name: Your Name
    email: youremail@arizona.edu

footer: "Your Name | Event Name | Date"
```

### Optional

```yaml
params:
  follow_along_url: "https://slides-url.com"  # QR code destination
  speaker_image: "assets/headshot.png"        # Or "" for icon
  speaker_title: "PhD"                        # Shown after name
  show_persistent_qr: true                    # Corner QR on all slides
  website_url: "https://..."
  github_url: "https://github.com/..."
  linkedin_url: "https://linkedin.com/in/..."
```

## CSS Classes

Use these in your slides:

```markdown
::: {.quote-box}
"Quoted text with left border"
:::

::: {.emphasis-box}
**Key Point:** Important information
:::

::: {.concept-box .blue}
Traditional Approach
:::

::: {.highlight-red}
Emphasized text in UA Red
:::
```

## Section Dividers

Create full-screen section headers:

```markdown
# {data-state="no-logo" background-color="#0C234B"}

[SECTION TITLE]{.r-fit-text}
```

Use `#0C234B` (UA Blue) or `#AB0520` (UA Red).

## Logos

Download from [UA Brand Resources](https://brand.arizona.edu/brand-assets) (requires NetID):

- `infosci-logo.png` - Main logo for title slide
- `infosci-logo-reverse.png` - White version for dark backgrounds
