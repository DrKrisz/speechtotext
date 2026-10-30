# Simple Speech to Text (EN/HU/NO)

A small static web app that turns speech into an editable transcript and exports
it as a `.txt` file.

[Open the published version](https://drkrisz.github.io/speechtotext/)

## Stack and features

Plain HTML, CSS and JavaScript in one `index.html`; browser Web Speech API,
Blob downloads and TextEncoder. There is no application backend or build step.

- Start/stop recognition, show interim and final text, clear and download.
- Language choices: English UK/US, Norwegian Bokmål and Hungarian.
- Recording timer, word counter and UTF-8 size display.
- Attempts to restart recognition when a session ends while recording.

## Run locally

With Python 3 installed, run from the repository directory:

```bash
python -m http.server 8000
```

Open [localhost:8000](http://localhost:8000) in a browser with speech recognition
support and allow microphone access. For deployment, serve the static page
over HTTPS, such as GitHub Pages.

## Architecture and development

All markup, styles, recognition event handlers and download logic are in
`index.html`. The app creates `SpeechRecognition` or
`webkitSpeechRecognition` when available. Recognition results update a text
buffer and textarea; download creates a local Blob URL.

The [public development history](https://github.com/DrKrisz/speechtotext/commits/main/)
records the page and subsequent interface/recognition changes under DrKrisz.
The app integrates a browser recognition service; it does not implement or
train a speech-recognition model.

## Privacy and browser limits

The page has no custom backend upload endpoint. **That does not guarantee local
or offline recognition:** the browser's recognition service may send microphone
audio to a remote service. This app does not request on-device processing.
See [MDN's SpeechRecognition notes](https://developer.mozilla.org/en-US/docs/Web/API/SpeechRecognition).

Support depends on the browser, platform, microphone permissions and recognition
service. The code detects API availability; if it is missing, typing and text
download remain available. There is no verified browser compatibility matrix.

## Checks before a demo

1. Open over HTTPS or localhost and grant microphone access.
2. Record a short phrase, stop, edit the text and download it.
3. Try changing language, clearing text and denying microphone access.
4. Check fallback typing/download in a browser without the API.

No automated recognition or microphone test is included. Recognition accuracy
and long-session reliability depend on the browser service.

## Current limitations

- No autosave: refreshing or closing the page loses the transcript.
- Automatic retries do not guarantee uninterrupted recording.
- The word counter currently combines the saved buffer with the textarea and can
  overcount recognized text.
- Editing during recognition can be overwritten by the next recognition result.
- No application-level encryption or control over the browser provider's
  recognition infrastructure.
