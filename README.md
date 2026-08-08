# Health Log

My personal health app. Everything runs in a single HTML file in the browser. No backend, no accounts, no tracking. All data stays on the device.

**Open it here: https://monsharen.github.io/stronglifts/**

| Summary | StrongLifts | Body |
|---|---|---|
| ![Summary](screenshots/summary.png) | ![StrongLifts stats](screenshots/stronglifts-stats.png) | ![Body](screenshots/body.png) |

| Meals | Awards |
|---|---|
| ![Meals](screenshots/meals.png) | ![Awards with 3D medal](screenshots/awards.png) |

## What's inside

- **Summary**: weekly activity rings (workouts, weigh-in days, win days), charts for weight lifted, weight logged, calories and waist, insights computed from my own data, a monthly recap, weekly medals as 3D coins and optional reminders.
- **StrongLifts**: full 5x5 logger. Alternating A/B workouts, automatic progression (+2.5 kg on success, repeat on failure, 10% deload after three fails), warm-up plans, a per-side plate calculator and a rest timer. Stats include the competition total (squat + bench + deadlift), session tonnage with warm-ups as a dotted line and PR charts per lift.
- **Body**: morning weigh-ins with BMI, a goal weight with pace and estimated finish date, a ghost race against my earlier runs, and tape measurements (waist, chest, arm, thigh) behind a Weight/Measure switch.
- **Meals**: no calorie counting, just meal slots. Tick breakfast, lunch, fika, dinner, drinks and snacks against a daily budget. A day under budget earns a star. Missed days are fine and count against nothing.
- **Awards**: 29 achievements as rotatable 3D medals in different materials, with the date earned engraved on the back. Everything unlocks from logged data, nothing to claim.

## How to use

1. Open the app at the link above.
2. Log workouts in StrongLifts: Start workout, tap the circles as you lift (once for all reps, again to count down), then Finish & save. The next session's weights are calculated automatically.
3. Weigh in each morning before breakfast in Body. Set height and goal weight in the profile to get BMI, pace and a finish date.
4. Tick meals during the day in Meals. Stay under budget to earn the star. Yesterday can be backfilled if a day slips.
5. Check Summary for rings, medals, recaps and insights.
6. Back up now and then: Copy backup in Summary puts everything on the clipboard as JSON, Import backup merges it on another device.

Reminders are opt-in: a workout nudge after 3+ idle days and a morning weigh-in nudge after two missed days. Nothing else nags.

## Install as an app (PWA)

- iPhone/iPad: open in Safari, tap Share, then Add to Home Screen.
- Android: open in Chrome, menu, Install app.
- Desktop: install icon in the address bar in Chrome/Edge.

Works fully offline once installed. Updates arrive on the next launch or two. Data lives in the browser that installed it, so use backup to move history between devices.

## Development

- `index.html`: the entire app. Styles, all views, hand-rolled SVG charts, CSS-transform 3D medals, celebration effects. No dependencies, no build step.
- `sw.js`: offline cache. Bump `CACHE` when shipping changes.
- `manifest.webmanifest` + icons: PWA metadata.

Edit `index.html`, open in a browser, refresh. Data is stored in localStorage under `sl.*` keys and the export format is a single JSON object.
