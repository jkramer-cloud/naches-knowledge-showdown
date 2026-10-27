# Naches Knowledge Showdown — Classroom Game Show Edition 1.1

A lightweight, same-device quiz game for **two or three teams**, designed for classroom Chromebooks, touchscreens, and GitHub Pages. The game uses its own Naches Valley theme and original questions; it is not an official or licensed *Jeopardy!* game.

## What's new in 1.1

- **Custom buzzer keys:** Each team chooses any letter **A–Z** or digit **0–9** during setup. Duplicate assignments are rejected; the selected key is shown prominently on the buzzer.
- **Input modes:** Keyboard, large touch/click buzzers, or both. Switch modes during a match using **Buzzers** near the top of the board or the control inside the clue dialog. Touch controls use large colored full-width buttons on narrow screens.
- **510 questions** across **21 grade/category combinations**. All 13 existing school-subject categories now have **30 questions each**, twice the previous 15; four new categories for middle school and four for high school each include 15 more questions. The new categories are Pop Culture & Gaming, Music & Entertainment, Slang & Language, and Sports & Recreation.
- **Category mix:** A balanced six-category board selects four academic and two age-relevant categories by default; you can manually choose any six.
- **Answer counts:** Choose **4**, **5** (default), or **6** multiple-choice answers. The timer is 25 / 30 / 35 seconds, respectively. The existing questions retain their original three incorrect answers; additional options are selected from the related category's question bank. The 315 new questions include five authored distractors apiece. Teachers should review supplementary options, particularly for older questions.
- **Sound options:** Separate controls for success/failure sounds, synthesized applause, and an **original** low-volume, slightly cheesy Summit Finale thinking tune. All three are **off by default** for quiet classrooms. Browsers may require user interaction before audio plays.
- **Existing features preserved:** Quick (18 clues) and Full (30 clues), hidden Valley Vault wagers, Summit Finale, local records, seen-question tracking, game resumes, and four visual themes.

## Upload to GitHub

GitHub repository: `naches-knowledge-showdown`

**Upload the following five files directly to the repository root** (not as a ZIP or nested directory):

```
index.html
styles.css
app.js
questions.json
README.md
```

The four browser files are needed for the game. `README.md` documents the repository.

To enable the site, open GitHub **Settings → Pages**, select **Deploy from a branch**, set **main** and **/(root)**, then save. With the repository name above, the expected URL is:

`https://jkramer-cloud.github.io/naches-knowledge-showdown/`

If the URL is already in the Naches Learning Hub, **you do not need to change the Hub**. After the GitHub commit publishes, hard-refresh the game with **Ctrl + Shift + R**.

## How to play

1. Set **2 or 3 teams**, give them names, and select **different buzzer keys**. Letters, digit keys, and the numeric keypad are supported.
2. Select **Keyboard**, **Touch**, or **Both**. For touchscreens, use **Touch** or **Both**. Switch mode any time during the game or during a buzzer question.
3. Choose middle school (grades 5–8) or high school (grades 9–12), 4–6 answer options, Quick or Full, and six categories. The **Balanced** preset chooses two age-specific topics; **Custom** allows any six.
4. Start a match. The active chooser selects a tile. For regular clues, players press their own key or tap their team button to buzz in. The first valid input gets the answer opportunity.
5. Select the best answer before the countdown expires. A correct answer earns points; a wrong answer loses points, and other teams may try to steal.
6. **Valley Vaults** award special wager-based questions to the chooser only, without buzzer competition.
7. After the board or with **Go to finale**, enter each team's private wager and answer the final question individually. Reveal all scores together at the end.
8. Scores and past question exposure are saved only in the current browser. The **Resume unfinished match** control is available after a refresh if local storage remains available.

### Audio options

In the upper-right header, toggle **Effects**, **Applause**, or **Music** separately. No copyrighted television theme music or sound files are included; sounds are synthesized locally using Web Audio. Depending on the browser, sound may only begin after a click/tap.

## Question bank

`questions.json` contains **510** questions (240 middle-school and 270 high-school). For every existing school category and question tier there are six question alternatives; for each added culture category and tier there are three. The question bank and custom game code run without network services once the static files are loaded.

Question structure: `id`, `band` (`middle`/`high`), `category`, `tier` (1–5), `clue`, `answer`, `wrong` (incorrect options), and `why` (brief feedback). See `QUESTION_AUTHORING_GUIDE.md` in the complete package for editing examples.

**Teacher review is required:** This is supplemental original quiz material, not a standards-certified assessment. Check content and answer options before classroom use. Pop culture and slang usage can vary by community or change over time.

## Limitations & privacy

- Same-device game only; no synchronized buzzer hardware, online multiplayer, accounts, or central teacher dashboard.
- Buzzers are processed in the order the browser receives their events. This is not a scientific reaction-time measurement.
- Records use browser `localStorage`; private/incognito browsing, switching devices, or clearing browser data can remove progress.
- An open question does not keep running while the page is closed; the current clue restarts its answering countdown when restored.
- Load from GitHub Pages (or any static web server). Opening the HTML directly as `file://` may prevent `questions.json` from loading.
- Tested programmatically in Chromium with the question bank loaded via an in-memory static-file substitute because this test environment blocks local server navigation. GitHub Pages deployment and physical school-device testing remain to be verified.

## Testing included in the complete ZIP

`test_showdown.py` checks key assignment validation, keyboard and touch buzzing, switching modes, six answers, simulated save/resume, audio toggles, mobile overflow, and Summit Finale transition.

`test_complete.py` simulates **12 entire Quick matches** across two grade bands, 2/3 teams, and 4/5/6 answer choices, then validates **all 510 questions in all three answer modes** for exactly one correct option and no repeated options.
