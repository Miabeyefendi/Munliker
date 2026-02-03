# 📘 Munliker: Detailed Configuration & Customization Guide

> **[TR] Türkçe rehber için [buraya tıklayın](egitim.md)** 
> *For the Turkish version of this guide, click the link above.*

Welcome to the technical deep-dive of **Munliker**. This guide explains the architecture of the bot, what each file does, and which specific lines you should modify to customize the bot's behavior, speed, and stealth levels.

---

## 🏗️ Project Architecture Overview

Munliker is built on a modular structure. Instead of one giant script, tasks are divided into specialized managers:
- **Core Logic:** `config.py` & `main.py`
- **Behavioral Simulation:** `human_actions.py`
- **Execution:** `unlike_manager.py`
- **Session & Auth:** `session_manager.py` & `instagram_auth.py`
- **Diagnostic Tools:** `debug.py`, `finder.py`, `detector.py`

---

## ⚙️ 1. `config.py` — The Central Brain

This is the most important file for users. Almost every numerical value that controls the bot is located here.

### 🕒 Unlike Speed & Limits
- **`MAX_UNLIKE_PER_HOUR`**: Set to `44` by default. 
  - *Modification:* If your account is old (5+ years), you can push this to `50-60`. If it's a new account, drop it to `20`.
- **`UNLIKE_DELAY`**: `(7, 45)` seconds. 
  - *Modification:* This is the random wait time between each unlike. To be ultra-safe, change it to `(30, 90)`.
- **`UNLIKE_FIRST_BATCH` & `SECOND_BATCH`**: 
  - *Logic:* The bot unlikes a few posts, then goes to watch Reels/DMs, then unlikes again. These tuples define the "count" per batch.

### 📱 Device Emulation (Samsung Galaxy S24 Ultra)
- **`VIEWPORT`**: `{"width": 412, "height": 915}`. Matches the S24 Ultra screen ratio.
- **`USER_AGENT`**: A specific string that tells Instagram you are using the latest Chrome on Android 14.
- **`DEVICE_PROFILE`**: Contains locale (`tr_TR`) and timezone. 
  - *Customization:* If you are using the bot outside Turkey, change `locale` and `timezone` to match your local area to avoid "Suspicious Login" flags.

---

## 🎭 2. `human_actions.py` — The Stealth Engine

This file contains "Filler Actions." If the bot only unliked posts, Instagram's AI would flag it instantly. This script makes the bot look like a bored human.

- **`REELS_VIEW_TIME_LONG`**: `(14, 35)` seconds.
  - *Logic:* Occasionally, the bot watches a full Reel instead of just skipping.
- **`REELS_LONG_CHANCE`**: `0.3` (30% chance).
  - *Modification:* Increase this to `0.5` to make the bot stay on Reels longer, increasing "Account Warmth."
- **`browse_home()`**: This function reloads the feed and scrolls randomly. It mimics checking for new posts from friends.

---

## 🧹 3. `unlike_manager.py` — The Executioner

This is where the actual clicking happens. It handles the navigation to the "Liked Posts" page and the logic of finding the "Unlike" button.

### 🔍 Grid Navigation System
Instagram's "Activity" page is a 3-column grid.
- **`row_start = 180`**: The vertical starting point (in pixels) where the first row of images begins.
- **`row_height = 130`**: The distance between rows.
- *Tip:* If Instagram updates its UI and the bot starts clicking "empty space," you need to adjust these pixel values using `finder.py`.

### 🔃 The Auto-Filter Logic
- **`apply_oldest_filter()`**: This is a sophisticated function that clicks the "Sort & Filter" button and selects "Oldest to Newest." 
  - *Why?* Cleaning your history from 2015 is safer than unliking your 2024 likes immediately.

---

## 🔐 4. `session_manager.py` & `auth` — Staying Logged In

- **`COOKIES_FILE = "cookies.json"`**: Once you log in manually for the first time, the bot saves your session here. 
- **`AutomationControlled`**: We use a specific browser argument `--disable-blink-features=AutomationControlled` to hide the fact that the browser is controlled by Playwright.

---

## 🛠️ 5. Diagnostic Tools (For Developers)

If the bot stops working, use these scripts to find out why:

1. **`debug.py`**: Runs a visual browser and logs every single network attempt. Check this if you are getting "Timeout" errors.
2. **`finder.py`**: A vital tool. It scans the current page and prints the **X and Y coordinates** of every button. If you want to add a new feature (like auto-commenting), use this to find the button coordinates.
3. **`detector.py`**: Analyzes the "Heart" icon. Instagram often changes the internal code of the Like button. This script detects the new SVG path or ARIA-label.

---

## ⚠️ Security Best Practices

To keep your account 100% safe:
1. **Don't Overdo It:** Don't run the bot 24/7. Use it for 2-3 hours, then stop.
2. **Manual Activity:** Log in to your Instagram on your real phone occasionally and browse normally while the bot is NOT running.
3. **IP Consistency:** If possible, run the bot on the same Wi-Fi network you usually use for your phone.

---

## 📝 How to Modify: A Quick Example

**Goal:** I want the bot to be much slower and only unlike 10 posts per hour.

1. Open `config.py`.
2. Change `MAX_UNLIKE_PER_HOUR = 10`.
3. Change `UNLIKE_DELAY = (60, 120)` (Wait 1 to 2 minutes between unlikes).
4. Save and run `python main.py`.

---
**Munliker** - *Engineered for Stealth, Built for Cleanliness.*
