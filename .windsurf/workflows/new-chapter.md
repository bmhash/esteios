---
description: Scaffold a new chapter with proper structure and metadata
---

# New Chapter Workflow

1. **Ask the user for chapter details:**
   - Chapter number (1-15)
   - Chapter title in Portuguese
   - Which circle: Logos (I), Ethos (II), or Cosmos (III)
   - Stoic anchor concept (e.g., "acceptance", "virtue", "mortality")
   - Greek term and its meaning (e.g., "apatheia — serenidade")

2. **Create the chapter file:**
   - Filename: `chapters/XX-slug.qmd` (number + URL-friendly slug)
   - Add frontmatter with title
   - Add epigraph placeholder with comment to add Stoic quote
   - Add concept box with Greek term and definition
   - Add prose section with writing prompt comment

3. **Add to `_quarto.yml`:**
   - Insert under the correct circle/part
   - Maintain the order within the circle
   - Verify the YAML structure is valid

4. **Commit the scaffold:**
   ```bash
   git add chapters/XX-slug.qmd _quarto.yml
   git commit -m "feat: scaffold capítulo XX — título"
   ```

5. **Suggest next steps:**
   - Find a relevant epigraph using `/extract-quote`
   - Start writing the prose
   - Preview locally with `quarto preview`

6. **Example chapter structure:**
   ```markdown
   ---
   title: "Título do Capítulo"
   ---

   ::: {.epigraph}
   *«Quote goes here.»*
   
   — Author, *Work*
   :::

   ::: {.concept}
   **Greek Term** (*transliteration*) — Definition in Portuguese
   :::

   <!-- Escreve aqui o conteúdo do capítulo -->
   ```
