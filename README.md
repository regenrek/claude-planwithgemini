# /planwithgemini

Generate a project‑wide implementation or refactor plan with Google Gemini CLI, using [Codefetch](https://github.com/regenrek/codefetch) for smart context selection, then continue execution in Claude Code.

IMPORTANT NOTE: These prompts work with Gemini and can be used as Claude Code slash commands (in `.claude/commands/planwithgemini`) or as Cursor rules. However, I recommend referencing them with "@" for more reliable execution, as rules can sometimes behave unpredictably. (Thats the reason why )

## Prompts

(or when used as claude slash commands)

- **`/planwithgemini-plan-auto-context`** - Analyzes your codebase and selects only relevant files/folders for your request
- **`/planwithgemini-plan`** - Uses entire codebase context (simpler but less efficient)

Both generate a plan file without writing code.

## Quick‑Start

⚠️ Add codefetch/ to your .gitignore file to avoid committing the fetched codebase.

### Install Gemini CLI 

```bash
# 1 Install Gemini CLI & Codefetch (once)
npm install -g @google/gemini-cli

# 2 Authenticate Gemini (once)
gemini            # or: export GEMINI_API_KEY=…
```

Note: Use Gemini CLI for free by logging in with a personal Google account to get a free Gemini Code Assist license. This gives you access to Gemini 2.5 Pro with a 1M token context window. The free tier includes 60 requests/minute and 1,000 requests/day. [Learn more about Gemini CLI](https://blog.google/technology/developers/introducing-gemini-cli-open-source-ai-agent/?utm_source=chatgpt.com).

Full [Install instructions](https://github.com/google-gemini/gemini-cli?tab=readme-ov-file#quickstart)

### Install Claude Code

```bash
# 1 Install Claude Code 
npm install -g @anthropic-ai/claude-code

# 2a Run Claude Code
claude

# 2b Yolo Mode
claude --dangerously-skip-permissions
```

Full [Install instructions](https://docs.anthropic.com/en/docs/claude-code/setup)



### Install Codefetch (Optional)

```
npm install -g codefetch@latest
```




Videos: 

[How to install Claude Code in Cursor](https://www.youtube.com/watch?v=RJZ5aTDpqKM)


## Contributing

We welcome contributions! Please see [CONTRIBUTING.md](CONTRIBUTING.md) for details.

## License

MIT

## Links

- X/Twitter: [@kregenrek](https://x.com/kregenrek)
- Bluesky: [@kevinkern.dev](https://bsky.app/profile/kevinkern.dev)

## Courses
- Learn Cursor AI: [Ultimate Cursor Course](https://www.instructa.ai/en/cursor-ai)
- Learn to build software with AI: [instructa.ai](https://www.instructa.ai)

## See my other projects:

* [AI Prompts](https://github.com/instructa/ai-prompts/blob/main/README.md) - Curated AI Prompts for Cursor AI, Cline, Windsurf and Github Copilot
* [codefetch](https://github.com/regenrek/codefetch) - Turn code into Markdown for LLMs with one simple terminal command
* [aidex](https://github.com/regenrek/aidex) A CLI tool that provides detailed information about AI language models, helping developers choose the right model for their needs.# tool-starter