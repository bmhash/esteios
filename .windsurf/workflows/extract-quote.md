---
description: Extract and verify a quote from Meditations or Paideia source PDFs
---

# Extract Quote Workflow

This workflow helps you find, extract, and verify quotes from the source texts.

1. **Ask the user:**
   - Which book: Meditations or Paideia?
   - What theme/concept are you looking for?
   - Any specific keywords or context?

2. **Search the source PDF:**
   - For Meditations: `data/Marcus Aurelius - The Meditations of Marcus Aurelius.pdf`
   - For Paideia: `data/Werner Jaeger-Paideia.pdf`
   - Use grep or PDF search tools to locate relevant passages
   - Note: Meditations is in English, Paideia is in Brazilian Portuguese

3. **Extract the passage:**
   - Read the relevant section from the PDF
   - Extract the exact quote with context
   - Note the book/section/page number for citation

4. **Format for chapter insertion:**
   ```markdown
   ::: {.epigraph}
   *«Quote in original language.»*
   
   — Author, *Work*, Book/Section
   :::
   ```

5. **Verify accuracy:**
   - Double-check the quote is exact (no paraphrasing)
   - Verify attribution is correct
   - Ensure translation (if needed) preserves meaning

6. **Optionally add to index:**
   - Ask if this quote should be added to the source-texts skill index
   - If yes, add to `.windsurf/skills/source-texts/meditations-index.md` or `paideia-index.md`
   - Organize by theme for future quick reference

7. **Provide the formatted quote to the user:**
   - Ready to paste into the chapter
   - Include citation information
   - Note any translation considerations (especially for Paideia quotes)

**Example output:**
```markdown
::: {.epigraph}
*«You have power over your mind — not outside events. Realize this, and you will find strength.»*

— Marcus Aurelius, *Meditations*, Book VII
:::
```
