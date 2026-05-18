---
description: Start a new writing session — re-establish context and pick up where we left off
---

# New Session Workflow

1. Read `_quarto.yml` to understand the current book structure
2. Run `git log --oneline -5` to see recent commits and activity
3. Run `git status` to check for any uncommitted work
4. Check which chapters have content vs. are still templates:
   - Look for `<!-- Escreve aqui` markers in chapter files
   - Note which chapters have been drafted
5. Summarize:
   - What chapters are complete or in progress
   - What's next according to the philosophical plan
   - Current deployment state (placeholder vs. full book)
6. Ask the user what they'd like to work on today
7. If starting a new chapter, offer to use `/new-chapter` workflow
8. If continuing an existing chapter, open the relevant file for context
