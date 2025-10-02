# Contributing to DevStandup

Welcome! 🎉 We love contributions from the community. This document guides you through contributing to DevStandup, whether you're fixing bugs, proposing features, improving docs, or just getting started.

## Table of Contents

- [Getting Started](#getting-started)
- [How to Contribute](#how-to-contribute)
- [Issue Tracking](#issue-tracking)
- [Pull Request Guidelines](#pull-request-guidelines)
- [Code Style](#code-style)
- [Beginner Friendly](#beginner-friendly)
- [Labels & Hacktoberfest](#labels--hacktoberfest)
- [Community Standards](#community-standards)
- [Contact & Support](#contact--support)

---

## Getting Started

1. **Fork the repository** and clone your fork:
   ```sh
   git clone https://github.com/<your-username>/devstandup.git
   ```
2. **Install Go** (see [Go installation guide](https://go.dev/doc/install)).
3. **Install dependencies**:
   ```sh
   go mod tidy
   ```
4. **Run tests** to verify setup:
   ```sh
   go test ./...
   ```

---

## How to Contribute

- Search [issues](https://github.com/indiana91/devstandup/issues) for work that interests you. Issues labeled `good first issue` are great for beginners.
- If your contribution is minor (typo, small doc fix), feel free to send a pull request (PR) directly.
- For significant changes, open an issue first to discuss your idea.
- For bug fixes, describe the problem and steps to reproduce.
- For new features, provide motivation and implementation plan if possible.

---

## Issue Tracking

- **Labels:** We use labels for difficulty (`beginner`, `intermediate`, `advanced`), type (`bug`, `enhancement`, `documentation`, etc.), and `hacktoberfest`.
- **Templates:** Use issue templates when available.
- **Link Related Issues:** If your PR or issue relates to others, mention them using `#<issue-number>`.

---

## Pull Request Guidelines

- Fork and create a feature branch (`feature/<your-feature>`, `fix/<your-fix>`, etc.).
- Write clear commit messages using [Conventional Commits](https://www.conventionalcommits.org/en/v1.0.0/) (e.g., `feat: add new theme support`).
- Keep PRs focused and concise.
- Ensure your code passes all tests and linting.
- Link issues your PR solves (e.g., `Closes #123`).
- Add tests for new features or bug fixes.
- Document new APIs or commands in README.md.

---

## Code Style

- Follow Go best practices. Run `gofmt` and `golint` before committing.
- Write clear, maintainable code.
- Use table-driven tests for Go code.
- Place new files in proper directories (e.g., `internal/ui/`, `examples/`).

---

## Beginner Friendly

- Issues labeled `good first issue` and `beginner` are great to start with.
- Don't hesitate to ask questions! We welcome new contributors.

---

## Labels & Hacktoberfest

- We use the `hacktoberfest` label for eligible PRs and issues.
- Issues are labeled by difficulty and type to help you choose.
- Please respect the contribution guidelines for Hacktoberfest.

---

## Community Standards

- Be respectful, inclusive, and welcoming.
- Use clear and constructive language.
- Report abusive behavior or spam to maintainers.

---

## Contact & Support

- For help, open a [discussion](https://github.com/indiana91/devstandup/discussions) or join our community chat (if available).
- For security issues, please email the maintainers directly.

---

Thank you for contributing! 🚀
