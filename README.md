# The Scout — marketing site

Static portfolio and landing page for the **The Scout** mobile app. Same look as the Flutter app: substitution-board identity, `#222` / `#2def81` palette, brand SVGs in `assets/brand/`.

This folder is meant to live **in its own Git repository** (sibling to the Flutter `the_scout` app is fine on your machine). It does **not** need to be inside the Flutter project.

## Preview locally

```bash
cd the_scout_website
python3 -m http.server 8080
```

Open [http://127.0.0.1:8080](http://127.0.0.1:8080).

## Connect to GitHub (new repository)

1. On GitHub, create a **new empty repository** (any name, e.g. `the-scout-site`). Do not add a README, `.gitignore`, or license in the UI if you want a simple first push.

2. In a terminal, from **this folder** (the one that contains `index.html`):

```bash
git init
git add .
git commit -m "Add The Scout marketing site"
git branch -M main
git remote add origin https://github.com/YOUR_USER/YOUR_REPO.git
git push -u origin main
```

Use your real GitHub user/org and repo name in the URL. Use SSH if you prefer: `git@github.com:YOUR_USER/YOUR_REPO.git`

3. **Turn on GitHub Pages**
   - Repo **Settings** → **Pages** → **Build and deployment** → **Source: GitHub Actions** (not “Deploy from a branch” for the workflow in this project).

4. The workflow **`.github/workflows/github-pages.yml`** runs on every push to `main` (or manually under **Actions**). The first run may ask you to **approve** the `github-pages` **environment** (one-time in **Settings** → **Environments** if needed).

5. After a green run, the site URL is usually:

   `https://YOUR_USER.github.io/YOUR_REPO/`

   Paths in this site are **relative**, so it works for project Pages URLs like the one above.

### If you do not use Actions

**Settings** → **Pages** → **Deploy from a branch** → branch `main`, folder **`/` (root)**. You do not need the workflow for that option.

## What’s in this folder

- `index.html` — one-page product story, pillars, features, store placeholders.
- `css/main.css` — layout and brand colors.
- `assets/brand/` — brand SVGs (copy fresh from the Flutter `assets/brand/` if you re-export artwork).
- `legal/` — privacy, terms, support (static HTML).
- `.nojekyll` — for GitHub Pages.
- `.github/workflows/github-pages.yml` — optional automatic deploy to Pages.

## Syncing art from the Flutter app

When `assets/brand/*.svg` changes in the mobile app, copy the updated files into this project’s `assets/brand/`.

## License

Match whatever you use for the main The Scout app.
