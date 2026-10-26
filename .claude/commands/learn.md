---
description: Tutor mode. Teach one concept, then check understanding with 2-3 questions
argument-hint: <topic>
---

Teach: **$ARGUMENTS**

Follow CLAUDE.md (identify the user first if you haven't).

1. **Locate it.** Find the concept in `notes/*/*.md` (match the slug or name loosely). Read the relevant materials for detail. If the topic isn't in any notes, check `materials/`. If it isn't there either, say so and offer to teach it marked **[outside materials]**.

2. **Check prerequisites.** If the concept map shows a prerequisite that is `weak` or not `learned` in the user's progress, mention it in one line and offer to cover it first. Let the user decide.

3. **Teach in small turns, waiting for the user between them:**
   - Turn 1: a hook. Plain English with a real-world situation or analogy. What problem does this solve? End with a quick "make sense?" or a prediction question.
   - Turn 2: the technical version. Notation and what each piece means.
   - Turn 3: when to use it vs alternatives, plus a worked example with real numbers.
   - Turn 4: common mistakes, framed as "spot the error" when possible.
   If the user is clearly getting it, compress. If they're lost, slow down.

4. **Check with 2–3 questions,** one at a time, with varied styles (apply it, compare it, spot the error, explain why). At least one must be application, not recall.
   - Right: confirm briefly and add one sharpening detail.
   - Wrong: say directly what's wrong and why, then **re-explain from a different angle** (new analogy, a visual or table, or a smaller number example). Don't repeat the first explanation. Then ask a fresh question on the same point.

5. **Update progress** (CLAUDE.md §7–8): concept attempts/correct/recent/weak/last_seen, `learned = true` if they got at least 2 of 3 (or passed the retry), mistakes, XP (+10 per correct answer, +3 per attempt, +5 for completing the concept), streak, log (`mode: "learn"`).

6. Close with a one-line recap of the key idea, the footer, and a suggested next concept from the concept map.
