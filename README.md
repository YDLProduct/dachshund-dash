# Dachshund Dash 🐾

A player-vs-CPU wiener dog racing game in a single HTML file. No build, no dependencies — open
[index.html](index.html) in any modern browser (double-click it, or serve the folder) and race.

**On a phone?** Use the portrait, thumb-controlled build at [mobile/index.html](mobile/index.html)
(optimized for Chrome/Safari on iPhone: big paw buttons, safe-area aware, separate saved records).
Serve the folder (e.g. `python3 -m http.server 8420`) and open `http://<your-computer-ip>:8420/mobile/`
on the phone over the same Wi-Fi.

Pick your pup from a roster of six dachshunds — FRANK (chestnut), UZI (black & tan),
PRETZEL (cream), MOCHA (chocolate), PEPPER (silver) and GOLDIE (gold). You race in the bottom
lane; the CPU automatically drafts one of the remaining pups when the race starts (it shows as a
mystery "???" silhouette until then). First dachshund over the 250m line wins.

## How to play

| Action | Keyboard | Touch |
|---|---|---|
| Run | Alternate **←/→** (or **A/D**) | Tap **left/right halves** of the screen alternately |
| Zoomies (speed boost) | **SPACE** when the meter is full | Tap the **⚡ button** |
| Pause | **P** or **ESC** | ⏸ button |
| Mute | **M** | 🔊 button |

- On the title screen: click a card (or **↑/↓**) to pick your pup, **←/→** to change difficulty.
- **Alternate paws!** Repeating the same side gives a much weaker stride.
- **Stamina** drains as you sprint and regenerates as you ease off. A tired dog takes weak strides —
  about 5 taps/second is sustainable; sprint in bursts.
- **🦴 Bones** on the track restore stamina and charge your zoomies meter. Your rival eats the
  bones in *its* lane, so don't get out-snacked.
- **Zoomies** give a 2.6-second +45% burst. Saving one for the final stretch wins photo finishes.

## Difficulties

- **EASY** — a relaxed jog. Beatable at ~3 taps/sec.
- **NORMAL** — a real race. Competitive at ~5 taps/sec.
- **HARD** — the rival means business (and times its zoomies). Bring ~6+ taps/sec.

Best times per difficulty are saved locally. Races stay close thanks to gentle rubber-banding,
and finishes within 0.18s get a photo-finish strip.

## Tech notes

- Single-file HTML5 canvas game: fixed-timestep (120 Hz) simulation decoupled from rendering,
  procedural art (no image assets), synthesized music & SFX via WebAudio (no audio assets).
- The CPU runs the *same physics* as you — only its tap cadence is computer-controlled.
- Auto-pauses when the tab is hidden; handles high-DPI displays, window resizing, and touch.
- `window.DD` exposes the game state for debugging/automation.
