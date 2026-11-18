# Trapped in Vim :: `:wq!`

A retro 8-bit browser platformer controlled entirely with Vim keys — escape the editor using nothing but `h` `j` `k` `l` and `f`. Vibe-coded with [Claude Code](https://claude.com/claude-code) in the terminal by **Syntax Labs**.

**[▶ Play free in browser](https://syntaxlabsapp.com/game/)** · **[📺 Devlog](https://youtube.com/@artem_kysylov)**

---

## Controls

| Key(s) | Action |
| --- | --- |
| `H` / ← | Move left |
| `L` / → | Move right |
| `K` / ↑ / `Space` | Jump — hold while airborne to thrust the jetpack once it's unlocked (limited fuel) |
| `J` / ↓ | Hold to crouch · tap once on a drop-through platform to fall through it |
| `F` | Fire blaster (only while the blaster power-up is active) |
| `Enter` / `Space` | Confirm / advance on menus, cutscenes, and results screens |

On touch devices, an on-screen D-pad (H/J/K/L) and a FIRE button appear automatically.

> The game captures `H`/`J`/`K`/`L`/`F` at the window level and keeps a hidden input focused during play specifically to stop keyboard-navigation extensions like Vimium from intercepting them — so play with those extensions enabled if you like the irony.

## Run Locally

The game is a static, dependency-free HTML5 Canvas app (vanilla JS ES modules, no build step). Assets are loaded with paths relative to `game/index.html` (e.g. `../assets/sprites/...`), so the `assets/` folder must stay a sibling of `game/`, exactly as it is in this repo:

```
.
├── assets/   # sprites, backgrounds, audio (do not move)
└── game/     # index.html, js/, style.css
```

Because it uses ES modules and `fetch()` for audio decoding, it **won't run from a `file://` URL** — serve it over HTTP from the repo root:

```bash
# from the repo root
python3 -m http.server 8000
# then open:
# http://localhost:8000/game/
```

Any static server works the same way (`npx serve .`, `npx http-server`, etc.) as long as it's rooted at the repo root, not inside `game/`.

## Ideas for Pull Requests

- Add a 4th level, or an extra secret room off the existing levels
- Rebalance the `MONITOR KERNEL` boss fight — attack cadence, laser speed, or the enrage threshold (see `BOSS` in `game/js/constants.js`)
- Add a local death counter or speedrun timer
- Add a CRT scanline toggle, or Game Boy / Amber retro color palettes
- Improve mobile touch controls (D-pad feel, button layout, haptics)

Please don't reformat or restructure existing files outside the scope of your change — keep diffs focused.

## License

MIT
