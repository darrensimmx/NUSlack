# NUSlack

> ⚠️ **Work in progress.** This project is an early-stage prototype — expect rough edges, placeholder files, and incomplete integration between components.

A browser-based mood-check companion for students. It watches your webcam to gauge your emotional state while you work/study, and (separately) can nudge you with periodic "check-in" notifications, e.g. to take a break or drink water.

## What's in here

### 🎭 `facialRecognition/` — Mood tracker
Uses [face-api.js](https://github.com/vladmandic/face-api) in the browser to:
- Detect your face and facial expression from your webcam every second
- Smooth raw emotion readings into a rolling "mood" score (`intermediate.js`)
- Pop up a message when a strong mood is detected, with two tones:
  - **Normal mode** — gentle, supportive prompts (e.g. "Let's take a 5-minute break!")
  - **Troll mode** — meme reactions with images from `TrollImages/`

Run it by opening `facialRecognition/facial.html` in a browser and clicking **Start Recognition**.

### 🔔 `notif/` — Check-in extension
A minimal Chrome extension (Manifest V3) that sets a recurring alarm and fires a system notification as a check-in reminder. Load it via `chrome://extensions` → **Load unpacked** → select the `notif/` folder.

## Tech stack
- Vanilla JS + HTML/CSS (no framework yet)
- [face-api.js](https://github.com/vladmandic/face-api) for facial expression detection
- Chrome Extension APIs (`alarms`, `notifications`, `storage`)
- Node dependencies (`axios`, `node-fetch`) present in `package.json` but not yet wired into the app

## Known gaps / TODO
- Facial recognition and the notification extension aren't connected to each other yet
- No backend — everything currently runs client-side only
- Several placeholder/scratch files still in the repo (`test.txt`, `testbranch.txt`, `facialRecognition.txt`)
- No build tooling, tests, or deployment setup

## Getting started
```bash
git clone https://github.com/darrensimmx/NUSlack.git
cd NUSlack
npm install
```
Then open `facialRecognition/facial.html` directly in a browser, and/or load `notif/` as an unpacked Chrome extension.

## License
Not yet specified.
