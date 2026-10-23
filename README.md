<div align="center">

<img src="assets/banner.svg" alt="Dart Mastery Tutor: a Claude skill for learning Dart" width="100%">

<br>

[![Latest release](https://img.shields.io/github/v/release/priyanshusingh-in/claude-dart-mastery-tutor?style=for-the-badge&color=0175C2&label=release)](https://github.com/priyanshusingh-in/claude-dart-mastery-tutor/releases/latest)
[![License: MIT](https://img.shields.io/badge/license-MIT-13B9FD?style=for-the-badge)](LICENSE)
[![Claude Skill](https://img.shields.io/badge/Claude-Skill-D97757?style=for-the-badge)](https://docs.claude.com/en/docs/agents-and-tools/agent-skills/overview)
[![Dart 3](https://img.shields.io/badge/Dart-3.x-02569B?style=for-the-badge&logo=dart&logoColor=white)](https://dart.dev)

**Your personal Dart tutor, code reviewer and interview coach, inside Claude.**

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
| 💼 **Interview prep in Dart** | DSA patterns with Dart-specific tools, three levels of AI use, and mock rounds including AI-assisted ones. |

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
| `/hint` | The smallest useful nudge. |
| `/solution` | Full solution, only after a real attempt. |
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

Optional branches once the foundations are solid: **Flutter from the language up**, **DSA for interviews**, **backend** (Shelf, Relic, Dart Frog, Serverpod, Cloud Functions) and **web** (`package:web`, Jaspr, AngularDart, OverReact).

### Interview track

- DSA by pattern, not problem count, with Dart tools like `dart:collection`, `PriorityQueue` from `package:collection`, `~/`, and `List.filled` vs `List.generate` pitfalls.
- Three levels of AI use enforced during practice: **no AI**, **AI as tutor**, **AI as reviewer**.
- AI-assisted rounds: you get unfamiliar buggy Dart code and are graded on how you navigate it, plan, verify and judge AI output.

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
│       └── interview-track.md # DSA in Dart, AI-assisted interviews, mock rounds
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

</div>
