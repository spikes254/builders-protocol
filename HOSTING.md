# Hosting Guide

Three platforms. One file. No ongoing cost.

---

## Option 1 — GitHub Pages (Recommended Primary)

### Step 1 · Create the repository

1. Go to [github.com](https://github.com) → sign in
2. Click **+** (top right) → **New repository**
3. Fill in:
   - **Repository name:** `builders-protocol`
   - **Description:** `A zero-dependency operating system for self-taught technical builders`
   - **Visibility:** ✅ Public  
   - **Initialize with README:** ✅ (tick this)
4. Click **Create repository**

---

### Step 2 · Upload the files

1. Inside your new repo, click **Add file** → **Upload files**
2. Drag and drop all files from this folder:
   - `index.html`
   - `README.md`
   - `HOSTING.md`
   - `LICENSE`
   - `.github/` folder (the whole folder)
3. Scroll down → **Commit message:** `Initial release`
4. Click **Commit changes**

> ⚠️ The main HTML file **must be named `index.html`** for GitHub Pages to serve it as the homepage.

---

### Step 3 · Enable GitHub Pages

1. In your repo, click **Settings** (top tab)
2. Left sidebar → scroll to **Pages**
3. Under **Source** → select **Deploy from a branch**
4. **Branch:** `main` | **Folder:** `/ (root)`
5. Click **Save**

Wait 2–3 minutes. Refresh the Settings → Pages screen.

Your URL will appear:
```
https://YOUR_USERNAME.github.io/builders-protocol
```

---

### Step 4 · Update the README badges

Open `README.md` → click the pencil icon (Edit) → replace `YOUR_USERNAME` with your actual GitHub username in these two lines:

```markdown
[![Live Demo](https://img.shields.io/badge/Live_Demo-Open_Now-f59e0b?style=flat-square&logo=github)](https://YOUR_USERNAME.github.io/builders-protocol)
```

Commit the change. Done.

---

### Step 5 · Add a custom domain (optional)

If you own a domain (e.g. `macray.dev`):

1. Settings → Pages → **Custom domain** → type your domain → Save
2. At your DNS provider, add a `CNAME` record:
   - **Name:** `www` (or `@` for root)
   - **Value:** `YOUR_USERNAME.github.io`
3. Tick **Enforce HTTPS** once DNS propagates (~10 min)

---

## Option 2 — Cloudflare Pages

You already know this workflow from your ATD site. Fastest deploy.

1. Go to [pages.cloudflare.com](https://pages.cloudflare.com) → **Create a project**
2. Choose **Direct Upload** (not Git — you don't need CI/CD for a single file)
3. **Project name:** `builders-protocol`
4. Upload `index.html`
5. Click **Deploy site**

Live at: `builders-protocol.pages.dev`

To connect your GitHub repo instead:
1. Choose **Connect to Git** → authorize GitHub
2. Select the `builders-protocol` repo
3. **Build command:** leave empty
4. **Build output directory:** `/` (root)
5. Deploy

Every push to `main` auto-deploys. Zero config.

---

## Option 3 — Internet Archive (Permanent Institutional Backup)

This is not a hosting platform — it is a permanent preservation service. Use it as your second URL, not your primary one.

1. Go to [archive.org/upload](https://archive.org/upload)
2. Sign in (or create a free account — only needed once)
3. Upload `index.html`
4. Fill in the metadata:

| Field | Value |
|---|---|
| **Title** | The Builder's Protocol — A Legacy Codex for Self-Taught Technical Builders |
| **Description** | *(see below)* |
| **Subject tags** | self-education, independent learning, digital products, income generation, web development, cybersecurity, Kenya, emerging markets, decision framework, productivity, builder mindset, static site, open resource, self-taught, technical skills |
| **Creator** | Macray |
| **Language** | English |
| **Media type** | Texts |

**Description to paste:**
```
A self-contained, zero-dependency guide for self-taught technical builders 
operating without institutional support. Contains five core axioms, a 
seven-step self-education protocol, an interactive decision engine for 
resolving common builder dilemmas, and a four-tier income architecture 
framework. Built for anyone learning to code, study independently, or 
generate income from technical skills — particularly in emerging markets. 
No account required. No internet connection required after download. 
Works in any browser indefinitely.
```

5. Click **Upload and Create Your Item**

Your permanent URL:
```
https://archive.org/details/the-builders-protocol
```

> The Internet Archive's institutional mandate is literal preservation. This file will outlive every cloud platform on this list.

---

## Recommended Final Setup

| Platform | Role | URL format |
|---|---|---|
| GitHub Pages | Primary — share this one | `username.github.io/builders-protocol` |
| Internet Archive | Permanent backup | `archive.org/details/the-builders-protocol` |
| Cloudflare Pages | Optional mirror | `builders-protocol.pages.dev` |

Add both URLs to the README. If one goes down in 20 years, the other survives.

---

## Verifying Everything Works

After deploying, run this checklist:

- [ ] Open the GitHub Pages URL — page loads with no console errors
- [ ] Open browser DevTools → Network tab → confirm zero external requests
- [ ] Disconnect WiFi → reload page → still works (cached)
- [ ] Open on mobile — layout renders correctly
- [ ] Click all five axioms — expand/collapse works
- [ ] Run the Decision Engine through at least two paths
- [ ] Confirm the Internet Archive URL resolves and the file is accessible

If all boxes tick: you're done. No further action ever required.
