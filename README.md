# azinfosci-templates

Quarto document templates with University of Arizona College of Information Science branding.

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

# General document (HTML/PDF/DOCX)
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

- Multi-format output (HTML, PDF, DOCX)
- Clean typography with UA colors
- Table of contents support

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

## Logo Setup

Due to trademark restrictions, UA logos are not distributed with these templates.

1. Download logos from [UA Brand Resources](https://brand.arizona.edu/brand-assets) (requires NetID)
2. Place in the `assets/` folder of your scaffolded template
3. See `assets/logos/README.md` for required filenames

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

## Troubleshooting

### Logo not appearing

1. Ensure you downloaded logos from [UA Brand Resources](https://brand.arizona.edu/brand-assets)
2. Verify filenames match exactly (case-sensitive): `infosci-logo.png`
3. Check the file is in your template's `assets/` folder

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

- [azinfosci](https://github.com/ryanstraight/azinfosci) - R package with ggplot2 themes and UA color utilities
