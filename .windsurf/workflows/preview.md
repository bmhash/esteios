---
description: Start local preview server to view the book while writing
---

# Preview Workflow

1. **Start Quarto preview server:**
   ```bash
   quarto preview
   ```
   - This runs in non-blocking mode
   - Server auto-refreshes when files change

2. **Print local URL:**
   - http://localhost:XXXX (Quarto will assign a port)
   - Usually http://localhost:4200 or similar

3. **Remind the user:**
   - Preview updates automatically when you save `.qmd` files
   - Press Ctrl+C in terminal to stop the server
   - Preview shows the current state (placeholder or full book depending on config)
   - Changes are local only — not published until you run `/publish`

4. **Troubleshooting:**
   - If port is already in use, Quarto will try another port
   - If preview fails, check `quarto render --to html` for errors
   - Check that `_quarto.yml` is valid YAML
