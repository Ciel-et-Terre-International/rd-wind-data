
# Contributing Guide – WindDatas

Thank you for your interest in WindDatas! While this is a personal project for now, it is designed to be extensible and collaborative. Here are some rules and best practices to contribute effectively.

---

## Prerequisites

- Python 3.9 or later
- Conda environment based on `environment.yml`
- Recommended knowledge: weather APIs, data processing, statistics, Git

---

## Setting Up the Project

```bash
git clone git@github.com:AdrienSalicis/WindDatas.git
cd WindDatas
conda env create -f environment.yml
conda activate winddatas
```

---

## Branching Strategy

- `main`: stable branch, validated version
- `dev`: main development branch
- `feature/<name>`: new features
- `bugfix/<name>`: bug fixes

---

## Commit Message Convention

Use clear and structured messages:

- `feat:` for new features
- `fix:` for bug fixes
- `refactor:` for code restructuring (no functional change)
- `test:` for adding or modifying tests
- `docs:` for documentation updates

Examples:

```bash
git commit -m "feat: add MERRA-2 fetcher"
git commit -m "fix: correct NOAA wind direction parsing"
```

---

## Running Tests

Before pushing your code, always run the tests:

```bash
python -m unittest discover -s tests
```

---

## Suggestions & Issues

- Use **GitHub Issues** to report problems or suggest improvements.
- Every **Pull Request** must:
  - Target the `dev` branch
  - Include appropriate comments
  - Pass all tests

---

## Contact

Author: Adrien Salicis  
Email: adrien.salicis@cieletterre.net  
Organization: Ciel & Terre International

---

Thank you for contributing 🙌
