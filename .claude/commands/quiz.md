---
description: Mixed multiple-choice and short-answer quiz on a unit, graded with explanations
argument-hint: <unit> [number of questions]
---

Quiz on: **$ARGUMENTS** (default 8 questions).

Follow CLAUDE.md (identify the user first if you haven't).

1. Load `notes/<course>/<unit>.md` (match the unit loosely) and the user's progress. Build the question set:
   - About 60% multiple choice, 40% short answer.
   - Spread across concepts, weighted toward `weak` concepts and concepts with low accuracy. Include at least one question on a concept they haven't seen yet, if there is one.
   - Vary the style: apply-a-formula with numbers, which-method-fits, spot-the-error, why-does-this-work, predict-what-happens-if.
   - MCQ distractors should be **real misconceptions** (common mistakes from the notes), not filler.
   - Ground questions in the materials. Mark any outside ones **[outside materials]**.

2. Ask **one question at a time**: `Q3/8 · <concept>`. For MCQ, label the options A–D.

3. After each answer, grade immediately:
   - ✅ or ❌, plus 1–3 sentences on *why*: why the right answer is right, and for MCQ, why their pick was tempting but wrong.
   - Partial credit is fine on short answers (say what was missing).

4. Update progress every few questions: concept stats and weak flags, mistakes (with the question, their answer, the correct answer, and why), XP (+10 per correct, +5 per partial, +3 per wrong attempt), streak, log (`mode: "quiz"`, score).

5. End with: score, the concepts that cost them points, one concrete next step (e.g. "`/learn pooled-variance`, since you missed it twice"), and the footer.
