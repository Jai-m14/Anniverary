# Anniverary — Publish Instructions

This repository contains a small static site (HTML/CSS/JS) for a 25th anniversary. This README explains how to publish it and run it locally.

How publishing works (automatic):
- A GitHub Actions workflow has been added at `.github/workflows/deploy-pages.yml`.
- On every push to the `main` branch the workflow packages the repository root and deploys it to GitHub Pages.
- The site will be available at `https://<your-github-username>.github.io/Anniverary` (replace `<your-github-username>` with your account). If you want a custom domain, configure it in the repository Pages settings.

How to trigger deployment manually:
1. Commit and push any changes to `main`:

```bash
git add .
git commit -m "Update site"
git push origin main
```

2. After the push, GitHub Actions will run the workflow and publish the site. You can view progress in the repository's Actions tab.

Run locally (static server):

```bash
cd /workspaces/Anniverary
python3 -m http.server 8000 --bind 127.0.0.1
# then open http://127.0.0.1:8000/index_2.html or index.html
```

Notes & troubleshooting:
- The workflow publishes the repository root. Make sure `index.html` (or whichever file you want served by default) is at the repository root.
- If you prefer to publish from a `build/` folder, update the workflow `path` in `.github/workflows/deploy-pages.yml` to point at that folder.
- If you want me to also create a CNAME or configure a different publishing strategy (Netlify / Vercel / S3), tell me which provider you prefer and I can add the necessary files or a CI workflow.

If you'd like, I can push these changes (workflow + README) to your remote and confirm the Pages URL — do you want me to do that now? (I need repository push permissions to do it from here.)
# Anniverary