# Naches Knowledge Showdown

A lightweight 2–3 player classroom quiz-board game built for GitHub Pages. Original local-themed naming, original questions, original CSS/SVG-style art; no dependency on the Jeopardy! brand or question materials.

## GitHub repo

`naches-knowledge-showdown`

### GitHub description

Naches-themed classroom quiz showdown for 2–3 players, with middle- and high-school questions, buzzer rounds, point wagers, a final challenge, and repeat-aware question tracking.

## Quick start

Upload `index.html`, `styles.css`, `app.js`, and `questions.json` to the repository root and enable Pages (main branch, root). Do not upload the ZIP itself.

Expected URL: `https://jkramer-cloud.github.io/naches-knowledge-showdown/`

### Playing

1. Choose 2 or 3 players, type nicknames or team names, and select grades 5–8 or 9–12.
2. Choose six categories. Middle school currently offers six, high school offers seven (choose six).
3. Choose a full board (30 clues) or quick board (18 clues).
4. The highlighted chooser picks a category and value. Once the clue appears, any player can buzz in with the on-screen button or keyboard 1/2/3.
5. The answering player has 25 seconds to select one of four answers. Correct answers earn the displayed points; incorrect answers deduct those points and allow other players one steal attempt.
6. Two hidden **Valley Vault** tiles let only the chooser wager up to the greater of their nonnegative score and 500 points before seeing the clue.
7. After all tiles are used, or when the teacher chooses to finish early, use **Summit Finale**. Each player privately enters a wager (up to their current nonnegative score), then answers the same final clue. Lock one response at a time so students cannot copy each other. Reveal scores after all contestants answer.
8. A tie receives a shared win and a draw-style closing screen. Finished games update local records.

### Questions and repetition

- `questions.json` has 195 original questions: 90 middle-school and 105 high-school, across 13 category names.
- Each category/point-value position has 3 alternatives.
- When a clue is revealed it is added to **local** seen history for that category/value; unseen alternatives are picked first.
- After all 3 alternatives for a position have been shown, the least recently used question can reappear.
- The game has no network accounts, server database, student identifiers, or content-delivery dependencies.

### Safety and limitations

- This is supplemental classroom content; it is **not an officially aligned or endorsed Washington standards test**. Review questions before class and adjust them for students' actual curricular readiness.
- Shared-device buzzers are *turn-taking controls*, not independently synchronized physical buzzers. The first on-screen or keyboard button event wins the buzz.
- Final round answer secrecy requires students to turn away when it is not their turn.
- LocalStorage saves question history and a suspended match *in that browser*. Switching computers, clearing data, or incognito mode may lose progress. The 'Reset data' button erases local saved records after confirmation.
- There is no central teacher dashboard, remote multiplayer, or real-time hosting.
- No copyrighted television branding, music, sets, or question content is used.
- The game requires a static web server (GitHub Pages works). Opening `index.html` locally as `file://` may block loading `questions.json` for browser-security reasons.

For adding categories and questions, see `QUESTION_AUTHORING_GUIDE.md`.
