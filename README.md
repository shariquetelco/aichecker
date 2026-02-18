# AiCHECKER

> A free, browser-only tool that detects whether content was AI-generated or human-written.

**Live demo:** [https://aichecker.vercel.app](https://aichecker.vercel.app)

---

## Features

- **URL Analysis** — Paste any public URL; the page is fetched via allorigins.win and its visible text is analysed.
- **Text / Code Paste** — Paste raw text, articles, essays, or code directly into the editor.
- **File Upload** — Upload `.pdf`, `.txt`, or `.html` files. PDF text is extracted client-side via PDF.js.
- **18+ heuristic signal checks** — filler phrases, passive voice, uniform paragraph lengths, generic variable names, docstring coverage, and more.
- **Animated SVG score ring** — colour-coded result from 0–100 with a smooth fill animation.
- **Four score categories**: Vibe Coded · Suspicious · Mixed Signals · Certified Human
- **100% private** — no data leaves your browser, no API calls, no login required.

---

## Score Formula

```
rawScore = weighted sum of all signal scores (0–100)
finalScore = 30 + 45 × tanh(rawScore / 30)
```

| Category        | Range   | Colour  |
|-----------------|---------|---------|
| Vibe Coded      | > 72    | Green   |
| Suspicious      | 50–72   | Amber   |
| Mixed Signals   | 35–50   | Orange  |
| Certified Human | < 35    | Red     |

---

## Tech Stack

- **Pure HTML / CSS / JS** — zero build step, zero dependencies
- **PDF.js** (CDN) for in-browser PDF text extraction
- **allorigins.win** CORS proxy for URL fetching
- **Google Fonts** — Cormorant Garamond + Montserrat
- **Vercel** for static hosting (free Hobby plan)

---

## Local Development

No build step needed — just open `index.html` in your browser:

```bash
# macOS / Linux
open index.html

# Windows
start index.html

# Or serve with any static server:
npx serve .
```

---

## Deployment (Vercel)

```bash
npm i -g vercel
vercel        # follow prompts — deploys in ~30 seconds
```

Every push to `main` triggers an automatic redeploy when the GitHub repo is linked in the Vercel dashboard.

---

## Project Structure

```
aichecker/
├── index.html      # Entire app — HTML + CSS + JS inline
├── vercel.json     # Static output config
├── .gitignore
└── README.md
```

---

## Author

**shariquetelco** · eshariq.am@gmail.com
GitHub: [github.com/shariquetelco/aichecker](https://github.com/shariquetelco/aichecker)

---

*No data is transmitted. All analysis runs locally in your browser.*
