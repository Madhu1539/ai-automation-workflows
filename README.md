<div align="center">

# 🤖 AI Automation Workflows

### A portfolio of production-ready n8n automation workflows built with AI agents, LLMs, and real-world APIs

[![n8n](https://img.shields.io/badge/Built%20with-n8n-orange?style=for-the-badge&logo=n8n)](https://n8n.io)
[![Gemini](https://img.shields.io/badge/Google-Gemini-blue?style=for-the-badge&logo=google)](https://aistudio.google.com)
[![OpenAI](https://img.shields.io/badge/OpenAI-GPT--4-412991?style=for-the-badge&logo=openai)](https://platform.openai.com)
[![Telegram](https://img.shields.io/badge/Telegram-Bots-26A5E4?style=for-the-badge&logo=telegram)](https://core.telegram.org/bots)
[![License: MIT](https://img.shields.io/badge/License-MIT-green?style=for-the-badge)](LICENSE)

---

*Built by a CS student exploring the intersection of AI, automation, and real-world problem solving.*

</div>

---

## 👋 About This Repository

This repository contains **8 fully functional AI automation workflows** built using [n8n](https://n8n.io) — a powerful open-source workflow automation platform. Each workflow solves a real-world problem using AI (Google Gemini, GPT-4, Groq Whisper), web APIs, and smart automation logic.

These projects demonstrate skills in:
- 🧠 **AI Agent Design** — Multi-step reasoning, tool use, memory
- 🔗 **API Integration** — 10+ real-world APIs connected
- ⚙️ **Workflow Automation** — Triggers, conditionals, data pipelines
- 🛡️ **Production Thinking** — Error handling, retries, smart filtering

---

## 📂 Project Overview

| # | Project | What It Does | Trigger | Key APIs |
|---|---------|-------------|---------|----------|
| 1 | [🧠 Learning Path Generator](#1-learning-path-generator) | AI creates a full study curriculum with Google Docs + Calendar | Chat | Gemini, SerpAPI, Google Docs, Calendar |
| 2 | [🧠 Learning Path Generator with Memory](#2-learning-path-generator-with-memory) | Same as above but with multi-turn conversation memory | Chat | Gemini, SerpAPI, Google Docs, Calendar |
| 3 | [🔗 Learning Path Generator (Webhook)](#3-learning-path-generator-webhook) | API-first variant — integrate with any app via HTTP POST | Webhook | Gemini, SerpAPI, Google Docs, Calendar |
| 4 | [🎨 AI Image Generator](#4-ai-image-generator) | Text-to-image generation using Freepik Mystic AI | Webhook | Freepik API |
| 5 | [📰 AI News Digest](#5-ai-news-digest) | Reads BBC + The Verge RSS, summarizes with GPT-4, emails you | Manual | OpenAI, Gmail, RSS |
| 6 | [🌦️ Weather Daily Planner](#6-weather-daily-planner) | Morning email with AI outfit + activity plan based on real weather | Schedule | OpenWeatherMap, Gemini, Gmail |
| 7 | [🛍️ Shopping Agent (Telegram)](#7-shopping-agent-telegram) | Telegram bot that searches Amazon India + gives styling advice | Telegram | Gemini, ScraperAPI, Groq, Telegram |
| 8 | [💼 LinkedIn Post Generator](#8-linkedin-post-generator) | Turns articles into LinkedIn posts and auto-publishes | Webhook | Gemini, LinkedIn API |
| 9 | [📡 AI News Summarizer](#9-ai-news-summarizer) | Daily AI industry digest from WIRED + AI Business | Schedule | Gemini, NewsAPI, Gmail, RSS |
| 10 | [🌾 Smart Agriculture Alert](#10-smart-agriculture-alert-system) | Monitors weather + soil + news → alerts farmers to crop risks | Schedule | Gemini, OpenWeatherMap, Weatherbit, NewsAPI |

---

## 🔍 Detailed Project Descriptions

---

### 1. 🧠 Learning Path Generator

**Folder:** [`learning-path-generator/`](./learning-path-generator/)

**What it does:** You describe a learning goal (e.g., *"Teach me Python in 7 days"*) and the AI plans a complete curriculum, researches real YouTube/article URLs using SerpAPI, writes a Google Doc with day-by-day content, and creates Google Calendar events for each study session.

**How it works:**
- Chat trigger → Gemini AI Agent → SerpAPI (2–3 searches for real URLs)
- Creates Google Doc with structured daily content + actual links
- Creates one 2-hour Calendar event per day (11 AM – 1 PM IST)
- Returns Doc URL + Calendar summary

**Tech Stack:** `Google Gemini` `SerpAPI` `Google Docs` `Google Calendar` `n8n Agent`

---

### 2. 🧠 Learning Path Generator with Memory

**Folder:** [`learning-path-generator-with-memory/`](./learning-path-generator-with-memory/)

**What it does:** The enhanced version of #1 that remembers your conversation. You can follow up: *"Make Day 3 easier"* or *"Add a bonus day on testing"* and the AI updates accordingly.

**Key difference from #1:** Adds a **Simple Memory (Buffer Window)** node that stores conversation history per session, enabling true multi-turn curriculum refinement.

**Tech Stack:** `Google Gemini` `SerpAPI` `Google Docs` `Google Calendar` `n8n Memory Buffer`

---

### 3. 🔗 Learning Path Generator (Webhook)

**Folder:** [`learning-path-generator-webhook/`](./learning-path-generator-webhook/)

**What it does:** API-first version of the Learning Path Generator. Exposes an HTTP POST endpoint that any external app can call — front-ends, mobile apps, Postman, or other automations.

**Key difference from #1:** Uses a **Webhook trigger** instead of n8n Chat, making it embeddable in other systems.

**Tech Stack:** `Google Gemini` `SerpAPI` `Google Docs` `Google Calendar` `n8n Webhook`

---

### 4. 🎨 AI Image Generator

**Folder:** [`ai-image-generator/`](./ai-image-generator/)

**What it does:** Accepts a text prompt via webhook → generates an AI image using Freepik's Mystic API → returns the final image as binary data. Handles async generation automatically with a 30-second wait + status check.

**Tech Stack:** `Freepik Mystic API` `n8n Webhook` `HTTP Request`

---

### 5. 📰 AI News Digest

**Folder:** [`ai-news-digest/`](./ai-news-digest/)

**What it does:** A one-click workflow that reads live RSS feeds from BBC World News and The Verge, uses GPT-4.1-mini to write a clean two-section summary (World News + Tech News), and emails it to you. Filters out distressing content automatically.

**Tech Stack:** `OpenAI GPT-4.1-mini` `BBC RSS Feed` `The Verge RSS Feed` `Gmail`

---

### 6. 🌦️ Weather Daily Planner

**Folder:** [`weather-daily-planner/`](./weather-daily-planner/)

**What it does:** Runs every morning at 8 AM. Fetches real-time weather for your city from OpenWeatherMap, feeds it to Gemini AI, and sends a personalized email with outfit suggestions, outdoor activity recommendations, and a weather reminder — all under 100 words.

**Tech Stack:** `OpenWeatherMap API` `Google Gemini` `Gmail` `n8n Schedule`

---

### 7. 🛍️ Shopping Agent (Telegram)

**Folder:** [`shopping-agent/`](./shopping-agent/)

**What it does:** A Telegram chatbot named **Maya** that acts as your personal shopping assistant and stylist. Supports text AND voice messages. For products: scrapes Amazon India in real time. For styling: multi-turn conversations with personalized outfit combinations.

**Standout Features:** Voice-to-text via Groq Whisper, per-user conversation memory, live Amazon scraping.

**Tech Stack:** `Google Gemini` `Telegram Bot API` `ScraperAPI` `Groq Whisper` `n8n Memory Buffer`

---

### 8. 💼 LinkedIn Post Generator

**Folder:** [`linkedin-post-generator/`](./linkedin-post-generator/)

**What it does:** A 2-stage AI pipeline: first summarizes an article (key insights, tone, audience implications), then transforms the summary into an engagement-optimized LinkedIn post with hashtags and a community question — and publishes it directly.

**Tech Stack:** `Google Gemini (x2)` `LinkedIn API` `n8n Webhook`

---

### 9. 📡 AI News Summarizer

**Folder:** [`ai-news-summarizer/`](./ai-news-summarizer/)

**What it does:** Runs daily at 10 AM. Reads from AI Business and WIRED's AI RSS feeds, merges the articles, and uses Gemini to write structured summaries: Quick Summary → Key Details → Why It Matters. Delivered by email. No API key needed for RSS feeds.

**Tech Stack:** `Google Gemini` `RSS Feeds (AI Business + WIRED)` `Gmail` `n8n Schedule`

---

### 10. 🌾 Smart Agriculture Alert System

**Folder:** [`smart-agriculture-alert/`](./smart-agriculture-alert/)

**What it does:** An AI-powered agricultural monitoring system that runs daily at 1 PM. Collects data from 3 sources simultaneously (weather, soil agri-forecast, India farming news), correlates all signals, and sends an email alert **only when Medium or High crop risk is detected** — no noise on safe days.

**Alert types:** Fungal disease risk, drought stress, pest outbreak, heat stress, flooding risk.

**Tech Stack:** `Google Gemini` `OpenWeatherMap` `Weatherbit Agri API` `NewsAPI` `Gmail`

---

## 🚀 How to Import and Run Locally

### Step 1 — Install n8n

```bash
npx n8n
```

Or install globally:

```bash
npm install -g n8n
n8n start
```

### Step 2 — Open n8n

Navigate to: [http://localhost:5678](http://localhost:5678)

### Step 3 — Import a Workflow

1. Click **"+"** → **"Import from file"**
2. Select any `workflow.json` from this repository
3. The workflow will open in the editor

### Step 4 — Add Your API Credentials

1. Click on any node that shows a credential warning
2. Click **"Create new credential"**
3. Enter your API key / OAuth token
4. Save and connect

### Step 5 — Activate & Run

1. Toggle the **"Active"** switch in the top-right
2. Use the trigger (Chat, Webhook, Schedule, or Manual) to start

---

## 🔑 Required API Keys — Where to Get Them (Free)

| Service | Free Tier | Sign Up Link |
|---------|-----------|-------------|
| **Google Gemini** | 15 RPM, 1M tokens/day | [aistudio.google.com](https://aistudio.google.com/) |
| **OpenAI** | $5 free credits | [platform.openai.com](https://platform.openai.com/) |
| **SerpAPI** | 100 searches/month | [serpapi.com](https://serpapi.com/) |
| **OpenWeatherMap** | 60 calls/min, 1M/month | [openweathermap.org/api](https://openweathermap.org/api) |
| **Freepik** | 100 AI images/month | [freepik.com/api](https://www.freepik.com/api) |
| **ScraperAPI** | 1,000 calls/month | [scraperapi.com](https://www.scraperapi.com/) |
| **Groq** | Very generous free tier | [console.groq.com](https://console.groq.com/) |
| **NewsAPI** | 100 requests/day | [newsapi.org](https://newsapi.org/) |
| **Weatherbit** | 500 calls/day | [weatherbit.io](https://www.weatherbit.io/) |
| **Telegram Bot** | Completely free | [@BotFather](https://t.me/botfather) on Telegram |
| **Google OAuth** | Free (Docs, Calendar, Gmail) | [console.cloud.google.com](https://console.cloud.google.com/) |
| **LinkedIn API** | Free for personal use | [linkedin.com/developers](https://www.linkedin.com/developers/) |

---

## 🛠️ Tech Stack

```
Automation Platform    →  n8n (self-hosted)
AI / LLMs             →  Google Gemini, OpenAI GPT-4.1-mini, Groq Whisper
Messaging             →  Telegram Bot API
Web Scraping          →  ScraperAPI
Search                →  SerpAPI
Weather               →  OpenWeatherMap, Weatherbit
News                  →  NewsAPI, RSS Feeds (BBC, WIRED, The Verge, AI Business)
Google Workspace      →  Gmail, Google Docs, Google Calendar
Social Media          →  LinkedIn API
Image Generation      →  Freepik Mystic API
Memory / State        →  n8n Buffer Window Memory
Languages             →  Python (code nodes), n8n expressions
```

---

## 📁 Repository Structure

```
ai-automation-workflows/
├── README.md                              ← You are here
├── .gitignore
│
├── learning-path-generator/
│   ├── workflow.json
│   └── README.md
│
├── learning-path-generator-with-memory/
│   ├── workflow.json
│   └── README.md
│
├── learning-path-generator-webhook/
│   ├── workflow.json
│   └── README.md
│
├── ai-image-generator/
│   ├── workflow.json
│   └── README.md
│
├── ai-news-digest/
│   ├── workflow.json
│   └── README.md
│
├── weather-daily-planner/
│   ├── workflow.json
│   └── README.md
│
├── shopping-agent/
│   ├── workflow.json
│   └── README.md
│
├── linkedin-post-generator/
│   ├── workflow.json
│   └── README.md
│
├── ai-news-summarizer/
│   ├── workflow.json
│   └── README.md
│
└── smart-agriculture-alert/
    ├── workflow.json
    └── README.md
```

---

## ⚠️ Security Notes

- ✅ **All API keys have been removed** from workflow files and replaced with `YOUR_*_HERE` placeholders
- ✅ **Never commit real credentials** — use n8n's built-in credential store instead
- ✅ The `.gitignore` excludes `.env` files, credential files, and common secret patterns
- ✅ Use environment variables in production n8n deployments

---

## 🤝 Connect With Me

> *I'm a CS student actively building AI and automation projects. Open to internships, collaborations, and feedback!*

[![LinkedIn](https://img.shields.io/badge/LinkedIn-Connect-0A66C2?style=for-the-badge&logo=linkedin)](https://linkedin.com/in/YOUR_LINKEDIN_HERE)
[![GitHub](https://img.shields.io/badge/GitHub-Follow-181717?style=for-the-badge&logo=github)](https://github.com/YOUR_GITHUB_HERE)

---

<div align="center">

*If this helped you, please ⭐ star the repo — it means a lot!*

**Made with ❤️ and n8n**

</div>
