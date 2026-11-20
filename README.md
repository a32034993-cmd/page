# Chronos Flow

Chronos Flow is a personal schedule and task workspace for turning a busy day into a clear, workable plan. It helps users see where their time is going, decide what matters next, reserve focus time, and finish the day with a concise progress summary.

## Features

- **Daily command dashboard:** See today's schedule, task completion, estimated workload, available deep-work time, and focus activity at a glance.
- **Schedule planning:** Add events, view the day on a 24-hour timeline, identify open time, and ask the app to suggest the next available 60-minute slot.
- **Task prioritization:** Organize work in an Eisenhower-style priority matrix, manage subtasks, and timebox a task into an open schedule slot.
- **Focus sessions:** Run 10-, 25-, or 50-minute Pomodoro sessions, link a session to a task, and track completed focus sessions.
- **Focus environment:** Generate adjustable brown noise with the Web Audio API, directly in the browser.
- **Daily wrap-up:** Generate a Markdown stand-up summary from the day's work and copy it for sharing.
- **Export and backup:** Download calendar events as iCalendar (`.ics`), back up app data as JSON, or download the standalone HTML app.
- **Personal preferences:** Switch between English and Traditional Chinese, light and dark themes, and standard or larger text.
- **Local-first storage:** App state is saved in the browser, so the core planner works without signing in.
- **Optional Firebase sync:** Sign in with Google and opt in to syncing this browser's state to the signed-in user's private Firestore document. The app asks before uploading local state or replacing it with an existing cloud copy.

## Run the app

Open `chronos_flow_v2_executive_edition.html` from an HTTPS site or a local web server. Firebase's browser modules and Google sign-in require an HTTP(S) origin; opening the file directly keeps the app in local-only mode.

## Firebase setup

- Firebase project: `project-2081971449067615714`
- Firestore database: `(default)`, Enterprise Native mode, `asia-east1` (Taiwan)
- User state path: `users/{uid}/appState/current`
- Security rules: [`firestore.rules`](firestore.rules)
- Firebase CLI project/config files: [`firebase.json`](firebase.json), [`.firebaserc`](.firebaserc)

Cloud sync is opt-in. A user must sign in and enable sync before app state is uploaded. Firestore rules restrict each account to its own current-state document and reject payloads larger than 700,000 characters.

## Technology

Vanilla HTML, CSS, and JavaScript with Firebase's modular Web SDK loaded from Google's CDN. No build step is required.
