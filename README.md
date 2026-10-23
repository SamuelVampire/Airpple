# Airpple ✳

Personal IELTS Writing phrase spelling trainer · Inspired by [Pêche](https://github.com/SamuelVampire/SV.peche).

## Open the app

The live URL will be added here once Vercel deployment is verified. **A GitHub repository URL is not the published app URL.**

## Features

- Pêche-inspired mint-to-turquoise gradient, frosted translucent cards, mobile-friendly UI.
- Spelling mode: Chinese prompt → type the complete English phrase; misspellings must be corrected and two correct attempts are required to finish.
- Review mode: due-first batches up to 25 phrases; successful review increases the interval (roughly 2.2×).
- Free practice and searchable-by-topic library selector.
- Session and review progress saved to the current browser's localStorage.

## Phrase data

Initial dataset: **94 deduplicated phrases** imported and curated from the user's Notion page **作文词组模版（g总结）** (23 October 2026). The source includes eight Task 2 themes plus argumentative patterns, reasons and Task 1 letter phrases. Data lives in `phrases.js` as `window.AIRPPLE_PHRASES`. New writing corrections can be appended in the same structure with `en`, `zh`, `category` and `source` fields. Avoid publishing private essay content without consent.

## Deployment

Static site: `index.html` + `phrases.js`, no build command, no framework, no dependencies. In Vercel choose framework **Other**, root directory `./`, build command blank, output directory default/project root. Git integration can deploy pushes to the `main` branch.

Private repository does not automatically mean a private deployment. Browser-local data is not synchronized across devices; clearing site data can erase progress. For cross-device sync, add a database and authentication later.
