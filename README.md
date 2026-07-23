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

- Data lives in your browser only. Clearing site data / browser data wipes your log.
- Default unit is **lb** and default rest is **90s** (easy to change in the code:
  `settings.unit` / `settings.rest` near the top of the script).
