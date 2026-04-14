# dev-timer

A minimal Pomodoro timer for the terminal. Stay focused, take breaks, repeat.

## Why?

Because sometimes you need a timer that doesn't require opening a browser or installing a heavy GUI app. This lives in your terminal where you're already working.

## Installation

```bash
curl -o ~/bin/dev-timer https://raw.githubusercontent.com/YOUR_USERNAME/dev-timer/main/dev-timer
chmod +x ~/bin/dev-timer
```

## Usage

```bash
# Start a 25-minute work session (default)
dev-timer

# Start a work session with a goal
dev-timer -g "Fix bug #123"

# Take a 5-minute break
dev-timer break

# Take a 15-minute long break
dev-timer long

# Custom timer
dev-timer custom 10

# With system notifications
dev-timer --notify

# Customize durations
dev-timer --work 50 --short 10 start

# View session statistics
dev-timer stats

# View today's sessions only
dev-timer stats --today

# View sessions with goals
dev-timer stats --goals

# Export data to CSV
dev-timer export --csv

# Export data to JSON with custom filename
dev-timer export --json my-sessions.json

# Reset statistics
dev-timer reset
```

## Features

- ⏱️  Simple countdown timer
- 🍅 Pomodoro technique built-in (25/5/15 defaults)
- 🎯 Session goals - track what you're working on
- 📊 Session tracking and statistics
- 📤 Export data to CSV or JSON
- 🔔 Optional system notifications
- 🎵 Sound alerts (or quiet mode)
- ⌨️  Keyboard interrupt (Ctrl+C)
- 🎨 Clean terminal UI

## Pomodoro Technique

The default times follow the classic Pomodoro Technique:
- **Work:** 25 minutes of focused work
- **Short break:** 5 minutes between sessions
- **Long break:** 15 minutes after 4 sessions

You can customize all of these with flags.

## Commands

- `start` - Start a work session (default)
- `break` - Start a short break
- `long` - Start a long break
- `custom MIN` - Start a custom timer
- `stats` - View session statistics
- `export` - Export session data to CSV or JSON
- `reset` - Reset all statistics

## Options

- `-w, --work MIN` - Work session length (default: 25)
- `-s, --short MIN` - Short break length (default: 5)
- `-l, --long MIN` - Long break length (default: 15)
- `-g, --goal "TEXT"` - Set a goal/description for this session
- `-n, --notify` - Send system notification when complete
- `-q, --quiet` - No sound alerts
- `-h, --help` - Show help
- `-v, --version` - Show version

## Statistics

dev-timer automatically tracks your sessions in `~/.dev-timer/sessions.log`. Use `dev-timer stats` to see:

- Total sessions completed
- Work vs break sessions
- Total time tracked
- Today's sessions
- Recent session history
- Session goals (when set)

### Stats Commands

- `dev-timer stats` - Full statistics with recent sessions
- `dev-timer stats --today` - Today's sessions only
- `dev-timer stats --goals` - Sessions with goals

### Export Data

You can export your session data for analysis in spreadsheets or other tools:

- `dev-timer export --csv` - Export to CSV (default: `sessions.csv`)
- `dev-timer export --csv my-data.csv` - Export to custom CSV file
- `dev-timer export --json` - Export to JSON (default: `sessions.json`)
- `dev-timer export --json my-data.json` - Export to custom JSON file

The JSON export includes a summary section with aggregate statistics.

Example CSV output:
```csv
timestamp,date,type,minutes,goal
"2026-04-14 08:00:00","2026-04-14","work",25,"Fix authentication bug"
"2026-04-14 08:30:00","2026-04-14","break",5,
"2026-04-14 08:40:00","2026-04-14","work",25,"Write unit tests"
```

Example JSON output:
```json
{
  "sessions": [
    {"timestamp":"2026-04-14 08:00:00","date":"2026-04-14","type":"work","minutes":25,"goal":"Fix authentication bug"},
    {"timestamp":"2026-04-14 08:30:00","date":"2026-04-14","type":"break","minutes":5,"goal":""}
  ],
  "summary": {
    "total_sessions": 2,
    "work_sessions": 1,
    "break_sessions": 1,
    "total_minutes": 30
  }
}
```

Example stats output:
```
📊 dev-timer Statistics
=======================

Total sessions:    42
Work sessions:     28
Break sessions:    14
Total time:        785 minutes (13.1 hours)

Today (2026-04-08):
  Sessions:        8
  Minutes:         185

Recent sessions:
  2026-04-08 09:15:32 - work (25m): Fix bug #123
  2026-04-08 09:45:18 - break (5m)
  2026-04-08 10:00:42 - work (25m): Write documentation
  ...
```

## Requirements

- Bash 4.0+
- Optional: `notify-send` (Linux) or `osascript` (macOS) for notifications

## License

MIT License - see LICENSE file

## Contributing

Pull requests welcome! Keep it simple and focused.
