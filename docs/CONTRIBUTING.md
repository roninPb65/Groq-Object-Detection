# Contributing to Vision AI Surveillance

Thanks for your interest in contributing! This is a single-file browser app, so contributions are straightforward.

---

## Getting Started

1. **Fork** the repository on GitHub
2. **Clone** your fork:
   ```bash
   git clone https://github.com/YOUR_USERNAME/vision-ai-surveillance.git
   cd vision-ai-surveillance
   ```
3. Create a **feature branch**:
   ```bash
   git checkout -b feature/your-feature-name
   ```
4. Make your changes in `index.html` (or docs files)
5. Test in multiple browsers
6. **Commit** with a clear message:
   ```bash
   git commit -m "feat: add text-to-speech alerts for driving mode"
   ```
7. **Push** and open a **Pull Request**

---

## What to Contribute

### High-priority features
- [ ] **Text-to-speech alerts** — speak hazard warnings aloud in driving mode
- [ ] **Bounding box overlay** — draw boxes around detected objects on the video canvas
- [ ] **Detection history log** — scrollable log of all past detections with timestamps
- [ ] **Export to CSV** — download detection log as a spreadsheet
- [ ] **Custom prompt editor** — UI for editing the mode prompt directly in the browser
- [ ] **PWA support** — manifest + service worker for installable offline app
- [ ] **Ollama integration** — option to use a local vision model (no API key needed)
- [ ] **OpenAI / Gemini support** — additional API provider options
- [ ] **Audio alerts** — beep or chime on ALERT detection

### Documentation
- Translations of README into other languages
- Video walkthrough / demo GIF
- Additional usage examples and screenshots

### Bug reports
Open an issue with:
- Browser and version
- Device type (desktop/mobile/tablet)
- Steps to reproduce
- Expected vs actual behavior
- Console errors (open DevTools → Console)

---

## Code Style

This project is intentionally dependency-free vanilla JS. Please keep it that way.

- **No frameworks** (no React, Vue, etc.)
- **No build step** — the app must run by opening `index.html` directly
- **No external dependencies** beyond the Tabler Icons CDN and the Groq API
- Keep CSS in the `<style>` block, JS in the `<script>` block
- Comment complex logic briefly but don't over-comment
- Use `const` and `let`, not `var`
- Prefer `async/await` over `.then()` chains

---

## Testing Checklist

Before submitting a PR, verify:

- [ ] App loads correctly by opening `index.html` directly (no server)
- [ ] App loads correctly via `python3 -m http.server`
- [ ] Camera starts and shows live feed
- [ ] API key entry and save works
- [ ] All 4 modes analyze correctly
- [ ] Chat interface works with and without a camera frame
- [ ] Auto-analysis runs every ~10 seconds
- [ ] Model fallback works (you can test by temporarily using a bad model name)
- [ ] Alerts display correctly in the sidebar
- [ ] Responsive layout works on mobile (< 640px width)
- [ ] Tested in at least 2 browsers

---

## Commit Message Format

Use [Conventional Commits](https://www.conventionalcommits.org/):

```
feat: add text-to-speech for driving mode
fix: prevent duplicate alerts from stacking
docs: add Ollama setup instructions
refactor: extract captureJpeg into a utility function
style: improve mobile layout for sidebar
```

---

## License

By contributing, you agree your contributions will be licensed under the MIT License.
