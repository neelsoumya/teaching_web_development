# INTERNAL (Deployment Instructions)

This document contains internal deployment instructions for the project. It is intended for use by the development and operations teams only.

## Deployment Steps

Generated using GPT-4:

Here’s a clear, copy-pasteable, step-by-step guide to publish your existing `README.md` as a GitHub Pages site **with literally zero build tooling**. I’ll include optional tweaks (front matter, index.md, .nojekyll, custom domain) and troubleshooting tips so you can pick whatever fits.

---

# Goal

Publish `README.md` in this repo as a static site at:
`https://neelsoumya.github.io/teaching_web_development/`

---

## 1 — Quick checklist (what you need)

* A GitHub repo (you already have `https://github.com/neelsoumya/teaching_web_development`).
* A `README.md` at the repo root (you already have one).
* A GitHub account with access to that repo.
* A minute or two to flip the Pages setting in the repo Settings.

---

## 2 — Step-by-step: enable GitHub Pages (root, no tooling)

1. Open your repo in the browser:
   `https://github.com/neelsoumya/teaching_web_development`

2. Click **Settings** (top row of tabs; sometimes a gear icon).
   *If you don’t see Settings, expand the left sidebar or look under “Code and automation” depending on UI version.*

3. In the Settings page, choose **Pages** in the left sidebar (or find the **Pages** section on the Settings page).

4. Under **Build and deployment** → **Source**, choose:

   * **Branch**: `main` (or whichever branch you use)
   * **Folder**: `/ (root)`
     Then click **Save** (or **Save/Save changes**).

5. After saving, GitHub will show a *deploy status* and the site URL (something like `https://neelsoumya.github.io/teaching_web_development/`). Click that URL after a minute to view your site.

> Note: GitHub takes a short time (usually under a minute) to build and publish. If you see a 404 immediately, wait ~60s, then refresh.

---

## 3 — Recommended small improvements (optional but useful)

### A. Use `index.md` instead of `README.md` (optional)

Although `README.md` works, `index.md` is the conventional homepage name for docs sites.

To create/rename locally:

```bash
git clone https://github.com/neelsoumya/teaching_web_development.git
cd teaching_web_development
git mv README.md index.md
git commit -m "Rename README.md -> index.md for GitHub Pages site"
git push origin main
```

(or edit in the GitHub web UI)

### B. Add simple Jekyll front matter for a page title (optional)

If you want control over the HTML `<title>`, add YAML front matter at the top of the Markdown file:

```markdown
---
title: Teaching Web Development
---
# Teaching Web Development

Welcome — the rest of your README content...
```

This helps Jekyll set the page title.

### C. Keep navigation between your `.md` files

Link to other markdown files using relative links:

```markdown
[URL components](url_components.md)
[Lesson 1](lesson1.md)
```

These links usually work when GitHub Pages (Jekyll) converts Markdown to HTML.

### D. (Optional) Add a `.nojekyll` file if you want GitHub to NOT run Jekyll

If you have files/folders that start with an underscore or want raw static serving:

```bash
touch .nojekyll
git add .nojekyll
git commit -m "Disable Jekyll processing"
git push origin main
```

This prevents Jekyll from filtering files beginning with `_`.

---

## 4 — How to edit content and update the site

* Edit the `README.md` (or `index.md`) in the repo (web UI or locally).
* Commit and push to `main`.
* GitHub Pages will automatically rebuild and update the site (usually within a minute).

Example local workflow:

```bash
# edit files
git add index.md
git commit -m "Update lesson content"
git push origin main
# wait ~60s and refresh your pages URL
```

---

## 5 — Custom domain & HTTPS (optional)

If you want a custom domain (e.g., `teaching.example.com`):

1. Create a file `CNAME` in the repo root containing your domain:

```
teaching.example.com
```

2. Push it to `main`.
3. In the Pages settings, add your custom domain and enable HTTPS once DNS is set up (you’ll need to point your DNS A/CNAME records to GitHub Pages per GitHub’s instructions).

---

## 6 — Troubleshooting & common gotchas

* **404 after enabling**: wait ~60 seconds; refresh. Then check the Pages settings for any build errors.
* **Page shows repo root listing instead of rendered Markdown**: Make sure you chose **root** folder and that `index.md` or `README.md` exists at repo root.
* **Links to other MD files not working**: use relative links and include the `.md` suffix (e.g., `lesson1.md`), or link to their HTML path after build. If you renamed files, check links.
* **Private repo**: GitHub Pages works for private repos on free accounts, but visibility and access differ — ensure your Pages settings allow public access if you want it public.
* **Want styling**: GitHub Pages uses Jekyll themes if you add front matter and a `_config.yml`. But that’s tooling territory — for “no tooling”, rely on plain Markdown.

---

## 7 — Quick checklist summary you can run now

1. Confirm `README.md` exists in root.
2. Go to **Settings → Pages**, set **Source = main / (root)**, Save.
3. Wait ~1 minute, then open `https://neelsoumya.github.io/teaching_web_development/`.
4. Edit `README.md` to update pages; commit + push to update the live site.

---


If you like, I can now:

* Produce a ready-to-commit `index.md` (converted from your README) with a small YAML front matter and a short site title — copy/paste ready.
* Or produce a one-line `.nojekyll` and `CNAME` example if you want to disable Jekyll or add a custom domain.

Which one would you like me to generate for immediate copy/paste into your repo?
