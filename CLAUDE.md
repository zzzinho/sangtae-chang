# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Overview

This is a Claude Code plugin (`sangtae-chang`) that provides a two-line statusline displaying session info, model, context usage bar, git branch, rate limits, and cost.

## Structure

- `.claude-plugin/plugin.json` — Plugin manifest (name, version, metadata)
- `.claude-plugin/marketplace.json` — Marketplace configuration for plugin distribution
- `settings.json` — Registers the statusline command using `${CLAUDE_PLUGIN_ROOT}` for portable paths
- `scripts/statusline-command.sh` — Shell script that reads JSON session data from stdin and renders the statusline
- `skills/setup/SKILL.md` — Setup skill invoked via `/sangtae-chang:setup`

## How the statusline works

The script receives JSON via stdin containing session state (model, context window, cost, rate limits, git info). It parses fields with `jq`, builds two output lines with ANSI color codes, and prints them:

- **Line 1**: Session name, model (with context size), context usage bar (▰▱), working directory, git branch with dirty indicator and line change counts
- **Line 2**: 5-hour and 7-day rate limit bars with reset times, session cost

## Local testing

```bash
claude --plugin-dir .
```
