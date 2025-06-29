---
allowed-tools: Bash(git ls-files:*), Bash(npx codefetch:*), Bash(gemini:*)
description: Draft a high‑level implementation/refactor plan – first derive the optimal Codefetch context from the Git file list, then query Gemini CLI and hand the result back to Claude. Do NOT begin writing or changing application code.
---

CRITICAL RULES: Dont plan or code anything!!

Follow steps:

The list below contains every tracked or untracked source file except those ignored by `.gitignore`, or Git’s default excludes. Claude should use this list to decide which folders/files matters.

!`git ls-files --cached --others --exclude-standard`

1. Analyse the file inventory: and the user’s request (`$ARGUMENTS`).  
2. Choose the minimal yet sufficient context:
   - Which top‑level dirs (`--include-dir`) or specific files (`--include-files`) must be included?  
   - info: The --include-dir option uses the splitValues() function which: Takes comma-separated values
   - Which heavy/irrelevant dirs (`--exclude-dir`) can be skipped?  
   - Feel free to limit by extension (`-e .js,.ts`, etc.) if appropriate.
   You can also add a project tree with `-t [depth]` (e.g., `-t 3`); choose a depth that makes sense.  
3. Explain your selection briefly: (one short paragraph).  
4. Run Codefetch with your chosen flags.

!`npx -y codefetch@latest <your-flags-here> -o "context.md"`

5. Call Gemini CLI (allowed tool) with the prepared context:

!`gemini -p "<codebase>@codefetch/context.md</codebase><requirements>$ARGUMENTS</requirements> analyze the <codebase /> and, in line with the <requirements />, deliver a detailed, full step-by-step implementation plan for my development team." > plans/<num>-plan-<short-title>.md`