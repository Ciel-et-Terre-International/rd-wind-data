
# Git Workflow – WindDatas Project

This document outlines the contribution rules, branch structure, and Git best practices to follow in the WindDatas project.

---

## Branch Structure

| Branch         | Purpose                                       |
|----------------|-----------------------------------------------|
| `main`         | Stable, published versions (tagged releases)  |
| `dev`          | Active development, integration of features   |
| `feature/...`  | New specific features                         |
| `bugfix/...`   | Isolated bug fixes                            |
| `docs/...`     | Documentation changes                         |

---

## Commit Convention

Use the following prefixes in your commit messages:

- `feat:` for a new feature
- `fix:` for a bug fix
- `chore:` for minor maintenance tasks (e.g., doc update)
- `refactor:` for code restructuring without functional changes
- `test:` for unit tests or test fixes
- `docs:` for pure documentation updates

Examples:

```bash
git commit -m "feat: add MERRA-2 fetcher"
git commit -m "fix: handle missing dates in Meteostat"
git commit -m "docs: add link to interactive globe"
```

---

## Standard Development Cycle

1. Clone the repository
2. Create a new branch from `dev`:
   ```bash
   git checkout dev
   git checkout -b feature/your-feature-name
   ```
3. Develop and test locally
4. Commit and push your changes:
   ```bash
   git push -u origin feature/your-feature-name
   ```
5. Open a Pull Request targeting `dev`
6. After review, merge into `dev`
7. Merge `dev` into `main` only for tagged release versions

---

## Versioning

We follow semantic versioning:

- `v1.1.0` → new major features
- `v1.1.1` → minor fixes
- `v2.0.0` → breaking changes or structural overhaul

Stable versions are tagged as follows:

```bash
git tag v1.1.0
git push origin v1.1.0
```

---

## Collaborative Work

- Use Issues to report bugs or propose tasks
- Stay aligned with the roadmap
- Always document your contributions clearly
