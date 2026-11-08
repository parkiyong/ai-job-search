---
name: setup
description: Onboard your profile (CV import or interview) and populate all profile files
---

# Setup

Antigravity adapter. The canonical spec is `.claude/commands/setup.md` (written for Claude Code). Read that file in full and follow it exactly, with these translations:
- `$ARGUMENTS` = whatever the user typed after `/setup` (ask if missing and needed).
- Claude "Agent"/subagent steps (drafter, reviewer, posting-fetcher, posting-scorer; specs in `.claude/agents/`): use `invoke_subagent` (type `self`) with the agent file's content as the prompt, or perform the role yourself sequentially if subagents are unavailable.
- `AskUserQuestion` = `ask_question`; WebFetch/WebSearch = your web tools (or `python3 tools/fetch_page.py`).
- Ignore Claude-only permission syntax. Still honor the repo safety rules (`tools/posting_guard.py`, robots checks, confirm before destructive actions).
- Run bun as `~/.bun/bin/bun` if `bun` is not on PATH.
