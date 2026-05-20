ALFARUK Support Center — static site for GitHub Pages

This directory contains a static demo site for the ALFARUK Support Center. The `app.html` page is intended as the Telegram Mini App entry and `staff.html` is a staff portal UI.

How to publish to GitHub Pages (recommended):

1. Create a public repository named exactly `ALFARUK-Support-Center` on GitHub, or use the `gh` CLI:

   ```bash
   # from inside this folder
   git init
   git add .
   git commit -m "Initial static site"
   gh repo create ALFARUK-Support-Center --public --source=. --remote=origin --push
   ```

   If you don't have the `gh` CLI, create the repo via GitHub web UI, then add the remote:

   ```bash
   git remote add origin https://github.com/<your-username>/ALFARUK-Support-Center.git
   git branch -M main
   git push -u origin main
   ```

2. Enable GitHub Pages:
   - Go to the repository Settings → Pages
   - Build and deployment: Choose "Deploy from a branch"
   - Branch: `main` (or `master`) and folder: `/ (root)`
   - Save. After a minute the site will be available at: `https://<your-username>.github.io/ALFARUK-Support-Center/`

3. Configure BotFather Mini App Menu Button:
   - Use the Page URL that serves `app.html`, for example:
     `https://<your-username>.github.io/ALFARUK-Support-Center/app.html`
   - Paste that URL into BotFather's "Configure Menu Button" → "Open a web app"

Notes:
- These pages are static demos. To connect to your running backend (the FastAPI app), update the JS fetch calls to point to your backend HTTPS endpoint (publicly reachable), and handle CORS if necessary.
- If you prefer automatic deployment, add a GitHub Action to push to `gh-pages` branch or use a build pipeline.

If you want, I can:
- Create a `gh-pages` GitHub Action to deploy automatically.
- Update the pages to call your deployed API endpoints (provide a public URL or set environment variables).
