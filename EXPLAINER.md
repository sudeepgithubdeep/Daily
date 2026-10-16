# Explainer

## What I built
Daily 5: five fill-in-the-blank English questions a day. Each has a picture, a short sentence and three words to choose from. You earn points, keep a streak, level up and collect badges.

## Why this idea
- **Modest Android phones, mobile data.** The app is one file of about 14 KB. There are no frameworks, web fonts or images, and it runs fully offline after the first load.
- **English as a second language.** Sentences are short and everyday. Every question has an emoji, a 🔊 Listen button (the phone's own speech engine), big tap targets, and ✓/✗ marks so meaning never depends on colour alone. There is no timer or speed bonus, because that punishes slower readers.
- **Rewards matter to people.** The daily set is the same for everyone and can only be played once. Progress survives a reload. Streak freezes mean one bad day does not wipe out weeks of effort.

## Rewards
Points, levels, a 7-day streak with freezes, and 7 badges. Points are easy to earn early and slower later (level n needs 50·n·(n-1) points), so the first level-ups come fast.

## Left out, on purpose
- **Leaderboard and real payouts.** Everything here lives in the browser, so anyone can edit their score or read the answers. That is fine for a demo and not fine when rewards are worth real money. A real version needs a server that sends the questions, checks the answers, stores the points, and rate-limits by account. I would rather say that than fake a leaderboard that could be cheated.
- **Accounts, push reminders, offline install (PWA)** and translation into local languages. These are my first next steps.
- **Automated tests.** I used a short manual checklist (see README).

## Where I used AI
I used Claude (Anthropic) to draft the code, README and this write-up. [Edit this to say what you actually did: what you reviewed, changed, tested on a real phone, and wrote yourself.]
