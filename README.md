<div align="center">

<img src="assets/banner.svg" alt="Dart Mastery Tutor: a Claude skill for learning Dart" width="100%">

<br>

[![Latest release](https://img.shields.io/github/v/release/priyanshusingh-in/claude-dart-mastery-tutor?style=for-the-badge&color=0175C2&label=release)](https://github.com/priyanshusingh-in/claude-dart-mastery-tutor/releases/latest)
[![License: MIT](https://img.shields.io/badge/license-MIT-13B9FD?style=for-the-badge)](LICENSE)
[![Claude Skill](https://img.shields.io/badge/Claude-Skill-D97757?style=for-the-badge)](https://docs.claude.com/en/docs/agents-and-tools/agent-skills/overview)
[![Dart 3](https://img.shields.io/badge/Dart-3.x-02569B?style=for-the-badge&logo=dart&logoColor=white)](https://dart.dev)

**Your personal Dart tutor, code reviewer, interview coach and stack mentor, inside Claude.**

[Demo](#-see-it-in-action) ·
[Install](#-install) ·
[Quick start](#-quick-start) ·
[Commands](#-commands) ·
[How it works](#-how-it-works) ·
[Contributing](#-contributing)

</div>

---

## ✨ What you get

| | |
|---|---|
| 🎯 **Diagnoses you first** | 5 quick questions, a 10-question adaptive interview and 1-2 coding tasks, so you start where you actually are. |
| 📚 **Teaches Dart 3 end to end** | Six stages from variables to mastery, plus Flutter, backend and web branches. Every topic links the exact dart.dev page. |
| 🔍 **Reviews your code** | Paste Dart and get a strict senior review: correctness, null safety, Effective Dart, complexity, a `package:test` idea, and a 1-10 score. |
| 📈 **Tracks a 0-100 rating** | 16 skill areas, each rated from evidence in your answers and code. Ratings are earned, never given. |
| 🧠 **Spaced repetition** | Concepts return as quick retrieval quizzes on Day 1, 3, 7, 14 and 30. |
| 🏗️ **Build with a Dart stack** | After Dart mastery, pick Flutter, Serverpod, Dart Frog, Relic, Jaspr and more. Four stages and a capstone project for each. |
| 🧩 **DSA by pattern, in Dart** | 17 patterns with recognition signals, tested Dart templates, a problem ladder per pattern and a hint ladder that never hands you the answer. |
| 💼 **Interview prep in Dart** | A step-by-step problem-solving framework, timed sets, three levels of AI use, and mock rounds including AI-assisted ones. |

---

## 🛤️ Pick your path

On day one the tutor asks about your goal and proposes one of four tracks. You can switch any time with `/track`.

| Track | For you if... | What happens |
|---|---|---|
| 🟦 **Dart** | You want to learn the language (for Flutter, backend or web). | Diagnostic, then six stages from foundations to mastery. DSA is left out of your rating, so you're never penalised for skipping it. |
| 🟩 **Dart + DSA** | You're new to Dart and preparing for coding interviews. | Dart Stages 1-2 first, then DSA stages D1-D5 run alongside the rest of the roadmap. |
| 🟧 **DSA sprint** | You already write Dart and want interview prep now. | Short Dart check, then straight into the DSA stages. Dart pitfalls are taught the moment a problem exposes them, and mock rounds start earlier. |
| 🟪 **Dart + Dev** | You want to build real things: apps, APIs, websites, serverless functions. | Dart Stages 1-4 first, then one primary stack of your choice (see below). Each stack has 4 stages and a capstone. `/stack` helps you pick. |

Dart mastery comes first for everyone who needs it. After that you can add DSA alongside a stack, but the tutor teaches one primary stack at a time. DSA concepts apply in any language, but every template, tool and pitfall the tutor teaches is Dart.

---

## 🎬 See it in action

<div align="center">
<img src="assets/demo.svg" alt="Animated example of a Dart Mastery Tutor session" width="720">
</div>

The tutor asks one question at a time and waits for your answer. It would rather ask than tell.

---

## 📦 Install

Pick the one that matches how you use Claude.

### Claude apps (web and desktop)

1. Download [`dart-mastery-tutor.zip`](https://github.com/priyanshusingh-in/claude-dart-mastery-tutor/releases/latest/download/dart-mastery-tutor.zip) from the latest release.
2. In Claude, open **Settings** and find **Skills** (it may sit under **Capabilities**).
3. Upload the zip and switch the skill on.

> Skills must be available on your Claude plan. If you don't see the option, check Anthropic's [Agent Skills docs](https://docs.claude.com/en/docs/agents-and-tools/agent-skills/overview).

### Claude Code

Personal install (all projects):

```bash
git clone https://github.com/priyanshusingh-in/claude-dart-mastery-tutor.git
mkdir -p ~/.claude/skills
cp -r claude-dart-mastery-tutor/dart-mastery-tutor ~/.claude/skills/
```

<details>
<summary>Windows PowerShell</summary>

```powershell
git clone https://github.com/priyanshusingh-in/claude-dart-mastery-tutor.git
New-Item -ItemType Directory -Force "$HOME\.claude\skills" | Out-Null
Copy-Item -Recurse .\claude-dart-mastery-tutor\dart-mastery-tutor "$HOME\.claude\skills\"
```

</details>

Single project only: copy the `dart-mastery-tutor` folder into `.claude/skills/` inside that project instead.

---

## 🚀 Quick start

Start a new chat and say:

```text
Teach me Dart
```

or **"Start my Dart tutor"**. In Claude Code you can also run `/dart-mastery-tutor`.

It begins with a short diagnostic, then builds your weekly roadmap. Paste Dart code at any time and it switches to code review.

> 💾 **Keep your progress.** Claude doesn't remember between chats on its own. At the end of each session the tutor prints a **Learner Card**. Save it (or run `/card` any time) and paste it at the start of your next chat to pick up exactly where you left off. If your Claude plan has Projects or memory, the card can live there.

---

## 🎮 Commands

Type `/help` in a session for the short list. Full reference:

| Command | What it does |
|---|---|
| `/roadmap` | Build or adjust your weekly roadmap: concepts, practice, milestones, progress checks. |
| `/explain <topic or text>` | Section-by-section plain-language explanation with an example, then 2 questions. |
| `/socratic <concept>` | Starts from a real-world example and guides you with one question at a time. |
| `/feynman <topic>` | You explain it back, the tutor finds the gaps and re-teaches only what you missed. |
| `/sprint <N days> <skill>` | Daily plan: one concept, one example, a 20-minute exercise, a common mistake, a success criterion. Mini-project every 3 days. |
| `/gaps <topic>` | 10 questions from basic to advanced, then a report on what you know and what to study next. |
| `/test <level> <topic>` | Adaptive test with scenarios and "explain why" questions, ending in a score and revision plan. |
| `/flashcards <topic>` | Flashcards, comparisons and misconception checks, added to your review queue. |
| `/review` | Strict senior review of the Dart code you paste. Pasting code with no message does the same. |
| `/hint` | The smallest useful nudge. On DSA problems it climbs a hint ladder: constraint, data structure, pattern, steps in words. |
| `/solution` | Full solution, only after a real attempt. |
| `/track` | Show or switch your track: Dart, Dart + DSA, DSA sprint, or Dart + Dev with a stack. |
| `/stack [goal]` | Not sure which framework? Get one recommendation and a backup, with honest maturity notes. |
| `/build` | Continue your stack track: next lesson, feature or capstone step. You build first, then review. |
| `/dsa` | Continue the DSA track: next pattern, problem set, timed set or re-solve that is due. |
| `/pattern <name>` | Learn one pattern: recognition, brute force, the idea, a Dart template, a problem ladder, teach-back. |
| `/problem [pattern \| easy \| medium \| hard]` | One problem, solved with the framework. No solution until you've really tried. |
| `/drill [patterns]` | Rapid-fire pattern recognition: 8 short statements, name the pattern, idea and complexity. |
| `/mock <dsa \| lld \| system-design \| ai-assisted>` | Mock interview round with a scorecard. |
| `/card` | Print your Learner Card to save and reuse. |
| `/help` | List the commands. |

---

## 🧭 How it works

### The loop

1. **Warm-up:** a short no-notes quiz on review items due today.
2. **Main block:** the next lesson, in whichever mode fits (explain, Socratic, Feynman).
3. **Practice:** an exercise you write and paste back.
4. **Wrap-up:** a 2-line summary, rating changes with reasons, an updated Learner Card, and what's next.

### Ratings

Each of the 16 areas is scored 0-100 from evidence only, in small steps (usually ±2-8 per session). The overall rating maps to a level:

| Overall | Level |
|---|---|
| < 20 | Novice |
| 20-39 | Apprentice |
| 40-59 | Practitioner |
| 60-74 | Advanced |
| 75-89 | Expert |
| 90+ | Master |

Master means you can explain *why* Dart behaves as it does, write idiomatic production-quality code, and teach the concept back clearly. Areas without evidence stay "not assessed" rather than guessed.

### Curriculum

| Stage | Focus | Ends with |
|---|---|---|
| 1. Foundations | Variables, types, control flow, functions, collections, null safety basics | A small interactive CLI app |
| 2. Core language | Classes, mixins, enums, extensions, generics, errors, the Iterable API | A domain model with tests |
| 3. Modern Dart 3 | Records, patterns, sealed classes, class modifiers, extension types, soundness | A parser using sealed classes and pattern matching |
| 4. Async & concurrency | Event loop, Futures, Streams, isolates | A concurrent fetcher with timeouts and retries |
| 5. Professional Dart | pub, tooling, linting, `package:test`, compile targets, interop | A published-quality package |
| 6. Mastery | Reading SDK source, API design, profiling | A non-trivial end-to-end project |

### Development stacks

Pick one after Dart Stage 4. Every stack follows the same four stages: **S1** setup and fundamentals, **S2** core features, **S3** data, state and testing, **S4** ship it. Each ends with a capstone and a separate **Stack rating** on your Learner Card.

| Stack | Best for | Capstone |
|---|---|---|
| **Flutter** | Mobile, desktop and web apps | An app with remote data, local persistence, error states and tests |
| **Serverpod** | Flutter apps with an all-Dart backend (typed client, ORM, auth, realtime) | A Flutter app with sign-in, a database-backed feature and live updates |
| **Dart Frog** | Small, fast REST APIs with file-based routing | A REST API with auth middleware, tests and a deployed container |
| **Relic** | A modern, strongly typed HTTP server with WebSockets | A REST + WebSocket service ported from Shelf |
| **Shelf** | Understanding handlers and middleware under every Dart server | A small API with logging and auth middleware |
| **Functions Framework** | Serverless HTTP and event functions on Google Cloud (via Cloud Run) | One HTTP and one event-driven function, deployed |
| **Cloud Functions for Firebase (Dart)** | Dart functions inside a Firebase project | A Flutter app backed by an HTTPS Dart function and Firestore |
| **Jaspr** | Websites in Dart: static, server-rendered or client-side | A content site or an SSR app with a backend |
| **AngularDart** | Maintaining existing AngularDart apps | A routed app with a service layer and component tests |
| **OverReact** | Typed React components in Dart, for React teams | A small app with Redux state |
| **Dart CLI** | Command-line tools and scripts | A tested, compiled command-line tool |

The tutor checks the current docs before teaching a stack and is upfront about maturity. For example, Cloud Functions for Firebase in Dart is still experimental, Functions Framework is community-supported and deploys to Cloud Run, and AngularDart is community-maintained.

### DSA track

| Stage | Focus |
|---|---|
| D1 Foundations | Big-O, arrays and strings, hash maps, two pointers, sliding window, prefix sums, stacks and queues, binary search |
| D2 Structures | Recursion, linked lists, trees, tries, heaps and top-K, intervals |
| D3 Graphs and search | BFS/DFS and grids, topological sort, union-find, shortest paths, backtracking, greedy |
| D4 DP and advanced | 1D/2D and string DP, knapsack-style DP, monotonic stack, bit manipulation |
| D5 Interview mastery | Mixed timed sets, mock rounds, AI-assisted rounds, weak-pattern repair |

Each stage ends with a gate: the four-step ladder on at least 3 patterns and a timed mixed set. For every problem you must **recognize** the pattern, **explain** the approach, **implement** it in Dart, and **solve a variation**. The tutor tracks all four per pattern on your Learner Card, and patterns and problems come back for a from-scratch re-solve on Day 1, 3, 7, 14 and 30.

Dart-specific traps are taught when they first bite: `removeAt(0)` is O(n), `%` vs `remainder` with negatives, 64-bit `int` on native vs 53-bit on web, `List.filled` aliasing in 2D grids, unstable `List.sort`, and more.

### Interview track

- Three levels of AI use enforced during practice: **no AI**, **AI as tutor**, **AI as reviewer**.
- AI-assisted rounds: you get unfamiliar buggy Dart code and are graded on how you navigate it, plan, verify and judge AI output.
- `/mock` rounds for DSA, low-level design, system design and AI-assisted, each ending in a scorecard.

---

## 🗂️ Repository layout

```text
claude-dart-mastery-tutor/
├── dart-mastery-tutor/        # the skill itself (this folder is what Claude loads)
│   ├── SKILL.md               # tutor behaviour, commands, code review, spaced repetition
│   ├── LICENSE
│   └── references/
│       ├── learner-card.md    # rating system and Learner Card template
│       ├── roadmap.md         # staged curriculum and ecosystem branches
│       ├── development-tracks.md # stack chooser, curriculum and capstone per stack
│       ├── dsa-track.md       # DSA stages, pattern catalog, framework, hint ladder, Dart templates
│       └── interview-track.md # AI-assisted interviews, levels of AI use, mock rounds
├── assets/                    # README banner and demo
├── .github/                   # issue and PR templates, CODEOWNERS
├── CONTRIBUTING.md
├── LICENSE
└── README.md
```

---

## 🤝 Contributing

Found a wrong Dart fact, an outdated feature, or a command that behaves badly? Please [open an issue](https://github.com/priyanshusingh-in/claude-dart-mastery-tutor/issues/new/choose). Pull requests are welcome too: fork the repo, change the files under `dart-mastery-tutor/`, and open a PR describing what you changed and why. Because Dart moves quickly, please link the relevant dart.dev page in your PR.

See [CONTRIBUTING.md](CONTRIBUTING.md) for the full guide. All changes to `main` are reviewed and merged by the maintainer.

---

## 📚 Sources

[dart.dev/language](https://dart.dev/language) · [dart.dev/learn](https://dart.dev/learn) · [Dart cheatsheet](https://dart.dev/resources/dart-cheatsheet) · [Effective Dart](https://dart.dev/effective-dart) · [TheAlgorithms/dart](https://github.com/TheAlgorithms/dart)

## 📄 License

[MIT](LICENSE)

<div align="center">

Made by [Priyanshu Singh](https://github.com/priyanshusingh-in) · If this helps you learn Dart, a ⭐ is appreciated

<sub>Unofficial community project, not affiliated with or endorsed by Google or Anthropic. Dart and the Dart logo are trademarks of Google LLC.</sub>

</div>
