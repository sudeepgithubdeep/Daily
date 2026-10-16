# Daily 5

**Live demo:** https://YOUR-USERNAME.github.io/daily5/  <!-- replace YOUR-USERNAME -->

A two-minute daily English word quiz with streaks, points, levels and badges. One HTML file. No build step, no dependencies, no network calls after the page loads.

## Run it

```bash
git clone <your-repo-url> daily5
cd daily5
python3 -m http.server 8000   # or: npx serve
```

Open http://localhost:8000 (on a phone, use your computer's LAN IP). Opening `index.html` directly also works.

## Deploy to GitHub Pages (free live link)

1. Create a public repo named `daily5` and push these files to `main`.
2. In the repo: **Settings → Pages → Build and deployment → Source: Deploy from a branch → Branch: `main` / `(root)` → Save**.
3. Wait about a minute. The live link is `https://<your-username>.github.io/daily5/` and also appears at the top of the Pages settings screen.

Or use the GitHub CLI:

```bash
gh repo create daily5 --public --source=. --push
gh api -X POST repos/{owner}/daily5/pages -f "source[branch]=main" -f "source[path]=/"
```

Alternative host: drag the folder onto https://app.netlify.com/drop.

## How it works

- Everyone gets the same 5 questions each day. They come from the `Q` array, picked by date.
- Scoring: 10 points per right answer, +10 for finishing, +20 for 5/5.
- Level `n` starts at `50·n·(n-1)` points.
- Streak counts consecutive days played. A freeze (earned every 7 days, max 2) covers a missed day.
- Progress is saved in `localStorage` under `daily5.v1`. Clear that key to reset.

## Add questions

Add a row to `Q`: `[emoji, "Sentence with ___", "right", "wrong", "wrong"]`.

## Checklist (manual)

1. Finish a set: score, points and a badge appear.
2. Reload mid-quiz: you resume on the same question.
3. Play again the same day: not allowed, shows today's score.
4. Change the device date to tomorrow: streak goes up. Skip two days: streak resets.

See `EXPLAINER.md` for the design choices and what was left out.
