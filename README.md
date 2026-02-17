# CodeAnalyzer Studio

A client-side web app that detects the programming language of pasted code using pattern- and keyword-based heuristics.

![CodeAnalyzer Studio](images/Code-Analyzer.png)

## Files
- `index.html` – App markup
- `styles.css` – Styling
- `script.js` – Detection logic and UI behavior
- `images/` – Logo assets

## Run
Open `index.html` in a browser.

## How to Use
1. Paste code into the center editor panel.
2. Press `Enter` to analyze (use `Shift+Enter` to add a new line), press `Ctrl+Enter`/`Cmd+Enter`, or click `Detect Language`.
3. See the detected language, confidence, and stats.
4. Use `Copy Result` to copy the full report.
5. Use `Clear` to reset the input and results.

## How It Works
- Each language has regex patterns and keyword lists in `languagePatterns` inside `script.js`.
- Matches add to a score per language; the highest score wins.
- Confidence is derived from the top score vs. total score.
- Extra boosts exist for TypeScript-only syntax (type annotations, `interface`, `type`, etc.) and filename hints (e.g., `// main.ts`).
- Very large inputs are truncated to the first 20,000 characters for performance.

## Features
- Heuristic language detection with a confidence score
- Line numbers and code stats (lines/characters)
- Detectable languages list with logos
- `Copy Result` button with a full report (language, confidence, stats, patterns, alternatives)
- Filename hint detection (e.g., `// main.ts`)
- Performance guard for large inputs
- Match explanation (pattern/keyword counts)

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

## Notes
- Detection is heuristic-based and may be incorrect for short or mixed snippets.
- No server or build step required.
- The app includes legacy history persistence in localStorage even though it is not currently exposed in the UI.
