---
name: setup
description: Install and configure the sangtae-chang statusline plugin for Claude Code.
disable-model-invocation: true
---

# Setup sangtae-chang Statusline

Set up the statusline for the user's Claude Code environment.

## Steps

1. **Check jq is installed**: Run `jq --version`. If missing, install it:
   - macOS: `brew install jq`
   - Ubuntu/Debian: `sudo apt-get install jq`
   - If the user cannot install jq, stop and explain it is required.

2. **Register the statusline in `~/.claude/settings.json`**:
   - Read the existing `~/.claude/settings.json` (create it if it does not exist).
   - Add or update the `statusLine` key so the file contains:
     ```json
     {
       "statusLine": {
         "type": "command",
         "command": "bash ~/.claude/plugins/cache/sangtae-chang/scripts/statusline-command.sh"
       }
     }
     ```
   - Preserve any other existing keys in the file — only set `statusLine`.
   - After writing, confirm the change to the user.

3. **Verify**: Ask the user to restart Claude Code (or run `/reload-plugins`) and confirm they can see the two-line statusline at the bottom.

4. If something is wrong, check:
   - `jq` is on PATH
   - `~/.claude/settings.json` contains the correct `statusLine` entry
   - The script exists at the expected path
