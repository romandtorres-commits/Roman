# Lift 🏋️

A clean, offline gym workout logger. Open it, pick an exercise, log your sets
(weight × reps), get a rest timer between sets, and finish. Next time you do the
same exercise, it shows you exactly what you lifted last time so you know what to
beat.

No account. No backend. Everything is stored **on your phone** in the browser
(`localStorage`), so it works fully offline.

## The flow

1. **Add an exercise** — tap **＋** (or type a name in the search box). e.g. "Bench Press".
2. **Open it** — you'll see *"Last time: 135×8 · 135×8 · 130×6"* so you know your target.
3. **Log a set** — enter weight + reps, tap **Log set**. A **rest timer** pops up automatically.
4. **Repeat** — the timer counts down (with a beep + buzz when done); tap **+15s / +30s** or **Skip** as needed. Log your next set.
5. **Finish** — tap **Finish** to save the session to that exercise's history.

Each set you log shows what you did on that same set number last time (*"was 135×8"*),
so progressive overload is right in front of you.

## Extras

- **Units** — tap the **lb/kg** chip in the top-right to switch. Steppers adapt
  (5 lb vs 2.5 kg jumps). It changes the display label going forward; it doesn't
  convert past numbers, so pick your unit once.
- **History & progress chart** — on any exercise, tap the 📈 button (top-right) to
  see your **heaviest set** and **estimated 1-rep-max**, a line chart of your top-set
  weight over time (with all-time gain), plus every past session broken out
  set-by-set with total volume. Delete any session from there.
- **Personal records** — beat your best estimated 1RM and you get a 🏆 **New PR!**
  toast when you finish, and a trophy on the record-setting set.
- **Edit anything** — tap a logged set to fix its weight/reps; in **Edit** mode
  (top-right of the exercises list) rename, reorder, or delete exercises.
- **Exercise suggestions** — start typing and Lift suggests ~60 common lifts so you
  don't hand-type every name.
- **Routines / workout days** — the **Routines** tab lets you group exercises into
  days like "Upper — Crunch Gym", "Lower — Chinatown Park". Each day card shows
  **when you last did that workout**. Open a day and every exercise shows its
  🏆 **best-ever set pinned on top**, plus your **last** session and the **time
  before** — so a tired day never hides your real target. Work through the day's
  exercises in order; finishing one drops you back into the day for the next.
- **Rest timer that behaves** — keeps the screen awake while it counts down, and
  is **clock-based**, so it stays accurate even if you leave the app: phones freeze
  a web app's timers in the background, so Lift tracks the real end-time and, the
  moment you return, shows the correct time left (or fires the "done" beep if it
  already finished while you were away). If you allow notifications it also buzzes
  you when the screen is off. *(Note: on iPhone, web apps can't reliably fire an
  alert while fully in the background — the beep/vibrate lands as soon as you
  reopen Lift.)*
- **Backup & restore** — the ⚙︎ settings sheet has **Export** (downloads all your
  data as a `.json` file) and **Import** (restore it, or move to a new phone). Also
  set your default rest time there.

## Use it on your phone

The easiest way — it's a single web page:

1. Host the folder anywhere static (see below), or open `index.html`.
2. On your phone, open the URL in the browser.
3. **iPhone:** Share → *Add to Home Screen*. **Android:** menu → *Install app / Add to Home Screen*.
4. It now opens fullscreen like a native app, works offline, and keeps your log.

### Free hosting via GitHub Pages

This repo is ready for it — it's just static files.

1. Push to GitHub.
2. Repo **Settings → Pages → Build from a branch →** pick this branch, folder `/ (root)`.
3. Open the given `https://<you>.github.io/<repo>/` URL on your phone and add to home screen.

Or run locally: `python3 -m http.server` then open `http://localhost:8000`.

## Files

| File | What it is |
|------|-----------|
| `index.html` | The entire app — UI, logic, styles. Self-contained. |
| `manifest.webmanifest` | Makes it installable as a home-screen app. |

## Notes

- Data lives in your browser only. Clearing site data / browser data wipes your log —
  so **Export a backup now and then** from the ⚙︎ settings sheet.
- Defaults are **lb** and **90s** rest; change the unit with the header chip and the
  rest time in settings.
