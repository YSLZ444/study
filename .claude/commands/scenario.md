---
description: Get a realistic situation, pick the right method, and justify the choice
argument-hint: <unit> [number of scenarios]
---

Scenario drill on: **$ARGUMENTS** (default 4 scenarios).

Follow CLAUDE.md (identify the user first if you haven't).

The point is **method selection**: knowing *which* tool fits, not just how to use it.

1. From `notes/<course>/<unit>.md`, list the methods and formulas that compete with each other (e.g. paired t vs two-sample t vs chi-square). Prefer weak concepts.

2. For each scenario:
   - Write a short, concrete, realistic situation (a business, a lab, a sports team, a hospital) with the key details needed to choose, plus one or two red herrings. Use real-feeling numbers.
   - Ask: **"Which method would you use, and why? What would make you choose differently?"**
   - Wait for the answer.

3. Grade on three parts:
   - **Choice**: right or wrong.
   - **Justification**: did they name the deciding features (data type, assumptions, sample size, goal)?
   - **Alternative awareness**: do they know what would change the answer?

   Be direct. A right pick with a bad reason gets partial credit, and say so. Then give the model answer in 2–4 lines, including the "if X were different, use Y instead" twist.

4. Optionally, if they chose right, ask them for the first step of applying it.

5. Update progress: concept stats for the correct method's concept (and the one they wrongly picked, if any, as a mistake), XP (+10 for right with a good reason, +5 partial, +3 attempt), streak, log (`mode: "scenario"`). End with a quick decision rule summary table if they missed 2 or more, then the footer.
