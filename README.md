# FactFlow

A browser-based times tables practice app for primary school students. FactFlow uses adaptive question selection to focus on the facts a student finds hardest, tracks mastery per individual fact, and rewards both accuracy and speed.

## Features

- **Adaptive engine** - questions are weighted toward facts the student struggles with or answers slowly
- **Live progress grid** - 11x11 grid showing every fact from x2 to x12, colour-coded by mastery
  - Yellow = introduced but not yet fluent
  - Green = answered correctly and quickly 3 times in a row, or high cumulative accuracy + speed
  - Cells never revert from green to locked on a single mistake
- **Mastery score** - a single 0-100 score combining accuracy, speed, and facts unlocked over time
- **Mastery over time graph** - session-by-session line graph with milestone markers when a new table is introduced
- **60-second timed rounds** - with a post-round cooldown before the next round can start
- **Facts per minute (FPM) meter** - live bar showing how fast the student is working
- **Streak meter** - visual fire indicator for consecutive correct answers
- **Dark mode** - full light/dark theme with manual toggle
- **Google login (optional)** - saves progress to localStorage; requires a Google OAuth 2.0 client ID

## How to use

1. Download `factflow.html`
2. Open it in any modern browser (Chrome, Firefox, Safari, Edge)
3. No installation, no server, no internet connection required after download

## Mastery colour logic

| Colour | Meaning |
|--------|---------|
| Green (Fluent) | `fastStreak >= 3` OR `correct >= 3` with cumulative accuracy >= 65% AND average speed within 1.4x the fluency threshold |
| Yellow (In progress) | Fact has been seen at least once but fluency not yet reached |
| Grey (Locked) | Fact has never been introduced |

## Mastery score formula

The score combines three components:

- **Coverage (30%)** - how many tables have been unlocked
- **Depth (50%)** - fraction of mastered facts out of 121 total
- **Fluency (20%)** - average response speed on mastered facts

## Google login setup (optional)

Replace `YOUR_CLIENT_ID` near the top of the HTML file with a real OAuth 2.0 client ID from [Google Cloud Console](https://console.cloud.google.com). Without this, the app still works fully - progress is stored in the browser session only.

## Browser support

Any modern browser released after 2020. No build tools or dependencies required. The entire app is a single self-contained HTML file.

## License

MIT
