# StillMind AI — Learn Better. Remember Longer.
Turn notes into a summary, a 5-question quiz and flashcards using the Google Gemini API.

## Features
Summary (copy, .txt download, read aloud) · Quiz with scoring and explanations · 3D flip flashcards with known/not-known · History in localStorage (search, filter, delete, clear) · Persistent dark/light mode · Quiz score chart · Full error handling and response validation.

## Technologies
HTML5, CSS3, vanilla JavaScript, Fetch API (async/await), localStorage, Speech Synthesis API, Gemini API (`gemini-2.5-flash`, `generateContent`).

## Run on a Mac
1. Open Terminal and `cd` into this folder.
2. Run `python3 -m http.server 8000`
3. Open http://localhost:8000 in Chrome or Safari.

## Get an API key
1. Go to https://aistudio.google.com/apikey and sign in.
2. Click "Create API key" and copy it.
3. In the app, open Study Workspace → Settings, paste the key, click "Save key". The status should show "API key configured".

The key is stored only in your browser's localStorage. localStorage can be read by any script on the page, so a production app should keep keys on a backend. Never commit a real key to GitHub.

## JSON schema (parser matches exactly)
`{ summary:{title,introduction,sections:[{heading,points[]}],keyTakeaways[]}, quiz:[5 × {question,options[4],correctAnswer 0-3,explanation}], flashcards:[{front,back}] }`

## Test checklist
- No key → "Add your Gemini API key" message.
- Empty notes/topic → input message.
- Wrong key → "API key was rejected".
- Turn off Wi-Fi → network error message.
- Valid key → three tabs filled; Generate button disabled while loading.
- Refresh → history and theme remain; click an entry to restore; delete works.

## Screenshots
(Add screenshots here.)

## GitHub and deployment
1. `git init && git add . && git commit -m "StillMind AI"`
2. Create an empty repo on github.com, then `git remote add origin <url>` and `git push -u origin main`.
3. Deploy free: repo Settings → Pages → deploy from `main` branch root. Users enter their own API key.
