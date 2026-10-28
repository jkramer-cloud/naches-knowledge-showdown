# Naches Knowledge Showdown — Classroom Game Show Edition 1.3

A lightweight, same-device quiz game for **two or three teams**, designed for classroom Chromebooks, touchscreens, and GitHub Pages. The game uses its own Naches Valley theme and original questions; it is not an official or licensed *Jeopardy!* game.

## What's new in 1.3 — Social Studies expansion

- **160 new curriculum-themed questions**, bringing the game to **670 questions**.
- Four grade-specific Social Studies banks for **grades 5, 6, 7, and 8** with **eight selectable subtopics per grade** (32 total subtopics).
- Choose **any six of eight** history/civics subtopics for the 30-clue board, or **Shuffle six topics**; quick mode has 18 clues.
- The existing Middle School and High School mixed-subject boards and their selectable categories are preserved.
- Each Social Studies subtopic currently has one authored question at each of the five point levels. This is a **starter question bank**; replays will encounter repeated clues until more variants are added.
- See `SOCIAL_STUDIES_TOPICS.md` for grade-by-grade coverage and content-review guidance.

## Previous release 1.2 — Fair-play question timers

- **Mandatory reading period:** After selecting a clue, the full question appears with buzzers disabled for **7 seconds** by default. The reading countdown cannot be skipped by buzzing early with the keyboard or touch controls.
- **Separate timed buzz window:** After reading, students have **8 seconds** by default to buzz. If no team buzzes, the clue closes with **zero points awarded or deducted**, reveals the correct answer, and returns to the board when you press the button.
- **Short answer clock:** Once a team buzzes, its answer choices appear with **12 seconds** by default. If that player does not answer before time expires, the current wrong-answer point penalty applies; other teams may then attempt a timed steal.
- **Large projector-friendly countdown:** A prominent seconds counter, circular progress ring, progress bar, and changing colors appear **to the right of the question** on desktops and below it on smaller screens.
- **Teacher timing controls:** Choose reading time (3–15 sec), buzz time (4–15 sec), and answer time (5–20 sec) before starting. The board also has a collapsible control to adjust subsequent timers during the match.
- **Valley Vault protection:** Wager clues also display a mandatory reading countdown before the chooser may answer.
- **Save continuity:** Timers use absolute deadlines instead of restarting on every browser refresh. Changing input mode doesn't reset the active timer.

## Features carried over from 1.1

- **Custom buzzer keys:** Each team chooses any letter **A–Z** or digit **0–9** during setup. Duplicate assignments are rejected; the selected key is shown prominently on the buzzer.
- **Input modes:** Keyboard, large touch/click buzzers, or both. Switch modes during a match using **Buzzers** near the top of the board or the control inside the clue dialog. Touch controls use large colored full-width buttons on narrow screens.
- **670 questions total (510 existing + 160 Social Studies)** across **21 grade/category combinations**. All 13 existing school-subject categories now have **30 questions each**, twice the previous 15; four new categories for middle school and four for high school each include 15 more questions. The new categories are Pop Culture & Gaming, Music & Entertainment, Slang & Language, and Sports & Recreation.
- **Category mix:** A balanced six-category board selects four academic and two age-relevant categories by default; you can manually choose any six.
- **Answer counts:** Choose **4**, **5** (default), or **6** multiple-choice answers. Answer clock lengths are configured independently of the number of choices. The existing questions retain their original three incorrect answers; additional options are selected from the related category's question bank. The 315 new questions include five authored distractors apiece. Teachers should review supplementary options, particularly for older questions.
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
3. Choose a mixed-subject Middle School or High School board, or a grade 5–8 Social Studies pack, 4–6 answer options, Quick or Full, and six categories. The **Balanced** preset chooses two age-specific topics; **Custom** allows any six.
4. Start a match. The active chooser selects a tile. Every team reads the full question during a locked countdown (7 seconds by default); attempting to buzz during this stage does nothing. Then a second countdown begins and teams may press their key or tap their button to buzz. If nobody buzzes before the window closes, **nobody scores** and the answer is revealed.
5. The first team that buzzes gets a shorter **answer countdown** (12 seconds by default). Select the best answer before it expires. Correct answers earn points; wrong answers or answer timeouts lose points, and other teams can try to steal within a new timed buzz window.
6. **Valley Vaults** award special wager-based questions to the chooser only. The chooser must read the clue during the same locked reading countdown before answering.
7. After the board or with **Go to finale**, enter each team's private wager and answer the final question individually. Reveal all scores together at the end.
8. Scores and past question exposure are saved only in the current browser. The **Resume unfinished match** control restores the active question and saved timer settings if browser storage remains available. If the original timer has expired during the interruption, the game applies its timeout rule.

### Audio options

In the upper-right header, toggle **Effects**, **Applause**, or **Music** separately. No copyrighted television theme music or sound files are included; sounds are synthesized locally using Web Audio. Depending on the browser, sound may only begin after a click/tap.

## Question bank

`questions.json` contains **670** questions (240 existing middle-school, 270 existing high-school, and 40 questions for each Social Studies grade 5, 6, 7, and 8). For every existing school category and question tier there are six question alternatives; for each added culture category and tier there are three. The question bank and custom game code run without network services once the static files are loaded.

Question structure: `id`, `band` (`middle`/`high`/`ss5`/`ss6`/`ss7`/`ss8`), `category`, `tier` (1–5), `clue`, `answer`, `wrong` (incorrect options), and `why` (brief feedback). See `QUESTION_AUTHORING_GUIDE.md` in the complete package for editing examples.

**Teacher review is required:** This is supplemental original quiz material, not a standards-certified assessment. Check content and answer options before classroom use. Pop culture and slang usage can vary by community or change over time.

## Limitations & privacy

- Same-device game only; no synchronized buzzer hardware, online multiplayer, accounts, or central teacher dashboard.
- Buzzers are processed in the order the browser receives their events. This is not a scientific reaction-time measurement.
- Records use browser `localStorage`; private/incognito browsing, switching devices, or clearing browser data can remove progress.
- An open question retains its absolute countdown deadline. After a reload, an expired phase advances or times out immediately rather than granting extra time.
- Load from GitHub Pages (or any static web server). Opening the HTML directly as `file://` may prevent `questions.json` from loading.
- Tested in Chromium with the question bank and files loaded into an isolated browser page because this test environment blocks local server navigation. The reading lock, no-buzz zero-score outcome, wrong-answer timeout, timed steal, saved timer settings, and mobile width check passed. GitHub Pages deployment and physical school-device testing remain to be verified.

## Verification

The v1.2 build passed JavaScript syntax validation and an interactive Chromium test with the 510-question bank loaded in memory. Checks covered reading lock for both keyboard and touch, no-buzz expiration (zero points), answer timeout and deductions, timed steal rounds, saving/restoring timer settings in an isolated browser test, and a 390px mobile screen with no horizontal scrolling. The actual hosted GitHub Pages page and school Chromebooks still need a final classroom check.
