# Code Language Detector Studio

A client-side web app that detects the programming language of pasted code using pattern and keyword heuristics.

## Features
- Heuristic language detection with confidence score
- Line numbers and code stats (lines/characters)
- Detectable languages list with logos
- Light/Dark mode toggle
- Copy Result button (language + confidence + stats)

## Detectable Languages
- JavaScript
- Python
- Java
- C++
- C
- C#
- Ruby
- PHP
- Swift
- Go
- Rust
- TypeScript
- Kotlin
- SQL
- HTML
- CSS
- JSON
- JSX

## Files
- `index.html` – App markup
- `styles.css` – Styling and themes
- `script.js` – Detection logic and UI behavior
- `images/` – Logo assets

## Run
Open `index.html` in a browser.

## Usage
1. Paste code into the left panel.
2. Click `Analyze Code` (or press `Ctrl+Enter` / `Cmd+Enter`).
3. See the detected language, confidence, and stats.
4. Use `Copy Result` to copy the summary.

## How Detection Works
- Each language has regex patterns and keyword lists in `languagePatterns` inside `script.js`.
- Matches add to a score per language; the highest score wins.
- Confidence is derived from the top score vs. total score.
- Extra boosts exist for TypeScript-only syntax (type annotations, `interface`, `type`, etc.) and filename hints (e.g., `// main.ts`).

## Notes
- Detection is heuristic-based and may be incorrect for short or mixed snippets.
- No server or build step required.
