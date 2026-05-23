# 🧠 Learning Path Generator (Webhook API)

> A webhook-powered variant of the Learning Path Generator that exposes an HTTP API endpoint — perfect for integrating with external apps, front-ends, or Postman testing.

---

## 🚀 What It Does

Same as the chat-based Learning Path Generator, but triggered via a **POST webhook** instead of the n8n chat UI. This makes it API-first and integration-ready — you can call it from any front-end, mobile app, Telegram bot, or other automation.

Send: `{ "text": "Teach me JavaScript in 5 days starting Monday" }`  
Get back: Google Doc URL + confirmation of calendar events created.

---

## ⚙️ How It Works — Step by Step

1. **Webhook (POST)** — Accepts `{ "text": "..." }` from any external client
2. **AI Agent (Gemini)** — Parses the request: topic, number of days, start date
3. **SerpAPI** — Searches for real YouTube URLs, articles, documentation (2–3 times)
4. **Create Google Doc** — Titled `"[X]-Day [Topic] Learning Path"`
5. **Update Google Doc** — Full day-by-day curriculum written in one call
6. **Calendar Events** — One 2-hour event per day at 11 AM IST
7. **Respond to Webhook** — Returns the full AI response including Google Doc URL

---

## 🆚 Difference vs Other Versions

| Feature | Chat Version | With Memory | Webhook (This) |
|---------|-------------|-------------|----------------|
| Trigger | n8n Chat UI | n8n Chat UI | HTTP POST API |
| Memory | ❌ | ✅ | ❌ |
| API-first | ❌ | ❌ | ✅ |
| Returns response | Chat | Chat | JSON/Text |
| Best for | n8n testing | Iterative use | App integration |

---

## 🛠️ Tools & APIs Used

| Tool | Purpose |
|------|---------|
| **Google Gemini** | Curriculum planning and content generation |
| **SerpAPI** | Real tutorial URL research |
| **Google Docs** | Curriculum document creation |
| **Google Calendar** | Daily learning event scheduling |
| **n8n Webhook** | HTTP API endpoint trigger |

---

## 🔑 Required Credentials

| Credential | Where to Get It |
|------------|----------------|
| Google Gemini API Key | [Google AI Studio](https://aistudio.google.com/) |
| SerpAPI Key | [serpapi.com](https://serpapi.com/) → Free 100/month |
| Google Docs (OAuth2) | n8n → Google Docs OAuth2 |
| Google Calendar (OAuth2) | n8n → Google Calendar OAuth2 |

---

## 📋 Setup Instructions

1. Import `workflow.json` into your n8n instance
2. Connect all credentials (Gemini, SerpAPI, Google Docs, Google Calendar)
3. Update `YOUR_CALENDAR_EMAIL_HERE` with your calendar email
4. Activate the workflow — get the webhook URL from the Webhook node
5. Send a POST request:

```bash
curl -X POST https://your-n8n-instance/webhook/85839d12-42f9-4aca-92ba-339b2456c93d \
  -H "Content-Type: application/json" \
  -d '{"text": "Teach me Docker in 3 days starting tomorrow"}'
```

---

## 📸 Screenshots

> *Add screenshots of the workflow canvas and a Postman/curl test here.*

---

## 🎬 Demo

> *[Add Loom / YouTube demo link here]*
