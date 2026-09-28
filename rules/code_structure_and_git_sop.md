# Global Agent Rule: Modular Packaging, Testing & Git Initialization SOP

> **Scope:** Generic User Standard (Portable to any project)

## 1. Enterprise Packaging Directory Layout (`src/` Layout)
Structure every project using a modular Clean Architecture / MVC packaging layout:
```text
project-name/
├── src/
│   └── package_name/
│       ├── main.py                     # Main application entrypoint
│       ├── controllers/                # API / CLI controllers & handlers
│       ├── services/                   # Core business logic & domain services
│       └── repository/                 # Data access layer & database persistence
├── tests/
│   ├── unit/                           # Unit tests per service/repository
│   └── integration/                    # End-to-end integration flows
├── data/
│   └── local/                          # Local databases (*.db), caches & exports (outside src/)
├── pyproject.toml / setup.py           # Editable package configuration (eliminates IDE import warnings)
├── .venv/                              # Hidden virtual environment
├── .gitignore
├── requirements.txt
└── README.md
```

## 2. Mandatory Testing Standard (`pytest`)
- For Python projects, default to **`pytest`** as the standard test runner (`./.venv/bin/pytest tests`).
- For any component written in `src/`, there MUST be corresponding test files under `tests/unit/` and `tests/integration/`.
- Test execution commands must be documented in `README.md` (e.g. `./.venv/bin/pytest tests`).

## 3. Pre-Completion Quality & IDE Hygiene Checks
Before completing any solution turn:
1. **Check for IDE / Linter Errors:** Verify there are no unhandled import errors, syntax issues, or static typing warnings in entrypoints (`app.py`, `mcp_server.py`, `main.py`).
2. **Zero Hardcoded Machine/User Paths:** Verify there are NO absolute user paths (e.g. `/Users/username/...`, `/home/...`) or environment secrets in committed files or documentation. Always use portable relative paths.

## 4. Major Tech & Framework Transition Protocol
- Whenever encountering a major library change, API interaction change, or programming language transition (e.g. Python -> TypeScript/Go):
  - **STOP & ASK THE USER** if a new testing framework or tool is needed.
  - Suggest 2–3 modern options tailored to the target tech stack.

## 5. Automatic Git Repository Initialization
- When initializing or starting any new project, check for `.git`.
- If `.git` does not exist, automatically execute `git init` and create `.gitignore`.
