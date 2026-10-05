---
type: home
module: "00"
tags: [concept]
topic: "CND Vault Home"
exam_weight: high
status: done
unresolved: []
---
# CND — Certified Network Defender

> [!info] Mission
> EC-Council CND study vault — generated strictly from the 20 module PDFs. Content: schematic, nothing invented.

## Exam bank
- [[quiz.html]] – unified bank (100 module + 56 external items), offline, shuffled every attempt
- [[Answer-Key]] – one-line justifications, module + topic cited (bank Q001–Q100 + external E/C/D/P/H/F)
- [[Quick-Review]] – numbered review callouts, all modules

## Unresolved collection
```base
filters:
  and:
    - file.inFolder("20-Notes")
    - 'file.ext == "md"'
    - '!unresolved.isEmpty()'
views:
  - type: list
    name: Unresolved
    order:
      - module
      - file.name
```

## Tag taxonomy
`concept · process · threat · tool · protocol · command · crypto · port · policy · bestpractice · exam` + `mod/NN`

## Canvases
```base
filters:
  and:
    - file.inFolder("40-Canvas")
    - 'file.ext == "canvas"'
views:
  - type: list
    name: Canvases
    order:
      - file.name
```
