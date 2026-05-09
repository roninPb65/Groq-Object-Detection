# API Reference

## Groq API

This app uses the [Groq API](https://console.groq.com/docs/openai) via the OpenAI-compatible endpoint.

### Endpoint

```
POST https://api.groq.com/openai/v1/chat/completions
```

### Authentication

```http
Authorization: Bearer gsk_your_api_key_here
```

### Vision Request (used for frame analysis)

```json
{
  "model": "meta-llama/llama-4-scout-17b-16e-instruct",
  "max_tokens": 600,
  "messages": [
    {
      "role": "system",
      "content": "You are a precise visual AI assistant..."
    },
    {
      "role": "user",
      "content": [
        {
          "type": "image_url",
          "image_url": {
            "url": "data:image/jpeg;base64,/9j/4AAQ..."
          }
        },
        {
          "type": "text",
          "text": "Analyze this frame and respond in the format..."
        }
      ]
    }
  ]
}
```

### Text-only Request (used for chat)

```json
{
  "model": "meta-llama/llama-4-scout-17b-16e-instruct",
  "max_tokens": 700,
  "messages": [
    { "role": "system", "content": "You are a visual AI assistant..." },
    { "role": "user",   "content": [{ "type": "text", "text": "User message here" }] }
  ]
}
```

---

## Vision Models Available on Groq

| Model | Speed | Context | Vision | Notes |
|-------|-------|---------|--------|-------|
| `meta-llama/llama-4-scout-17b-16e-instruct` | ⚡ Fastest | 131K | ✅ | Default — best for real-time |
| `meta-llama/llama-4-maverick-17b-128e-instruct` | ⚡ Fast | 131K | ✅ | Fallback #1 |
| `llava-v1.5-7b-4096-preview` | Fast | 4K | ✅ | Fallback #2, smaller context |

The app automatically falls back to the next model if one returns a model error.

---

## Rate Limits (Free Tier)

Groq's free tier is generous. As of 2025:

| Resource | Limit |
|----------|-------|
| Requests per minute | 30 |
| Tokens per minute | 6,000 |
| Tokens per day | 500,000 |

With the app's 10-second auto-analysis interval and ~600 tokens per request, you'll use approximately:
- ~6 requests/minute if analyzing continuously
- ~360 tokens/minute
- Well within free limits for hours of use

---

## Frame Capture Details

The app captures JPEG frames from the video stream at reduced resolution to stay within API limits:

```javascript
// Captured at max 640px wide, 72% JPEG quality
const scale = Math.min(1, 640 / video.videoWidth);
canvas.width  = Math.round(video.videoWidth  * scale);
canvas.height = Math.round(video.videoHeight * scale);
ctx.drawImage(video, 0, 0, canvas.width, canvas.height);
const base64 = canvas.toDataURL('image/jpeg', 0.72).split(',')[1];
```

Typical frame size: 40–80 KB, well under Groq's image limits.

---

## Extending the App

### Adding a new mode

1. Add an entry to `MODE_PROMPTS` in `index.html`:
```javascript
const MODE_PROMPTS = {
  // ... existing modes ...
  retail: `You are a retail analytics AI. Analyze this camera frame and return:
SCENE: store area description
CUSTOMERS: count and general activity
PRODUCTS: visible product categories
DISPLAY: shelf/display conditions
ALERT: any issue requiring staff attention (else: ALERT: none)`
};
```

2. Add a mode hint to `MODE_HINTS`:
```javascript
const MODE_HINTS = {
  // ... existing ...
  retail: 'Monitoring customer activity and store conditions.'
};
```

3. Add a tab button in the HTML:
```html
<button class="tab" onclick="setMode('retail')" id="tab-retail">RETAIL</button>
```

### Using a different AI provider

The app uses the OpenAI-compatible API format. To switch providers, change the endpoint URL and model name:

```javascript
// OpenAI
const API_URL = 'https://api.openai.com/v1/chat/completions';
const MODEL   = 'gpt-4o-mini';

// Ollama (local)
const API_URL = 'http://localhost:11434/v1/chat/completions';
const MODEL   = 'llava';
```
