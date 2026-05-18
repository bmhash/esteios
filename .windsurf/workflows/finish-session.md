---
description: End a writing session — commit, log progress, update status
---

# Finish Session Workflow

1. Run `git status` to check for uncommitted changes
2. If there are modified `.qmd` files, show word count for each:
   - Use `wc -w` to count words
   - Estimate reading time (250 words/minute)
3. If there are uncommitted changes, commit with proper message format:
   - `draft(capítulo-X): breve descrição` for chapter drafts
   - `feat(capítulo-X): título` for completed chapters
   - `chore: descrição` for configuration or structure changes
4. Push to GitHub: `git push`
   - Note: This does NOT trigger deployment (manual-only)
5. Summarize what was accomplished:
   - Which chapters were worked on
   - Word count added
   - What to tackle next session
6. Remind: To publish changes, use `/publish` (placeholder) or `/publish-book` (full book)
