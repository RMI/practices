# Contributing

Thanks for your interest in contributing.

This guide covers how to open issues and pull requests. For local setup, commands, and development workflows, see [`HACKING.md`](./HACKING.md) if your repository includes one.

## The Most Important Rule

Contributors should understand the changes they submit.

If you open a change, you should be able to explain:
- what it does
- why it is correct
- what tradeoffs it introduces
- and how it was tested

Using AI tools is allowed. Submitting AI-generated changes you do not understand is not.

## AI-Assisted Changes

AI assistance does not change quality standards.

- Keep AI-assisted PRs small and focused on a single concern.
- Split large AI-generated output into multiple PRs that can be reviewed independently.
- In your PR description, call out:
  - what AI was used for,
  - what you verified manually,
  - and what tests validate the change.

## How to Contribute

### External Contributors (without write access)

- Fork the repository and branch from the default branch.
- Make your changes in your fork.
- Open a PR from your fork when your change is ready for review.

### Contributors with write access

- Create a branch in this repository.
- Open a PR to the default branch.
- Merge only after required checks and approvals pass.

## Issues

Use issues to report bugs or suggest features.

When possible, include:
- steps to reproduce,
- expected vs actual behavior,
- logs, stack traces, or screenshots,
- environment details (OS, runtime version, dependency versions).

## Pull Request Expectations

Draft PRs are recommended for early feedback.

Mark a PR ready for review once:
- required checks are passing,
- the scope is clear,
- and the description explains what changed and why.

PRs are more likely to be accepted when they:
- stay focused on one concern,
- include tests for behavior changes,
- update docs for user-facing changes,
- and link related issues/tickets when relevant.

Avoid mixing unrelated refactors into feature/fix PRs.

All changes should be submitted via Pull Request.

## Architectural Changes

Architectural changes should be discussed and pre-approved before implementation.

Start with an issue or design discussion that explains:
- the proposed change,
- rationale and alternatives,
- tradeoffs,
- and migration/rollout impact.

## Merge Strategy

Follow this repository's configured merge policy.

If maintainers have not documented one yet, prefer:
- preserving meaningful commit history,
- avoiding force-pushes to shared branches,
- and using the merge method required by branch protection rules.

## Commit and Branch Guidelines

- Prefer Conventional Commits (for example: `feat(api): add resource ownership filter`).
- Keep commit messages clear and specific.
- Use short, descriptive branch names (for example: `docs/add-contributing-guide`, `fix/api-auth-header`).

## Development and Testing

Before opening a PR, run this repository's validation checks from the repository root.

Examples (use what exists in your repo):

```bash
make check
# or
npm test
# or
cargo test
```

If your repo has a `HACKING.md` or equivalent developer guide, follow its package-specific lint/test/format commands.

## Documentation Requirements

Update documentation when behavior changes, including:
- API behavior or endpoints,
- setup and run instructions,
- environment/configuration expectations,
- and user-visible behavior.

## Code of Conduct

Be respectful and constructive. Focus feedback on code and behavior.

If this repository includes one, follow [`CODE_OF_CONDUCT.md`](./CODE_OF_CONDUCT.md).

## Licensing

By contributing, you agree your contributions are licensed under this repository's [license](./LICENSE).

## Repository-Specific Overrides (Optional)

Maintainers may add repository-specific requirements here, for example:
- ticket/issue naming conventions,
- release branch rules,
- deployment approval requirements,
- security review requirements.
