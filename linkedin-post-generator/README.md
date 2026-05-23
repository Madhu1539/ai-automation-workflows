# 💼 LinkedIn Post Generator

> A webhook-triggered n8n workflow that takes any article or text, summarizes it with AI, transforms it into an engaging LinkedIn post, and publishes it automatically to your LinkedIn profile.

---

## 🚀 What It Does

Paste in an article URL or text → the workflow runs it through two AI steps — first summarizing the key insights, then formatting it into a recruiter-friendly, engagement-optimized LinkedIn post with hashtags, emojis, and a call-to-action. Published automatically.

---

## ⚙️ How It Works — Step by Step

1. **Webhook (POST)** — Receives article text via `{ "text": "article content here" }`
2. **Article Summarizer (Gemini)** — Extracts the top 3 insights in under 200 words, maintaining the original tone
3. **LinkedIn Post Writer (Gemini)** — Transforms the summary into a LinkedIn post:
   - Hook opening line
   - 2–3 specific insights or skills
   - Real-world application reflection
   - Relevant hashtags: `#AIBootcamp #LearningJourney #GenerativeAI`
   - Community engagement question
4. **LinkedIn Node** — Posts directly to your LinkedIn profile
5. **Respond to Webhook** — Confirms successful posting

---

## 🛠️ Tools & APIs Used

| Tool | Purpose |
|------|---------|
| **Google Gemini** | Article summarization and post writing (two separate LLM chains) |
| **LinkedIn API (OAuth2)** | Publishing posts to your LinkedIn profile |
| **n8n Webhook** | HTTP endpoint to trigger the workflow |

---

## 🔑 Required Credentials

| Credential | Where to Get It |
|------------|----------------|
| Google Gemini API Key | [Google AI Studio](https://aistudio.google.com/) → Create API Key |
| LinkedIn (OAuth2) | n8n → Credentials → LinkedIn OAuth2 API |

---

## 📋 Setup Instructions

1. Import `workflow.json` into your n8n instance
2. Connect two **Google Gemini** credentials (one per LLM chain)
3. Connect your **LinkedIn OAuth2** credential:
   - In the `Create a post` node, update `YOUR_LINKEDIN_PERSON_ID_HERE` with your LinkedIn Person URN (found in n8n's LinkedIn credential setup)
4. Activate the workflow — get your webhook URL from the Webhook node
5. Trigger it with a POST request:

```bash
curl -X POST https://your-n8n-instance/webhook/YOUR_PATH \
  -H "Content-Type: application/json" \
  -d '{"text": "Paste your article text here..."}'
```

---

## 📝 Sample Output Format

```
🚀 Just explored the future of AI agents today, and the insights are mind-blowing!

Here's what I learned:

✅ AI agents can now plan multi-step tasks autonomously...
✅ Tool-use allows LLMs to interact with real APIs...
✅ Memory systems enable truly contextual conversations...

This directly applies to building production-ready AI pipelines — 
something every developer should understand.

What's your experience with AI agents? Drop a comment! 👇

#AIBootcamp #LearningJourney #GenerativeAI #TechSkills #100DaysOfCode
```

---

## 📸 Screenshots

> *Add screenshots of the workflow canvas and a sample published LinkedIn post here.*

---

## 🎬 Demo

> *[Add Loom / YouTube demo link here]*
