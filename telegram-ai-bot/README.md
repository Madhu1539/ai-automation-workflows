# 🤖 Telegram AI Bot

> A feature-rich Telegram chatbot powered by Google Gemini that can answer questions, search the web in real time, perform calculations, look up Wikipedia, and create Google Calendar events — all from a single chat interface.

---

## 🚀 What It Does

This is a multi-tool AI assistant that lives in your Telegram. Ask it anything — it intelligently selects the right tool:
- **General questions** → Answers directly using Gemini
- **"What's the latest news about..."** → Uses SerpAPI for live web search
- **"What is 35% of 12000?"** → Uses Calculator tool
- **"Tell me about Elon Musk"** → Uses Wikipedia
- **"Schedule a meeting tomorrow at 3 PM"** → Creates Google Calendar event

All with persistent **per-user memory** — it remembers your conversation.

---

## ⚙️ How It Works — Step by Step

1. **Telegram Trigger** — Listens for any incoming message to your bot
2. **AI Agent (Gemini)** — Analyzes the user's intent and selects the right tool:
   - 💬 Direct Gemini response for general chat
   - 🔍 SerpAPI for real-time web search
   - 🧮 Calculator for math and unit conversions
   - 📖 Wikipedia for factual lookups
   - 📅 Google Calendar for scheduling events
3. **Simple Memory (Buffer)** — Per-user session key (`user.id`) maintains conversation history
4. **Send Text Message** — Returns the AI's response back to the user on Telegram

---

## 🛠️ Tools & APIs Used

| Tool | Purpose |
|------|---------|
| **Google Gemini** | Primary AI reasoning and response generation |
| **Telegram Bot API** | Chat interface — trigger and response |
| **SerpAPI** | Live web search for current events/prices/news |
| **Calculator** | Math, percentages, unit conversions |
| **Wikipedia** | Factual information about people and companies |
| **Google Calendar (OAuth2)** | Creating and managing calendar events |
| **Simple Memory** | Per-user conversation context |

---

## 🔑 Required Credentials

| Credential | Where to Get It |
|------------|----------------|
| Telegram Bot Token | [@BotFather](https://t.me/botfather) → `/newbot` command |
| Google Gemini API Key | [Google AI Studio](https://aistudio.google.com/) → Create API Key |
| SerpAPI Key | [serpapi.com](https://serpapi.com/) → Free 100 searches/month |
| Google Calendar (OAuth2) | n8n → Credentials → Google Calendar OAuth2 |

---

## 📋 Setup Instructions

1. **Create a Telegram bot**:
   - Message [@BotFather](https://t.me/botfather) on Telegram
   - Send `/newbot` → Follow prompts → Copy the bot token
2. Import `workflow.json` into your n8n instance
3. In the **Telegram Trigger** and **Send a text message** nodes → add your Telegram credential
4. Connect your **Google Gemini** credential
5. Connect your **SerpAPI** credential
6. Connect your **Google Calendar** credential and update `YOUR_CALENDAR_EMAIL_HERE`
7. Activate the workflow
8. Open Telegram, find your bot, and start chatting!

---

## 💬 Example Interactions

```
User:  "What's the weather like in Tokyo today?"
Bot:   [Uses SerpAPI] "According to current data, Tokyo is..."

User:  "Convert 100 USD to INR"
Bot:   [Uses Calculator + SerpAPI] "100 USD = approximately ₹8,350..."

User:  "Schedule a meeting called 'Project Review' on Friday at 4 PM"
Bot:   [Uses Google Calendar] "Done! I've created 'Project Review' on 
       Friday at 4:00 PM in your calendar."

User:  "Tell me about NVIDIA"
Bot:   [Uses Wikipedia] "NVIDIA Corporation is an American..."
```

---

## 📸 Screenshots

> *Add Telegram conversation screenshots showing different tool usages here.*

---

## 🎬 Demo

> *[Add Loom / YouTube demo link here]*
