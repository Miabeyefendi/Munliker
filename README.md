# 🚀 Munliker: Humanized Instagram Unlike Bot

[TR | Türkçe Oku](README.tr.md)

**Munliker** is a smart, humanized Instagram cleaning tool. Unlike standard bots, it mimics real user behavior (watching Reels, checking Explore/DMs) to safely mass-unlike posts without triggering bans. Built with Playwright and modeled after a Samsung Galaxy S24 Ultra.

![Python](https://img.shields.io/badge/Python-3.8+-blue.svg)
![Playwright](https://img.shields.io/badge/Framework-Playwright-green.svg)
![Device](https://img.shields.io/badge/Device-Samsung_S23_FE-orange.svg)

---

## ✨ Features

- **🕵️ Advanced Stealth:** Emulates a Samsung Galaxy S24 Ultra with realistic User-Agent, viewport, and touch behaviors.
- **🎭 Human Logic:** Performs "filler" actions like browsing the home feed, watching Reels, and checking DMs between unliking batches.
- **⏳ Smart Rate Limiting:** Built-in hourly limits and random delays to stay under Instagram's radar.
- **🔄 Auto-Filter:** Automatically sorts likes from "Oldest to Newest" to clean your history chronologically.
- **📂 Session Persistence:** Saves and loads `cookies.json` to avoid repeated login attempts.

---

## 🛠️ Installation

1. **Clone the repo:**
```bash
git clone https://github.com/yourusername/munliker.git
cd munliker
```

2. **Install dependencies:**
```bash
pip install playwright
playwright install chromium
```

3. **Start the bot:**
```bash
python main.py
```

---

## 📖 Configuration Guide

You can customize the bot's behavior in the following files:

- **`config.py`**: The main brain. Change `MAX_UNLIKE_PER_HOUR`, adjust `UNLIKE_DELAY`, or modify device profiles.
- **`human_actions.py`**: Adjust how many Reels to watch or how many times to scroll the Explore page.
- **`unlike_manager.py`**: Modify the grid clicking logic or filtering system.
- **`ui.py`**: Customize console outputs and logging styles.

---

## ⚠️ Disclaimer

This tool is for educational purposes only. Using bots on Instagram may violate their Terms of Service. The developer is not responsible for any account restrictions or bans. **Recommendation:** Keep the limit below 30 unlikes per hour for safety.

---

## 🤝 Contributing

Contributions, issues, and feature requests are welcome! Feel free to check the issues page.

---
**Munliker** - *Clean your past, keep your account safe.*
