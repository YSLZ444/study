---
description: Show your dashboard. Cards due, streak, accuracy per concept, weak spots, recent mistakes
argument-hint: "[name (optional)]"
---

Show the progress dashboard for: **$ARGUMENTS** (default: the current user; identify them if you haven't).

Read-only. **Do not modify any files and do not award XP.**

Get today's date with `date +%F`. Load the person's progress file plus all `cards/**/*.json` and `notes/**/*.md`. You may compute the numbers with a short `python3 -c` script for accuracy.

Display compactly, in this order:

```
<name> · Lv 3 (412 XP, 88 to Lv 4) · 🔥 5 days (best 9) · today 40/50 XP

Cards: 14 due today (3 weak) · 22 new available · 61 in review · next 7 days: 9 / 4 / 12 / ...

Weak spots
  ⚠ pooled-variance  (stats/unit2)  2/6  33%  last seen 3d ago
  ⚠ type-ii-error    (stats/unit2)  3/7  43%

Concepts (accuracy)
  unit2-hypothesis-testing   ██████░░░░ 62%  9/14 learned
    t-test            8/9   89%
    p-value           5/8   63%
    ...
  Not started: welchs-t, power-analysis

Recent mistakes
  10-24 quiz · p-value: said "probability H0 is true". It's P(data this extreme | H0).
  ...(latest 5)

Last 7 days: M ▇ T ▃ W · T ▇ F ▅ S · S ▂
```

Rules:
- Level progress: the next level needs xp = 50 × level².
- Sort concepts by accuracy within each unit. Show all weak ones and limit the rest to about 8 per unit (summarise the remainder).
- End with **one** recommendation: the single most useful command to run next and why (e.g. "`/cards`: 14 due, and 3 of them are weak spots").
