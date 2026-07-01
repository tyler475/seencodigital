# seen — studio site

Single-page site for seen. Static HTML, no build step, no framework. Deploys to GitHub Pages as-is.

## Structure

```
index.html        the whole site (one file)
404.html          redirect to home
assets/           logos, screenshots, background texture
.nojekyll         tells GitHub Pages to serve files as-is
.gitignore
```

## Deploy to GitHub Pages (manual)

1. Create a new repo on GitHub (e.g. `seen-site`).
2. From this folder:
   ```bash
   git init
   git add .
   git commit -m "seen site"
   git branch -M main
   git remote add origin https://github.com/YOUR_USERNAME/seen-site.git
   git push -u origin main
   ```
3. On GitHub: Settings → Pages → Source: `Deploy from a branch` → Branch: `main` / root → Save.
4. Wait ~1 minute. Site is live at `https://YOUR_USERNAME.github.io/seen-site/`.

### Custom domain (seen.co)
- Add a file named `CNAME` containing just `seen.co`, commit and push.
- At your domain registrar, point the apex/`www` records at GitHub Pages per GitHub's docs.

## Editing

Everything is in `index.html`. Colors, fonts, copy, and the scripts for the cursor, the scroll-lit approach line, the hover-to-scroll work strip, and the magnify-on-hover product row are all inline at the bottom. Swap any image by replacing the matching file in `assets/`.

## Terminal prompt

See `PROMPT.md` for the exact prompt to paste into Claude Code if you want an agent to set up the repo and push it for you.
