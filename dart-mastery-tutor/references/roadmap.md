# Roadmap

Adjust pace to the onboarding diagnostic: skip what the learner has proven, drill what they haven't. Each stage ends with a small project and a `/gaps` check before moving on. Link the matching dart.dev page for every topic.

## Stage 1 — Foundations
Variables, `var`/`final`/`const`, built-in types, operators, comments, control flow (loops, branches), functions (positional, named, optional, default params, arrow syntax), lists/sets/maps basics, null safety basics (`?`, `!`, `??`, `?.`), string and number edge cases (`~/`, `int` vs `double`, interpolation).
Project: a small interactive CLI app (like the official dart.dev tutorial).
Sources: https://dart.dev/language, https://dart.dev/learn/tutorial

## Stage 2 — Core language
Classes and constructors (generative, named, factory, const, redirecting, initializer lists, primary constructors on Dart versions that have them), getters/setters, inheritance and `@override`, implicit interfaces, abstract classes, mixins, enums and enhanced enums, extension methods, generics and bounded generics, typedefs, libraries/imports/privacy (`_`), error handling (`Exception` vs `Error`, `rethrow`, `finally`), the Iterable API in depth (lazy vs eager, `map`/`where`/`fold`/`expand`, collection `if`/`for`, spread).
Project: a small domain model with tests (e.g. a library or inventory system).

## Stage 3 — Modern Dart 3
Records, patterns and pattern types, destructuring, `switch` expressions, exhaustiveness checking, `sealed`/`final`/`base`/`interface` class modifiers, extension types, dot shorthands, callable objects. Type system deep dive: soundness, type promotion and why it fails (https://dart.dev/tools/non-promotion-reasons), covariance, `dynamic` vs `Object?`.
Project: a JSON or expression parser modelled with sealed classes and pattern matching.

## Stage 4 — Async and concurrency
Event loop, microtask vs event queue, `Future` and error handling, `async`/`await` pitfalls (unawaited futures, sequential vs parallel `Future.wait`), Streams (single-subscription vs broadcast, `StreamController`, `async*`/`yield`, `await for`, transformers, cancellation), isolates and `Isolate.run`, when concurrency actually helps.
Project: a concurrent file or HTTP fetcher with timeouts, retries and tests.

## Stage 5 — Professional Dart
`pub`, `pubspec.yaml`, semantic versioning and constraints, workspaces, `dart analyze`/`format`/`fix`/`test`/`compile`, lints and `analysis_options.yaml`, `package:test` (unit, async, mocks/fakes), JSON serialization, `dart:io`, `dart:convert`, compile targets (JIT, AOT, JS, Wasm), interop overview (FFI, JS interop), DevTools basics, writing docs, publishing a package.
Project: publish (or prepare to publish) a small, well-tested package.

## Stage 6 — Mastery
Read real Dart source (SDK core libraries, popular packages), consult the language spec on tricky areas, API design (Effective Dart: Design), performance profiling and memory, teach-back sessions (`/feynman`) on hard topics, and one non-trivial end-to-end project.

## Branches (start once the stage they depend on is solid)

Always check current official docs before teaching a branch; these ecosystems change faster than the core language.

- **DSA for interviews** (start after Stage 2, run alongside Stages 3+): see `dsa-track.md` for the stages D1-D5 and `interview-track.md` for AI-assisted rounds and mocks.
- **Development stacks** (start after Stage 4): see `development-tracks.md` for the stack chooser and the four-stage curriculum and capstone of each stack.
  - **Flutter** (from the language up): how Dart shapes Flutter — `const` widgets, immutability, async in UI, isolates for heavy work, state-management trade-offs, testing.
  - **Backend:** Shelf (foundation) → Dart Frog, Relic or Serverpod; Functions Framework for Dart and Cloud Functions for Firebase (Dart) for serverless.
  - **Web:** Jaspr (modern default), AngularDart (existing codebases), OverReact (React teams); `package:web` and JS interop underneath.
  - **Dart CLI** tools.
