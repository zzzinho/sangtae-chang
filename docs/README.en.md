# sangtae-chang

A Claude Code plugin that adds a two-line statusline with session info, context usage, git status, rate limits, and cost tracking.

[한국어](../README.md)

```
🏷️  my-session  🤖 Opus (200K context)  ▰▰▰▰▰▰▱▱▱▱▱▱▱▱▱▱▱▱▱▱ 45K/200K (30%)  📔 ~/Code/my-project  🌿 main* (+42 -7)
🔋 5h ▰▰▰▰▰▰▱▱▱▱▱▱ 48% →14:30  🗓️  7d ▰▰▰▱▱▱▱▱▱▱▱▱ 25%  💰 Cost $1.23
```

## What it shows

**Line 1 — Environment**
- Session name or ID
- Model name with context window size
- Context usage progress bar (color-coded: green/yellow/red)
- Token usage (used/max)
- Working directory
- Git branch with dirty indicator and line change counts (+/-)

**Line 2 — Usage**
- 5-hour rate limit bar with reset time
- 7-day rate limit bar
- Session cost (USD)

## Requirements

- [jq](https://jqlang.github.io/jq/) — JSON parser used by the statusline script
- git (optional, for branch/dirty status)

## Installation

### 1. Add marketplace and install

```bash
# Add marketplace (one-time)
/plugin marketplace add zzzinho/sangtae-chang

# Install the plugin
/plugin install sangtae-chang@sangtae-chang

# Setup statusline
/sangtae-chang:setup
```

## Uninstall

```
/plugin uninstall sangtae-chang
```

## License

MIT
