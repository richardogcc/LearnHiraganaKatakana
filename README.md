# Learn Hiragana & Katakana

A tiny, self‑contained web app to practice reading Japanese hiragana and katakana.

The trainer runs entirely in the browser using a single `index.html` file (no build step or backend required).

## Features

- **Hiragana & Katakana**
  - Basic syllabaries (vowels + K / S / T / N / H / M / Y / R / W / N rows).
  - Extended sets with **dakuten / handakuten** (G, Z, D, B, P rows).
- **Multiple practice modes**
  - Kana → romaji and romaji → kana.
  - Separate modes for hiragana / katakana and their extended sets.
- **Inline help**
  - Click the big character/romaji to reveal the answer without leaving the mode.
  - Quick reference charts for hiragana / katakana with basic + extended sets.
- **Session stats**
  - Remaining characters in the current round.
  - Current streak and best streak.
  - Session timer with stable UI badge.
- **Light / dark theme**
  - Theme toggle with persistence in `localStorage`.
  - Charts and game screen restyled for both themes.

## Getting started

You only need a browser. From the repository root:

```bash
# Option 1: open directly
open index.html  # macOS (or double‑click the file)

# Option 2: simple local server
python3 -m http.server 8000
# then visit http://localhost:8000/
```

## How to use

1. Open the page in your browser.
2. Choose a **Hiragana** or **Katakana** mode:
   - e.g. `あ → a` (kana → romaji) or `a → あ` (romaji → kana).
3. Type the correct answer in the input box:
   - On success, the character flashes green and the next one appears.
   - The **remaining** counter, **streak**, and **timer** update automatically.
4. Need help on a character?
   - Click the large character/romaji to toggle the answer.
5. Need to review the whole chart?
   - Click **Show hiragana chart** or **Show katakana chart**.
   - You’ll see the basic set and dakuten/handakuten set for that script.
6. Press **Menu** at any time to return to the mode selection.

## Project structure

```text
.
├── index.html   # UI, styles, and game logic
├── README.md    # This file
└── LICENSE      # Repository license
```

All logic (data sets, state machine, stats, dark mode, modal charts) lives inside `index.html`.

## Optional: browser tests with Playwright

If you want to add automated UI tests later, one straightforward option is [Playwright Test](https://playwright.dev/):

```bash
npm init -y
npm install --save-dev @playwright/test
npx playwright install
```

Then you can create tests under a `tests/` or `e2e/` folder that open `index.html`, click on modes, and assert that characters, stats, and charts behave as expected.

## License

See `LICENSE` for details.
