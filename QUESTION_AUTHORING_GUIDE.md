# Question bank authoring guide — Naches Knowledge Showdown

The question bank is stored entirely in `questions.json`, separate from UI and game logic. To grow the library, **do not edit `app.js`** unless you are changing the game mechanics.

## Schema

The root JSON object has a `version`, `sourceNote`, and `questions` array.

Each question has:
- `id`: globally unique stable string; never recycle an ID for a changed question.
- `band`: `middle` (grades 5–8) or `high` (grades 9–12).
- `category`: must exactly match a category listed in `app.js` under `CATS`.
- `tier`: integer from 1 (100 points) through 5 (500 points).
- `clue`: a single clear question or clue.
- `answer`: exactly one defensible best answer, written as it should appear.
- `wrong`: exactly 3 plausible, distinct incorrect alternatives, none of which satisfies the literal question.
- `why`: a concise explanation of the answer or calculation; this is shown only after the point round has fully resolved.

Example:

```json
{
  "id": "middle-new-science-3-a",
  "band": "middle",
  "category": "Science Lab",
  "tier": 3,
  "clue": "Which part of the cell contains most genetic material in a eukaryote?",
  "answer": "Nucleus",
  "wrong": ["Cell wall", "Ribosome", "Cytoplasm only"],
  "why": "The nucleus holds most of a eukaryotic cell's DNA."
}
```

## Recommended expansion plan

1. Add 3–10 more questions **per category per tier**, not just to one category. This reduces repeats evenly.
2. Add PE/health, Washington geography, music, financial literacy, coding, agriculture, environmental science, and local-history categories as additional choices in the grade band. Update the `CATS` array in `app.js` and enter 3+ questions for each of its five tiers. The display lets players choose six categories at a time.
3. For higher grade levels, use interpretation and reasoning (graphs, calculations, causal evidence, source credibility) instead of just more obscure trivia.
4. Keep answers short so students can read them rapidly on a Chromebook or shared screen.
5. Verify all four displayed choices for ambiguity. Avoid time-sensitive facts (e.g., current elected officials), speculative or culturally biased questions, and unverified local claims.
6. Check numerical questions independently and ensure only one complete answer is correct. Indicate rounding and units when appropriate.
7. Use attribution and appropriate licensing if adapting any external questions. Current 195 items are original supplemental classroom prompts, not copies of televised trivia questions.
8. On GitHub, replace **only `questions.json`** to add content. Existing seen history is tied to stable question IDs, so adding IDs remains backward compatible.

## Curriculum notes

Washington State's standards identify subject-area learning expectations. These original questions are broad enrichment and review prompts, **not individually standards-tagged**. Teacher review, a standard-by-standard crosswalk, assessment validity, and grade-specific piloting remain future work.
