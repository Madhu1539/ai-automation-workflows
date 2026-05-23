# 🌾 Smart Agriculture Alert System

> A scheduled n8n AI automation that monitors real-time weather, agricultural soil conditions, and the latest farming news — and sends intelligent crop risk alerts to farmers via email when threats are detected.

---

## 🚀 What It Does

Every day at 1 PM, this system collects data from 3 sources (weather, soil/agri-forecast, news), merges it all, and feeds it to an AI agricultural analyst. The AI identifies risks — excess rainfall, high humidity, pest outbreaks, drought stress — and sends a structured alert email **only when Medium or High risk is detected**. Safe conditions = no email, no noise.

---

## ⚙️ How It Works — Step by Step

1. **Schedule Trigger** — Runs daily at 1:00 PM
2. **Parallel Data Collection** (3 simultaneous HTTP calls):
   - 🌤️ **OpenWeatherMap** — Temperature, humidity, rainfall, wind speed
   - 🌍 **Weatherbit Agri API** — Soil temperature, soil moisture, evapotranspiration
   - 📰 **NewsAPI** — Latest agriculture news, crop disease alerts, pest warnings from India
3. **Merge (3-input)** — Combines all data streams
4. **Aggregate** — Bundles into a single payload for AI analysis
5. **AI Agent (Gemini)** — Performs 5-step risk analysis:
   - Weather risk analysis
   - Soil condition evaluation
   - Crop disease/pest detection from news
   - Signal correlation
   - Alert level classification (Safe / Low / Medium / High)
6. **If Node** — Checks alert level — only sends email if risk is `Medium` or `High`
7. **Gmail Alert** — Sends a structured alert with problem, cause, affected crops, and recommended actions

---

## 🛠️ Tools & APIs Used

| Tool | Purpose |
|------|---------|
| **Google Gemini** | Multi-source agricultural risk analysis |
| **OpenWeatherMap API** | Real-time weather: temp, humidity, rainfall |
| **Weatherbit Agri Forecast API** | Soil moisture, evapotranspiration, soil temp |
| **NewsAPI** | Agriculture news, crop disease alerts, pest warnings |
| **Gmail** | Risk alert email delivery |
| **If Node** | Smart filtering — only alerts on real risk |

---

## 🔑 Required Credentials

| Credential | Where to Get It |
|------------|----------------|
| Google Gemini API Key | [Google AI Studio](https://aistudio.google.com/) → Create API Key |
| OpenWeatherMap API Key | [openweathermap.org/api](https://openweathermap.org/api) → Free tier |
| Weatherbit API Key | [weatherbit.io](https://www.weatherbit.io/) → Free 500 calls/day |
| NewsAPI Key | [newsapi.org](https://newsapi.org/) → Free 100 requests/day |
| Gmail (OAuth2) | n8n → Credentials → Gmail OAuth2 |

---

## 📋 Setup Instructions

1. Import `workflow.json` into your n8n instance
2. **OpenWeatherMap node** — Replace:
   - `YOUR_CITY_HERE` → e.g., `Satna`, `Bhopal`, `Nagpur`
   - `YOUR_OPENWEATHERMAP_API_KEY_HERE`
3. **Weatherbit node** — Replace:
   - `YOUR_LATITUDE_HERE` and `YOUR_LONGITUDE_HERE` (use Google Maps to find coords)
   - `YOUR_WEATHERBIT_API_KEY_HERE`
4. **NewsAPI nodes** — Replace `YOUR_NEWSAPI_KEY_HERE` in both HTTP nodes
5. Connect **Google Gemini** credential
6. **Gmail node** — Replace `YOUR_EMAIL_HERE` and connect OAuth2
7. Activate the workflow

---

## 📧 Sample Alert Email

```
Subject: Smart Agriculture Alert System

ALERT LEVEL: High

Problem Detected:
High humidity and rainfall may cause fungal disease in wheat crops.

Cause:
Continuous rainfall and humidity above 85% create ideal conditions for 
fungal growth.

Affected Crops:
Wheat, barley

Recommended Action:
- Inspect crops for early signs of fungal infection
- Apply recommended fungicide immediately
- Improve field drainage before next rainfall
- Avoid excessive irrigation for the next 5 days
```

---

## 🌱 Real-World Impact

This system can help small and medium farmers:
- Get early warnings **before** crop damage occurs
- Reduce losses from preventable fungal and pest outbreaks
- Make informed irrigation and spraying decisions
- Stay updated with agriculture news without manual research

---

## 📸 Screenshots

> *Add screenshots of the workflow, the 3-branch data collection, and a sample alert email here.*

---

## 🎬 Demo

> *[Add Loom / YouTube demo link here]*
