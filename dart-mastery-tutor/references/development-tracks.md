# Development tracks (after Dart mastery)

For the **Dart + Dev** track. The learner picks a primary stack after Dart roadmap Stages 1-4 (async and concurrency) are solid. DSA can run alongside a stack, but teach one primary stack at a time.

## Teaching rule for every stack

These ecosystems change faster than the Dart language. Before teaching any stack:

1. Check the current docs (web search, or the docs MCP if available) and state which package or SDK version you are teaching.
2. Check the stack's status and Dart/Flutter SDK compatibility. Say plainly if it is experimental, community-maintained or slow-moving.
3. Never invent an API. If you are not sure, say so and point to the docs page.
4. Have the learner run the real tools (`dart --version`, `flutter doctor`, the stack's CLI) and paste output when something breaks.

Notes below were checked in October 2026; treat them as a starting point and re-check.

## Choosing a stack (`/stack`)

Ask about the goal, then recommend one stack and one backup with reasons.

| Goal | Start with |
|---|---|
| Mobile, desktop or web apps with a rich UI | Flutter |
| A Flutter app with an all-Dart backend (typed client, ORM, auth, realtime) | Serverpod |
| A small, fast REST API with file-system routing | Dart Frog |
| A modern, strongly typed HTTP server with built-in routing and WebSockets | Relic |
| Understanding the handler/middleware model underneath Dart servers | Shelf |
| Serverless HTTP or event functions on Google Cloud | Functions Framework for Dart |
| Cloud Functions inside a Firebase project, written in Dart | Cloud Functions for Firebase (Dart) |
| Websites in Dart: SSR, static sites, or client-side apps | Jaspr |
| Joining or maintaining an existing AngularDart codebase | AngularDart |
| Typed React components in Dart, or a team already on React | OverReact |
| Command-line tools and scripts | Dart CLI |

If the learner has no strong reason to pick AngularDart or OverReact for new work, say so and suggest Jaspr or Flutter web.

## Shape of every stack track

Four stages, each ending with something the learner builds without AI first, then reviews with AI as reviewer (see `interview-track.md`, levels of AI use):

- **S1 Setup and fundamentals:** install, create a project, run it, the mental model, project structure.
- **S2 Core features:** the stack's main building blocks (routing, widgets, components, endpoints).
- **S3 Data, state and testing:** persistence or state, error handling, tests that prove it works.
- **S4 Ship:** build, configure, deploy, observe, and a capstone project.

Rate a **Stack rating** (0-100, separate from the Dart rating) over five areas from evidence only: core concepts, structure and idioms, data and state, testing, deploy and operations. Record it in the Learner Card. Review items follow the usual Day 1/3/7/14/30 schedule.

Cross-cutting for every stack: Git, project layout, configuration and secrets, logging, error handling, tests, CI, and verifying AI-generated code before trusting it.

## Flutter

Docs: https://docs.flutter.dev. Check `flutter --version` against the Dart version the learner already knows.

- **S1:** `flutter create`, widget tree, `StatelessWidget` vs `StatefulWidget`, `setState`, hot reload, `const` widgets.
- **S2:** layout and the constraints model ("constraints go down, sizes go up"), lists and scrolling, forms, navigation (`Navigator`, then a router package), theming.
- **S3:** state management: start with `setState` and lifting state up, then teach the trade-offs of the common approaches (for example Provider, Riverpod, Bloc) rather than pushing one; async UI (`FutureBuilder`, `StreamBuilder`), HTTP and JSON, local storage, isolates for heavy work, unit, widget and integration tests.
- **S4:** performance and DevTools (rebuilds, jank), platform integration, release builds, store or web deployment.
- **Capstone:** an app with remote data, local persistence, error states and tests.

## Serverpod

Docs: https://docs.serverpod.dev. Full-stack Dart: server, generated client and Flutter app in one workspace.

- **S1:** `serverpod create` produces three packages (`_server`, `_client`, `_flutter`); the code generator and what never to hand-edit (`generated/`).
- **S2:** endpoints are classes extending `Endpoint` with async methods taking a `Session` first; typed return values; data models defined in the server package and generated into the client; streaming endpoints.
- **S3:** database (Postgres), ORM and migrations, caching, authentication, endpoint tests under `test/integration`.
- **S4:** configuration per run mode, deployment (check the docs for current options), logging.
- **Capstone:** a Flutter app with sign-in, a database-backed feature and live updates.

## Dart Frog

Docs: https://dartfrog.vgv.dev (or the dart-frog-dev repository). Minimal backend framework that builds on Shelf.

- **S1:** `dart_frog create`, `dart_frog dev`, the `routes/` directory.
- **S2:** file-system routing (nested and dynamic routes), request and response handling, `_middleware.dart`, `dart_frog new route` and `new middleware`.
- **S3:** dependency injection through middleware and `context.read`, validation, error handling, testing routes with mocks.
- **S4:** `dart_frog build`, Docker, deploying to a container host.
- **Capstone:** a REST API with auth middleware, tests and a deployed container.

## Relic

Docs: https://github.com/serverpod/relic (see its docs site). A newer, Shelf-inspired framework with strongly typed APIs, built-in routing and WebSocket support. Check its maturity and version before recommending it for production.

- **S1:** `RelicApp`, handlers returning `Response`, running the server.
- **S2:** routing with path parameters (`/users/:id`), middleware scoped by path (`app.use('/api', ...)`), typed request and response bodies.
- **S3:** WebSockets, errors, testing handlers.
- **S4:** deployment; migrating a small Shelf app to Relic (the differences are documented: routing syntax, middleware, bodies).
- **Capstone:** a REST plus WebSocket service, ported from Shelf.

## Shelf

Docs: https://pub.dev/packages/shelf. The foundation concepts: handlers, middleware, `Pipeline`, `shelf_router`, `shelf_static`.

- **S1-S2:** write a handler; compose middleware; routing; serving static files.
- **S3:** test handlers directly without starting a server; error and logging middleware.
- **S4:** containerize and deploy.
- **Capstone:** a small API with logging and auth middleware. This makes Dart Frog, Functions Framework and Relic easier to learn.

## Functions Framework for Dart

Docs: https://pub.dev/packages/functions_framework. Portable functions written as Shelf-style handlers with a `@CloudFunction()` annotation; can unmarshal CloudEvents. Community-supported with no SLA, and Google Cloud Functions has no officially supported Dart runtime, so the documented path is a container on Cloud Run (also App Engine and Knative). Say this clearly.

- **S1:** a `@CloudFunction()` handler, run locally, build the Docker image.
- **S2:** HTTP functions, request parsing, typed responses; event (CloudEvent) functions.
- **S3:** testing a function as a plain handler, configuration, error handling.
- **S4:** deploy to Cloud Run, logs, cold starts, cost basics.
- **Capstone:** one HTTP function and one event-driven function, deployed.

## Cloud Functions for Firebase (Dart)

Docs: https://pub.dev/packages/firebase_functions and the Google codelab "Build a full-stack Dart app with Cloud Functions for Firebase". Verified status: experimental; only HTTPS triggers are supported in production, other triggers vary. Setup uses `firebase experiments:enable dartfunctions` then `firebase init functions` and choosing Dart (check the codelab for current steps). `firebase_js_interop` is an older alternative that compiles Dart to JavaScript. Tell the learner the experimental status up front and re-check it.

- **S1:** Firebase project, Firebase CLI, `firebase init functions` with Dart, run in the emulator.
- **S2:** HTTPS functions (`runFunctions`, `onRequest`), request and response handling.
- **S3:** Firestore and the Admin SDK from a function, config and parameters, logging, testing.
- **S4:** deploy, monitor, costs; pair with a Flutter app that calls the function.
- **Capstone:** a Flutter app backed by an HTTPS Dart function and Firestore.

## Jaspr

Docs: https://docs.jaspr.site. Website framework in Dart with a Flutter-like component model for HTML and CSS. Three rendering modes set in `pubspec.yaml` (`jaspr: mode: static | server | client`): static site generation, server-side rendering, or client-only.

- **S1:** the `jaspr` CLI (`create`, `serve`, `build`), components, the three modes and when to use each.
- **S2:** components, HTML and CSS in Dart, `jaspr_router` routes, interactivity.
- **S3:** state, data loading, SEO and pre-rendering, tests.
- **S4:** `jaspr build` output; deploy static or client builds to static hosting, server builds as a Dart server or container.
- **Capstone:** a content site (static mode) or an SSR app with a backend (server mode).

## AngularDart

Docs: https://pub.dev/packages/ngdart. Maintained by the AngularDart Community, not by Google; the latest stable release on pub.dev was published years ago, so check SDK and toolchain compatibility before recommending it for anything new. Best for maintaining existing AngularDart apps.

- **S1:** project setup, `@Component` with selector and template, running the app.
- **S2:** templates and bindings, `@Input` / `@Output`, directives, forms, routing.
- **S3:** dependency injection and providers, services, HTTP, testing components.
- **S4:** production build, upgrading or migrating (point out Jaspr or Flutter web as modern options).
- **Capstone:** a small routed app with a service layer and component tests.

## OverReact

Docs: https://github.com/Workiva/over_react. Typed React components written in Dart. Requires basic React concepts (props, state, hooks, rendering); teach those first if missing.

- **S1:** setup, code generation with `build_runner` (check the docs for the current setup), `UiProps` mixins, the `Dom.div()..prop = value` builder syntax.
- **S2:** function components with `uiFunction` and hooks, class components (`UiComponent2`, `UiStatefulComponent2`), events and children.
- **S3:** OverReact Redux (`ReduxProvider`, `useSelector`, `useDispatch`), testing components.
- **S4:** build, bundle and deploy; interop with JavaScript React libraries.
- **Capstone:** a small app with global state managed through Redux.

## Dart CLI

Docs: https://dart.dev/tutorials/server/cmdline.

- **S1-S2:** `dart create`, `package:args`, `dart:io` (files, stdin, processes), exit codes.
- **S3:** structured output, config files, tests with `package:test`.
- **S4:** `dart compile exe`, packaging, publishing to pub.dev.
- **Capstone:** a useful, tested command-line tool.
