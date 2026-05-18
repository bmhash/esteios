---
description: Manually publish the current state to GitHub Pages (placeholder or full book)
---

# Publish Workflow

1. Verify local build succeeds:
   - Run `quarto render --to html`
   - Check for any errors in the output
2. Check for uncommitted changes:
   - Run `git status`
   - If there are changes, commit them first
3. Push to GitHub:
   - Run `git push`
4. Trigger manual deployment:
   - Run `gh workflow run "Publish Quarto Book to GitHub Pages"`
5. Monitor deployment:
   - Run `gh run list --workflow=quarto-publish.yml --limit 1`
   - Wait for workflow to complete (usually 1-2 minutes)
6. Print the live URL:
   - https://bmhash.github.io/esteios/
7. Remind the user:
   - Current state: placeholder page ("Paciência") if `.quartoignore` is active
   - To publish full book: use `/publish-book` workflow
