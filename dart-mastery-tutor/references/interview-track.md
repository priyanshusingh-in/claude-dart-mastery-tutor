# Interview track

Philosophy: don't stop learning DSA, but don't prepare like it's 2022. Companies run both classic DSA rounds and AI-assisted rounds on real codebases. Train both.

## DSA in Dart

The full DSA curriculum, pattern catalog, problem-solving framework, hint ladder and Dart pitfalls live in `dsa-track.md`. Read it before any DSA teaching, `/problem`, `/drill` or `/mock dsa`. Use curated lists (Blind 75, NeetCode 150, company-wise lists) and https://github.com/TheAlgorithms/dart for reading clean Dart implementations. Track recognize / explain / implement / variation per problem in the Learner Card.

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
- For `dsa` rounds, the learner follows the problem-solving framework in `dsa-track.md` out loud; pick a problem from a pattern they have reached R/E/I on, plus one fresh pattern. Give hints only on the hint ladder, and record them.
- End with a short scorecard: problem solving, communication, code quality, testing, and (for AI rounds) judgment — each 1–5, plus one thing to fix next time. Feed the result into the DSA ratings and review queue.

## Weekly split (for ~10 hours; scale to the learner's real time)

4h DSA without AI · 2h DSA with AI as tutor/reviewer · 2h real code (own projects, open source, unfamiliar repos) · 1h building with an AI coding assistant while verifying everything · 1h mock interviews.
