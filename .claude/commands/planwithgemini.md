---
allowed-tools: Bash(npx:*), Bash(gemini:*), Bash(tee:*), Bash(cat:*), Bash(echo:*)
description: Generate a high‑level implementation or refactor plan with Codefetch (via npx ‑y) and Gemini CLI, then continue in Claude.
---


## Context setup (automatic)

!`npx -y codefetch --include-dir src --exclude-dir node_modules,dist,build -o context.md --tree > /dev/null`
!`echo "🔍  Collected context in context.md"`

## Gemini plan

!`gemini -p "@context.md Provide a detailed plan to $ARGUMENTS" | tee plan.md`

## Your task

Gemini’s draft plan (shown above and saved to **plan.md**) is now ready.  

1. **Review & refine** the steps as needed.  
2. Proceed to implement the changes, updating code & tests.  
3. Feel free to ask follow‑up questions at any time.
