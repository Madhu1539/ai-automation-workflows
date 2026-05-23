# 🌦️ Weather Daily Planner

> A scheduled n8n automation that fetches real-time weather data every morning and uses Google Gemini to generate a personalized daily plan — delivered straight to your inbox before you start your day.

---

## 🚀 What It Does

Every morning at 8 AM, this workflow checks the live weather for your city, feeds the data to an AI, and emails you a friendly, personalized daily plan — covering outfit suggestions, outdoor activity recommendations, and weather reminders. All under 100 words, so you can read it in seconds.

---

## ⚙️ How It Works — Step by Step

1. **Schedule Trigger** — Runs automatically every day at 8:00 AM
2. **OpenWeatherMap API** — Fetches current temperature, weather condition, and humidity for your city
3. **Gemini LLM Chain** — Generates a personalized 3-section plan:
   - 👕 **Outfit Suggestion** — Based on current temperature
   - 🌳 **Outdoor Activity** — Matching the weather and humidity
   - ☂️ **Weather Reminder** — Practical tip (umbrella, sunscreen, etc.)
4. **Gmail** — Sends the formatted plan to your email

---

## 🛠️ Tools & APIs Used

| Tool | Purpose |
|------|---------|
| **OpenWeatherMap API** | Real-time weather data (temp, humidity, conditions) |
| **Google Gemini** | Natural language plan generation |
| **Gmail** | Email delivery |
| **Schedule Trigger** | Daily automation at 8 AM |

---

## 🔑 Required Credentials

| Credential | Where to Get It |
|------------|----------------|
| OpenWeatherMap API Key | [openweathermap.org/api](https://openweathermap.org/api) → Free tier (60 calls/min) |
| Google Gemini API Key | [Google AI Studio](https://aistudio.google.com/) → Create API Key |
| Gmail (OAuth2) | n8n → Credentials → Gmail OAuth2 |

---

## 📋 Setup Instructions

1. Import `workflow.json` into your n8n instance
2. In the **HTTP Request** node:
   - Replace `YOUR_CITY_HERE` with your city name (e.g., `Bhopal`, `Mumbai`, `Delhi`)
   - Replace `YOUR_OPENWEATHERMAP_API_KEY_HERE` with your API key
3. Connect your **Google Gemini** credential
4. In the **Gmail** node:
   - Replace `YOUR_EMAIL_HERE` with your email address
   - Connect Gmail OAuth2
5. Activate the workflow — it will run every morning at 8 AM

---

## 📧 Sample Email Output

```
Good morning! Here's your weather-ready plan for today!

OUTFIT SUGGESTION
Light cotton shirt and breathable trousers work perfectly today.

OUTDOOR ACTIVITY
Great day for a morning walk or cycling in the park.

WEATHER REMINDER
Keep sunscreen handy — UV levels may be high by noon.

Your Daily Weather Assistant
```

---

## 📸 Screenshots

> *Add screenshots of the workflow canvas and a sample email here.*

---

## 🎬 Demo

> *[Add Loom / YouTube demo link here]*
