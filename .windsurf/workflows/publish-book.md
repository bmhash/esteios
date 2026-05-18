---
description: Switch from placeholder to full book publication and deploy to GitHub Pages
---

# Publish Full Book Workflow

This workflow transitions from the placeholder page to publishing the complete book.

1. **Remove `.quartoignore`:**
   ```bash
   rm .quartoignore
   ```

2. **Update `_quarto.yml` from website to book mode:**
   - Change `project: type: website` to `type: book`
   - Change `output-dir: _site` to `output-dir: _book`
   - Add back the full book structure with all chapters organized by circles
   - Update format section to include book-specific settings (toc, theme, etc.)
   - Reference the configuration in README.md for the complete structure

3. **Restore `index.qmd` with the introduction:**
   - Replace the placeholder content with the original introduction letter
   - The original content is preserved in Git history (commit before placeholder)
   - Use `git log --all --full-history -- index.qmd` to find it
   - Or recreate based on the philosophical plan

4. **Update GitHub Actions workflow:**
   - In `.github/workflows/quarto-publish.yml`
   - Change artifact path from `_site` to `_book`

5. **Test the build locally:**
   ```bash
   quarto render --to html
   ```
   - Verify all chapters render correctly
   - Check for any errors or warnings

6. **Commit all changes:**
   ```bash
   git add .
   git commit -m "feat: publish full book - switch from placeholder to complete Esteios"
   git push
   ```

7. **Trigger deployment:**
   ```bash
   gh workflow run "Publish Quarto Book to GitHub Pages"
   ```

8. **Monitor and verify:**
   - Wait for deployment to complete (2-3 minutes)
   - Visit https://bmhash.github.io/esteios/
   - Verify the full book is visible with navigation, chapters, and content

9. **Remind the user:**
   - The book is now publicly accessible
   - Future updates: write → commit → push → `/publish`
   - To unpublish: restore `.quartoignore` and placeholder `index.qmd`
