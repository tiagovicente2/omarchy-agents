# Omarchy Agents

Multi-agent AI coding subscription monitor, token usage fuel gauges, and pacing panel for [Omarchy](https://omarchy.org/).

---

## Features

- **Multi-Agent Support**: Native rate-limit and token metrics for **Claude Code**, **OpenAI Codex**, **Antigravity (AGY)**, **Grok**, **Fireworks**, and **Kimi**.
- **Fuel-Gauge Meters**: Real-time visualization of current session limits, 7-day allowances, and credit balances.
- **Usage Breakdown**: Daily token bar charts and model breakdown with input/output/cache splits.
- **Synced Aggregation**: Optional cross-device usage aggregation across laptop and desktop workstations.
- **Self-Hiding**: Hides automatically from the bar if no AI subscriptions or usage are detected on the system.

---

## Installation

```bash
omarchy plugin add https://github.com/tiagovicente2/omarchy-agents.git --enable
~/.config/omarchy/plugins/omarchy-agents/install-helper.sh
```

---

## Configuration

Configure the widget in `~/.config/omarchy/shell.json` or via the Omarchy CLI:

```bash
# Change refresh interval (seconds)
omarchy bar set omarchy-agents refreshIntervalSec 300 --json

# Enable cross-machine sync
omarchy bar set omarchy-agents syncMode "On"
omarchy bar set omarchy-agents syncDir "~/Sync/agent-usage"
```

### Antigravity (AGY) Quota Configuration

Antigravity quota limits can be customized in `~/.config/omarchy/agents/agy.json`:

```json
{
  "quotaMode": "both"
}
```

- `"both"` (default): Shows both **Gemini Models** (Session, Weekly, and Gemini 4 Argon) and **Claude & GPT models** limits.
- `"gemini"`: Shows only **Gemini Models** and **Gemini 4 Argon** quota limits.
- `"claude"`: Shows only **Claude & GPT models** quota limits.


---

## Interactions & IPC

- **Left-Click**: Open agent details panel.
- **Middle-Click**: Switch to the next enabled agent subscription.
- **Right-Click**: Launch configured default agent terminal.
- **IPC Commands**:
  ```bash
  omarchy-shell omarchy-agents toggle      # Open/close panel
  omarchy-shell omarchy-agents refresh     # Force usage update
  omarchy-shell omarchy-agents next        # Cycle active agent
  ```

---

## License

[MIT](LICENSE)
