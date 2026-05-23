# 📡 AI News Summarizer

> A fully automated n8n workflow that runs every day at 10 AM, pulls the latest AI industry news from multiple RSS feeds, and delivers a smart, structured summary email — keeping you effortlessly up to date with the AI world.

---

## 🚀 What It Does

Every morning, this workflow silently reads the latest articles from AI Business and WIRED's AI section, merges and aggregates the data, then uses Google Gemini to write a concise, well-structured summary for each article — covering what happened, who's involved, and why it matters. Delivered to your inbox automatically.

---

## ⚙️ How It Works — Step by Step

1. **Schedule Trigger** — Fires automatically every day at 10:00 AM
2. **RSS Read (AI Business)** — Fetches latest articles from `aibusiness.com/rss.xml`
3. **RSS Read (WIRED AI)** — Fetches latest articles from WIRED's AI feed
4. **Merge** — Combines both feeds into a single data stream
5. **Aggregate** — Bundles all articles into one batch for efficient processing
6. **Gemini LLM Chain** — For all articles, generates structured summaries:
   - **Quick Summary** (2–3 lines)
   - **Key Details** (bullet points)
   - **Why It Matters** (impact & insights)
7. **Gmail** — Sends the complete summary to your inbox

---

## 🛠️ Tools & APIs Used

| Tool | Purpose |
|------|---------|
| **Google Gemini** | AI-powered article summarization |
| **RSS Feeds (AI Business + WIRED)** | Latest AI news sources — no API key needed |
| **Gmail** | Email delivery |
| **Schedule Trigger** | Daily automation at 10 AM |
| **Merge + Aggregate** | Data pipeline combining multiple feeds |

---

## 🔑 Required Credentials

| Credential | Where to Get It |
|------------|----------------|
| Google Gemini API Key | [Google AI Studio](https://aistudio.google.com/) → Create API Key |
| Gmail (OAuth2) | n8n → Credentials → Gmail OAuth2 |

> **Note:** RSS feeds are public — no API keys needed for news sources!

---

## 📋 Setup Instructions

1. Import `workflow.json` into your n8n instance
2. Connect your **Google Gemini** credential
3. In the **Gmail** node:
   - Replace `YOUR_EMAIL_HERE` with your recipient email
   - Connect Gmail OAuth2 credential
4. *(Optional)* Add more RSS feed sources by duplicating the RSS Read nodes and connecting to Merge
5. Activate the workflow — it runs daily at 10 AM automatically

---

## 📧 Sample Email Output

```
Subject: Today's AI News For You....

Quick Summary:
Google announced major updates to Gemini 2.5, including...

Key Details:
• New context window of 1M tokens now available...
• Pricing reduced by 50% for developer tier...
• Integration with Google Workspace now live...

Why It Matters:
This signals a major shift in how enterprises will adopt AI...
```

---

## 📸 Screenshots

> *Add screenshots of the workflow and a sample email here.*

---

## 🎬 Demo

> *[Add Loom / YouTube demo link here]*
