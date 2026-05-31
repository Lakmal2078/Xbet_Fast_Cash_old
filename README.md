# ⚡ Xbet Fast Cash — Payment Gateway

> ශ්‍රී ලාංකික ක්‍රීඩා ඔට්ටු ක්‍රීඩාකරුවන් සඳහා ක්ෂණික තැන්පතු, ආපසු ගැනීම් සහ 24/7 සහාය.  
> Instant deposits, withdrawals, and AI-powered support for Sri Lankan sports bettors.

---

## 📋 Overview

**Xbet Fast Cash** is a mobile-first single-page web application that acts as a **1xbet payment gateway** for Sri Lankan users. It provides a seamless interface for submitting deposits, requesting withdrawals, viewing bank details, and getting AI-assisted support — all styled in a modern dark-UI aesthetic.

---

## ✨ Features

| Feature | Description |
|---|---|
| 🏦 **Bank Details** | View and copy account numbers for Sampath, Peoples, LOLC, and iPay |
| 💸 **Deposit Form** | Submit deposit requests (redirects to WhatsApp with pre-filled message) |
| 💳 **Withdrawal Form** | Submit withdrawal requests (redirects to WhatsApp) |
| 🤖 **AI Assistant** | Claude-powered chatbot for support, answering in English or Sinhala |
| 📢 **Promo Code** | One-tap copy of promo code `VGSL` for new user bonus |
| 📊 **Live Transactions** | Real-time simulated activity feed for social proof |
| ⭐ **Customer Reviews** | Static review cards with star ratings |
| ❓ **FAQ Accordion** | Expandable FAQ in Sinhala + English |
| 💬 **WhatsApp FAB** | Floating action button for direct WhatsApp contact |

---

## 🗂️ File Structure

```
index.html          — Main application (single-file SPA)
README.md           — This file
```

Everything is contained in a single `index.html` file — no build step, no bundler, no server required.

---

## 🚀 Getting Started

### Option 1 — Open Directly

Simply open `index.html` in any modern browser. No setup needed.

```bash
open index.html
# or
double-click index.html
```

### Option 2 — Local HTTP Server (recommended for API calls)

```bash
# Python 3
python -m http.server 8080

# Node.js (npx)
npx serve .
```

Then visit `http://localhost:8080` in your browser.

---

## 🔧 Configuration

### Bank Accounts

Edit the `BANK_CONFIG` array near the bottom of `index.html`:

```js
window.BANK_CONFIG = [
  {
    bank: 'Sampath Bank',
    display: '123 456 7890',       // Display-formatted number
    number: '1234567890',          // Raw number (copied to clipboard)
    name: 'N. OSHADHI',
    color: '#60a5fa'                 // Accent colour for this card
  },
  // Add more banks here...
];
```

### WhatsApp Number

Search for `wa.me/947123456789` and replace with your number:

```
https://wa.me/<COUNTRY_CODE><NUMBER>
```

### Referral / Registration Link

Change the `href` on the **Register New Account** button:

```html
<a href="https://reffpa.com/L?tag=..." ...>Register New Account</a>
```

### Promo Code

Find `VGSL` in the HTML/JS and replace with your current code.

### AI Assistant System Prompt

The chatbot persona and knowledge base is defined in the `_chatHistory` array:

```js
const _chatHistory = [{
  role: 'system',
  content: 'You are the friendly AI support assistant for Xbet Fast Cash...'
}];
```

Update this string to change what the AI knows about your service.

---

## 🤖 AI Chatbot (Claude API)

The AI Assistant calls the **Anthropic Claude API** directly from the browser.

- **Model**: `claude-sonnet-4-20250514`
- **Max tokens**: `400` per response
- **Languages**: English and Sinhala (සිංහල)
- **API endpoint**: `https://api.anthropic.com/v1/messages`

> ⚠️ **Note**: The API key is injected server-side by the hosting environment. If self-hosting, you must add your Anthropic API key to the request headers or proxy the request through a backend.

---

## 📱 Forms & Validation

### Deposit Form
| Field | Validation |
|---|---|
| 1xbet Player ID | Required, numeric |
| Amount (LKR) | Min: 100, Max: 1,000,000 |
| Payment Method | Required (Bank Transfer / Card / Mobile Banking) |

### Withdrawal Form
| Field | Validation |
|---|---|
| Player ID | Required, 9–16 digits |
| Amount (LKR) | Min: 100, Max: 500,000 |
| Security Code | Required, min 3 characters |

Both forms redirect to **WhatsApp** with a pre-filled message on submit.

---

## 💅 Tech Stack

| Technology | Usage |
|---|---|
| **HTML5 / CSS3** | Structure and all styling (CSS variables, animations) |
| **Vanilla JavaScript** | All interactivity — no framework dependencies |
| **Tailwind CSS** (CDN) | Utility classes via CDN |
| **Google Fonts** | `Syne` (display) + `DM Sans` (body) |
| **Anthropic API** | AI chat assistant |

No npm, no build step, no dependencies to install.

---

## 🎨 Design System

```css
--bg:       #06001a   /* Deep purple-black background */
--accent:   #c8ff00   /* Neon lime accent */
--accent2:  #00e5ff   /* Cyan accent */
--gold:     #ffd700   /* Promo/star gold */
--green:    #00ff88   /* Success / online status */
--red:      #ff4d6d   /* Error / warning */
```

Glassmorphism cards (`backdrop-filter: blur`), animated gradient blobs, and smooth CSS transitions throughout.

---

## 📞 Support Contacts

| Channel | Details |
|---|---|
| WhatsApp | +94 71 1230 4567 |
| Email | lakmal25@gmail.com |
| Live Chat | Coming Soon |

---

## ⚠️ Disclaimer

This application is a **payment facilitation gateway** for 1xbet, intended for adult users in Sri Lanka. Please ensure compliance with local laws and regulations regarding online gambling and financial transactions in your jurisdiction.

---

## 📄 License

Private / proprietary. All rights reserved.

---

*Built with ⚡ for the Sri Lankan betting community.*
