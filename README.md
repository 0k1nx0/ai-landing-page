# Abdullah Mohammed — Portfolio

Personal portfolio website. AI Developer specializing in Computer Vision and Data Annotation.

🔗 **Live:** https://0k1nx0.github.io  *(after setup below)*

## Tech
Single self-contained `index.html` — no frameworks, no build step. Pure HTML/CSS/JS.

## Deploy to GitHub Pages (free)

1. Create a new repository named **`0k1nx0.github.io`** (must match your username exactly).
2. Upload `index.html`, `Abdullah_Mohammed_Resume.pdf`, and this README.
3. Go to **Settings → Pages → Source: `main` branch / root** → Save.
4. Your site goes live at **https://0k1nx0.github.io** in ~1 minute.

### Or deploy by drag-and-drop
- **Netlify:** https://app.netlify.com/drop — drag the whole `portfolio` folder.
- **Vercel:** https://vercel.com — import or drag the folder.

## 🔴 Live "trending in AI" headline + bot

The hero headline cycles in a **live trend** that auto-updates. A GitHub Action
(`.github/workflows/update-trending.yml`) is the "bot": on a schedule it pulls real
Hacker News top stories, asks a **free OpenRouter model** to turn them into a short phrase,
and — **only if it changed** — saves it to `data/trending.json`, **emails you the new trend**,
and pings the site + Hugging Face Space to keep them warm. If nothing changed, it does nothing
(no commit, no email). If the file is missing entirely, the headline falls back to built-in
phrases — nothing breaks.

**When does the bot run?** 4×/day (01:17, 07:17, 13:17, 19:17 UTC). Change the `cron:` line to
adjust. You can also run it on demand: **Actions tab → "Trending bot" → Run workflow**.

### Required GitHub secrets
Repo → **Settings → Secrets and variables → Actions → New repository secret**:

| Secret | Value |
|---|---|
| `OPENROUTER_API_KEY` | Free key from https://openrouter.ai/keys |
| `MAIL_USERNAME` | `kingabdullah9194@gmail.com` |
| `MAIL_PASSWORD` | A Gmail **App Password** (see below) — NOT your normal password |

**Getting the Gmail App Password** (needed so the bot can email you):
1. Turn on 2-Step Verification: https://myaccount.google.com/security
2. Create an app password: https://myaccount.google.com/apppasswords → name it "Portfolio Bot" → copy the 16-character code.
3. Paste that code as the `MAIL_PASSWORD` secret.

### One more setting
Repo → **Settings → Actions → General → Workflow permissions → "Read and write permissions"** → Save.
(Lets the bot commit the updated JSON, which auto-redeploys GitHub Pages.)

### How you'll know it worked
- You get an **email** with the new phrase whenever it changes.
- Visit **https://amtoz.in/data/trending.json** — `source` changes from `"seed"` to
  `"Hacker News + OpenRouter…"` and `updatedAt` shows a recent time.
- The headline on the site rotates the new phrase in.

**Reliability (why it won't break):**
- The bot tries **several free AI models in order** (`MODELS:` line). If one is rate-limited
  (HTTP 429) it instantly tries the next.
- If **all** free models are busy, it falls back to building the phrase **directly from the top
  Hacker News headline** — no AI, no key, no credits. So a run essentially never hard-fails.
- The **email is optional**: if you don't set `MAIL_USERNAME` / `MAIL_PASSWORD`, the bot still
  updates the trend silently — it just won't email you.
- **Cost:** $0. Everything uses free models / free APIs.

## Contact
- Email: kingabdullah9194@gmail.com
- GitHub: https://github.com/0k1nx0
- LinkedIn: https://linkedin.com/in/mohammed-abdullah-82191a380
