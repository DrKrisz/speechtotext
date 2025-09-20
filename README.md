# Simple Speech to Text (EN/HU/NO)

**Live site:** https://drkrisz.github.io/speechtotext/

A minimal browser app that turns speech into text and lets you download the transcript as a `.txt` file. Everything runs locally in your browser using the Web Speech API.

## Features
- Record, Stop, and Download `.txt`
- Live transcript with interim text
- Language dropdown: English (UK), English (US), Norwegian Bokmål (no-NO), Hungarian (hu-HU)
- Clear button to wipe the transcript
- Live size meter (B, KB, MB, GB)
- Auto extend for long sessions: recognition restarts to keep recording

## How it works
- Uses the browser built in speech recognition (Web Speech API)
- No server or cloud calls
- Best in Chromium browsers (Chrome, Edge)
- Microphone permission is required

## Quick start

### Run locally
Web Speech API needs HTTPS or `localhost`.

**Python 3**
```bash
python -m http.server 8000
# open http://localhost:8000
```

**Node (npx)**
```bash
npx serve .
# open the printed localhost URL
```

### Deploy to GitHub Pages
1. Put `index.html` in the repo root.
2. Push to `main` (or `master`).
3. In GitHub: Settings -> Pages -> set Source to deploy from the root.
4. Your site will be available at `https://<username>.github.io/<repo>/`.

Already live here: https://drkrisz.github.io/speechtotext/

## Browser support
- Chrome and Edge: supported
- Safari and Firefox: limited or no Web Speech API support
- If the API is not available, you can still type and download the text

## Tips
- Keep the tab focused while recording
- If recognition stops after a while, press Record again
- Use a decent microphone and avoid loud background noise

## Known limitations
- Accuracy and stability come from the browser engine and vary by device
- Punctuation and capitalization may need manual edits
- Very long sessions can hiccup; the app restarts recognition to extend time

## Roadmap
- Optional punctuation cleanup
- Autosave to local storage
- Timestamped paragraphs and notes
- More language variants on demand

## Development
All logic is in a single `index.html`. Edit styles or scripts and reload.

## License
MIT License. Use, modify, and share at your own risk.
