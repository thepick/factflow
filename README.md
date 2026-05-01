# FactFlow

FactFlow is a local-first multiplication fluency web app designed for student practice. It helps learners build speed, accuracy, and confidence with multiplication facts through short timed rounds, adaptive review, and clear progress tracking.

## What it does

FactFlow gives students focused multiplication practice while tracking how they are doing on each fact. The app adjusts practice based on performance, so facts that are slow, missed, or not yet fluent can appear again while mastered facts gradually need less attention.

Students can use FactFlow without signing in. Progress is saved on the device by default. Students may also choose to sign in with Google to sync their progress across devices using a hidden Google Drive app data file.

## Key features

- Timed multiplication practice rounds
- Adaptive fact selection based on accuracy, speed, and recent performance
- Progress grid showing fluent, in-progress, and locked facts
- Mastery score and progress graph
- Streak and facts-per-minute tracking
- Light mode, dark mode, and match-device appearance options
- Optional mobile haptic feedback
- Local device storage with no account required
- Optional Google sign-in for cross-device progress sync
- Google Drive app data sync without Firebase, a database, or a custom backend
- Offline-friendly practice with sync catching up when available

## Google Drive sync

FactFlow can optionally sync progress through the student's Google Drive app data folder. This keeps the sync file hidden from the student's normal Drive view and limits the app to its own progress data.

Sync is local-first:

- Progress is saved immediately on the device.
- If Google sync is enabled, progress is also saved to Google Drive.
- When the app is opened on another device, the latest synced progress can be merged and shown.
- If the internet is unavailable, students can keep practicing locally.
- Sync resumes when the device is online and the student is signed in again.

Google sync is optional. Students can continue using FactFlow fully without signing in.

## Designed for students

The interface is simple and classroom-friendly. Students can start a round, answer using the on-screen keypad, and see immediate feedback. The progress tools help students and teachers quickly understand which facts are becoming fluent and which still need practice.

## Privacy and storage

FactFlow saves progress locally using browser storage. No login is required for local use.

If Google sync is enabled, FactFlow stores a progress file in the student's Google Drive app data folder. This file is used only for FactFlow progress syncing. FactFlow does not need Firebase, a separate database, or a custom server.

FactFlow should not store student names, class lists, or other unnecessary personal information in the progress file.

## Best use case

FactFlow works well for daily multiplication fluency practice in upper elementary classrooms, intervention groups, homework stations, or independent review. It is especially useful when students may practice across more than one device, such as a home computer, mobile browser, and school computer.
