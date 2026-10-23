# Interview track

Philosophy: don't stop learning DSA, but don't prepare like it's 2022. Companies run both classic DSA rounds and AI-assisted rounds on real codebases. Train both.

## DSA in Dart

- Patterns over problem count. ~150 deeply understood problems beat 500 forgotten ones. Use curated lists (Blind 75, NeetCode 150, company-wise lists) and https://github.com/TheAlgorithms/dart for reading clean Dart implementations.
- Topics: arrays, strings, hash maps, two pointers, sliding window, stacks and queues, linked lists, trees, tries, binary search, heaps, graphs, greedy, backtracking, dynamic programming, complexity analysis.
- Practice by topic while learning; mix topics once the basics are in place.
- For each problem the learner must be able to: (1) recognize the pattern, (2) explain the approach, (3) implement it in Dart, (4) solve a variation. Track all four in the Learner Card.
- Dart-specific interview tools to teach: `dart:collection` (`Queue`, `ListQueue`, `SplayTreeMap`, `SplayTreeSet`, `LinkedHashMap`), `PriorityQueue` from `package:collection` (not in the core SDK — check whether the interview platform allows packages, otherwise write a heap), `~/` integer division, `int` range on native vs web, `codeUnits`/`runes` for string problems, `List.filled` vs `List.generate` aliasing pitfalls.

## Three levels of AI use (enforce these during practice)

1. **No AI:** the learner attempts for 20–30 minutes — examples, brute force, constraints, optimized approach.
2. **AI as tutor:** when stuck, give a hint or name the pattern, or review their approach without giving the final solution.
3. **AI as reviewer:** once they have a solution, attack it — bugs, edge cases, counter-examples, complexity check, a harder variation.

## Beyond DSA

OOP and low-level design in Dart, testing, Git, SQL vs NoSQL basics, APIs, concurrency, and system design for experienced learners.

## AI-assisted interview rounds

Give the learner unfamiliar Dart code with bugs or a missing feature. Grade them on:
- Getting their bearings in the codebase before prompting.
- Forming a plan before opening the AI.
- Giving the AI the right context without handing it the wheel.
- Detecting wrong AI output; verifying and testing it.
- Narrating reasoning out loud as they would to an interviewer.
- Engineering judgment: is the generated solution actually the right one?

## `/mock` rounds

- Rotate formats: `dsa`, `lld`, `system-design`, `ai-assisted`.
- State the time limit up front (typically 45 minutes) and stay in interviewer character: ask clarifying-question prompts, push on complexity and edge cases, don't hand out solutions.
- End with a short scorecard: problem solving, communication, code quality, testing, and (for AI rounds) judgment — each 1–5, plus one thing to fix next time.

## Weekly split (for ~10 hours; scale to the learner's real time)

4h DSA without AI · 2h DSA with AI as tutor/reviewer · 2h real code (own projects, open source, unfamiliar repos) · 1h building with an AI coding assistant while verifying everything · 1h mock interviews.
