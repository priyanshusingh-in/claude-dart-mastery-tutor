# Learner Card and rating system

Rate each area 0–100 using only evidence from the learner's answers and code. Note the evidence briefly. Move ratings in small steps (usually ±2–8 per session); a big jump needs strong evidence such as a correct, idiomatic solution to a hard problem plus a clear explanation.

## Levels

| Overall | Level |
|---|---|
| < 20 | Novice |
| 20–39 | Apprentice |
| 40–59 | Practitioner |
| 60–74 | Advanced |
| 75–89 | Expert |
| 90+ | Master |

"Master" requires being able to explain *why* the language behaves as it does, write idiomatic production-quality code, and teach the concept back clearly.

Overall rating = weighted average of the areas, weighting the areas the current stage depends on most.

## Template

```
LEARNER CARD — <name> — <date>
Overall Dart rating: __/100   Level: <level>
Stage: <stage from roadmap>   Sessions: __
Goal: <goal and timeline>   Weekly time: <hours>

Skill areas (0–100, with short evidence):
- Syntax, variables, operators, control flow:
- Built-in types, strings, numbers:
- Collections & Iterable API:
- Functions, closures, higher-order functions:
- Null safety & type system (promotion, generics, variance):
- OOP: classes, constructors, inheritance, mixins, interfaces:
- Class modifiers, sealed types, enums, extension methods/types:
- Records & patterns:
- Error handling:
- Async: Future, Stream, async*/await for:
- Concurrency: event loop, microtasks, isolates:
- Libraries, packages, pub, tooling (analyze/format/fix/test):
- Testing:
- Idiomatic Dart (Effective Dart):
- Performance, memory, compilation (JIT/AOT/JS/Wasm):
- DSA in Dart:

Strengths:
Weak spots (top 3, with evidence):
Misconceptions to fix:
Review queue (item → next due date):
DSA patterns: recognized / explained / implemented / variation solved
Next session plan:
```

Leave an area as "not assessed" rather than guessing a number.
