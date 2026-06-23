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

## 🔴 Live "trending in AI" headline (optional)

The hero headline can cycle in a **live trend** that auto-updates. A GitHub Action
(`.github/workflows/update-trending.yml`) runs every ~6 hours, pulls real Hacker News
top stories, asks a **free OpenRouter model** to turn them into a short phrase, and writes
it to `data/trending.json`. The site reads that file. If the file is missing or you skip
this, the headline just uses its built-in phrases — nothing breaks.

**Setup (one time):**
1. Get a free API key at https://openrouter.ai/keys
2. In your GitHub repo: **Settings → Secrets and variables → Actions → New repository secret**
   - Name: `OPENROUTER_API_KEY`
   - Value: your key
3. Make sure Actions can write: **Settings → Actions → General → Workflow permissions → Read and write permissions**.
4. Trigger it once: **Actions tab → "Update trending phrase" → Run workflow**.

**Notes**
- **Cost:** uses OpenRouter `:free` models — $0. Free models change names occasionally; if a run
  fails with "model not found", edit the `MODEL:` line in the workflow.
- **When free credits run out:** the workflow run **fails**, and GitHub **emails you automatically**
  (this is the built-in failure notification — no extra setup). The website keeps showing the last
  good phrase until credits reset and the next run succeeds.
- **Make sure notifications are on:** GitHub → your **Settings → Notifications → Actions →** check
  "Email" for failed workflows, and confirm your GitHub email is `kingabdullah9194@gmail.com`.

## Contact
- Email: kingabdullah9194@gmail.com
- GitHub: https://github.com/0k1nx0
- LinkedIn: https://linkedin.com/in/mohammed-abdullah-82191a380
