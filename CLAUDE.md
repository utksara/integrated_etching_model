# CLAUDE.md

Guardrails for AI assistants working on the Integrated Etching Model (IEM). Read `README.md` for the project objective and component list.

## 1. Scope: edit only what you are asked to edit (most important)
- Only create, update, rename or delete the files you were explicitly asked to change.
- Do not "fix", reformat, refactor or tidy anything outside the requested scope, even if it looks wrong. Mention it to the user instead.
- Do not create extra files (helpers, tests, configs, docs, examples) unless asked.
- If a request is ambiguous about which files to touch, ask before acting.
- When you finish, list every file you created, changed, renamed or deleted.

## 2. Code style: modular and easy to read (most important)
- Every component must be understandable by a human without AI help.
- One physics/numerical/architectural component per module; a module must be runnable and testable on its own without importing unrelated components.
- Components interact only through clearly defined inputs and outputs; document every pairwise interaction in the relevant module's Markdown file.
- Prefer small, single-purpose functions with descriptive names and explicit inputs/outputs.
- Use clear variable names that match the symbols in the documented equations, and state units (SI) in docstrings or comments.
- Each function that implements an equation must reference that equation in the module's Markdown file.
- Prefer plain, explicit code over clever tricks; avoid deep nesting, hidden global state and magic numbers (name physical constants).
- Keep each module's Markdown file and Python file in sync: the Markdown describes inputs, outputs, equations and numerical methods; the Python implements exactly that.

## 3. Project conventions
- Module code and documentation live in `./iem` as `<module>.py` (or `.rs` for Rust) and `<MODULE>.md`.
- Native numerical methods are in Python (`numerical_methods.py`); HPC/multicore methods are in Rust (`numerical_methods_hpc.rs`).

## 4. General safety guardrails
- Never run destructive commands (`rm -rf`, overwriting files, `git reset --hard`, force pushes) without explicit confirmation.
- Look at a file before overwriting or deleting it.
- Never commit, push or publish anything unless asked.
- Never add secrets, credentials or personal information to code, docs or commits.
- Do not install packages or change the environment without asking.
- Do not send project code or data to external services unless asked.
- Report results honestly: if something was not tested, failed or was skipped, say so.
- Do not invent physics: if an equation, coefficient or reaction rate is uncertain, flag it and cite its source rather than guessing.
