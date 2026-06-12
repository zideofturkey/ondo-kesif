<div align="center">

# OndoKeşif
### AI-Powered Ondo Finance Intelligence Dashboard

[![Live Demo](https://img.shields.io/badge/🌐_Live_Demo-zideofturkey.github.io-black?style=for-the-badge)](https://zideofturkey.github.io/ondo-kesif)
[![Claude AI](https://img.shields.io/badge/Powered_by-Claude_AI-CC785C?style=for-the-badge)](https://anthropic.com)
[![Cloudflare Workers](https://img.shields.io/badge/Cloudflare-Workers-F38020?style=for-the-badge&logo=cloudflare&logoColor=white)](https://workers.cloudflare.com)
[![GitHub Pages](https://img.shields.io/badge/Hosted_on-GitHub_Pages-222?style=for-the-badge&logo=github)](https://pages.github.com)

*Ondo Finance'i gerçek zamanlı veriler ve yapay zeka destekli haberlerle takip edin.*

</div>

---

## What is this?

OndoKeşif is a single-page intelligence dashboard built to monitor **Ondo Finance (ONDO)** — a real-world asset (RWA) tokenization protocol with $3.7B+ TVL and 53% market share in tokenized equities.

The site is designed for both beginners and expert investors, with a toggle that adapts the content depth accordingly.

---

## Features

### 📡 Live Market Data
- Real-time ONDO price with 24h change, fetched from **CoinGecko API**
- Clickable performance popup: daily, weekly, monthly, 2-month, 6-month, 1-year returns
- BTC, ETH, SOL comparison in the same popup with their own performance breakdowns
- Market opportunity section powered by **DeFiLlama API** (live TVL, RWA market share)

### 🤖 AI-Powered News Analysis
- One-click analysis: Claude searches the web and explains **why ONDO is moving**
- Returns a structured report: market catalyst type, relevant news, market comparison
- Compares ONDO movement against BTC/ETH/SOL — identifies correlation vs. divergence
- Secured via **Cloudflare Worker** proxy — API key never exposed in frontend code
- Daily usage limit with password bypass for admin

### 🎨 Design & UX
- Minimal dark theme with a premium **expert mode atmosphere** (navy gradients, edge glow, corner hotspots)
- Smooth section reveal animations, scroll progress bar
- Mobile-first responsive layout with a slide-in navigation panel
- Beginner / Expert mode toggle that adapts content depth across all sections

### 🏗️ Content
- Comprehensive Ondo Finance explainer (what it is, why it matters, products, partners)
- Interactive ecosystem section — 10 institutional partners with expandable detail panels
- Timeline of key milestones (NYSE 7/24, Solana integration, Binance partnership, etc.)
- Regulation tracker (SEC, GENIUS Act, KYC/AML status)
- Honest risk analysis section

---

## Tech Stack

| Layer | Technology |
|---|---|
| Frontend | Vanilla HTML + CSS + JavaScript (no frameworks) |
| Live Price & Market Data | CoinGecko API |
| TVL & RWA Market Data | DeFiLlama API |
| AI News Analysis | Anthropic Claude (Haiku) + Web Search Tool |
| API Security | Cloudflare Workers (serverless proxy) |
| Hosting | GitHub Pages |

> Built entirely as a single HTML file. No build tools, no dependencies, no backend — except the Cloudflare Worker that keeps the API key off the client.

---

## How the AI Analysis Works

```
User clicks "Analiz Et"
        ↓
Confirmation popup (daily limit check)
        ↓
Frontend sends market context to Cloudflare Worker
(current ONDO %, BTC/ETH/SOL performance, 24h volume)
        ↓
Worker forwards to Anthropic API (key stored securely in env)
        ↓
Claude runs two web searches:
  1. "Ondo Finance news this week"
  2. "ONDO token price movement reason today"
        ↓
Returns structured JSON:
  - summary (Turkish)
  - catalyst type (news_driven / market_driven / technical_recovery / unknown)
  - up to 6 news cards with source, date, impact tag
  - market comparison vs BTC/ETH/SOL with correlation analysis
        ↓
Rendered on page with catalyst badge + market strip
```

---

## Setup

This project is intentionally zero-dependency. To run locally, just open `index.html` in a browser.

To enable the AI analysis feature, you'll need:

1. An [Anthropic API key](https://console.anthropic.com/settings/keys) with credits
2. A free [Cloudflare Workers](https://workers.cloudflare.com) account

Deploy `ondo-worker.js` as a Cloudflare Worker, set `ANTHROPIC_API_KEY` as an encrypted environment variable, then update the `WORKER_URL` constant in `index.html`.

---

## Project Background

This project was built iteratively — starting from a Gemini-generated prototype, then developed feature by feature into a full intelligence dashboard. Core additions include the real-time data layer, the AI analysis engine, the performance popup, the expert mode atmospheric design, and the complete mobile experience.

---

<div align="center">

Built by **Ediz Kaçmaz** · [ediz@edizkacmaz.com](mailto:ediz@edizkacmaz.com)

*Eğitim ve bilgi amaçlıdır. Yatırım tavsiyesi değildir.*

</div>
