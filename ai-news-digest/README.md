# 📰 AI News Digest

> A manually-triggered n8n workflow that reads live news from multiple RSS feeds, uses GPT-4.1-mini to generate a clean daily summary of world and tech news, and emails it directly to your inbox.

---

## 🚀 What It Does

With one click, this workflow fetches today's top headlines from BBC World News and The Verge (tech), runs them through an OpenAI-powered AI agent, and delivers a clean, bullet-pointed summary email — filtering out distressing content and prioritizing major developments.

---

## ⚙️ How It Works — Step by Step

1. **Manual Trigger** — Click "Execute Workflow" in n8n to start
2. **Get Tech News** — Reads RSS feed from The Verge (`theverge.com/rss`)
3. **Get World News** — Reads RSS feed from BBC World News
4. **AI Summary Agent (GPT-4.1-mini)** — Analyzes both feeds and creates:
   - A **World News** section (up to 5 bullet points)
   - A **Tech News** section (up to 5 bullet points)
   - Filters out distressing or negative content
5. **Output Node** — Extracts the summary text
6. **Gmail** — Sends the formatted summary to your configured email

---

## 🛠️ Tools & APIs Used

| Tool | Purpose |
|------|---------|
| **OpenAI GPT-4.1-mini** | Summarizing and filtering news content |
| **RSS Feed (BBC)** | World news source |
| **RSS Feed (The Verge)** | Technology news source |
| **Gmail** | Sending the daily digest email |
| **n8n Manual Trigger** | On-demand execution |

---

## 🔑 Required Credentials

| Credential | Where to Get It |
|------------|----------------|
| OpenAI API Key | [platform.openai.com](https://platform.openai.com/) → API Keys |
| Gmail (OAuth2) | n8n → Credentials → Gmail OAuth2 |

---

## 📋 Setup Instructions

1. Import `workflow.json` into your n8n instance
2. Connect the **OpenAI Model** node:
   - Add your OpenAI API key as a credential in n8n
   - Replace `YOUR_OPENAI_CREDENTIAL_NAME` with your credential name
3. Connect the **Gmail** node:
   - Set up Gmail OAuth2 credential in n8n
   - Update `YOUR_EMAIL_HERE` with your recipient email address
4. Click **Execute Workflow** to test
5. *(Optional)* Add a Schedule Trigger to run this every morning automatically

---

## ✨ Value for End Users

- **Saves 20–30 minutes** of daily news browsing
- **Curated & filtered** — no clickbait, no distressing content
- **Two-section format** — World News + Tech News for easy reading
- Delivered directly to your inbox, ready to read with morning coffee

---

## 📸 Screenshots

> *Add screenshots of the workflow canvas and a sample email output here.*

---

## 🎬 Demo

> *[Add Loom / YouTube demo link here]*
