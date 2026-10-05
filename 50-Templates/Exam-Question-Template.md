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
Optional `"img": "assets/NN-slug.png — description"` shows the image, else an IMG-NEEDED box.
