# Airpple ✳

Personal IELTS Writing phrase spelling trainer · Inspired by [Pêche](https://github.com/SamuelVampire/SV.peche).

### [✳ 打开 Airpple / Open Airpple](https://samuelvampire.github.io/Airpple/)

> 使用 GitHub Pages 发布（main 分支 / 根目录）。如果刚启用 Pages，网站可能需要片刻才会显示。

## Features

- Pêche-inspired airy white translucent cards, subtle lime gradients and brat-green accents. The home screen has three raised, Pêche-style shortcut cards. Home and inner panels share subtle translucent frosted-glass surfaces.
- Spelling mode: Chinese prompt → type the complete English phrase; misspellings must be corrected and two correct attempts are required to finish. English (en-GB) browser speech synthesis automatically plays on each question and after a correct answer; Tab replays it. Actual pronunciation depends on installed browser voices; automatic audio may be restricted until the user interacts with the page.
- Keyboard: `S` starts Spelling, `R` opens Review, `L` opens Library from home; during training `Enter` checks and advances on the answer screen, `Space` also advances, `Tab` replays the current phrase and `Esc` returns home.
- A misspelling reveals the correct phrase and resets the two-correct streak to `0/2`. Press Next to continue; the missed phrase is recycled within the moving five-phrase window instead of blocking on an immediate retry.
- Each spelling card displays its `0/2` → `1/2` → `2/2` streak, with two small progress dots. In both Spelling and Review, at most five phrases stay active in a continuously sliding window within a batch of up to 25. After an item reaches `2/2`, it drops out and the next phrase comes in: `ABCDE → BCDEF → CDEFG` as the front items graduate. Missed phrases move toward the end of the active five and can follow later new phrases; examples include `EFGHB` (B still difficult) and `HIJAB` (A and B still difficult). Unfinished sessions migrate without clearing progress.
- Review mode selects due-first batches; successful review increases the interval (roughly 2.2×). A missed phrase is due again after roughly 10 minutes once the current review is completed.
- Searchable-by-topic phrase library, without a duplicate free-practice mode.
- Spelling and Review use independent sessions. Switching modes preserves each unfinished batch, including its streaks and current position. Existing v1 session data is migrated where possible.
- Session and review progress saved to the current browser's localStorage.

## Phrase data

Initial dataset: **94 deduplicated phrases** imported and curated from the user's Notion page **作文词组模版（g总结）** (23 October 2026). The source includes eight Task 2 themes plus argumentative patterns, reasons and Task 1 letter phrases. Data lives in `phrases.js` as `window.AIRPPLE_PHRASES`. New writing corrections can be appended in the same structure with `en`, `zh`, `category` and `source` fields. Avoid publishing private essay content without consent.

## Deployment

GitHub Pages：Settings → Pages → Deploy from a branch → `main` → `/(root)`。本项目只使用 `index.html` 和 `phrases.js`，无需构建工具或 Vercel。

学习进度保存在当前浏览器的 localStorage，不会自动在不同设备之间同步；清理浏览器网站数据可能删除进度。
