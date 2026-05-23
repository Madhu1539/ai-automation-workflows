# 🛍️ Shopping Agent (Telegram Bot — Maya)

> A Telegram-based AI shopping assistant named Maya that searches Amazon India for products and provides personalized styling advice — supporting both text and voice messages.

---

## 🚀 What It Does

Users chat with Maya on Telegram. She understands shopping queries and styling requests:
- **"Show me running shoes under ₹2000"** → Scrapes Amazon India → Shows top 5 products with price, rating, and links
- **"How to style a blue kurti?"** → Asks questions → Gives outfit combinations, color tips, and accessory recommendations
- **Voice messages** → Transcribed via Groq Whisper → Processed like text

---

## ⚙️ How It Works — Step by Step

1. **Telegram Trigger** — Receives any message (text or voice) from the user
2. **If Node** — Checks if the message is a voice note
   - **Voice path**: Downloads audio → Converts `.oga` to `.ogg` (Python code) → Sends to Groq Whisper for transcription
   - **Text path**: Passes directly
3. **Merge Node** — Combines both paths into unified input
4. **AI Agent (Gemini + Memory)** — Processes the message with conversation history:
   - **Product search** → Calls ScraperAPI tool with Amazon India search URL
   - **Styling advice** → Engages in multi-turn conversation for personalized tips
5. **ScraperAPI HTTP Tool** — Scrapes Amazon search results (`div.s-search-results`)
6. **Telegram Send** — Replies to the user with formatted results

---

## 🛠️ Tools & APIs Used

| Tool | Purpose |
|------|---------|
| **Google Gemini** | AI reasoning for shopping and styling decisions |
| **Telegram Bot API** | User interface — sending & receiving messages |
| **ScraperAPI** | Web scraping Amazon India product listings |
| **Groq Whisper (whisper-large-v3-turbo)** | Voice message transcription |
| **Simple Memory (Buffer)** | Per-user conversation context |
| **Python Code Node** | File format conversion (.oga → .ogg) |

---

## 🔑 Required Credentials

| Credential | Where to Get It |
|------------|----------------|
| Telegram Bot Token | [@BotFather](https://t.me/botfather) on Telegram → `/newbot` |
| Google Gemini API Key | [Google AI Studio](https://aistudio.google.com/) → Create API Key |
| ScraperAPI Key | [scraperapi.com](https://www.scraperapi.com/) → 1000 free calls/month |
| Groq API Key | [console.groq.com](https://console.groq.com/) → Free tier available |

---

## 📋 Setup Instructions

1. Import `workflow.json` into your n8n instance
2. Create a Telegram bot via [@BotFather](https://t.me/botfather) and get your token
3. In the **Telegram Trigger** and **Send a text message** nodes, connect your Telegram credential
4. In the **HTTP Request** (ScraperAPI) node, replace `YOUR_SCRAPERAPI_KEY_HERE`
5. In the **HTTP Request1** (Groq) node, replace `YOUR_GROQ_API_KEY_HERE`
6. Connect your **Google Gemini** credential
7. Activate the workflow and message your bot on Telegram!

---

## 💬 Example Conversations

```
User: "show me wireless earbuds under 1500"
Maya: 🎧 Top Wireless Earbuds Under ₹1500
      1. boAt Airdopes 141
         Price: ₹899 | Rating: 4.1 | [View on Amazon]
      ...

User: "outfit ideas for a college farewell party"
Maya: "I'd love to help! Quick questions:
       - Western or ethnic look?
       - Any color preferences?"
```

---

## 📸 Screenshots

> *Add Telegram conversation screenshots here.*

---

## 🎬 Demo

> *[Add Loom / YouTube demo link here]*
