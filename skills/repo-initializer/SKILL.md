---
name: repo-initializer
description: Step-by-step instructions for initializing new software repositories according to global agent standards.
---

# Global Skill: Repository Initializer

Follow this procedure whenever initializing a new repository:

1. **Check Git Status:** If `.git` directory is missing, run `git init`.
2. **Create Standard Packaging (`src/` Layout):** Create `src/pkg_name/` (`main.py`, `controllers/`, `services/`, `repository/`).
3. **Set Up Data Isolation:** Create `data/local/` for local databases and exports.
4. **Set Up Testing (`tests/` Layout):** Create `tests/unit/` and `tests/integration/` with `pytest` compatibility.
5. **Create Hidden Virtual Environment:** Set up `.venv` (`python3 -m venv .venv`).
6. **Create `.gitignore`:** Include `.venv/`, `data/local/*.db`, outputs, and OS metadata.
7. **Create Root `README.md`:** Document setup commands, execution instructions, and component previews.
8. **Initialize `.agents/LOGBOOK.md`:** Create timestamped session progress ledger.
