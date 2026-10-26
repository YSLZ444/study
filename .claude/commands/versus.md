---
description: Head-to-head. Both people answer the same question set; compare scores
argument-hint: "[unit] [number of questions] | results"
---

Versus mode. Arguments: **$ARGUMENTS** (default: all ingested units, 10 questions).

Follow CLAUDE.md (identify the user first if you haven't).

Challenges live in `progress/versus/<YYYY-MM-DD>-<slug>.json` so both people answer **exactly the same questions**, either in the same sitting (hot-seat) or asynchronously via git.

```json
{
  "id": "2026-10-26-unit2",
  "created_by": "zaeem",
  "created": "2026-10-26",
  "scope": ["stats/unit2-hypothesis-testing"],
  "questions": [
    { "n": 1, "concept": "stats/unit2-hypothesis-testing/p-value", "type": "mcq",
      "question": "...", "options": ["A ...", "B ...", "C ...", "D ..."], "answer": "B", "explanation": "..." }
  ],
  "results": {
    "zaeem": { "date": "2026-10-26", "answers": ["B", "..."], "score": 7, "out_of": 10, "seconds": 412 }
  }
}
```

**Flow**

1. Run `git pull --rebase --autostash` first (if a remote exists) to pick up the friend's challenges.
2. If the argument is `results`, skip to step 5 for the latest challenge.
3. Look in `progress/versus/` for an open challenge that the current user **hasn't** answered yet.
   - **One exists:** say "<friend> challenged you on <scope>. Their score is hidden until you finish." Run it.
   - **None:** create a new challenge. Mix MCQ, short answer and one calculation, spread across concepts, with **equal difficulty for both people** (don't weight toward either person's weak spots). Save the file *before* asking question 1.
4. **Run it:** one question at a time, timing with `date +%s`. **No feedback until the end** (so it stays fair and can't be spoiled). Then grade, show the score, and give the correct answers with short explanations. Save their entry under `results`. Update their own progress file as usual (concept stats, mistakes, XP: +10 per correct, +3 per attempt, +15 for completing a versus; log `mode: "versus"`).
5. **Compare** (only if both have results):
   - Head-to-head: score and time for each, and the winner (time breaks a tie).
   - A per-question grid showing who got what (✅/❌), and the questions *both* missed (worth a `/learn`).
   - A season view from both progress files (read-only for the other person): total XP, level, streak, overall accuracy, and versus wins/losses across all `progress/versus/*.json`.
   - Keep the trash talk light and short.
   If the friend hasn't played yet, say so and suggest committing and pushing so they can.
6. Offer to sync: `git add progress/versus/ progress/<name>.json && git commit -m "<name>: versus <id>" && git pull --rebase && git push`.

Never edit the other person's progress file, and never change their `results` entry.
