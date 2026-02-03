# 🚀 Munliker: Advanced Stealth Instagram Unlike Bot | By: @miabeyefendi

[![Python](https://img.shields.io/badge/Python-3.8+-blue.svg?style=for-the-badge&logo=python)](https://www.python.org/)
[![Playwright](https://img.shields.io/badge/Framework-Playwright-green.svg?style=for-the-badge&logo=playwright)](https://playwright.dev/)
[![Device](https://img.shields.io/badge/Device-Samsung_S24_Ultra-orange.svg?style=for-the-badge&logo=samsung)](https://github.com/Miabeyefendi/Munliker)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg?style=for-the-badge)](https://opensource.org/licenses/MIT)

[TR | Türkçe Oku](README.tr.md) | [Technical Tutorial](TUTORIAL.md) | [Türkçe Eğitim](egitim.md)

**Munliker** is a high-performance, human-mimicking Instagram activity cleaner.  
Unlike traditional mass-unlike scripts that trigger *Suspicious Activity* flags, Munliker uses advanced behavioral simulation to safely clean your liked posts history while staying completely under Instagram’s radar.

---

## 🔥 Why Munliker?

Traditional bots follow a predictable **click–click–click** pattern.  
**Munliker** breaks this pattern by behaving like a real human on a real mobile device.

- 🕵️ **Samsung Galaxy S24 Ultra Emulation**  
  Emulates a modern flagship device including screen resolution, touch behavior, and Android 14 user-agent strings.

- 🎭 **Humanized Filler Actions**  
  Scrolls the home feed, watches Reels for random durations, and checks DMs between actions.

- 🔄 **Smart Chronological Cleaning**  
  Automatically sorts liked posts from **Oldest to Newest**, allowing deep history cleanup first.

- ⏳ **Dynamic Rate Limiting**  
  Uses randomized human-like delays instead of static timers.

---

## ✨ Core Features

- **Advanced Stealth**  
  Anti-bot detection bypass including `navigator.webdriver` mitigation.

- **Session Persistence**  
  Saves authenticated sessions to `cookies.json` to avoid repeated logins.

- **Autonomous Filtering**  
  Fully automates Instagram’s *Sort & Filter* interface.

- **Detailed Logging**  
  Real-time console output with cycle plans and progress metrics.

- **Safety First**  
  Built-in hourly limits to reduce account restriction risk.

---

## 🛠️ Getting Started

### Prerequisites
- Python 3.8+
- Playwright

### Installation

Clone the repository:
```bash
git clone https://github.com/Miabeyefendi/munliker.git
cd munliker
```

Install dependencies:
```bash
pip install playwright
playwright install chromium
```

Launch the bot:
```bash
python main.py
```

**Note:**  
On first run, a browser window will open for manual login.  
Once you reach the Instagram home feed, the session is saved and automation begins.

---

## 📖 Detailed Guides

- 📘 **English Tutorial** — `TUTORIAL.md`  
  Deep dive into configuration, stealth logic, and behavior modeling.

- 📕 **Türkçe Eğitim** — `egitim.md`  
  Güvenli kullanım, hız ayarı ve profil özelleştirme rehberi.

---

## 📈 Version History

**v1.0.0**
- Samsung Galaxy S24 Ultra profile support
- Automated Oldest → Newest filtering
- Human-like batch processing (Reels / DMs / Explore)
- Added finder.py and debug.py for advanced troubleshooting

---

## ⚠️ Disclaimer & Safety

Munliker is developed for educational purposes only.  
Automated interaction with Instagram violates their Terms of Service.

The developer is not responsible for bans or restrictions.

**Pro Tip:**  
Keep MAX_UNLIKE_PER_HOUR under 30 and avoid running the bot continuously.

---

## 🤝 Contributing

Contributions are welcome.

1. Fork the project
2. Create your feature branch:
   ```bash
   git checkout -b feature/AmazingFeature
   ```
3. Commit your changes:
   ```bash
   git commit -m "Add AmazingFeature"
   ```
4. Push to the branch:
   ```bash
   git push origin feature/AmazingFeature
   ```
5. Open a Pull Request
