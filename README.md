<div align="center">

<img src="banner.png" alt="Lumi" width="100%" />

<br/>

<img src="logo.png" alt="Lumi Logo" width="72" />

# Lumi

### ✨ AI-powered social media autopilot

**Generates & posts content on X, Instagram, TikTok and LinkedIn — automatically. Zero API cost.**

<br/>

[![MIT License](https://img.shields.io/badge/License-MIT-blue.svg?style=for-the-badge)](LICENSE)
[![Python](https://img.shields.io/badge/Python-3.10+-3776AB?style=for-the-badge&logo=python&logoColor=white)](https://python.org)
[![Playwright](https://img.shields.io/badge/Playwright-45ba4b?style=for-the-badge&logo=playwright&logoColor=white)](https://playwright.dev)
[![Claude AI](https://img.shields.io/badge/Claude_AI-CC785C?style=for-the-badge&logo=anthropic&logoColor=white)](https://anthropic.com)
[![Twitter API](https://img.shields.io/badge/Twitter_API-$0-success?style=for-the-badge&logo=x&logoColor=white)]()

[![Stars](https://img.shields.io/github/stars/nuoyadev/lumi?style=for-the-badge&color=FFD700)](https://github.com/nuoyadev/lumi/stargazers)
[![Issues](https://img.shields.io/github/issues/nuoyadev/lumi?style=for-the-badge)](https://github.com/nuoyadev/lumi/issues)
[![Last Commit](https://img.shields.io/github/last-commit/nuoyadev/lumi?style=for-the-badge)](https://github.com/nuoyadev/lumi/commits/main)

</div>

---

## 📌 What is Lumi?

**Lumi** is a fully autonomous AI agent that manages your social media presence — so you can focus on building.

It reads your GitHub activity and custom ideas, then uses **Claude or GPT-4** to craft platform-native content and automatically posts it via **Playwright browser automation**. No paid social API. No manual work.

```
You ship something cool
       ↓
  Lumi reads your GitHub
       ↓
  AI crafts the post
       ↓
Playwright posts it live
       ↓
X • Instagram • TikTok • LinkedIn
```
---

## ⚡ Key Features

| | Feature | Description |
|---|---|---|
| 🤖 | **AI Content Generation** | Claude or GPT-4 crafts platform-native posts from your GitHub activity and ideas |
| 🌐 | **Browser-Based Posting** | Playwright automates the browser — zero paid API required |
| ⏰ | **Smart Scheduling** | GitHub Actions cron job runs Lumi daily, fully hands-off 24/7 |
| 🎯 | **Platform-Native Tone** | Different voice and format adapted per platform |
| 🔄 | **Multi-Platform** | Twitter/X, Instagram, TikTok, LinkedIn supported |
| 🛡️ | **Dry-Run Mode** | Preview every post before it goes live |
| 📦 | **No Paid API** | 100% free — uses browser automation, not official APIs |

---

## 🚀 Quick Start

### Prerequisites

- Python 3.10+
- Claude or OpenAI API key (for content generation)
- Twitter/X and/or Instagram credentials

### Installation

```bash
git clone https://github.com/nuoyadev/lumi.git
cd lumi
pip install -r requirements.txt
playwright install chromium
cp .env.example .env
# Fill in your keys and credentials in .env
```

### Run

```bash
# Preview without posting
python lumi.py --all --dry-run

# Post to all platforms
python lumi.py --all

# Post to specific platform
python lumi.py --platform twitter
```

### Automate with GitHub Actions

1. Fork this repo
2. `Settings → Secrets → Actions` — add your credentials
3. Lumi runs automatically every day at 9am UTC

```yaml
on:
  schedule:
    - cron: "0 9 * * *"   # Daily at 9am UTC
```

---

## 📁 Project Structure

```
lumi/
├── lumi.py                   # Entry point & orchestrator
├── content_generator.py      # LLM content generation (Claude/GPT-4)
├── scheduler.py              # Timing & scheduling logic
├── poster/
│   ├── twitter_poster.py     # Twitter/X Playwright automation
│   └── instagram_poster.py   # Instagram Playwright automation
├── config/
│   ├── platforms.yaml        # Per-platform settings & tone
│   └── prompts.yaml          # LLM prompt templates
├── .github/workflows/
│   └── lumi.yml              # GitHub Actions daily schedule
├── CLAUDE.md                 # AI instructions for Cursor
├── .env.example              # Environment variable template
└── README.md
```

---

## 🛠️ Tech Stack

| Layer | Technology |
|---|---|
| **Language** | Python 3.10+ |
| **AI Engine** | Claude (Anthropic) / GPT-4 (OpenAI) |
| **Browser Automation** | Playwright (async) |
| **Scheduling** | GitHub Actions (cron) |
| **Configuration** | YAML + .env |
| **Platforms** | Twitter/X, Instagram, TikTok, LinkedIn |

---

## 📍 Roadmap

### Phase 1 — Foundation
- [x] Project setup and architecture
- [x] CLAUDE.md — AI instructions for Cursor
- [ ] `content_generator.py` — LLM integration
- [ ] `twitter_poster.py` — Twitter/X Playwright bot
- [ ] `instagram_poster.py` — Instagram Playwright bot
- [ ] `scheduler.py` — orchestration & timing
- [ ] `.github/workflows/lumi.yml` — GitHub Actions schedule

### Phase 2 — Intelligence
- [ ] GitHub activity auto-reader
- [ ] Dry-run preview mode
- [ ] Post history & deduplication
- [ ] Optimal posting time detection

### Phase 3 — Scale
- [ ] TikTok & LinkedIn support
- [ ] Multi-account management
- [ ] Web dashboard & analytics
- [ ] Custom content queue (JSON/YAML)

---

## 🔐 Environment Setup

```env
# .env.example

# LLM Provider (at least one required)
ANTHROPIC_API_KEY=sk-ant-...
OPENAI_API_KEY=sk-...              # Optional fallback
LLM_PROVIDER=claude                # claude | openai

# Twitter / X
TWITTER_USERNAME=@yourhandle
TWITTER_PASSWORD=yourpassword

# Instagram
INSTAGRAM_USERNAME=yourhandle
INSTAGRAM_PASSWORD=yourpassword

# Settings
DRY_RUN=false
POST_PLATFORMS=twitter,instagram
POSTING_TIME=09:00
```

---

## 🤝 Contributing

Contributions are welcome!

1. Fork the project
2. Create your feature branch: `git checkout -b feature/amazing-feature`
3. Commit your changes: `git commit -m "feat: add amazing feature"`
4. Push: `git push origin feature/amazing-feature`
5. Open a Pull Request

Please follow [Conventional Commits](https://www.conventionalcommits.org/) for commit messages.

---

## 📄 License

Distributed under the **MIT License**. See [`LICENSE`](LICENSE) for more information.

---

## 👤 Author

**Talon Cutler** — [@nuoyadev](https://github.com/nuoyadev)

> *"Because building is more important than posting about building — so let Lumi handle it."*

---

<div align="center">

<img src="wordmark.png" alt="Lumi — AI Social Media Autopilot" width="600" />

<br/><br/>

**⭐ If Lumi saves you time, give it a star!**

[![GitHub stars](https://img.shields.io/github/stars/nuoyadev/lumi?style=social)](https://github.com/nuoyadev/lumi/stargazers)

</div>
