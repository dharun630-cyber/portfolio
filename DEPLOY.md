# Deploying to GitHub Pages

## 1. Create the repo
- Go to github.com → **New repository**
- Name it `portfolio` (or `yourusername.github.io` if you want it at the root domain — see note at the bottom)
- Set it to **Public** (GitHub Pages on the free tier requires public repos)
- Don't initialize with a README (you already have one)

## 2. Push these files
From this folder, in a terminal:

```bash
git init
git add .
git commit -m "Initial portfolio site"
git branch -M main
git remote add origin https://github.com/YOUR_USERNAME/portfolio.git
git push -u origin main
```

## 3. Turn on GitHub Pages
- In your repo, go to **Settings → Pages**
- Under "Build and deployment", set **Source** to `Deploy from a branch`
- Set **Branch** to `main`, folder `/ (root)`
- Save

Give it 1–2 minutes. Your site will be live at:
```
https://YOUR_USERNAME.github.io/portfolio/
```

## 4. Custom domain (optional)
If you buy a domain later, add it under **Settings → Pages → Custom domain**, and add a `CNAME` record at your DNS provider pointing to `YOUR_USERNAME.github.io`.

## Note on repo naming
If you name the repo exactly `YOUR_USERNAME.github.io`, GitHub serves it directly at `https://YOUR_USERNAME.github.io` (no `/portfolio/` path). This only works for one repo per account, so it's worth reserving that name for this site specifically if you don't plan to host anything else at your root domain.

## Updating the site later
Any time you edit `index.html` and want the live site to reflect it:
```bash
git add .
git commit -m "Update portfolio"
git push
```
GitHub Pages redeploys automatically within a minute or two.
