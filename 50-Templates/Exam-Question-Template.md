---
type: exam
module: "NN"
tags: [exam, mod/NN]
topic: "Module NN — quiz item template (for quiz.html)"
exam_weight: medium
status: draft
unresolved: []
---

# Quiz item template (quiz.html DATA entry)

Questions live in `quiz.html` (`const DATA`), not in markdown. Copy, fill, append to DATA,
then add the matching one-liner to `30-Exam/Answer-Key.md`.

```json
{
  "id": "101",
  "mod": "NN",
  "modname": "Module Name As In Quiz Filter",
  "stem": "Scenario + single-best-answer question? No 'courseware' wording.",
  "opts": ["A) ...", "B) ...", "C) ...", "D) ..."],
  "answer": 0,
  "why": "Key letter + one-line justification (Module NN · Topic). Third-party items: prefix provenance, e.g. [Site ID · published key] or [Site ID · PDF-derived: Mod NN pN]."
}
```

Rules: id unique (`001`–`100` bank, `E/C/D/P/H/F` + number external, `mod: "ext"` for third-party).
No bare `<...>` placeholders outside backticks (they break Obsidian rendering as unclosed HTML).
Optional `"img": "assets/NN-slug.jpg"` — **bare path only**, no description in the value (it is used verbatim as `src`). Pair it with `"cap": "short caption (Mod NN pN)"`, rendered under the image; a missing file falls back to an IMG-NEEDED box.
Optional `"ex": "| col | col |\n|---|---|\n| … | … |"` — a markdown table exhibit (used for printed tables that are legible text, so no crop is needed). Rendered above the options.
