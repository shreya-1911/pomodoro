# Quiet Timer — a calm Pomodoro timer

A single-file Pomodoro timer built as one self-contained HTML page. No installs, no build step — just open it in a browser.

## Features

- **25-minute focus sessions** followed automatically by **5-minute rest breaks**, looping continuously.
- **Soothing chime** (~3 seconds, built with the Web Audio API — no sound files needed) plays at the start of each break and the start of each new focus session, so you always know when a phase changes even if you're not looking at the screen.
- **Color shift by phase** — the whole page gently shifts palette so you can tell your state at a glance:
  - Focus: soft lilac
  - Rest: warm sand
- **Progress ring** around the timer fills as the current phase elapses.
- **Session dots** track how many focus sessions you've completed (resets every 4).
- **Tab title updates** with the live countdown, so you can see your remaining time from another tab.
- Respects `prefers-reduced-motion` and has visible keyboard focus states.

## How to use it

1. Open `pomodoro-timer.html` in any modern browser (Chrome, Firefox, Safari, Edge).
2. Click **Start** to begin a 25-minute focus session.
3. Work until the chime plays — it'll automatically switch to a 5-minute rest.
4. Another chime signals the end of the break, and focus starts again.
5. Use **Pause** to stop the countdown, or **Reset** to return to a fresh 25-minute focus session at any time.

## Notes

- The page needs an internet connection the first time you open it, to load its two Google Fonts (Space Grotesk and Newsreader). After that it works fully offline.
- Because it's a single HTML file, you can rename, move, or share it freely — everything it needs (styling, logic, and sound) is self-contained.
- Timing is based on your browser tab staying open. If your device sleeps or the tab is closed, the timer stops.

## Customizing

All the key numbers live near the top of the `<script>` section in `pomodoro-timer.html`:

```js
const FOCUS_SECONDS = 25 * 60;  // length of a focus session
const REST_SECONDS = 5 * 60;    // length of a rest break
```

Colors are defined as CSS variables near the top of the `<style>` section (`--focus-*` and `--rest-*`), if you'd like to adjust the palette.