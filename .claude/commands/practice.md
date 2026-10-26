---
description: Work problems. You attempt first, then see the step-by-step solution
argument-hint: <unit> [number of problems]
---

Practice problems on: **$ARGUMENTS** (default 3 problems).

Follow CLAUDE.md (identify the user first if you haven't).

1. From the notes and materials, pick formulas and methods to practise. Prefer weak concepts, then ones with low accuracy, then unseen ones. If the materials contain example or exercise problems, model yours on them (same style and difficulty). Don't copy them verbatim unless the user asks.

2. For each problem:
   - Give a realistic problem with concrete numbers. Escalate difficulty: problem 1 is straightforward, the last one has a twist (a missing step, a trap, or a combination of methods).
   - Say "Your turn. Show your working; rough is fine." **Don't give hints unless asked.** If they ask, give the smallest useful hint (e.g. "what's the first thing you need: the SE or the df?").
   - When they answer, compare with the correct solution **step by step**: mark where they went right, where they first went wrong, and why.
   - Then show the clean full solution: numbered steps, each with a short "why this step" note, and the final answer with units.
   - Name the mistake type if there was one (setup / formula choice / algebra / arithmetic / interpretation).

3. Update progress per problem: concept stats, weak flags, mistakes (store the mistake type in `why`), XP (+10 correct, +5 right method but arithmetic slip, +3 attempt), streak, log (`mode: "practice"`).

4. End with: which mistake types showed up, one tip to avoid the most common one, and the footer.
