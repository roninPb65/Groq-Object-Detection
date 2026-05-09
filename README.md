# 🎯 Vision AI Surveillance

A **live browser-based video surveillance system** with real-time AI object detection, powered by **Groq's free API** (Llama 4 Scout vision model). No backend required — runs entirely in your browser.

![Vision AI Surveillance](docs/screenshot-placeholder.png)

## ✨ Features

- 📷 **Live camera feed** with HUD overlay
- 🔍 **Real-time object detection** — auto-scans every 10 seconds
- 🚗 **Driving mode** — dashcam assistant for traffic safety, sign reading, hazard detection
- 🔒 **Security mode** — people counting, activity monitoring, anomaly alerts
- 🌐 **General mode** — full scene description and object listing
- 💬 **AI chat assistant** — ask questions about what the camera sees
- ⚡ **Powered by Groq** — free, ultra-fast inference (Llama 4 Scout vision)
- 📱 **Mobile friendly** — works on phone browsers, great for dashcam use

## 🚀 Quick Start

### 1. Clone the repo
```bash
git clone https://github.com/YOUR_USERNAME/vision-ai-surveillance.git
cd vision-ai-surveillance
```

### 2. Get a free Groq API key
1. Go to [console.groq.com](https://console.groq.com)
2. Sign up for free (no credit card needed)
3. Navigate to **API Keys** → **Create API Key**
4. Copy your key (starts with `gsk_...`)

### 3. Run it
Just open `index.html` in your browser — no server needed!

```bash
# Option A: Open directly
open index.html

# Option B: Simple local server (recommended)
npx serve .
# or
python3 -m http.server 8080
```

### 4. Use it
1. Paste your Groq API key in the field at the top
2. Click **START CAMERA** and allow camera access
3. Select a mode (General / Driving / Security / Custom)
4. Watch live detections appear, or chat with the AI

## 🎮 Modes

| Mode | Best For | What It Does |
|------|----------|-------------|
| **GENERAL** | Everyday use | Detects all objects, people, scene context |
| **DRIVING** | Dashcam / car | Traffic signs, vehicles, pedestrians, hazard alerts |
| **SECURITY** | Home / office | People counting, activity monitoring, access points |
| **CUSTOM** | Anything | Freeform — you give instructions via chat |

## 🏎️ Driving Mode Setup

Mount your phone or laptop facing the road and switch to **DRIVING** mode. The AI will:
- Read traffic signs and signals
- Identify nearby vehicles and pedestrians
- Alert you to potential hazards
- Give real-time driving guidance

> ⚠️ **Safety note:** Never interact with the app while driving. Mount the device securely and use audio/glance only.

## 🛠️ Tech Stack

| Component | Technology |
|-----------|-----------|
| Frontend | Vanilla HTML/CSS/JavaScript |
| AI Vision | Groq API — `meta-llama/llama-4-scout-17b-16e-instruct` |
| Fallback models | `llama-4-maverick-17b`, `llava-v1.5-7b` |
| Camera | Browser `getUserMedia` API |
| Hosting | Any static host (GitHub Pages, Netlify, Vercel) |

## 📁 Project Structure

```
vision-ai-surveillance/
├── index.html          # Main application (self-contained)
├── README.md           # This file
├── LICENSE             # MIT License
├── .gitignore          # Git ignore rules
├── .env.example        # Environment variable template
└── docs/
    ├── SETUP.md        # Detailed setup guide
    ├── MODES.md        # Mode documentation
    ├── API.md          # Groq API reference
    └── CONTRIBUTING.md # Contribution guide
```

## 🌍 Deploy to GitHub Pages

1. Push to GitHub
2. Go to **Settings** → **Pages**
3. Set source to **main branch / root**
4. Your app is live at `https://YOUR_USERNAME.github.io/vision-ai-surveillance`

## 🔒 Privacy & Security

- **Your API key is never stored** — it lives only in memory during your session
- **No video is uploaded** — frames are processed locally then sent to Groq for analysis
- **No backend, no database** — everything runs in your browser
- Camera feed is never recorded or saved

## 🤝 Contributing

Contributions are welcome! See [docs/CONTRIBUTING.md](docs/CONTRIBUTING.md) for guidelines.

Ideas for contributions:
- [ ] Text-to-speech alerts for driving mode
- [ ] Object detection bounding boxes drawn on video
- [ ] Custom prompt editor for Custom mode
- [ ] Export detection logs as CSV
- [ ] PWA support for offline use
- [ ] Additional AI provider support (OpenAI, Ollama)

## 📄 License

MIT License — see [LICENSE](LICENSE) for details.

## 🙏 Acknowledgements

- [Groq](https://groq.com) for the blazing-fast free API
- [Meta AI](https://ai.meta.com) for the Llama 4 vision models
- [Tabler Icons](https://tabler.io/icons) for the icon set
