# azinfosci-templates

> **Work in Progress**: This template collection is under active development. Some templates may have incomplete styling or missing features. Contributions and feedback welcome!

Quarto document templates with University of Arizona College of Information Science branding.

## Examples

See rendered examples of each template:

**PDF Templates** (viewable directly in GitHub):

- [Letter](examples/letter.pdf) - Formal correspondence
- [Memo](examples/memo.pdf) - Internal memoranda
- [Report](examples/report.pdf) - Formal reports with title page
- [Working Paper](examples/working-paper.pdf) - Academic preprints
- [Agenda](examples/agenda.pdf) - Meeting agendas

**HTML Templates** (viewable on GitHub Pages):

- [Document](https://ryanstraight.github.io/azinfosci-templates/document.html) - Training materials and documentation
- [Assignment](https://ryanstraight.github.io/azinfosci-templates/assignment.html) - Course assignments
- [Lab Notebook](https://ryanstraight.github.io/azinfosci-templates/lab-notebook.html) - Research documentation
- [One-Pager](https://ryanstraight.github.io/azinfosci-templates/one-pager.html) - Executive summaries
- [Poster](https://ryanstraight.github.io/azinfosci-templates/poster.html) - 36"x24" conference poster
- [Presentation](https://ryanstraight.github.io/azinfosci-templates/presentation.html) - Reveal.js slides

Browse all examples: [ryanstraight.github.io/azinfosci-templates](https://ryanstraight.github.io/azinfosci-templates/)

## Prerequisites

- [Quarto](https://quarto.org/) >= 1.4.0
- For presentation QR codes: `jmbuhr/quarto-qrcode` extension (install instructions below)
- For persistent QR codes in presentations: R with `qrcode` package (optional)

## Installation

Use `quarto use template` to scaffold any template:

```bash
# Presentation (revealjs slides)
quarto use template ryanstraight/azinfosci-templates/presentation

# Conference poster (HTML, 36x24")
quarto use template ryanstraight/azinfosci-templates/poster

# General document (HTML)
quarto use template ryanstraight/azinfosci-templates/document

# Formal letter
quarto use template ryanstraight/azinfosci-templates/letter

# Internal memo
quarto use template ryanstraight/azinfosci-templates/memo

# Course assignment/handout
quarto use template ryanstraight/azinfosci-templates/assignment

# Meeting agenda
quarto use template ryanstraight/azinfosci-templates/agenda

# One-page fact sheet
quarto use template ryanstraight/azinfosci-templates/one-pager

# Research lab notebook
quarto use template ryanstraight/azinfosci-templates/lab-notebook

# Formal report
quarto use template ryanstraight/azinfosci-templates/report

# Academic working paper
quarto use template ryanstraight/azinfosci-templates/working-paper
```

## Adding UA Logos (Required)

Due to trademark restrictions, official UA logos **cannot be distributed** with these templates. You must add them manually after scaffolding a template.

### Step 1: Download Logos

1. Go to [UA Brand Resources](https://brand.arizona.edu/brand-assets) (requires UA NetID login)
2. Navigate to **Logos** → **College of Information Science** (or your unit)
3. Download the logo files you need

### Step 2: Prepare Logo Files

Templates expect specific filenames in the `assets/` folder:

| Template | Required File | Description |
|----------|---------------|-------------|
| Most templates | `assets/infosci-logo.png` | Standard logo (dark text on light background) |
| Poster, Presentation | `assets/infosci-logo-reverse.png` | White/light logo for dark backgrounds |
| Poster | `assets/ua-logo-white.png` | UA block logo (white) for header |

### Step 3: Place Files

After running `quarto use template`, copy your logo files into the `assets/` folder:

```
your-project/
├── template.qmd
├── assets/
│   ├── infosci-logo.png      ← Add this
│   ├── infosci-logo-reverse.png  ← For poster/presentation
│   └── ua-logo-white.png     ← For poster
└── ...
```

### Logo Specifications

- **Format**: PNG with transparent background preferred
- **Resolution**: At least 300 DPI for print templates (poster, letter, memo)
- **Variants needed**:
  - Standard (dark logo for light backgrounds)
  - Reverse (light/white logo for dark backgrounds) - poster and presentation

### If You Don't Have Access to UA Logos

- Templates will render with placeholder text where logos would appear
- Contact your department's communications office for logo files
- For non-UA use, replace logo references in the SCSS/template files with your own branding

## Templates

### presentation

Revealjs slides with UA branding. Features:

- 1920x1080 widescreen format
- Custom SCSS theme with UA colors
- "Follow Along" QR code slide
- Section divider slides (blue/red backgrounds)
- Quote and emphasis box styles
- Speaker notes support
- APA citation support

**Setup:**

```bash
quarto use template ryanstraight/azinfosci-templates/presentation
quarto add jmbuhr/quarto-qrcode  # Required for QR code slides
```

Render: `quarto render presentation.qmd`

### poster

Conference poster using HTML/CSS with print optimization. Features:

- 36" x 24" landscape format
- Three-column CSS Grid layout
- Section boxes with UA blue headers
- Stat highlight boxes
- Callout boxes
- QR code placeholder
- Print-optimized (use browser Print → Save as PDF)

Render: `quarto render template.qmd` then print to PDF from browser.

### document

Versatile template for training materials, protocols, and documentation.

- Clean typography with UA colors
- Left-side table of contents
- Callout boxes, code blocks, diagrams

### letter

Formal correspondence with UA letterhead styling.

- Professional header layout
- Signature block
- Date formatting

### memo

Internal memoranda with To/From/Date/Subject format.

- UA branded header
- Standard memo structure

### assignment

Course assignments and handouts.

- Due date display
- Grading rubric support
- Clean formatting for student distribution

### agenda

Meeting agendas with YAML-driven structure.

- Attendee list from YAML
- Agenda items with time allocations
- Action item tracking

### one-pager

Executive summaries and fact sheets.

- Metrics display boxes
- Key points formatting
- Contact information block

### lab-notebook

Research documentation with date-based entries.

- Entry headers by date
- Observation and analysis sections
- Progressive documentation style

### report

Formal reports with title page.

- Table of contents
- Numbered sections
- Executive summary support

### working-paper

Academic preprints and working papers.

- Abstract and keywords
- Author affiliations with ORCID
- Bibliography support (APA)
- Numbered sections

## Customization

Each template includes:

- `template.qmd` or `template.typ` - main document
- `*.scss` - theme customization (where applicable)
- `assets/` - logos, CSL files, images
- `references.bib` - bibliography (where applicable)

Edit the YAML front matter to customize metadata, then modify content as needed.

## UA Brand Colors

Templates use official UA brand colors:

- **Arizona Blue**: `#0C234B`
- **Arizona Red**: `#AB0520`
- **Oasis**: `#378DBD`
- **Sky**: `#81D3EB`
- **Cool Gray**: `#E2E9EB`

See the full palette at [UA Brand Colors](https://brand.arizona.edu/applying-the-brand/colors).

## Troubleshooting

### Logo not appearing

1. Ensure you downloaded logos from [UA Brand Resources](https://brand.arizona.edu/brand-assets)
2. Verify filenames match exactly (case-sensitive): `infosci-logo.png`
3. Check the file is in your template's `assets/` folder
4. For poster: ensure you have both `infosci-logo-reverse.png` and `ua-logo-white.png`

### Presentation QR codes not rendering

Install the QR code extension in your project directory:

```bash
quarto add jmbuhr/quarto-qrcode
```

### Fonts look different than expected

The templates use Adobe Fonts (Proxima Nova) which require internet access. If fonts appear as Arial/system fonts:

- Check internet connectivity
- Some institutional networks block Adobe CDNs
- Templates will fall back to system fonts automatically

### Poster colors not printing

When printing the poster to PDF, enable "Background graphics" or "Print backgrounds" in your browser's print dialog to preserve the colored headers and boxes.

### "Extension not found" errors

Run the template command from the correct directory and ensure the extension installed:

```bash
quarto list extensions
```

## License

Templates are provided for use by University of Arizona faculty, staff, and students. UA trademarks and brand assets are subject to [UA Brand Guidelines](https://brand.arizona.edu/).

## Related

- [azinfosci-thesis](https://github.com/ryanstraight/azinfosci-thesis) - Quarto extension for UA-branded thesis/dissertation formatting
