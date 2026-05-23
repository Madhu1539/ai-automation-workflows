# 🎨 AI Image Generator

> A webhook-powered n8n workflow that accepts a text prompt, generates an AI image using the Freepik Mystic API, and returns the image directly — no UI required.

---

## 🚀 What It Does

Send a POST request with a text prompt → receive a generated AI image in response. The workflow handles the asynchronous generation process automatically: submitting the prompt, waiting 30 seconds for processing, checking the result, and returning the final image as binary data.

---

## ⚙️ How It Works — Step by Step

1. **Webhook (POST)** — Receives a JSON body with `{ "text": "your prompt here" }`
2. **Send Prompt to Freepik** — POSTs the prompt to Freepik's Mystic AI image generation API
3. **Wait (30s)** — Pauses to allow the model to generate the image
4. **Check Status** — Polls the Freepik API to retrieve the generated image URL
5. **Retrieve Image** — Downloads the final image as binary data
6. **Respond to Webhook** — Returns the image directly as a binary response

---

## 🛠️ Tools & APIs Used

| Tool | Purpose |
|------|---------|
| **Freepik Mystic API** | AI image generation from text prompts |
| **n8n Webhook** | HTTP trigger to accept external requests |
| **n8n Wait Node** | Handles async generation delay |
| **HTTP Request** | API communication and image retrieval |

---

## 🔑 Required Credentials

| Credential | Where to Get It |
|------------|----------------|
| Freepik API Key | [freepik.com/api](https://www.freepik.com/api) → Free tier available |

---

## 📋 Setup Instructions

1. Import `workflow.json` into your n8n instance
2. In the **"Send Text Prompt to FreePik API"** node, replace `YOUR_FREEPIK_API_KEY_HERE` with your actual Freepik API key
3. In the **"Check Status"** node, the URL will be dynamically set from step 2's response
4. Activate the workflow — your webhook URL will appear in the Webhook node
5. Test with a POST request:

```bash
curl -X POST https://your-n8n-instance/webhook/YOUR_WEBHOOK_PATH \
  -H "Content-Type: application/json" \
  -d '{"text": "a futuristic city at sunset, cyberpunk style"}'
```

---

## 🎨 Example Prompts

- `"a serene mountain lake at dawn, photorealistic"`
- `"a robot reading a book in a cozy library, warm lighting"`
- `"abstract geometric art, neon colors on black background"`
- `"portrait of a Bengal tiger in the jungle, ultra detailed"`

---

## 📸 Screenshots

> *Add screenshots of the workflow canvas and sample generated images here.*

---

## 🎬 Demo

> *[Add Loom / YouTube demo link here]*
