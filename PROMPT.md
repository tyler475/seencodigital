# Terminal prompt for Claude Code

This site is already built and final. The prompt below does NOT ask an agent to recreate the design (it can't reproduce your exact logos, screenshots, and hero video). It has Claude Code take the files in THIS folder and get them live on GitHub Pages, exactly like your other sites.

## Steps

1. Unzip `seen-site.zip` if you haven't already.
2. Open a terminal INSIDE the unzipped folder (the one containing `index.html` and the `assets/` folder).
3. Run `claude`.
4. Paste the prompt below.

---

```
This folder is a finished static website: index.html, an assets/ folder (images + a hero.mp4 video), plus 404.html, .nojekyll, .gitignore, and README.md. The design is final and verified. Do NOT change any HTML, CSS, JavaScript, copy, or assets. Your only job is to publish it to GitHub Pages.

Do this:
1. If there's no git repo here, run: git init, then stage everything (git add -A) and commit with the message "seen site". Make sure assets/hero.mp4 is included in the commit -- do not gitignore or skip it.
2. Create a new public GitHub repo named "seen-site" under my account and push to it, using the gh CLI: gh repo create seen-site --public --source=. --remote=origin --push
   - If gh isn't installed, stop and tell me the exact command to install it for my OS, then wait.
   - If gh isn't authenticated, stop and tell me to run "gh auth login", then wait.
3. Make sure the default branch is "main" and everything (including the video) is pushed.
4. Enable GitHub Pages on the main branch at root using the gh API, then tell me the live URL (https://<my-username>.github.io/seen-site/).
5. Once Pages is live, curl the URL and confirm HTTP 200. Also curl assets/hero.mp4 and assets/seen.png and confirm both return 200 so I know the video and images load.

Rules:
- Never edit index.html, the assets, or any styling. This build is final.
- Do not add a build step, framework, bundler, or package.json. It is intentionally plain static HTML.
- If anything 404s, tell me exactly which file and stop. Do not "fix" it by editing site files.
- Don't set up a custom domain unless I ask.
```

---

## Before you run it: one-time setup

Claude Code publishes through the GitHub CLI (gh), acting as YOU. You need it installed and logged in once:

- Install (Mac): brew install gh
- Log in: gh auth login (choose GitHub.com, HTTPS, authenticate in the browser)

After that, the prompt handles everything. Whatever GitHub account you logged in as is where seen-site gets created.

## Don't want to use the agent?

The manual path is in README.md: about five git commands plus flipping on Pages in the repo's Settings. Just as fast for a one-time deploy.

## Custom domain (seen.co)

Once it's live and you want your domain on it, add a file named CNAME containing just seen.co, commit and push, then point your DNS at GitHub Pages. Ask and I'll give you the exact records.
