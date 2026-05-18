---
name: quarto-book
description: Technical knowledge for Quarto book operations, configuration, and deployment for the Esteios project.
---

# Quarto Book Technical Guide

## Project Configuration

### Current State
- **Project type**: `website` (for placeholder page)
- **Output directory**: `_site`
- **Deployment**: Manual-only via GitHub Actions
- **Live URL**: https://bmhash.github.io/esteios/

### Two Modes

#### Placeholder Mode (Current)
- Project type: `website`
- Output: `_site/`
- `.quartoignore` active (excludes chapters, data, fragments, sources)
- Only `index.qmd` published with "Paciência" centered
- No navigation, no sidebar, no TOC

#### Full Book Mode (For Publishing)
- Project type: `book`
- Output: `_book/`
- `.quartoignore` removed
- All 15 chapters published with navigation
- Full book structure with three circles/parts

## Key Files

### `_quarto.yml`
Main configuration file. Controls:
- Project type (website vs book)
- Output directory
- Book metadata (title, author, language)
- Chapter structure and organization
- Theme and styling
- Format options (HTML, PDF, ePub)

### `.quartoignore`
Lists files/directories to exclude from rendering:
```
chapters/
data/
fragments/
sources/
```
Remove this file to publish the full book.

### `index.qmd`
Landing page. Two versions:
- **Placeholder**: Minimal HTML with "Paciência" centered
- **Full book**: Introduction letter to daughter

## Quarto Commands

### Local Development
```bash
# Preview with auto-refresh
quarto preview

# Render to HTML
quarto render --to html

# Render specific file
quarto render index.qmd --to html

# Check Quarto version
quarto --version
```

### Output Formats
```bash
# HTML only (current)
quarto render --to html

# PDF (requires TinyTeX)
quarto install tinytex
quarto render --to pdf

# ePub
quarto render --to epub

# All formats
quarto render
```

## Theme & Styling

### Current Theme
- **Base**: Bootswatch `litera` theme
- **Custom typography**: `styles/typography.scss`
  - Font: Crimson Text (serif)
  - Readable size: 1.1rem
  - Generous line height: 1.75

### Custom CSS
- `styles/minimal.css` — Hides navigation for placeholder page
- `styles/landing.css` — Additional layout resets
- `styles/typography.scss` — Font and spacing overrides

## Deployment

### GitHub Actions Workflow
File: `.github/workflows/quarto-publish.yml`

**Trigger**: Manual only (`workflow_dispatch`)
- Never runs automatically on push
- Must be triggered manually via CLI or GitHub UI

**Steps**:
1. Checkout repository
2. Setup Quarto
3. Render to HTML
4. Upload artifact (from `_site` or `_book`)
5. Deploy to GitHub Pages

### Manual Deployment
```bash
# Via GitHub CLI
gh workflow run "Publish Quarto Book to GitHub Pages"

# Check status
gh run list --workflow=quarto-publish.yml --limit 1

# Via GitHub web UI
# Actions → Publish Quarto Book to GitHub Pages → Run workflow
```

## Switching Modes

### Placeholder → Full Book
Use `/publish-book` workflow:
1. Remove `.quartoignore`
2. Change `_quarto.yml`: website → book, `_site` → `_book`
3. Restore introduction in `index.qmd`
4. Update workflow artifact path
5. Render, commit, deploy

### Full Book → Placeholder
1. Create `.quartoignore` with exclusions
2. Change `_quarto.yml`: book → website, `_book` → `_site`
3. Replace `index.qmd` with minimal placeholder
4. Update workflow artifact path
5. Render, commit, deploy

## Troubleshooting

### Build Fails
- Check `_quarto.yml` is valid YAML (indentation matters)
- Verify all referenced chapter files exist
- Check for syntax errors in `.qmd` files
- Run `quarto render --to html` locally to see detailed errors

### Preview Not Working
- Check port isn't already in use
- Verify Quarto is installed: `quarto --version`
- Try `quarto render` first to catch errors

### Deployment Fails
- Check GitHub Actions logs
- Verify artifact path matches output directory
- Ensure GitHub Pages is enabled in repo settings
- Check workflow has proper permissions

## Book Structure

### Three Circles Organization
```yaml
book:
  chapters:
    - index.qmd
    - part: "Círculo I — O Eu Interior (Logos)"
      chapters:
        - chapters/01-nao-es-o-que-te-acontece.qmd
        # ... more Logos chapters
    - part: "Círculo II — Com os Outros (Ethos)"
      chapters:
        - chapters/03-a-coragem-nao-e-a-ausencia-do-medo.qmd
        # ... more Ethos chapters
    - part: "Círculo III — No Mundo (Cosmos)"
      chapters:
        - chapters/08-sobre-o-fracasso.qmd
        # ... more Cosmos chapters
```

### Chapter File Format
```markdown
---
title: "Chapter Title"
---

::: {.epigraph}
*«Quote»*

— Author, *Work*
:::

::: {.concept}
**Greek Term** — Definition
:::

Chapter prose here...
```

## References

- Quarto documentation: https://quarto.org/docs/books/
- Bootswatch themes: https://bootswatch.com/
- GitHub Pages: https://pages.github.com/
