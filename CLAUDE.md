# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a personal academic website for Dr. Edmond Kwan, built using Quarto. The site showcases research, publications, presentations, and professional information for a genitourinary cancer medical oncologist and research scientist.

## Build and Development Commands

**Render the entire website:**
```bash
quarto render
```

**Preview the website locally:**
```bash
quarto preview
```

**Render a single page:**
```bash
quarto render index.qmd
# or
quarto render publications.qmd
```

## Project Structure

- **Source files** (`.qmd`): Main content files in the root directory
  - `index.qmd` - About/home page
  - `research.qmd` - Research interests, grants, committees
  - `publications.qmd` - Selected publications with images
  - `presentations.qmd` - Embedded videos and presentation links
  - `cv-archive.qmd` - CV archive page

- **Configuration**: `_quarto.yml` - Site-wide settings, navigation, theme (flatly), and output directory (`docs/`)

- **Styling**: `styles.css` - Custom CSS for rounded images, publication formatting, icon lists, and typography

- **Output**: `docs/` - Rendered HTML output (this is what gets published to GitHub Pages)

- **Extensions**: `_extensions/` - Quarto extensions for FontAwesome and Academicons icons
  - `fontawesome/` - Font Awesome icons (e.g., `{{< fa brands twitter >}}`)
  - `schochastics/academicons/` - Academic icons (e.g., `{{< ai google-scholar >}}`)

## Key Architecture Patterns

**Grid Layout System**: Pages use Quarto's grid system extensively:
```qmd
:::: {.grid}
::: {.g-col-3}
[Left column content - typically images]
:::
::: {.g-col-8}
[Right column content - typically text]
:::
::::
```

**Custom CSS Classes**:
- `.roundedimg` - Circular profile images
- `.publication-title` - Styled red publication titles
- `.publication-author` - Smaller author text
- `.icon-list` - Icon + link combinations

**Icon Usage**: The site uses two icon extension systems. Use the appropriate shortcode syntax:
- FontAwesome: `{{< fa brands twitter >}}`
- Academicons: `{{< ai google-scholar >}}`

## Important Notes

- Output directory is `docs/` (configured for GitHub Pages)
- Theme is "flatly" (can be changed in `_quarto.yml`)
- Table of contents is disabled globally (`toc: false`)
- Images are stored in `docs/images/` and PDFs in `docs/pdfs/`
- The `.nojekyll` file prevents GitHub from processing the site with Jekyll
