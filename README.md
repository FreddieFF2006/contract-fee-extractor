# Contract Fee Equation Extractor

An AI-powered tool that reads any contract PDF, finds every fee and royalty calculation section, extracts the algebra, and generates a ready-to-use Python module.

## Live Site

> Deployed via GitHub Pages — see the URL at the top of this repo.

## How it works

1. You enter your [Anthropic API key](https://console.anthropic.com) (stored only in your browser session — never sent anywhere except directly to Anthropic)
2. Drop any contract PDF (service schedules, licensing agreements, distribution contracts, etc.)
3. The tool extracts the text client-side using PDF.js, sends it to Claude, and parses every fee section
4. Results are displayed with variable definitions, tier conditions, and algebraic equations
5. Download a `.py` module with docstrings and `print_equation_summary()`

## What gets extracted

For each fee type found:
- Plain-English description
- Named variable definitions (e.g. `N = total users`, `S = pro-rata share`)
- Per-tier equations with conditions (e.g. Column A / B / C tiers)
- Combined total equation
- Notes on floors, caps, exemptions

## Tech stack

- Pure HTML/CSS/JS — no build step, no dependencies to install
- [PDF.js](https://mozilla.github.io/pdf.js/) for client-side PDF text extraction
- [Claude API](https://docs.anthropic.com) (`claude-sonnet-4-20250514`) for fee section analysis
- Hosted on GitHub Pages

## Local development

Just open `index.html` in a browser — no server needed.

## Deployment

This repo is configured for GitHub Pages. Any push to `main` updates the live site automatically.
