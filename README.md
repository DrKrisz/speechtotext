# Simple Speech to Text (EN/HU/NO)

**Live site:** https://drkrisz.github.io/speechtotext/

A minimal browser app that turns speech into text and lets you download the transcript as a .txt file. Everything runs locally in your browser using the Web Speech API.

## Features
- Record, Stop, and Download .txt
- Live transcript with interim text
- Language dropdown: English (UK), English (US), Norwegian Bokmål (no-NO), Hungarian (hu-HU)
- Clear button to wipe the transcript
- Live size meter (B, KB, MB, GB)
- Auto extend for long sessions: recognition restarts under the hood so you can keep going

## How it works
- Uses the browser built in speech recognition (Web Speech API)
- No server or cloud calls
- Best experience in Chromium browsers (Chrome, Edge)
- Microphone permission is required

## Quick start

### Run locally
Web Speech API needs HTTPS or localhost.

Python 3:
```bash
python -m http.server 8000
# open http://localhost:8000
