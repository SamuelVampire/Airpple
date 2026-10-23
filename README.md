# Airpple ✳

Personal IELTS Writing phrase spelling trainer · Inspired by [Pêche](https://github.com/SamuelVampire/SV.peche).

### [✳ 打开 Airpple / Open Airpple](https://samuelvampire.github.io/Airpple/)

> 使用 GitHub Pages 发布（main 分支 / 根目录）。如果刚启用 Pages，网站可能需要片刻才会显示。

## Features

- Pêche-inspired mint-to-turquoise gradient, frosted translucent cards, mobile-friendly UI.
- Spelling mode: Chinese prompt → type the complete English phrase; misspellings must be corrected and two correct attempts are required to finish. English (en-GB) browser speech synthesis automatically plays on each question and after a correct answer; Tab replays it. Actual pronunciation depends on installed browser voices; automatic audio may be restricted until the user interacts with the page.\n- Keyboard: `S` starts Spelling, `R` opens Review, `L` opens Library from home; during training `Enter` checks and advances on the answer screen, `Space` also advances, `Tab` replays the current phrase and `Esc` returns home.\n- A misspelling reveals the correction briefly; it disappears when typing begins again.
- Review mode: due-first batches up to 25 phrases; successful review increases the interval (roughly 2.2×). A misspelled phrase is due again after roughly 10 minutes once the current review is completed.
- Free practice and searchable-by-topic library selector.
- Spelling, Review and Free Practice use independent sessions. Switching modes preserves each unfinished batch, including its streaks and current position. Existing v1 session data is migrated where possible.\n- Session and review progress saved to the current browser's localStorage.

## Phrase data

Initial dataset: **94 deduplicated phrases** imported and curated from the user's Notion page **作文词组模版（g总结）** (23 October 2026). The source includes eight Task 2 themes plus argumentative patterns, reasons and Task 1 letter phrases. Data lives in `phrases.js` as `window.AIRPPLE_PHRASES`. New writing corrections can be appended in the same structure with `en`, `zh`, `category` and `source` fields. Avoid publishing private essay content without consent.

## Deployment

GitHub Pages：Settings → Pages → Deploy from a branch → `main` → `/(root)`。本项目只使用 `index.html` 和 `phrases.js`，无需构建工具或 Vercel。

学习进度保存在当前浏览器的 localStorage，不会自动在不同设备之间同步；清理浏览器网站数据可能删除进度。
