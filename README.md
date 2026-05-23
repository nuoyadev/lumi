<div align="center">

<!-- TYPING SVG -->
[![Typing SVG](https://readme-typing-svg.demolab.com?font=Fira+Code&weight=700&size=32&pause=1000&color=A855F7&center=true&vCenter=true&width=600&lines=ghostpilot;Your+AI+Social+Media+Autopilot;Post+while+you+sleep+%F0%9F%A4%96)](https://github.com/nuoyadev/ghostpilot)

[![LICENSE](https://img.shields.io/badge/license-MIT-purple?style=flat-square)](LICENSE)
[![Python](https://img.shields.io/badge/python-3.10+-blue?style=flat-square&logo=python)](https://python.org)
[![Playwright](https://img.shields.io/badge/playwright-latest-green?style=flat-square&logo=playwright)](https://playwright.dev)
[![LLM](https://img.shields.io/badge/LLM-Claude%20%7C%20GPT--4-orange?style=flat-square)](https://anthropic.com)
[![Status](https://img.shields.io/badge/status-active-brightgreen?style=flat-square)]()
[![Zero API Cost](https://img.shields.io/badge/Twitter%20API-$0-success?style=flat-square)]()

> **Post on Twitter/X & Instagram automatically. No API fees. No manual work. Just results.**
>
> Built by [@nuoyadev](https://github.com/nuoyadev) — Because building is more important than posting about building.
>
> </div>

---

## 🧠 What is ghostpilot?

**ghostpilot** is an AI-powered social media autopilot that runs silently in the background and posts for you — every single day — while you focus on what actually matters: building.

It uses **LLMs (Claude / GPT-4)** to generate platform-native content from your ideas, projects, and GitHub activity, then uses **Playwright** to post directly via the browser — completely **free**, no API keys required for posting.

```
Your ideas / GitHub activity
        ↓
  LLM generates content
  (Twitter-optimized + IG-optimized)
        ↓
  Playwright opens browser
  → posts on Twitter/X
  → posts on Instagram
        ↓
  GitHub Actions runs this every morning at 9am
        ↓
  You wake up. Already posted. ✅
```

---

## 💀 The problem it kills

| Without ghostpilot | With ghostpilot |
|---|---|
| ❌ 0 posts because "no time" | ✅ Daily posts on autopilot |
| ❌ Twitter API costs $100+/mo | ✅ $0 — browser-based posting |
| ❌ Content feels generic | ✅ LLM-generated, platform-native tone |
| ❌ Posting manually is a job | ✅ Fully automated, runs on GitHub Actions |
| ❌ Your projects go unnoticed | ✅ Every commit, build & idea becomes content |

---

## ⚡ Features

- 🤖 **AI Content Generator** — Claude or GPT-4 generates tweets and Instagram captions from your topics, projects, or a simple prompt
- - 🎭 **Playwright Poster** — Posts directly via a real browser session. No official API. No cost.
  - - 🐦 **Twitter/X Support** — Full tweet posting with thread support (coming soon)
    - - 📸 **Instagram Support** — Caption-based posts with optional image
      - - ⏰ **GitHub Actions Scheduler** — Runs every morning via cron, zero infrastructure needed
        - - 🧠 **GitHub-Aware Mode** — Detects your latest commits and auto-generates content about what you built
          - - 📋 **Content Queue** — Pre-load ideas in a JSON file, ghostpilot picks one daily
            - - 🌍 **Multi-platform tone** — Automatically adapts tone: punchy for Twitter, storytelling for Instagram
             
              - ---

              ## 🗂️ Project Structure

              ```
              ghostpilot/
              ├── 📁 src/
              │   ├── generator.py        # LLM content generation (Claude / GPT-4)
              │   ├── poster_twitter.py   # Playwright Twitter/X poster
              │   ├── poster_instagram.py # Playwright Instagram poster
              │   ├── github_scanner.py   # Scans your recent commits for content ideas
              │   └── scheduler.py        # Main orchestrator
              ├── 📁 content/
              │   └── queue.json          # Your content idea queue
              ├── 📁 .github/
              │   └── workflows/
              │       └── daily_post.yml  # GitHub Actions cron (runs daily at 9am)
              ├── config.example.py       # Config template (copy to config.py)
              ├── requirements.txt
              ├── .gitignore
              └── README.md
              ```

              ---

              ## 🚀 Quick Start

              ### 1. Clone the repo

              ```bash
              git clone https://github.com/nuoyadev/ghostpilot.git
              cd ghostpilot
              ```

              ### 2. Install dependencies

              ```bash
              pip install -r requirements.txt
              playwright install chromium
              ```

              ### 3. Configure

              ```bash
              cp config.example.py config.py
              ```

              Edit `config.py` with your settings:

              ```python
              # config.py
              LLM_PROVIDER = "claude"        # "claude" or "openai"
              LLM_API_KEY = "your-api-key"

              TWITTER_USERNAME = "your_username"
              TWITTER_PASSWORD = "your_password"

              INSTAGRAM_USERNAME = "your_username"
              INSTAGRAM_PASSWORD = "your_password"

              GITHUB_USERNAME = "nuoyadev"   # for GitHub-aware mode
              POST_TIME = "09:00"            # daily post time (UTC)
              ```

              ### 4. Add your content ideas

              Edit `content/queue.json`:

              ```json
              [
                {
                  "topic": "Just shipped a new feature on cerocrates — MCP-native agent routing",
                  "platforms": ["twitter", "instagram"],
                  "tone": "technical"
                },
                {
                  "topic": "Why most AI agents fail silently and how to fix it",
                  "platforms": ["twitter"],
                  "tone": "opinion"
                }
              ]
              ```

              ### 5. Run manually (test)

              ```bash
              python src/scheduler.py --dry-run     # preview generated content
              python src/scheduler.py --post-now    # post immediately
              ```

              ### 6. Deploy on GitHub Actions

              Push to GitHub. The `.github/workflows/daily_post.yml` cron job will run automatically every morning.

              Add your secrets in **Settings → Secrets → Actions**:
              - `LLM_API_KEY`
              - - `TWITTER_USERNAME` / `TWITTER_PASSWORD`
                - - `INSTAGRAM_USERNAME` / `INSTAGRAM_PASSWORD`
                 
                  - ---

                  ## 🛠️ Tech Stack

                  | Layer | Technology |
                  |---|---|
                  | 🧠 Content Generation | Claude API / OpenAI GPT-4 |
                  | 🎭 Browser Automation | Playwright (Chromium, headless) |
                  | ⏰ Scheduling | GitHub Actions (cron) |
                  | 🐍 Language | Python 3.10+ |
                  | 📋 Content Queue | JSON file |
                  | 🔐 Secrets Management | GitHub Actions Secrets |

                  ---

                  ## 🗺️ Roadmap

                  - [x] Core architecture & repo setup
                  - [ ] - [ ] `generator.py` — LLM content generation
                  - [ ] - [ ] `poster_twitter.py` — Twitter/X Playwright poster
                  - [ ] - [ ] `poster_instagram.py` — Instagram Playwright poster
                  - [ ] - [ ] `github_scanner.py` — Auto-detect commits for content
                  - [ ] - [ ] GitHub Actions workflow
                  - [ ] - [ ] Dry-run / preview mode
                  - [ ] - [ ] Thread support for Twitter
                  - [ ] - [ ] Image generation for Instagram (DALL-E / Stable Diffusion)
                  - [ ] - [ ] Web dashboard to manage queue
                 
                  - [ ] ---
                 
                  - [ ] ## 💭 Dev Philosophy
                 
                  - [ ] ```python
                  - [ ] class GhostPilot:
                  - [ ]     def __init__(self):
                  - [ ]         self.mission = "Post while you build"
                  - [ ]             self.cost = "$0"
                  - [ ]                 self.platforms = ["Twitter/X", "Instagram"]
                  - [ ]                     self.engine = ["Claude", "GPT-4", "Playwright"]
                 
                  - [ ]                     def run(self):
                  - [ ]                         while True:
                  - [ ]                                 content = self.generate()   # LLM creates the post
                  - [ ]                                         self.post(content)          # Playwright sends it
                  - [ ]                                                 self.sleep(hours=24)        # Repeat tomorrow
                  - [ ]                                             ```
                 
                  - [ ]                                         > *"The best builders ship in silence. ghostpilot makes sure the world still hears them."*
                 
                  - [ ]                                     ---
                 
                  - [ ]                                 ## 📄 License
                 
                  - [ ]                             MIT — free to use, fork, and build on.
                 
                  - [ ]                         ---
                 
                  - [ ]                     <div align="center">

                  Built with 🤖 by [Talon Cutler](https://github.com/nuoyadev) · [@TheTalonAlgo](https://x.com/TheTalonAlgo) · [@taloncutler](https://instagram.com/taloncutler)

                  **⭐ Star this repo if you're tired of posting manually**

                  </div>
