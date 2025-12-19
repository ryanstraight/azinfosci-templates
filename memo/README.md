# InfoSci Memo Template

An internal memorandum template with University of Arizona College of Information Science branding.

## Usage

```r
library(azinfosci)
use_infosci_memo("department_update.qmd")
```

## Features

- UA-branded header with logo and "MEMORANDUM" title
- Standard memo fields: TO, FROM, DATE, RE
- Automatic date insertion
- UA brand colors (Arizona Blue, Arizona Red)

## Customization

1. **Memo fields**: Edit the TO, FROM, and RE fields in the Typst header block (lines 43-50)
2. **CC line**: Uncomment line 68 to add carbon copy recipients
3. **Body**: Replace placeholder text with your memo content

## Output

Renders to PDF via Typst. Use:

```bash
quarto render my_memo.qmd
```

## Assets Required

- `assets/infosci-logo.png` - UA InfoSci logo (placeholder provided)
