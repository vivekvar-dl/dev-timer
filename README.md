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
```

## Features

- ⏱️  Simple countdown timer
- 🍅 Pomodoro technique built-in (25/5/15 defaults)
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

## Options

- `-w, --work MIN` - Work session length (default: 25)
- `-s, --short MIN` - Short break length (default: 5)
- `-l, --long MIN` - Long break length (default: 15)
- `-n, --notify` - Send system notification when complete
- `-q, --quiet` - No sound alerts
- `-h, --help` - Show help
- `-v, --version` - Show version

## Requirements

- Bash 4.0+
- Optional: `notify-send` (Linux) or `osascript` (macOS) for notifications

## License

MIT License - see LICENSE file

## Contributing

Pull requests welcome! Keep it simple and focused.
