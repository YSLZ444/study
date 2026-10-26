---
description: Timed-style mixed exam across one or more units, graded at the end
argument-hint: <unit> [unit ...] [minutes]
---

Mock exam on: **$ARGUMENTS** (a trailing number = time limit in minutes; default 30 minutes and about 12 questions).

Follow CLAUDE.md (identify the user first if you haven't).

1. **Build the paper** from the notes of each unit listed (match loosely; "all" = every ingested unit). Mix:
   - about 40% multiple choice (misconception distractors)
   - about 30% short answer or explain-why
   - about 20% calculation problems with real numbers
   - about 10% scenario: pick the method and justify it
   Spread across units and concepts, with a slight weight toward weak concepts but mostly representative of the materials' emphasis. Assign marks per question (MCQ 1, short 2, calc 3–4, scenario 3).

2. **Start the clock:** record the start with `date +%s`, state the time limit and total marks, and present the questions **one at a time** as `Q4/12 · [3 marks]`.
   - **No feedback during the exam.** Just log the answer and move on. If they ask "was that right?", say "Results at the end."
   - Every 4 questions, show the time used (via `date +%s`).
   - "skip" is allowed. They can come back to skipped questions at the end.
   - If time runs out, say so, but let them finish the current question; mark it as overtime.

3. **Grade at the end:**
   - A table: Q · concept · marks earned/available · ✅/❌/partial.
   - Total, percentage, and time taken.
   - For each wrong or partial answer: the correct answer and a 1–2 line why.
   - A per-unit and per-concept breakdown, and the 3 concepts to fix first.

4. **Update progress once at the end** (save answers in your context as you go): concept stats for every question, weak flags, mistakes, XP (+10 per fully correct, +5 partial, +3 attempt, +20 for finishing a full exam), streak, log (`mode: "exam"`, scope = units, score = marks and %). Footer.
