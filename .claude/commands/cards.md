---
description: Review today's due flashcards one at a time with SM-2 scheduling
argument-hint: "[course or unit (optional)]"
---

Run a flashcard review. Optional filter: **$ARGUMENTS**

Follow CLAUDE.md §4–§5 (identify the user first if you haven't).

1. **Build the queue.** Get today's date (CLAUDE.md §1b). Load all `cards/**/*.json` (filtered by the argument if one was given) and the user's `progress/<name>.json`.
   - Due: the person's card state has `due <= today`.
   - New: card not in the person's `cards` map. Take up to `10 - today.new_cards_seen`.
   - Weak boost: put cards whose concept is `weak` first, and add 1–2 not-yet-due cards per weak concept.
   - Order: weak due → other due (most overdue first) → new. Lightly shuffle within each group, and avoid back-to-back cards on the same concept.
   - If the queue is empty, say so, give the date of the next due card, and suggest `/learn` on an unlearned concept or `/practice`.

2. Tell the user the queue size in one line ("14 due, 3 weak-spot cards up first."), then go **one card at a time**:
   - Show `[3/14] · type · concept` and the **front** only.
   - Wait for their answer. If they say "skip" or "idk", treat it as Again.
   - Reveal the **back**, grade with one short line of why ("Good. You nailed the reason, but say *estimated* σ."), and suggest a grade. They can override by typing again/hard/good/easy. Otherwise apply your suggestion.
   - For a wrong answer, add one sentence explaining the misconception, not just the right answer.

3. **Apply SM-2** exactly as in CLAUDE.md §5. Again cards go back into this session's queue (show again after 3+ other cards); their final interval is 1 day.

4. **Update progress after every 3–5 cards** and at the end: card state, concept stats (each card answer counts as a concept attempt; correct = Good or Easy), weak flags, mistakes for Again answers, `today.cards_reviewed` / `new_cards_seen`, XP (+10 for Good/Easy, +3 for Again/Hard), streak, log (`mode: "cards"`). Validate the JSON.

5. Finish with: score (e.g. 11/14 Good+), concepts that wobbled, how many cards are due tomorrow, and the footer.

The user can stop any time ("stop", "done"). Save immediately and show the summary.
