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

**Track decides what counts.** The stack rating is separate from the overall Dart rating and never changes it. On the **Dart** and **Dart + Dev** tracks, "DSA in Dart" is marked "not in scope" and is left out of the overall rating, so learners are never penalised for skipping it. On **Dart + DSA** and **DSA sprint**, it counts and gets extra weight once the learner reaches DSA stage D1. Rate "DSA in Dart" from the pattern matrix below: patterns at R/E/I/V, hints used, timed-set results, and quality of complexity and edge-case reasoning. Problem count is never evidence.

## Template

```
LEARNER CARD — <name> — <date>
Overall Dart rating: __/100   Level: <level>
Track: <Dart | Dart + DSA | DSA sprint | Dart + Dev (<stack>)>
Stage: <Dart stage from roadmap>   DSA stage: <D1-D5 or n/a>   Stack stage: <S1-S4 or n/a>   Sessions: __
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
- DSA in Dart: <0-100 with evidence | not in scope>

Strengths:
Weak spots (top 3, with evidence):
Misconceptions to fix:
Review queue (item → next due date; Dart concepts, patterns and problems to re-solve):

DSA pattern matrix (only on tracks that include DSA; R = recognized, E = explained, I = implemented, V = variation solved):
- <pattern>: R E I V (tick what is earned) — problems done: <names> — hints used: <n>
- ...
Timed sets: <date, problems, result>
Mock rounds: <date, format, scorecard summary>

Stack (only on the Dart + Dev track):
- Stack and version taught: <e.g. Flutter 3.x>   Stage: <S1-S4>
- Stack rating (0-100, separate from the Dart rating): __
  Core concepts: __  Structure and idioms: __  Data and state: __  Testing: __  Deploy and operations: __
- Projects: <built, with date and what was learned>   Capstone: <not started | in progress | done>

Next session plan:
```

Leave an area as "not assessed" rather than guessing a number.
