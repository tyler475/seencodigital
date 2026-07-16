# Deploy prompt for Claude Code — seencodigital.com

Open a terminal in the folder that directly contains index.html (run `ls` — you should
see index.html, assets, CNAME, README.md). Run `claude`, then paste:

---

```
This folder is a finished static website that must be published to GitHub Pages exactly as-is. It contains: index.html, CNAME (holds the custom domain seencodigital.com), 404.html, .nojekyll, .gitignore, README.md, and an assets/ folder with 12 image files. Do NOT change, add, or remove any HTML, CSS, JavaScript, images, or copy. Publishing only.

Steps:
1. If there is no git repo here, run: git init. Then stage everything with: git add -A  (must include CNAME and all of assets/). Commit with message: "seen site".
2. Create a new PUBLIC GitHub repo named "seencodigital" under my account and push, using: gh repo create seencodigital --public --source=. --remote=origin --push
   - If gh is not installed, stop and give me the install command for my OS, then wait.
   - If gh is not authenticated, stop and tell me to run "gh auth login", then wait.
3. Confirm the default branch is "main" and that CNAME is in the pushed commit (git ls-files must list it).
4. Enable GitHub Pages on the main branch, root folder, using the gh API.
5. GitHub Pages reads the CNAME file and sets the custom domain automatically. Tell me the DNS records I must add at my registrar:
   - Apex seencodigital.com -> A records: 185.199.108.153, 185.199.109.153, 185.199.110.153, 185.199.111.153
   - www.seencodigital.com -> CNAME -> <my-username>.github.io
6. Verify: curl -I https://<my-username>.github.io/seencodigital/ and confirm HTTP 200. Also curl -I the assets/seenco.png path and confirm 200. Report results and the live URL.

Rules:
- Never edit index.html, the assets, or the CNAME. This build is final and verified.
- Do NOT add a build step, framework, bundler, package.json, or CI config. It is intentionally plain static HTML.
- The contact form posts to Formspree (https://formspree.io/f/mgogvpal). Do not change or "improve" it.
- If any file 404s after deploy, tell me exactly which path and stop. Do not edit site files to fix it.
```

---

## One-time setup

If you've never used gh:
- Install (Mac): brew install gh
- Log in: gh auth login
