---
description: Smart study session. Picks what you need most and rotates modes
argument-hint: "[minutes or focus (optional)]"
---

Run a study session. Optional length or focus: **$ARGUMENTS** (default about 20 minutes).

Follow CLAUDE.md (identify the user first if you haven't).

1. **Diagnose** (silently): today's date, the user's progress, all cards and notes. Count:
   - cards due today (and how many are weak-concept cards)
   - weak concepts
   - concepts in notes that aren't `learned` yet (in concept-map order: prerequisites first)
   - recent mistakes (last 7 days)
   - days since last study, and how far today's XP is from the goal

2. **Plan 3–4 blocks** and show the plan in 2–3 lines ("Plan: 8 due cards → re-learn *pooled variance* (weak) → 2 scenarios → new concept *Welch's t*. Go?"). Priority:
   1. Due cards, if 5 or more are due (cap the block at about 15 cards).
   2. Weak concepts: a short `/learn`-style re-teach from a *new angle*, or `/practice`.
   3. Unlearned concepts: `/learn` the next one in the concept map.
   4. Consolidation: `/scenario`, `/teachback`, or a mini `/quiz` on recent material.

   **Rotate modes.** Never run two blocks of the same mode back to back, and don't reuse the dominant mode from the last session in the `log`. Finish on something they're likely to get right.

3. Run each block following the rules of its command file in `.claude/commands/` (cards.md, learn.md, practice.md, etc.), but keep each block compact. Between blocks, give a one-line transition with the running XP.

4. Save progress after each block (log each block with its own mode, plus one `mode: "session"` entry at the end).

5. Wrap up with: what they did, the one thing that improved, the one thing still weak, what's due tomorrow, and the footer. Offer to git-sync their progress file.

The user can say "skip", "harder", "easier", or "switch" at any time. Adapt immediately.
