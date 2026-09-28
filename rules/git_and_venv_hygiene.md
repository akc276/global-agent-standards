# Global Agent Rule: Git & Virtual Environment Hygiene

> **Scope:** Generic User Standard (Portable to any project)

## Repository Hygiene Rules
1. **Hidden Virtual Environment:** Always use `.venv` (hidden folder) for Python virtual environments (`./.venv/bin/python`).
2. **Strict `.gitignore`:** Keep `.venv/`, runtime database files (`*.db`, `*.sqlite`), temporary output directories, OS metadata (`.DS_Store`), and environment secrets out of version control.
3. **Local Database Auto-Initialization:** If a runtime database is ignored in `.gitignore`, agents must automatically invoke an initialization routine on startup to create tables if missing.
