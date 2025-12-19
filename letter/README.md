# InfoSci Letter Template

A professional letter template with University of Arizona College of Information Science branding.

## Usage

```r
library(azinfosci)
use_infosci_letter("my_letter.qmd")
```

## Features

- UA-branded header with logo and contact information
- Georgia typeface for professional appearance
- Automatic date insertion
- Signature image support (optional)

## Customization

1. **Header contact info**: Edit lines 22-27 in the Typst header block
2. **Signature**: Add `signature.png` to the `assets/` folder and uncomment line 54
3. **Body**: Replace placeholder text with your letter content

## Output

Renders to PDF via Typst. Use:

```bash
quarto render my_letter.qmd
```

## Assets Required

- `assets/infosci-logo.png` - UA InfoSci logo (placeholder provided)
- `assets/signature.png` - Your signature image (optional)
