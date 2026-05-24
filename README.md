# 7 Brew Caffeine Calculator — Neon Coffee Lab Edition

> A lightweight cross-browser extension that calculates caffeine, calories, and energy levels for 7 Brew drinks. Pick your drink, size, and extra shots — get your numbers instantly.

<p align="center">
  <a href="https://chromewebstore.google.com/detail/7-brew-caffeine-calculato/nhgkbdedfmeijiephbkacjjfmdhhpdoa">
    <img src="https://img.shields.io/badge/Chrome-Add%20to%20Chrome-4285F4?style=for-the-badge&logo=googlechrome&logoColor=white" alt="Chrome Web Store" />
  </a>
  &nbsp;
  <a href="https://addons.mozilla.org/en-US/firefox/addon/7-brew-caffeine-calculator/">
    <img src="https://img.shields.io/badge/Firefox-Add%20to%20Firefox-FF7139?style=for-the-badge&logo=firefox&logoColor=white" alt="Firefox Add-ons" />
  </a>
  &nbsp;
  <a href="EDGE_ADDON_LINK_HERE">
    <img src="https://img.shields.io/badge/Edge-Add%20to%20Edge-0078D7?style=for-the-badge&logo=microsoftedge&logoColor=white" alt="Microsoft Edge Add-ons" />
  </a>
</p>

---

## ✨ Features

- **Animated Energy Gauge** — Circular SVG progress ring with four tiers: `LOW` · `MODERATE` · `HIGH` · `EXTREME`
- **Full Drink Database** — Search and filter the complete 7 Brew menu including Cold Brew, Blondie, Brunette, Smooth 7, Mochas, and more
- **Size Selection** — Small (16 oz), Medium (24 oz), Large (32 oz)
- **Espresso Shot Additions** — Add up to 2 extra shots; caffeine (+75mg) and calories (+5 kcal) update in real time
- **Live FDA Limit Tracker** — Progress bars tracking your intake against the 400mg daily caffeine limit
- **Favorites** — Save drink + size + shot combinations and reload them as one-tap pills
- **⚡ OVERLOAD** — Instantly load max-caffeine configuration (Large Cold Brew + 2 shots)
- **🌱 ZERO-CAL Filter** — One tap to filter the menu to drinks under 150 kcal (Small size)
- **No account required** — Everything is stored locally on your device using `chrome.storage.local`
- **No tracking, no analytics, no data collection**

---

## 🌐 Install from Store

| Browser | Link |
|---|---|
| Google Chrome | [Chrome Web Store →](https://chromewebstore.google.com/detail/7-brew-caffeine-calculato/nhgkbdedfmeijiephbkacjjfmdhhpdoa) |
| Mozilla Firefox | [Firefox Add-ons (AMO) →](https://addons.mozilla.org/en-US/firefox/addon/7-brew-caffeine-calculator/) |
| Microsoft Edge | [Edge Add-ons →](EDGE_ADDON_LINK_HERE) |

---

## 🛠 Load Locally (Developer Mode)

### Google Chrome / Chromium
1. Go to `chrome://extensions/`
2. Enable **Developer mode** (top-right toggle)
3. Click **Load unpacked**
4. Select the `caffeine-calculator/chrome/` folder

### Mozilla Firefox
1. Go to `about:debugging#/runtime/this-firefox`
2. Click **Load Temporary Add-on...**
3. Navigate to `caffeine-calculator/firefox/` and select `manifest.json`

### Microsoft Edge
1. Go to `edge://extensions/`
2. Enable **Developer mode** (bottom-left toggle)
3. Click **Load unpacked**
4. Select the `caffeine-calculator/edge/` folder

---

## 📁 Project Structure

```
7 brew menu/
│
├── caffeine-calculator/        # Browser Extension
│   ├── shared/                 # Master source files (edit here)
│   │   ├── assets/             # Master icon assets
│   │   ├── data/               # drinks.json — drink database
│   │   ├── logic/              # calculator.js — core caffeine/calorie logic
│   │   └── popup/              # popup.html · popup.css · popup.js
│   │
│   ├── chrome/                 # Built Chrome extension (auto-generated)
│   ├── edge/                   # Built Edge extension (auto-generated)
│   ├── firefox/                # Built Firefox add-on (auto-generated)
│   │
│   ├── sync.py                 # Syncs shared/ → chrome/, edge/, firefox/
│   └── generate_icons.py       # Generates neon icon set programmatically
│
└── neon-coffee-lab-theme/      # Matching browser theme
    ├── chrome/
    ├── edge/
    └── firefox/
```

---

## 🔧 Development

All source code lives in `caffeine-calculator/shared/`. Never edit the browser-specific folders directly — they are overwritten by the sync script.

### Sync changes to all browsers
```bash
cd caffeine-calculator
python sync.py
```

### Regenerate icons
```bash
cd caffeine-calculator
python generate_icons.py
python sync.py
```

---

## 📊 Caffeine Reference

| Energy Level | Caffeine Range | Visual |
|---|---|---|
| LOW | < 100 mg | Neon teal glow |
| MODERATE | 100 – 199 mg | Warm amber glow |
| HIGH | 200 – 349 mg | Neon orange glow |
| EXTREME | ≥ 350 mg | Pulse-animated red glow |

> FDA recommended daily maximum: **400 mg**

**Shot additions:** +75 mg caffeine · +5 kcal per extra espresso shot

---

## 🎨 Neon Coffee Lab Theme

A matching dark browser theme ships alongside the extension. It applies to Chrome, Edge, and Firefox and uses the same color palette as the extension UI.

| Element | Color |
|---|---|
| Frame / Background | `#0f1115` — Near black |
| Toolbar | `#161920` — Deep espresso charcoal |
| URL Bar | `#12141a` — Dark slate |
| Tab & Bookmark Text | `#f5f5f5` — Soft white |
| Browser Controls | `#00c2ff` — Electric neon blue |

Install it the same way as the extension via **Load unpacked** from the `neon-coffee-lab-theme/chrome/` (or `/edge/`, `/firefox/`) folder.

---

## 🔒 Privacy

- **Permissions used:** `storage` only
- **What is stored:** Your saved favorite drink configurations (drink name, size, shot count)
- **What is NOT stored:** Browsing history, personal information, or any identifiable data
- **Data location:** Your device only — nothing is ever transmitted or shared

---

## 📄 License

MIT — free to use, fork, and modify.
