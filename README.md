# Combined Experience — GitHub Pages deployment

This is a single self-contained HTML file (all 4 videos are embedded as base64 data URIs — no external images, CSS, JS, or fonts needed).

## How to publish it on GitHub Pages

1. Create a new GitHub repo (or use an existing one).
2. Add these two files to the repo root:
   - `index.html` (must be named exactly this so GitHub serves it as the homepage)
   - `.nojekyll` (empty file — tells GitHub Pages to skip the Jekyll build step, which isn't needed here and can occasionally choke on huge inline base64 content)
3. Commit and push.
4. In the repo, go to **Settings → Pages**, set:
   - Source: "Deploy from a branch"
   - Branch: `main` (or whichever branch you pushed to), folder `/ (root)`
5. Save. GitHub will give you a URL like `https://<username>.github.io/<repo-name>/` within a minute or two.

### Notes
- The file is ~6.4 MB, well under GitHub's 100 MB per-file limit and 1 GB recommended repo size, so no Git LFS needed.
- No build step, no dependencies — it just needs to be served as a static file.
- If you want it at a custom domain, add a `CNAME` file with your domain name to the repo root and configure your DNS per GitHub's docs.
