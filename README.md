# azinfosci-templates

[![Quarto](https://img.shields.io/badge/Quarto-%E2%89%A51.4-blue?logo=quarto)](https://quarto.org/)
[![Templates](https://img.shields.io/badge/Templates-11-AB0520)](https://ryanstraight.github.io/azinfosci-templates/)
[![GitHub Pages](https://img.shields.io/github/deployments/ryanstraight/azinfosci-templates/github-pages?label=Examples&logo=github)](https://ryanstraight.github.io/azinfosci-templates/)
[![License](https://img.shields.io/badge/License-UA_Brand_Guidelines-0C234B)](https://brand.arizona.edu/)

**Professional Quarto templates with University of Arizona College of Information Science branding.**

Create polished academic documents, presentations, and reports with consistent UA styling — no design work required.

> [!NOTE]
> This template collection is under active development. Some templates may have incomplete styling or missing features. Contributions and feedback welcome!

## Quick Start

```bash
quarto use template ryanstraight/azinfosci-templates/presentation
```

Then add your [UA logos](#adding-ua-logos-required) to the `assets/` folder and render.

## Template Gallery

| Template | Format | Description | Example |
|:---------|:------:|:------------|:-------:|
| **presentation** | HTML | Reveal.js slides with 1920×1080 widescreen, QR codes, section dividers | [View](https://ryanstraight.github.io/azinfosci-templates/presentation.html) |
| **poster** | HTML | 36"×24" conference poster with three-column layout | [View](https://ryanstraight.github.io/azinfosci-templates/poster.html) |
| **document** | HTML | Training materials and documentation with TOC | [View](https://ryanstraight.github.io/azinfosci-templates/document.html) |
| **assignment** | HTML | Course assignments with due dates and rubrics | [View](https://ryanstraight.github.io/azinfosci-templates/assignment.html) |
| **lab-notebook** | HTML | Research documentation with date-based entries | [View](https://ryanstraight.github.io/azinfosci-templates/lab-notebook.html) |
| **one-pager** | HTML | Executive summaries with metrics display | [View](https://ryanstraight.github.io/azinfosci-templates/one-pager.html) |
| **letter** | PDF | Formal correspondence with UA letterhead | [View](examples/letter.pdf) |
| **memo** | PDF | Internal memoranda (To/From/Date/Subject) | [View](examples/memo.pdf) |
| **report** | PDF | Formal reports with title page and TOC | [View](examples/report.pdf) |
| **working-paper** | PDF | Academic preprints with abstract and bibliography | [View](examples/working-paper.pdf) |
| **agenda** | PDF | Meeting agendas with YAML-driven structure | [View](examples/agenda.pdf) |

Browse all examples: **[ryanstraight.github.io/azinfosci-templates](https://ryanstraight.github.io/azinfosci-templates/)**

## Features

- **Official UA brand colors** — Arizona Blue, Arizona Red, and accent palette
- **Multiple formats** — PDF (via Typst), HTML, and Reveal.js presentations
- **One-command setup** — `quarto use template` scaffolds everything you need
- **Fully customizable** — SCSS themes and YAML configuration
- **Citation support** — APA 7th edition with BibTeX integration
- **Data visualization ready** — Mermaid diagrams, code blocks, and R/Python integration

## Prerequisites

- [Quarto](https://quarto.org/) >= 1.4.0
- For presentation QR codes: `jmbuhr/quarto-qrcode` extension
- For persistent QR codes: R with `qrcode` package (optional)

## Installation

Use `quarto use template` to scaffold any template:

```bash
# Presentations
quarto use template ryanstraight/azinfosci-templates/presentation

# Posters
quarto use template ryanstraight/azinfosci-templates/poster

# Documents
quarto use template ryanstraight/azinfosci-templates/document
quarto use template ryanstraight/azinfosci-templates/assignment
quarto use template ryanstraight/azinfosci-templates/lab-notebook
quarto use template ryanstraight/azinfosci-templates/one-pager

# Correspondence
quarto use template ryanstraight/azinfosci-templates/letter
quarto use template ryanstraight/azinfosci-templates/memo

# Reports & Papers
quarto use template ryanstraight/azinfosci-templates/report
quarto use template ryanstraight/azinfosci-templates/working-paper
quarto use template ryanstraight/azinfosci-templates/agenda
```

## Adding UA Logos (Required)

Due to trademark restrictions, official UA logos **cannot be distributed** with these templates. You must add them manually after scaffolding.

### Step 1: Download Logos

1. Go to [UA Brand Resources](https://brand.arizona.edu/brand-assets) (requires UA NetID)
2. Navigate to **Logos** → **College of Information Science** (or your unit)
3. Download the logo files you need

### Step 2: Add Logo Files

Templates expect specific filenames in the `assets/` folder:

| Template | Required File | Description |
|----------|---------------|-------------|
| Most templates | `assets/infosci-logo.png` | Standard logo (dark on light background) |
| Poster, Presentation | `assets/infosci-logo-reverse.png` | White/light logo for dark backgrounds |
| Poster | `assets/ua-logo-white.png` | UA block logo (white) for header |

```
your-project/
├── template.qmd
├── assets/
│   ├── infosci-logo.png           ← Required
│   ├── infosci-logo-reverse.png   ← For poster/presentation
│   └── ua-logo-white.png          ← For poster
└── ...
```

### Logo Specifications

- **Format**: PNG with transparent background
- **Resolution**: 300+ DPI for print templates (poster, letter, memo)

### No UA Access?

- Templates render with placeholder text where logos would appear
- Contact your department's communications office for logo files
- For non-UA use, replace logo references in SCSS/template files with your branding

## UA Brand Colors

Templates use official UA brand colors:

| Color | Hex | Usage |
|-------|-----|-------|
| **Arizona Blue** | `#0C234B` | Primary headers, accents |
| **Arizona Red** | `#AB0520` | Highlights, dividers |
| **Oasis** | `#378DBD` | Links, secondary accents |
| **Sky** | `#81D3EB` | Backgrounds, callouts |
| **Cool Gray** | `#E2E9EB` | Borders, subtle backgrounds |

See the full palette at [UA Brand Colors](https://brand.arizona.edu/applying-the-brand/colors).

## Customization

Each template includes:

| File | Purpose |
|------|---------|
| `template.qmd` | Main document with YAML front matter |
| `*.scss` | Theme customization (where applicable) |
| `assets/` | Logos, CSL files, images |
| `references.bib` | Bibliography (where applicable) |

Edit the YAML front matter to customize metadata, then modify content as needed.

## Troubleshooting

<details>
<summary><strong>Logo not appearing</strong></summary>

1. Ensure you downloaded logos from [UA Brand Resources](https://brand.arizona.edu/brand-assets)
2. Verify filenames match exactly (case-sensitive): `infosci-logo.png`
3. Check the file is in your template's `assets/` folder
4. For poster: ensure you have both `infosci-logo-reverse.png` and `ua-logo-white.png`

</details>

<details>
<summary><strong>Presentation QR codes not rendering</strong></summary>

Install the QR code extension in your project directory:

```bash
quarto add jmbuhr/quarto-qrcode
```

</details>

<details>
<summary><strong>Fonts look different than expected</strong></summary>

Templates use Adobe Fonts (Proxima Nova) which require internet access. If fonts appear as Arial/system fonts:

- Check internet connectivity
- Some institutional networks block Adobe CDNs
- Templates fall back to system fonts automatically

</details>

<details>
<summary><strong>Poster colors not printing</strong></summary>

When printing to PDF, enable "Background graphics" or "Print backgrounds" in your browser's print dialog.

</details>

<details>
<summary><strong>"Extension not found" errors</strong></summary>

Run the template command from the correct directory and verify installation:

```bash
quarto list extensions
```

</details>

## License

Templates are provided for use by University of Arizona faculty, staff, and students. UA trademarks and brand assets are subject to [UA Brand Guidelines](https://brand.arizona.edu/).

## Related

- [azinfosci-thesis](https://github.com/ryanstraight/azinfosci-thesis) — Quarto extension for UA-branded master's thesis formatting
