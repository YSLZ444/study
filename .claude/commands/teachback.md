---
description: Explain a concept in your own words; the tutor finds the gaps
argument-hint: <concept>
---

Teach-back on: **$ARGUMENTS**

Follow CLAUDE.md (identify the user first if you haven't).

1. Find the concept in `notes/` and the materials. Privately build a checklist of what a complete explanation needs: what it is, why it exists, what the pieces mean, when to use it vs alternatives, an example, and the common traps.

2. Prompt: "Explain **<concept>** to me like I'm a classmate who missed the lecture. Include why it exists and when you'd use it." Don't hint.

3. When they answer, give feedback in this shape (keep it tight):
   - **Solid:** what they got right (1–2 bullets).
   - **Gaps:** checklist items they missed.
   - **Wrong:** anything incorrect, stated directly with the correction.
   - **Fuzzy:** vague wording that hides shaky understanding ("it makes it more accurate": more accurate *how*?).
   - Score: `x/6` checklist items.

4. Probe the biggest gap with one follow-up question. Let them retry that part.

5. Update progress: one concept attempt (correct if 4/6 or better after the probe), weak flag, mistakes for anything wrong, XP (+10 if they pass, +3 otherwise, +5 completion bonus), streak, log (`mode: "teachback"`). Footer.
