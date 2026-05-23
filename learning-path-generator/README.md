# 🧠 Learning Path Generator

> An AI-powered n8n workflow that transforms any learning goal into a structured, day-by-day curriculum — complete with a Google Doc and Google Calendar events, all generated automatically.

---

## 🚀 What It Does

You type: *"Teach me Python in 7 days starting tomorrow"*  
The AI does the rest — plans topics, researches real resources, writes a curriculum doc, and schedules 7 calendar sessions at 11 AM.

---

## ⚙️ How It Works — Step by Step

1. **Chat Trigger** — User sends a learning goal via the n8n chat interface
2. **AI Agent (Gemini)** — Parses the goal: topic, number of days, start date
3. **SerpAPI Search** — Searches for YouTube tutorials, articles, and documentation (2–3 searches)
4. **Create Google Doc** — Creates a titled document: *"7-Day Python Learning Path"*
5. **Update Google Doc** — Fills in day-by-day content with descriptions, key points, and real URLs
6. **Google Calendar Events** — Creates one 2-hour event per day (11 AM – 1 PM IST) with full content
7. **Final Response** — Returns Google Doc link + calendar summary to the user

---

## 🛠️ Tools & APIs Used

| Tool | Purpose |
|------|---------|
| **Google Gemini (Flash Lite)** | Curriculum planning and content generation |
| **SerpAPI** | Finding real tutorial URLs, YouTube links, documentation |
| **Google Docs** | Creating and populating the curriculum document |
| **Google Calendar** | Scheduling daily learning sessions |
| **n8n Chat Trigger** | User input interface |

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
2. Connect credentials:
   - `YOUR_GEMINI_CREDENTIAL_NAME` → Add your Gemini API key
   - `YOUR_SERPAPI_CREDENTIAL_NAME` → Add your SerpAPI key
   - `YOUR_GOOGLE_DOCS_CREDENTIAL_NAME` → Connect via Google OAuth2
   - `YOUR_GOOGLE_CALENDAR_CREDENTIAL_NAME` → Connect via Google OAuth2
3. Update `YOUR_CALENDAR_EMAIL_HERE` with your Google Calendar email
4. Activate the workflow and open the Chat interface
5. Type: *"Create a 5-day Machine Learning learning path starting Monday"*

---

## 💬 Example Prompts

- `"Teach me React in 5 days starting tomorrow"`
- `"Create a 10-day DSA study plan starting next Monday"`
- `"I want to learn Docker in 3 days from today"`

---

## 📸 Screenshots

> *Add screenshots of the workflow canvas, generated Google Doc, and calendar events here.*

---

## 🎬 Demo

> *[Add Loom / YouTube demo link here]*
