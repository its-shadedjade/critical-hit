# critical-hit — Critical Hit!

A pixel-art dice battle game that runs entirely in the browser: **one
self-contained HTML file per game**, no build step, no dependencies, no
server. Public repo; published via GitHub Pages at
<https://its-shadedjade.github.io/critical-hit/>.

**This file is the brain. Read it first, every session, on any machine.**

## Session protocol (the same in every one of Jade's repos)

1. **Start**: read this file, then `notes/LOG.md` (newest entry on top).
   `git pull` — another machine may have moved things.
2. **During**: decisions and rationale go in `DESIGN.md`; loose ideas in
   `TODO.md`.
3. **End**: a dated entry in `notes/LOG.md` (what changed, what was learned,
   what's next), then commit and push. **Unpushed = forgotten.**

Git history is the fine-grained archive under LOG.md — write commit messages
that explain *why*, so `git log` stays readable years later.

## Where things live

| Path | What |
|---|---|
| `index.html` | Landing page (the Pages entry point) |
| `critical_hit_dice_game.html` | **Duel** — the full game, single file |
| `critical_hit_boss_test.html` | Boss-fight-only test build |
| `frames/`, `dice_roll*.gif/png` | Pixel dice animation source + exports |
| `README.md` | Player-facing rulebook (kept accurate — it IS the manual) |

## How it works / house rules

- **Self-contained is the whole point.** Everything — styles, sprites,
  logic — inlines into the one HTML file. No frameworks, no bundler, no CDN.
  If a change would add a dependency, it's the wrong change.
- **Open the file to test.** No dev server; double-click, or `open
  critical_hit_dice_game.html`. Verify in a real browser before claiming it
  works.
- **Two files, one game.** Balance or animation changes usually need to land
  in BOTH the duel and the boss-test file — check the other one.
- **This repo is PUBLIC** (the only one of Jade's that is). Nothing personal,
  no keys, no work references, no homelab detail.
- **The README is the rulebook.** Change a payout, a kill zone, or a limit
  break, and the README changes in the same commit.

## The game, in brief

50 HP a side, bet in steps of 50, roll 1/2/4 dice for damage or (once) a
heal; reach the 45–49 kill zone then **Strike**; overkill reflects onto you.
4 of a Kind 10×, Straight 5×, exactly 50 5×. Win three fights (tracked ● ● ●)
to unlock the **Boss**: 100 HP, doubled rewards, free healing, kill zone
90–99, and a once-per-fight **Limit Break** of 12 dice. Start with 1000 gil;
lose it all and revive at 1000.
