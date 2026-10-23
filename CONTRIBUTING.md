# Contributing

Thanks for helping make this a better Dart tutor. Every change to `main` is reviewed and merged by the maintainer, [@priyanshusingh-in](https://github.com/priyanshusingh-in).

## Good things to contribute

- **Wrong or outdated Dart facts.** Dart moves fast; link the exact [dart.dev](https://dart.dev) page that shows the correct behaviour.
- **Better teaching.** Clearer explanations, analogies, exercises or misconception checks in `dart-mastery-tutor/`.
- **Curriculum, DSA and stack content.** Gaps or outdated advice in `references/roadmap.md`, `dsa-track.md`, `development-tracks.md` or `interview-track.md`. For stack content (Flutter, Serverpod, Dart Frog, Jaspr and so on), link the current official docs and say which version you checked.
- **New stacks or DSA patterns.** Open an issue first to agree on scope.
- **Behaviour bugs.** The tutor ignores a command, breaks the one-question-at-a-time rule, or hands out solutions too early.

## How to contribute

1. Open an issue first for anything bigger than a typo, so we can agree on the direction.
2. Fork the repo and create a branch from `main`.
3. Edit files under `dart-mastery-tutor/` (the skill itself). `README.md` and `assets/` are the project page.
4. Open a pull request and fill in the template. Explain what changed and why.

## Guidelines for the skill files

- Keep `SKILL.md` focused. Detailed material belongs in `references/`, which the skill reads only when needed.
- Keep the `name` in the `SKILL.md` frontmatter equal to the folder name (`dart-mastery-tutor`).
- Teach modern Dart 3.x with sound null safety. Cite a source for any non-obvious claim.
- Keep the tutor honest and Socratic: ask before telling, never flatter, earn ratings with evidence.
- Test your change: load the modified skill in Claude and run the commands it affects (for example the onboarding, `/review` and `/card`). Mention what you tried in the PR.

## License

By contributing you agree your work is released under the [MIT License](LICENSE).
