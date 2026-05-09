# Setup Guide

## Prerequisites

- A modern browser (Chrome, Firefox, Edge, Safari 15+)
- A device with a camera (laptop, phone, tablet)
- A free Groq account

---

## Step 1: Get a Free Groq API Key

1. Visit [https://console.groq.com](https://console.groq.com)
2. Click **Sign Up** (free — no credit card required)
3. After signing in, go to **API Keys** in the left sidebar
4. Click **Create API Key**, give it a name (e.g. `vision-ai`)
5. Copy the key — it starts with `gsk_`

> Keep your API key private. Never commit it to Git.

---

## Step 2: Get the App

### Option A — Download ZIP
1. Click the green **Code** button on GitHub
2. Select **Download ZIP**
3. Extract the folder

### Option B — Clone with Git
```bash
git clone https://github.com/YOUR_USERNAME/vision-ai-surveillance.git
cd vision-ai-surveillance
```

---

## Step 3: Run the App

### Simplest: Open directly in browser
```bash
open index.html          # macOS
start index.html         # Windows
xdg-open index.html      # Linux
```

### Recommended: Local web server
Using Python (built-in):
```bash
python3 -m http.server 8080
# Open http://localhost:8080
```

Using Node.js:
```bash
npx serve .
# Opens automatically
```

Using VS Code:
- Install the **Live Server** extension
- Right-click `index.html` → **Open with Live Server**

> A local server is recommended because some browsers restrict camera access on `file://` URLs.

---

## Step 4: Use the App

1. **Paste your Groq API key** into the field at the top and click **SAVE**
2. Click **▶ START CAMERA** — your browser will ask for camera permission, click Allow
3. **Select a mode:**
   - `GENERAL` — everyday object detection
   - `DRIVING` — mount in car for traffic guidance
   - `SECURITY` — home/office surveillance
   - `CUSTOM` — freeform, give instructions via chat
4. The AI will auto-analyze every 10 seconds, or click **ANALYZE FRAME NOW**
5. Chat with the assistant about what it sees

---

## Driving / Dashcam Setup

1. Mount your phone or laptop facing the road (windshield mount, dashboard, etc.)
2. Open the app and connect your Groq key
3. Switch to **DRIVING** mode
4. The AI will:
   - Identify vehicles, pedestrians, cyclists
   - Read traffic signs and signals
   - Warn about hazards
   - Provide real-time guidance

> ⚠️ **Safety First:** Never interact with the app while the vehicle is moving. Mount securely, glance only. The AI is an assistance tool, not a replacement for your attention on the road.

---

## Troubleshooting

| Problem | Solution |
|---------|----------|
| Camera won't start | Make sure you granted camera permission in the browser |
| "Invalid key" error | Groq keys start with `gsk_` — check you copied the full key |
| Model not found | The app auto-retries with a fallback model — wait a moment |
| Black screen on mobile | Some browsers on iOS require Safari. Try switching to front camera |
| Slow analysis | Groq is very fast — check your internet connection |
| CORS error | Run via a local server instead of opening `file://` directly |

---

## Deploy to GitHub Pages (Free Hosting)

1. Push your repo to GitHub
2. Go to **Settings → Pages**
3. Under **Source**, select **Deploy from a branch**
4. Choose `main` branch, `/ (root)` folder
5. Click **Save**

Your app will be live at:
`https://YOUR_USERNAME.github.io/vision-ai-surveillance/`

---

## Supported Browsers

| Browser | Support |
|---------|---------|
| Chrome 90+ | ✅ Full support |
| Firefox 90+ | ✅ Full support |
| Edge 90+ | ✅ Full support |
| Safari 15+ | ✅ Full support |
| Mobile Chrome | ✅ Full support |
| Mobile Safari | ✅ Full support |
| IE 11 | ❌ Not supported |
