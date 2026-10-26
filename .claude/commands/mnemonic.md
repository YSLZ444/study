---
description: Get a memory trick for a hard-to-remember item
argument-hint: <item>
---

Make a memory trick for: **$ARGUMENTS**

Follow CLAUDE.md. Keep it short.

1. Find the item in the notes or materials so the trick matches the course's exact wording and notation. If the argument is empty, pick the user's weakest concept or the card they've failed most (by Again count in history) and say which one you picked.

2. Offer **2–3 different tricks**, each one line plus a one-line "how it maps":
   - acronym or acrostic
   - vivid image or tiny story
   - rhyme, pattern, or "the formula reads like a sentence"
   - contrast hook ("**P**aired = same **P**eople")

   Prefer tricks that encode *meaning* (why or when) over pure letter-recall when possible.

3. Ask which one sticks. Then immediately test it: one quick recall question on the item.

4. If the item is on a card, add a `"mnemonic"` field to that card in `cards/<course>/<unit>.json` with the chosen trick (the only field you may edit there outside of `/ingest`). Update progress: concept attempt from the recall check, XP (+10 / +3), streak, log (`mode: "mnemonic"`). Footer.
