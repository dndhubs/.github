# Contributing to {{PACKAGE_NAME}}

Thank you for your interest in contributing to the **DNDHUB Ecosystem**.

This document defines the standard contribution flow for **L0–L7 OSS and gated libraries**. Project-specific details may extend this file, but should not contradict it.

## Code of Conduct

By participating in this project, you agree to abide by the [Code of Conduct](./CODE_OF_CONDUCT.md).

## Before You Start

Before opening a pull request:

1. Read the package README and architecture notes.
2. Confirm the target layer and allowed dependency boundaries.
3. Check open issues, discussions, and roadmap notes to avoid duplicate work.
4. For gated/internal packages, confirm you are authorized to contribute.

## Ways to Contribute

### Report Bugs

Please include:

- package name and version
- runtime environment
- reproduction steps
- expected result
- actual result
- logs or screenshots where helpful

### Suggest Enhancements

Please include:

- a clear problem statement
- the proposed change
- why the change belongs in this package and layer
- any compatibility or migration concerns

### Submit Pull Requests

1. Fork the repository or create a working branch.
2. Branch from `main`.
3. Keep changes focused and scoped.
4. Add or update tests.
5. Update docs when behavior changes.
6. Run lint, type-check, and build before submitting.
7. Open a pull request using the project template.

## Development Expectations

### Layer Discipline

Contributions must respect the layer model and dependency boundaries.

- **L0–L5 OSS libraries** should stay portable and reusable.
- **L6–L7 shared product libraries** may depend on lower layers only.
- Do not introduce cross-layer violations.
- Do not add same-layer imports where the architecture forbids them.
- Do not move higher-layer concerns into lower layers.

### API Stability

For public OSS packages:

- prefer additive changes over breaking changes
- document breaking changes clearly
- preserve existing exports unless the change is intentional and versioned

### Security

- never commit secrets, tokens, credentials, or production data
- do not publish internal-only assets in public packages
- report vulnerabilities using the process in [SECURITY.md](./SECURITY.md)

## Commit Convention

Use Conventional Commits where possible:

- `feat:`
- `fix:`
- `docs:`
- `refactor:`
- `test:`
- `build:`
- `chore:`

Example:

```bash
feat: add browser-safe path normalization helper
```

## Pull Request Checklist

Before requesting review, confirm:

- [ ] The package builds successfully
- [ ] Type checks pass
- [ ] Tests pass
- [ ] Lint passes
- [ ] Exports are intentional and documented
- [ ] No secrets or private assets are included
- [ ] Documentation was updated where necessary
- [ ] Changes respect the layer boundary rules

## Publishing Notes

For packages published to npm:

- verify the package contents with `npm pack --dry-run`
- prefer a strict `files` list in `package.json`
- use `.npmignore` only as a secondary guardrail
- verify that `README`, `LICENSE`, and declaration files are included where needed

## Recognition

Contributors may be recognized in release notes, changelogs, or project documentation.

Thank you for helping improve the DNDHUB Ecosystem.
