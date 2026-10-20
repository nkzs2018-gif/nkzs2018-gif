# Setup Guide – Claude Agent Game Studio (Android, no installs)

Everything runs in your browser. You need a Claude Pro (or higher) plan,
a free GitHub account, and an Android phone for playtesting.

## Step 1 – Create a GitHub account and repository
1. Sign up at https://github.com (free).
2. Click **New repository**. Name it exactly `YOUR-USERNAME.github.io`
   (with your real GitHub username). This puts the game at the root of
   `https://YOUR-USERNAME.github.io`, which the Android app needs to open
   full screen without a browser bar.
3. Make it **Public** (free GitHub Pages needs a public repository), tick
   "Add a README file", and create it.

## Step 2 – Upload the studio files
1. Unzip `game-studio.zip` on your computer.
2. In the repository, click **Add file → Upload files** and drag in
   everything *inside* the `game-studio` folder, including the `.claude`
   folder. Commit.
3. Check that `.claude/agents/` shows 8 files. If the `.claude` folder didn't
   upload (some systems hide it), use **Add file → Create new file** and
   type `.claude/agents/game-designer.md` as the name, then paste that
   file's contents. Repeat for each agent.

## Step 3 – Turn on GitHub Pages
In the repository: **Settings → Pages → Source: GitHub Actions**. The
engine-programmer agent writes the workflow that publishes the game.

## Step 4 – Start the studio in the cloud
1. Open https://claude.ai/code (or the **Code** tab in the Claude app).
2. Connect GitHub when asked and give access to your repository.
3. Start a session on your repository.

## Step 5 – Design the game
Paste:
> Use the game-designer agent to interview me about my Android game, one
> question at a time, then fill in the GDD.

## Step 6 – Build the prototype
Paste:
> Run a work cycle on Milestone 1 from docs/TASKS.md, following CLAUDE.md.
> Stop after each finished task and give me a status update.

When asked, let Claude push its changes to your repository (or create a pull
request and merge it on GitHub). Each push to `main` republishes the game.

## Step 7 – Playtest on your phone
Open `https://YOUR-USERNAME.github.io` in Chrome on your Android phone and
play. Tip: use Chrome's menu → **Add to Home screen** to play it like an app.
Tell the Producer what to change, then run the next work cycle.

## Step 8 – Release (later)
The engine-programmer writes `docs/RELEASE.md` with the exact steps. In short:
1. Pay the one-time $25 Google Play developer fee.
2. Paste your game URL into https://www.pwabuilder.com and download the
   Android package. **Keep the signing key file safe and never upload it to
   GitHub.**
3. Give the generated `assetlinks.json` to the Producer to add to the game.
4. Upload the .aab to a closed test in Google Play Console. New personal
   accounts need at least 12 testers opted in for 14 days in a row before
   publishing.

## Tips to save usage
- Run one or two agents at a time on the Pro plan.
- Keep tasks small and specific.
- To make an agent cheaper, change `model: sonnet` to `model: haiku` in its file.
