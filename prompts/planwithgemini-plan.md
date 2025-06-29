---
allowed-tools: Bash(npx -y codefetch:*), Bash(gemini:*)
description: Draft a high‑level implementation/refactor plan – first derive the optimal Codefetch context from the Git file list, then query Gemini CLI and hand the result back to Claude. Do NOT begin writing or changing application code.
---

CRITICAL RULES: Dont plan or code anything!!

!`npx -y codefetch@latest -o "context.md"`

5. Call Gemini CLI (allowed tool) with the prepared context:

!`gemini -p "<codebase>@codefetch/context.md</codebase><requirements>$ARGUMENTS</requirements> analyze the <codebase /> and, in line with the <requirements />, deliver a detailed, full step-by-step implementation plan for my development team." > plans/<num>-plan-<short-title>.md`