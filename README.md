Simple Speech to Text (EN/HU/NO)

Live site: https://drkrisz.github.io/speechtotext/

A minimal browser app that turns speech into text and lets you download the transcript as a .txt file. Everything runs locally in your browser using the Web Speech API.

Features

Record, Stop, and Download .txt

Live transcript with interim text

Language dropdown: English (UK), English (US), Norwegian Bokmål (no-NO), Hungarian (hu-HU)

Clear button to wipe the transcript

Live size meter (B, KB, MB, GB)

Auto extend for long sessions: recognition restarts under the hood so you can keep going

How it works

Uses the browser built-in speech recognition (Web Speech API)

No server or cloud calls

Best experience in Chromium browsers (Chrome, Edge)

Microphone permission is required

Quick start
Run locally

Web Speech API needs HTTPS or localhost.

Python 3

python -m http.server 8000
# open http://localhost:8000


Node (npx)

npx serve .
# open the printed localhost URL

Deploy to GitHub Pages

Put index.html in the repo root.

Push to main (or master).

In GitHub: Settings -> Pages -> set Source to deploy from the root.

Your site will be available at https://<username>.github.io/<repo>/.

Already live here: https://drkrisz.github.io/speechtotext/

Browser support

Chrome and Edge: supported

Safari and Firefox: limited or no Web Speech API support

If the API is not available, typing still works and you can download what you typed

Tips

Keep the tab focused while recording for stable results

If recognition stops after a while, press Record again

Use a decent microphone and avoid loud background noise for better accuracy

Known limitations

Accuracy and stability come from the browser engine and vary by device

Punctuation and capitalization may need manual edits

Very long sessions can hiccup; the app auto restarts recognition to extend time

Roadmap

Optional punctuation cleanup

Autosave to local storage

Timestamped paragraphs and notes

More language variants on demand

Development

All logic is in a single index.html. Open it, tweak styles or scripts, and reload.

License

MIT License. Use, modify, and share at your own risk.
