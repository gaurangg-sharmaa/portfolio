# Gaurang Sharma — Portfolio

A single-page portfolio site for Gaurang Sharma, Java Spring Boot Backend Developer.
Built as a plain HTML/CSS/JS static site — **no build step, no framework, no npm install required.** This keeps it fast, dependency-free, and trivial to host anywhere (Vercel, Netlify, GitHub Pages).

All content (experience, projects, skills, education, contact info) is pulled directly from the resume — nothing invented.

## Project structure

```
portfolio/
├── index.html      # entire site (markup + inline CSS + inline JS)
├── resume.pdf       # downloadable resume (linked from the nav and hero)
├── vercel.json       # optional Vercel config (clean URLs, cache headers)
├── .gitignore
└── README.md
```

## Run it locally

No install needed — any static file server works:

```bash
# Option 1: Python (already on most machines)
python3 -m http.server 8080
# then open http://localhost:8080

# Option 2: Node, if you have it
npx serve .
```

## What's already been checked

- ✅ All HTML tags balanced, no broken markup
- ✅ Every nav link (`/about`, `/experience`, `/projects`, `/skills`, `/education`, `/contact`) resolves to a real section on the page
- ✅ `resume.pdf` loads and downloads correctly
- ✅ Responsive from mobile (375px) through desktop, with a working hamburger menu below 780px
- ✅ Keyboard-focus outlines and a "skip to content" link for accessibility
- ✅ Respects `prefers-reduced-motion`
- ✅ LinkedIn (`linkedin.com/in/gaurang-sharma`) and GitHub (`github.com/gaurang003`) links point to the exact handles from the resume

**One thing to double check yourself:** the LinkedIn and GitHub URLs were built from the handles printed on your resume. Open both links once after deploying to confirm they're live and spelled correctly — I can't verify third-party account status from here.

## Deploy for free — step by step

### 1. Push to GitHub

```bash
cd portfolio
git init
git add .
git commit -m "Initial portfolio site"
git branch -M main
git remote add origin https://github.com/gaurang003/portfolio.git
git push -u origin main
```

(Create the empty `portfolio` repo on GitHub first at github.com/new — don't initialize it with a README so this push doesn't conflict.)

### 2. Deploy to Vercel

**Easiest path — Vercel dashboard (no CLI needed):**
1. Go to https://vercel.com/new
2. Click **Import Git Repository** and select `gaurang003/portfolio`
3. Framework Preset: choose **"Other"** (it's a static site — no build command needed)
4. Leave Build Command and Output Directory blank
5. Click **Deploy**

You'll get a live URL like `https://portfolio-gaurang003.vercel.app` in under a minute.

**Or via CLI, if you prefer the terminal:**

```bash
npm install -g vercel   # one-time
cd portfolio
vercel login
vercel --prod
```

Follow the prompts (link to a new project, accept the defaults). This deploys straight from your local folder without needing GitHub at all, though pushing to GitHub first is recommended so Vercel can auto-redeploy on every future `git push`.

### 3. (Optional) Custom domain / cleaner URL

In the Vercel dashboard → your project → **Settings → Domains**, you can rename the project (e.g. `gaurang-sharma.vercel.app`) for free, or attach a custom domain if you buy one later.

## Putting it on your resume / LinkedIn

Once deployed, add the Vercel URL to:
- Your resume header, next to your email/phone
- Your LinkedIn profile's "Contact info" → Website field
- Your LinkedIn "Featured" section

## Updating content later

Everything lives in `index.html` — experience bullets, project descriptions, and skills are plain text in clearly labeled sections (`<!-- EXPERIENCE -->`, `<!-- PROJECTS -->`, etc.). Edit directly, then:

```bash
git add .
git commit -m "Update content"
git push
```

Vercel auto-redeploys on every push to `main` once the GitHub repo is connected.
