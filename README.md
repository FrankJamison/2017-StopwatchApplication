# JavaScript Stopwatch & Countdown Timer

A lightweight, browser-based time tool that provides:

- **Stopwatch** with Start/Stop and Clear
- **Countdown timer** with Start/Pause and input validation

This project is intentionally simple: no build step, no dependencies—just open the page and use it.

## Features

### Stopwatch

- Displays time as **minutes:seconds:hundredths** (`mm:ss:hh`)
- **Start/Stop** toggles running state
- **Clear** resets the display to `00:00:00`

### Countdown Timer

- Enter a start time in **`mm:ss:hh`** format
- **Start/Pause** toggles running state
- Shows clear validation messages for invalid input
- When the timer reaches `00:00:00`, it stops and shows **“Time is up!”**

## Getting Started

1. Open the application page in any modern web browser.
2. Use either the Stopwatch section or the Countdown Timer section.

No installation is required.

## How To Use

### Using the Stopwatch

1. Click **Start/Stop** to begin counting up.
2. Click **Start/Stop** again to pause.
3. Click **Clear** to reset back to `00:00:00`.

### Using the Countdown Timer

1. In the input field, type a start time using the format `mm:ss:hh`.
2. Click **Start/Pause** to begin counting down.
3. Click **Start/Pause** again to pause.
4. To start a new countdown, enter a new time and click **Start/Pause**.

## Time Format Rules (Countdown Timer)

The countdown input must be exactly:

- `mm:ss:hh` where:
	- `mm` is minutes
	- `ss` is seconds (`00`–`59`)
	- `hh` is hundredths of a second (`00`–`99`)

The timer is limited to **10 minutes maximum**.

Examples of valid inputs:

- `00:30:00` (30 seconds)
- `01:15:50` (1 minute, 15.50 seconds)
- `10:00:00` (10 minutes)

Examples of invalid inputs:

- `1:15:50` (missing leading zero)
- `00:60:00` (seconds out of range)
- `10:00:01` (greater than 10 minutes)

## Implementation Notes (For Developers)

- Time is tracked internally in **hundredths of a second**.
- The display is derived from that counter and rendered as `mm:ss:hh`.
- Both the stopwatch and timer advance using a repeating `setTimeout(..., 10)` loop.

## Troubleshooting

- **The countdown won’t start:** double-check the input format is exactly `mm:ss:hh` and does not exceed `10:00:00`.
- **The timer shows an error message:** correct the input and try again.
- **The time display looks “off” in a background tab:** browsers may throttle timers in inactive tabs, which can affect perceived timing accuracy.

## Credits

Created as a JavaScript timing application project.