# TETRANOID

Arkanoid meets Tetris: smash descending bricks, clear full lines, and survive as long as you can.

🎮 **Play:** `https://glougloufr66.github.io/tetranoid/`

*Français : Arkanoid rencontre Tetris. Détruis les briques qui descendent, complète des lignes et survis le plus longtemps possible.*

## Features

- Endless survival: rows of bricks keep descending, faster with every wave
- The arena gets wider as the difficulty increases
- XP and level-ups with a choice of 3 random upgrades (laser cannons, magnet, multi-ball, explosive ball, lightning, safety net…)
- Power-ups and penalties dropped by bricks
- Bricks with gaps: hit the lowest brick of a column and it slides up to fill the gap; a full line disintegrates and the bricks below move up
- Synthwave music and sound effects generated with the Web Audio API (no audio files)
- Leaderboard with nicknames and a Stats tab on the home screen
- Available in English, French and Spanish
- Single HTML file, no dependencies

## Controls

| Action | Control |
|---|---|
| Move the paddle | Mouse, or ← → / A D |
| Launch the ball | Click or Space |
| Pause | P or Esc |
| Mute | M |

## Run locally

Open `index.html` in any modern browser. No build step needed.

## Deploy on GitHub Pages

1. Put `index.html` at the root of the repository.
2. Go to **Settings → Pages**, choose **Deploy from a branch**, branch `main`, folder `/ (root)`.
3. The game is live after a minute or two.

## Shared leaderboard and stats (optional)

GitHub Pages is static, so by default scores and stats are stored in each player's browser (`localStorage`). To share them between all players:

1. Create a [Firebase Realtime Database](https://firebase.google.com/).
2. In `index.html`, set `DB_URL` in the `CFG` constant (no trailing slash):
   ```js
   const CFG={DB_URL:'https://YOUR-PROJECT-default-rtdb.europe-west1.firebasedatabase.app'};
   ```
3. In the database **Rules** tab, allow public read/write on `scores` (with `".indexOn":"score"`) and `plays` (with `".indexOn":"t"`).

If the server is not configured or unreachable, the game falls back to local storage.

> Public write rules mean anyone can submit fake scores. Add server-side validation if that matters to you.

## License

Add a license of your choice (for example MIT).
