# README.md

# Claude Loop Engineering Skill

Stop prompting Claude like a chatbot.

Start using Claude as a controlled engineering loop.

This repository contains a practical `skill.md` for Claude / Claude Code that turns AI-assisted development into a safer, more structured, more verifiable workflow.

Instead of relying on one big prompt and hoping Claude does the right thing, this skill forces Claude to work through repeatable engineering loops:

1. Understand
2. Inspect
3. Plan
4. Execute
5. Verify
6. Fix
7. Report
8. Stop

The goal is simple:

**Small loop. Verified change. Clear report. Stop.**

---

## Why This Exists

Most AI coding failures do not happen because the model is “bad.”

They happen because the workflow is uncontrolled.

Common problems:

* Claude starts coding before understanding the project
* Too many unrelated files get changed
* A small request turns into a full refactor
* The build breaks and Claude keeps adding more code
* UI becomes generic or inconsistent
* Auth, database, or API logic gets accidentally broken
* The model wastes usage by scanning too much context
* The user loses control of what changed and why

This skill is designed to prevent that.

---

## Prompt Engineering vs Loop Engineering

### Prompt Engineering

You write a prompt.

Claude gives an answer.

You manually check it.

Then you prompt again.

This works for simple tasks, but it becomes risky for real projects.

---

### Loop Engineering

You define a controlled workflow.

Claude must follow a loop.

Claude must inspect before editing.

Claude must verify after editing.

Claude must fix before continuing.

Claude must stop when the task is complete.

This is better for real software projects, SaaS builds, AI apps, dashboards, landing pages, APIs, mobile apps, and automation systems.

---

## What This Skill Does

This skill makes Claude behave more like an engineering operator.

It forces Claude to:

* work on one task at a time
* inspect relevant files before editing
* create a short plan before implementation
* make the smallest safe change
* avoid unnecessary refactors
* verify changes using build, typecheck, lint, tests, or manual checks
* fix broken verification before adding more features
* report exactly what changed
* stop instead of endlessly continuing

---

## Best Use Cases

This skill is useful for:

* Claude Code projects
* SaaS development
* Next.js apps
* React apps
* TypeScript projects
* Supabase projects
* API development
* dashboards
* AI automation systems
* landing pages
* mobile apps
* bug fixing
* UI improvement
* refactoring
* release checks

---

## How To Use

Copy `skill.md` into your Claude project or Claude Code skill setup.

Then use prompts like this:

```text
Use the Claude Loop Engineering Skill.

Task:
Implement the new pricing section on the landing page.

Scope:
Only edit the landing page and related UI components.

Do not:
Do not change routing, auth, database, or API logic.

Verification:
Run npm run build.

Stop condition:
Stop after the task is complete, verified, and reported.
```

---

## Recommended Prompt Format

Use this format for most tasks:

```text
Use the Claude Loop Engineering Skill.

Task:
[Describe the exact task]

Scope:
[Define what Claude may touch]

Do not:
[Define what Claude must not change]

Verification:
[Define build/test/manual checks]

Stop condition:
Stop when the task is completed, verified, and reported.
```

---

## Example: Feature Loop

```text
Use the Claude Loop Engineering Skill.

Task:
Add a customer notes field to the admin client detail page.

Scope:
Only touch the admin client detail page, related form component, and existing client update API if required.

Do not:
Do not change authentication, tenant logic, database schema, or unrelated pages.

Verification:
Run npm run build.

Stop condition:
Stop when the field is visible, save behavior works, build passes, and a report is provided.
```

---

## Example: Bugfix Loop

```text
Use the Claude Loop Engineering Skill.

Task:
Fix the TypeScript error from npm run build.

Scope:
Only edit files directly related to the error.

Do not:
Do not refactor unrelated components.

Verification:
Run the same failing build command again.

Stop condition:
Stop when the original error is gone and the result is reported.
```

---

## Example: UI Improvement Loop

```text
Use the Claude Loop Engineering Skill.

Task:
Improve the hero section so it looks more premium and less generic.

Scope:
Only edit the hero section and related styling.

Do not:
Do not change backend logic, routing, or page content structure outside the hero.

Verification:
Check desktop and mobile layout. Run npm run build.

Stop condition:
Stop when the hero is visually improved, responsive, build passes, and changes are reported.
```

---

## Core Principle

Claude should not optimize for large impressive changes.

Claude should optimize for:

1. correctness
2. safety
3. minimum unnecessary changes
4. verified output
5. low usage
6. clean structure
7. clear reporting

---

## Final Rule

If the build fails, Claude must not continue building new features.

Claude must fix the failure first.

No feature work on top of broken verification.

---

## License

MIT License.

Use, modify, and share freely.
