# seen.co — seencodigital.com

Single-page studio site. Static HTML, no build step, no framework. Deploys to GitHub Pages as-is.

## Files

```
index.html        the whole site
CNAME             custom domain: seencodigital.com
404.html          redirect to home
.nojekyll         serve files as-is
assets/           logos + site screenshots
```

## Member sign in

The nav and footer link to the client portal at:

    https://portal.seencodigital.com

If that is not the right URL, search index.html for `nav-signin` and for
`portal.seencodigital.com` (2 places: nav + footer) and update both.

## Contact form

The form posts to Formspree at https://formspree.io/f/mgogvpal
Submissions land in that Formspree account's inbox. No server needed.
To change where mail goes, update the address on the Formspree account (not this code).

## Deploy

From this folder:

```bash
git init
git add -A
git commit -m "seen site"
git branch -M main
gh repo create seencodigital --public --source=. --remote=origin --push
```

Then: GitHub -> repo Settings -> Pages -> Source: Deploy from a branch -> main / root -> Save.
GitHub reads CNAME and sets the domain to seencodigital.com automatically.

## DNS (to activate seencodigital.com)

At your registrar:
- Apex `seencodigital.com` -> A records: 185.199.108.153, 185.199.109.153, 185.199.110.153, 185.199.111.153
- `www.seencodigital.com` -> CNAME -> YOUR_USERNAME.github.io

The github.io URL works immediately; the custom domain follows once DNS propagates.

## Editing

Everything is in index.html. Swap any image by replacing the file in assets/.
