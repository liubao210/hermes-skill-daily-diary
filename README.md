# 📔 Daily Diary — Hermes Agent Skill

A configurable markdown diary system for [Hermes Agent](https://hermes-agent.nousresearch.com).

Write entries via `#diary-start` / `#diary-end`, store as ISO-week-organised markdown files, set an optional smart cron reminder that only fires when you haven't written yet.

## Features

- **`#diary-start` / `#diary-end`** — record entries with text and images
- **ISO-week storage** — `2026-W21/2026-05-18.md`, one file per day
- **Obsidian-ready** — relative image paths, markdown format, works with any vault
- **Smart cron reminder** — only reminds if no entry exists for today
- **Configurable** — storage directory, reminder time, command aliases
- **First-run wizard** — interactive setup via Hermes Agent
- **Image support** — `images/` subdirectory with relative references
- **Weather annotation** — optional, configurable default location

## Installation

```bash
# Via Hermes Skills Hub (recommended)
hermes skills install daily-diary

# Or manual — copy to ~/.hermes/skills/
cp -r daily-diary ~/.hermes/skills/productivity/
```

## First Run

After installation, just say:

> Set up my diary

The agent will walk you through:

1. **Storage directory** — default `~/Documents/Diary/`, or your Obsidian vault, or iCloud Drive
2. **Reminder time** — e.g. `21:00` for a daily nudge (smart — skips if you already wrote)
3. A cron job is created automatically

## Usage

| Command | What it does |
|---|---|
| `#diary-start` | Begin recording an entry. Send text and images freely. |
| `#diary-end` | Stop recording. |
| `#view-diary` | Read back today's or recent entries. |
| "Change my diary settings" | Update path, time, or commands. |
| "Remove diary" | Delete cron job and config (files stay on disk). |

## Diary Format

```
~/Documents/Diary/               # configurable
├── 2026-W21/
│   ├── 2026-05-18.md
│   └── images/
│       ├── 2026-05-18-001.jpg
│       └── 2026-05-18-002.jpg
```

Entry format:

```markdown
# 2026-05-18 Monday

> ☀️ 21°C · Beijing

## 08:34

Today was a good day.

## 20:15

Watched a movie. Great ending.

![Movie scene](images/2026-05-18-002.jpg)
```

## Requirements

- [Hermes Agent](https://hermes-agent.nousresearch.com) (any version with skill support)
- macOS or Linux
- Optional: [Obsidian](https://obsidian.md) for rich reading on mobile/desktop

## License

MIT
