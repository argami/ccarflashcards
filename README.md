# CCAR-F Flashcards

Study material for the **Claude Certified Architect – Foundations (CCAR-F)** exam: 79 scenario-based
multiple-choice cards over Domain 1 (*Agentic Architecture & Orchestration*), bilingual EN/ES.

**Unofficial.** Not affiliated with, endorsed by, or produced by Anthropic. Built from the public exam
guide and the publicly available lesson pages, with every citation an exact quote from those sources.

## What's in here

| File | |
|---|---|
| `index.html` | landing page (English by default, ES/EN toggle) |
| `ccarflashcards.html` | the study app — one self-contained file, no server, no CDN, works from `file://` |
| `ccarflashcards.apkg` | the same 79 cards as an Anki deck (model v2, 19 fields, 5 sub-decks) |
| `.nojekyll` | tells GitHub Pages to serve the files as-is |

## Two ways to study

**In the browser.** Open `ccarflashcards.html`. Answer with keys `1`–`4`, `Space` for the next card.
Each card gives correctness feedback, why every distractor fails, the trap it's testing, and the source
citations. Progress is stored in your browser's `localStorage` — it does not sync between devices, and
clearing site data resets it. Study queue is a Leitner ladder (0-1-3-7-16 days).

**In Anki.** Import `ccarflashcards.apkg` (Anki desktop, AnkiDroid, AnkiMobile, AnkiWeb — all free).
You get real spaced repetition scheduling and sync across devices, at the cost of needing an app.

The two artifacts share content but not progress. Pick one.

## Deck contents

- 79 cards, all Domain 1, seven sub-domains: 1.1 agentic loops (14), 1.2 orchestration patterns (10),
  1.3 subagent invocation & context (12), 1.4 workflow enforcement & handoff (10), 1.5 Agent SDK hooks
  (14), 1.6 task decomposition (9), 1.7 session state & resumption (10).
- 124 citations, all verbatim substrings of the source corpus.
- Every card exists in English and Spanish; the app and the deck each have their own language switch
  (the deck's default is configurable at build time: `--lang en|es|both`).
- Tags: `domain::D1`, `sub::1.5`, `trap::determinism_drift`, `difficulty::hard`, `origin::generated`.
- Difficulty split: 43 core / 36 hard.

Domains 2–5 (73% of the exam) are **not** covered yet.

## Exam facts

60 items · 120 minutes · pass 720/1000 · 4 scenarios drawn from a bank of 6 · $125 USD · Pearson VUE ·
valid 12 months. Weights: D1 27%, D2 18%, D3 20%, D4 20%, D5 15%.

## Rebuilding

These files are generated, never hand-edited. The generator lives outside this repo
(`build/make_app.py`, `build/make_anki.py`, `build/make_site.py`, source of truth `cards/cards.json`).

```bash
.venv/bin/python build/make_app.py     # -> build/ccarflashcards.html
.venv/bin/python build/make_anki.py    # -> build/ccarflashcards.apkg
.venv/bin/python build/make_site.py    # -> site/ (landing + copies + .nojekyll)
```

## License

Content quotes the publicly published Anthropic exam guide and lesson pages; the card writing,
explanations and app code are original. Use it to study, don't resell it.
