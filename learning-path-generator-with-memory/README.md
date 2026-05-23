# 🧠 Learning Path Generator with Memory

> An enhanced version of the Learning Path Generator that remembers your conversation context — allowing multi-turn conversations, follow-up questions, and iterative curriculum refinement.

---

## 🚀 What It Does

Unlike the basic version, this workflow maintains **conversation memory** across multiple messages. You can:
- Ask follow-up questions: *"Make Day 3 more beginner-friendly"*
- Change dates: *"Actually start on Monday instead"*
- Add topics: *"Add a bonus day on Testing"*
- The AI remembers everything from your current session

---

## ⚙️ How It Works — Step by Step

1. **Chat Trigger** — User opens the n8n chat interface and sends a message
2. **Simple Memory (Buffer Window)** — Stores the last N messages for context
3. **AI Agent (Gemini)** — Processes the message with full conversation history
4. **SerpAPI Search** — Finds real URLs: YouTube courses, documentation, articles
5. **Create Google Doc** — Generates a titled, formatted learning path document
6. **Update Google Doc** — Writes all day-by-day content with actual hyperlinks
7. **Google Calendar** — Schedules one study session per day at 11 AM IST
8. **Response** — Returns doc link + calendar summary

---

## 🧩 Key Differentiator vs Basic Version

| Feature | Basic Version | With Memory |
|---------|--------------|-------------|
| Multi-turn chat | ❌ | ✅ |
| Follow-up refinements | ❌ | ✅ |
| Session context | ❌ | ✅ |
| Trigger type | Chat | Chat |
| Real URLs in doc | ✅ | ✅ |

---

## 🛠️ Tools & APIs Used

| Tool | Purpose |
|------|---------|
| **Google Gemini** | Curriculum generation with contextual understanding |
| **SerpAPI** | Finding real tutorial URLs and video links |
| **Simple Memory (Buffer)** | Maintains multi-turn conversation context |
| **Google Docs** | Creating and writing the curriculum document |
| **Google Calendar** | Day-wise event scheduling |
| **n8n Chat Trigger** | Conversational user interface |

---

## 🔑 Required Credentials

| Credential | Where to Get It |
|------------|----------------|
| Google Gemini API | [Google AI Studio](https://aistudio.google.com/) → Create API Key |
| SerpAPI | [serpapi.com](https://serpapi.com/) → Free 100 searches/month |
| Google Docs (OAuth2) | n8n → Credentials → Google Docs OAuth2 |
| Google Calendar (OAuth2) | n8n → Credentials → Google Calendar OAuth2 |

---

## 📋 Setup Instructions

1. Import `workflow.json` into your n8n instance
2. Connect all credentials (Gemini, SerpAPI, Google Docs, Google Calendar)
3. Update `YOUR_CALENDAR_EMAIL_HERE` with your Google Calendar email
4. Activate the workflow
5. Start a conversation and iterate freely!

---

## 💬 Example Conversation

```
User: "Teach me Kubernetes in 5 days"
AI:   [Creates doc + 5 calendar events]

User: "Make Day 1 easier, I'm a beginner"
AI:   [Updates Day 1 content in the doc]

User: "Add a day on Helm charts"
AI:   [Adds Day 6 to the doc and calendar]
```

---

## 📸 Screenshots

> *Add screenshots of multi-turn conversation and the generated Google Doc here.*

---

## 🎬 Demo

> *[Add Loom / YouTube demo link here]*
