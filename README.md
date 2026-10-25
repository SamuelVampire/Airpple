# Airpple ✳

Personal IELTS Writing phrase spelling trainer · Inspired by [Pêche](https://github.com/SamuelVampire/SV.peche).

### [✳ 打开 Airpple / Open Airpple](https://samuelvampire.github.io/Airpple/)

> 使用 GitHub Pages 发布（main 分支 / 根目录）。如果刚启用 Pages，网站可能需要片刻才会显示。

## Features

- Pêche-inspired airy white translucent cards, subtle lime gradients and brat-green accents. The home screen has three raised, Pêche-style shortcut cards. Home and inner panels share subtle translucent frosted-glass surfaces.
- Spelling mode: Chinese prompt → type the complete English phrase; misspellings must be corrected and two correct attempts are required to finish. English (en-GB) browser speech synthesis automatically plays on each question and after a correct answer; Tab replays it. Actual pronunciation depends on installed browser voices; automatic audio may be restricted until the user interacts with the page.
- Keyboard: `S` starts Spelling, `R` opens Review, `L` opens Library from home; during training `Enter` checks and advances on the answer screen, `Space` also advances, `Tab` replays the current phrase and `Esc` returns home.
- A misspelling reveals the correction briefly; it disappears when typing begins again. The same phrase is retried immediately and its two-correct streak resets to 0/2.
- Each spelling card displays its current two-correct-attempt streak: `0/2` → `1/2` → `2/2`, with two small progress dots. Misspelling resets it to `0/2`. Each batch still contains up to 25 phrases, but only five rotate at a time. After a phrase is answered correctly twice it leaves the active window, and the next waiting phrase joins. If four of the five current phrases have passed and the last phrase has had a spelling error, that difficult phrase is carried forward into the next five-phrase window (four following phrases plus the carried phrase), rather than blocking the current group. Existing saved sessions migrate without clearing progress.
- Spelling and Review both use the five-phrase rolling window, within batches of up to 25 phrases. Review mode: due-first batches; successful review increases the interval (roughly 2.2×). A misspelled phrase is due again after roughly 10 minutes once the current review is completed.
- Searchable-by-topic phrase library, without a duplicate free-practice mode.
- Spelling and Review use independent sessions. Switching modes preserves each unfinished batch, including its streaks and current position. Existing v1 session data is migrated where possible.
- Session and review progress saved to the current browser's localStorage.

## Phrase data

Initial dataset: **94 deduplicated phrases** imported and curated from the user's Notion page **作文词组模版（g总结）** (23 October 2026). The source includes eight Task 2 themes plus argumentative patterns, reasons and Task 1 letter phrases. Data lives in `phrases.js` as `window.AIRPPLE_PHRASES`. New writing corrections can be appended in the same structure with `en`, `zh`, `category` and `source` fields. Avoid publishing private essay content without consent.

## Deployment

GitHub Pages：Settings → Pages → Deploy from a branch → `main` → `/(root)`。本项目只使用 `index.html` 和 `phrases.js`，无需构建工具或 Vercel。

学习进度保存在当前浏览器的 localStorage，不会自动在不同设备之间同步；清理浏览器网站数据可能删除进度。
