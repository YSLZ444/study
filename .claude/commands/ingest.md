---
description: Read a unit's materials, write a concept map to notes/, and generate flashcards into cards/
argument-hint: <course> <unit>
---

Ingest course materials for: **$ARGUMENTS** (first word = course, second = unit).

Follow CLAUDE.md. Steps:

1. **Find the files.** List everything in `materials/<course>/<unit>/`. If the folder is missing or empty, say so, show what does exist under `materials/`, and stop.

2. **Read everything.**
   - PDFs: use the Read tool with `pages` (20 pages at a time for big files).
   - Images and slide screenshots: Read them directly.
   - `.md` / `.txt`: read them directly.
   - `.pptx` / `.docx`: extract the text with `python3 -c` using the `zipfile` module (slides: `ppt/slides/slide*.xml`; docs: `word/document.xml`), stripping XML tags. If that fails, ask the user to export to PDF.
   - Note the source file and page or slide for each idea.

3. **Write `notes/<course>/<unit>.md`** with this structure:

   ```markdown
   # <Course>: <Unit>
   _Sources: file1.pdf, file2.pptx · ingested YYYY-MM-DD_

   ## Big picture
   2–4 sentences: what this unit is about and why it matters.

   ## Concepts
   | slug | concept | one-line plain-English meaning | source |
   |---|---|---|---|
   | t-test | t-test | Compares means when σ is unknown | lec5 p.12 |

   ## Concept map
   How the concepts connect (prerequisites, "is a type of", "used instead of when..."), as an indented list or a mermaid `graph TD` block.

   ## Formulas & methods
   For each: the formula (in code or LaTeX), what each symbol means, when to use it vs alternatives, and one-line common mistake.

   ## Likely exam angles
   3–6 bullets: what's most testable, based on emphasis in the materials.

   ## Gaps / unclear bits
   Anything ambiguous in the materials. Mark outside additions **[outside materials]**.
   ```

   Concept slugs are kebab-case and stable. If notes already exist, **update** them and keep existing slugs.

4. **Write `cards/<course>/<unit>.json`** using the schema in CLAUDE.md §4.
   - About 3–5 cards per concept, more for formulas.
   - Type mix: definition 30% or less; the rest spread across why, when-to-use, formula and scenario.
   - Formula cards ask for meaning and use, not just recall ("In s/√n, what happens to the SE if you quadruple n, and why?").
   - Scenario cards: a short realistic situation on the front, and the method plus the reason on the back.
   - Fronts are one question. Backs are short (1–3 sentences) but complete.
   - IDs: `<course>-<unit>-NNN`. If the file already exists, **keep existing cards and IDs** and only append new cards with the next numbers. Edit a card's text only if it was wrong.

5. Validate the JSON with `python3 -m json.tool`.

6. **Report briefly:** number of concepts, number of cards by type, the 3 trickiest-looking concepts, and anything flagged as unclear. Suggest `/learn <first concept>` or `/session` next.

Don't touch any progress file during ingest (ingest earns no XP).
