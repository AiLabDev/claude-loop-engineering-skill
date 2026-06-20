# Bugfix Loop Example

Use the Claude Loop Engineering Skill.

## Task

Fix the error that appears when running the project build.

## Current Problem

The project fails during verification.

Example command:

```bash
npm run build
```

Claude must treat the build error as the main task.

The goal is not to add new features.

The goal is to find and fix the root cause of the error.

---

## Scope

Claude may only inspect and edit files directly related to the error.

Claude should first read:

* the terminal error message
* the file path mentioned in the error
* related imports
* related components, types, or functions
* relevant config files only if needed

---

## Do Not

Claude must not:

* refactor unrelated files
* redesign the UI
* change business logic unless required by the error
* modify authentication
* modify database schema
* change routing unless the error is route-related
* install new packages unless clearly necessary
* delete files without permission
* continue building new features while the build is failing

---

## Required Loop

Claude must follow this loop:

1. Read the exact error message
2. Identify the file and line related to the error
3. Inspect only the relevant code
4. Explain the likely root cause briefly
5. Apply the smallest safe fix
6. Run the same failing command again
7. If the error remains, make a second focused fix attempt
8. Stop after the issue is fixed or after 2 failed focused attempts

---

## Verification

Run the same command that failed originally.

Example:

```bash
npm run build
```

If the project has additional checks, run only the relevant ones:

```bash
npm run typecheck
npm run lint
```

---

## Stop Condition

Stop when:

* the original error is fixed
* the verification command passes, or the remaining error is clearly different
* changed files are listed
* the root cause is explained
* risks or assumptions are reported

---

## Final Report Format

Claude must finish with:

```md
## Done

- Fixed the build error.

## Root Cause

- Explain what caused the error.

## Changed

- File path: short reason for the change.

## Verified

- Command run.
- Result.

## Risks / Notes

- Any remaining issue or assumption.

## Next

- One recommended next step.
```

---

## Example Prompt

```text
Use the Claude Loop Engineering Skill.

Task:
Fix the error from npm run build.

Scope:
Only edit files directly related to the error.

Do not:
Do not refactor unrelated components.
Do not add new features.
Do not change auth, database, routing, or UI unless the error requires it.

Verification:
Run npm run build again after the fix.

Stop condition:
Stop when the original error is gone, verification result is reported, and changed files are summarized.
```
