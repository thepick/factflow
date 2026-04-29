# FactFlow

A browser-based times tables practice app for primary school students. FactFlow uses adaptive question selection to focus on the facts a student finds hardest, tracks mastery per individual fact, and rewards both accuracy and speed.

## Features

- **Adaptive engine** - questions are weighted toward facts the student struggles with or answers slowly
- **Live progress grid** - 11x11 grid showing every fact from x2 to x12, colour-coded by mastery
  - Yellow = introduced but not yet fluent
  - Green = answered correctly and quickly, or high cumulative accuracy + speed
  - Cells never revert from green to locked on a single mistake
- **Auto level-up** - the app promotes the student to the next times table mid-round the moment mastery is achieved, with a brief on-screen notification
- **Mastery score** - a single 0-100 score combining accuracy, fluency, and facts mastered over time
- **Mastery over time graph** - session-by-session line graph with milestone markers when a new table is introduced
- **60-second timed rounds** - with a post-round cooldown before the next round can start
- **Facts per minute (FPM) meter** - live bar showing how fast the student is working
- **Streak meter** - visual fire indicator for consecutive correct answers; the Session Best stat locks in the highest streak of the round and never drops on a miss
- **Personal Best** - all-time highest streak saved across sessions
- **Dark mode** - full light/dark theme with manual toggle; preference is saved across sessions
- **Google login (optional)** - saves progress to localStorage; requires a Google OAuth 2.0 client ID

## How to use

1. Download `factflow-v16`
2. Open it in any modern browser (Chrome, Firefox, Safari, Edge)
3. No installation, no server, no internet connection required after download

## Favicon setup

Place the included PNG files in the same folder as the main file. The `<link>` tags are already present in `<head>`. Sizes provided: 16, 32, 48, 64, 180, 192, 512px.

## Mastery colour logic

| Colour | Meaning |
|--------|---------|
| Green (Fluent) | `fastStreak >= 3` OR `correct >= 3` with cumulative accuracy >= 65% AND average speed within 1.4x the fluency threshold |
| Yellow (In progress) | Fact has been seen at least once but fluency not yet reached |
| Grey (Locked) | Fact has never been introduced |

## Mastery score formula

The score combines three independent components:

- **Accuracy (40%)** - ratio of correct to attempted answers this session; rewards answering correctly without guessing
- **Fluency (35%)** - facts per minute, normalised against a target of 20 FPM; reflects automaticity, the primary goal of times tables practice
- **Depth (25%)** - fraction of the 121 total facts (x2 through x12) that have reached mastery threshold; rewards long-term progress

> **Why these weights?** Automaticity - recalling facts instantly without counting or calculating - is the specific learning goal of times tables practice. Fluency gets the highest single weight (35%) to reflect this. Accuracy (40%) still leads overall because correct recall is prerequisite to speed. Depth (25%) anchors the score to cumulative learning without letting long-term progress overshadow how well the student is performing right now.

## Settings and reset

Signed-in users can access a **gear icon** in the header to reset all saved progress. The reset requires two deliberate clicks to prevent accidents. Students not signed in can refresh the page to clear the session.

## Google login setup (optional)

Replace `YOUR_CLIENT_ID` near the top of the HTML file with a real OAuth 2.0 client ID from [Google Cloud Console](https://console.cloud.google.com). Without this, the app still works fully - progress is stored in the browser session only.

## Browser support

Any modern browser released after 2020. No build tools or dependencies required. The entire app is a single self-contained HTML file.

## License

MIT
