# Deploying to GitHub Pages

This project is configured as a static site that deploys to the `/docs` folder for GitHub Pages.

## 🚀 Quick Setup (3 Steps)

### Step 1: Push to GitHub

First, push your code to GitHub:

```bash
git add .
git commit -m "Setup GitHub Pages deployment"
git push origin main
```

### Step 2: Enable GitHub Pages

1. Go to your repository on GitHub
2. Click **Settings** → **Pages**
3. Under "Build and deployment":
   - **Source**: Select **"Deploy from a branch"**
   - **Branch**: Select **"main"**
   - **Folder**: Select **"/docs"**
4. Click **Save**

### Step 3: Wait for Build (Optional)

- The GitHub Actions workflow will automatically build and update the `/docs` folder
- After the workflow completes, your site will be live!
- **First time**: You can use the placeholder page immediately, the full site will replace it after the first build

**Your site will be live at:**
- User/Org page: `https://yourusername.github.io/` (if repo is named `username.github.io`)
- Project page: `https://yourusername.github.io/repository-name/`

---

## 📁 How It Works

**Static Site in `/docs` Folder**

- The built website (including `index.html`) lives in the `/docs` folder
- GitHub Pages serves files from `/docs` as if they were at the root
- Every push to `main` triggers a build that updates `/docs`

**Files:**
- `docs/index.html` ← This is your site's entry point
- `.github/workflows/deploy.yml` ← Builds and updates /docs automatically
- `docs/.nojekyll` ← Prevents Jekyll processing

---

## ⚙️ Base Path Configuration (Optional)

### User/Organization Page (`username.github.io`)
✅ **No configuration needed!** The site works immediately.

### Project Page (`username.github.io/repo-name`)
⚠️ **May need base path** for assets to load correctly.

If you're deploying to a project page and assets don't load:
1. Open `vite.config.ts`
2. Add `base: '/your-repo-name/',` inside `defineConfig({})`
3. Commit and push

---

## 🛠️ Local Development

The project uses Vite for development. To run locally:

```bash
npm install
npx vite
```

To manually build:

```bash
npm install
npx vite build
```

Built files will be in `dist/public/`, which the GitHub Actions workflow copies to `docs/`

## Project Structure

- `client/` - React frontend application
- `client/src/components/` - UI components (Navbar, Hero, Features, etc.)
- `client/src/pages/` - Page components
- `.github/workflows/deploy.yml` - GitHub Actions deployment workflow
- `.nojekyll` - Tells GitHub Pages to not process with Jekyll

## Features

- ✅ Automatic deployment on push to main branch
- ✅ React + TypeScript
- ✅ Tailwind CSS + shadcn/ui components
- ✅ Responsive design
- ✅ Dark mode support
- ✅ Modern landing page with Hero, Features, About sections

## Troubleshooting

### Site shows 404 or README
- Verify you selected **"Deploy from a branch"** (not GitHub Actions) in Settings → Pages
- Confirm **Branch: main** and **Folder: /docs** are selected
- Wait a few minutes for GitHub to process the deployment
- Check that `docs/index.html` exists in your repository

### Blank page or assets not loading (Project Pages)
- **Most common cause**: Missing base path in vite.config.ts for project pages
- If your repo is NOT named `username.github.io`:
  1. Open `vite.config.ts`
  2. Add `base: '/your-repo-name/',` inside `defineConfig({})`
  3. Commit and push
- Check browser console for 404 errors on .js/.css files

### Build not updating /docs
- Check the **Actions** tab on GitHub for workflow failures
- Ensure the workflow has write permissions (Settings → Actions → General → Workflow permissions)
- The workflow needs **Read and write permissions** to commit to /docs

### First deployment shows placeholder page
- This is expected! The placeholder helps you get started quickly
- After the first GitHub Actions build completes, it will be replaced with your full site
- Check the Actions tab to see build progress
