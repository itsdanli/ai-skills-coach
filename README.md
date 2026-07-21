# AI Skills Coach

A self-updating static site of daily, hands-on lessons that make you sharper at Claude and adjacent AI tooling. A scheduled task adds one lesson every weekday morning (7am), rebuilds the clickable index, and appends to `ai-daily-log.md`.

## Structure

```
ai-skills-coach/
  index.html          # clickable list of all lessons (newest first) — rebuilt each run
  style.css           # shared styling, no branding
  ai-daily-log.md     # source of truth: one row per lesson (Date | Day | Topic | Bookmark | File)
  lessons/
    day-01-*.html      # one self-contained page per lesson
  README.md
```

## View it locally

Just open `index.html` in a browser and click through. That's it — no build step, no server needed.

## Host it free on GitHub Pages

You only do this once; after that every new daily lesson goes live when you push.

1. **Create a repo.** On github.com, click **New repository**, name it (e.g. `ai-skills-coach`), keep it Public, and create it.

2. **Push this folder.** In a terminal, from inside `ai-skills-coach/`:
   ```bash
   git init
   git add .
   git commit -m "Day 1"
   git branch -M main
   git remote add origin https://github.com/<your-username>/ai-skills-coach.git
   git push -u origin main
   ```

3. **Turn on Pages.** In the repo: **Settings → Pages**. Under "Build and deployment," set **Source: Deploy from a branch**, **Branch: main**, folder **/ (root)**. Save.

4. **Wait ~1 minute**, then visit:
   ```
   https://<your-username>.github.io/ai-skills-coach/
   ```

5. **Publish new lessons.** Each morning after the task runs, push the new files:
   ```bash
   git add .
   git commit -m "New lesson"
   git push
   ```
   The site updates within a minute. (Want this fully automatic? Ask Claude to add a GitHub Action that commits daily, or run the three git commands as their own scheduled task.)

### Notes
- Everything is plain HTML/CSS — GitHub Pages serves it as-is.
- The site is generated from `ai-daily-log.md`; that file is the record of what's been taught (used to avoid repeating a topic within 14 days).
