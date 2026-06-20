# UI Improvement Loop Example

Use the Claude Loop Engineering Skill.

## Task

Improve one existing UI section without breaking functionality.

Example:

Improve the hero section so it looks more premium, modern, readable, and less generic.

---

## Goal

The goal is to improve visual quality while preserving existing functionality.

Claude must treat UI improvement as a controlled loop, not as a full redesign.

The improvement should focus on:

* layout
* spacing
* typography
* visual hierarchy
* button clarity
* responsive behavior
* mobile readability
* overall premium feel

---

## Scope

Claude may only edit:

* the selected page or section
* related UI components
* related styling files
* local copy/text inside that section if needed

Example allowed files:

* `app/page.tsx`
* `components/Hero.tsx`
* `components/Pricing.tsx`
* `components/LandingSection.tsx`
* related CSS or Tailwind classes

---

## Do Not

Claude must not:

* change backend logic
* change API routes
* change authentication
* change database logic
* change payment logic
* modify unrelated pages
* redesign the entire app
* replace the design system
* remove existing functionality
* create a generic SaaS template look
* add fake features
* add unused components

---

## Required UI Checks

Claude must check the UI against these quality points:

### Visual Hierarchy

* Is the main headline clear?
* Is the primary CTA obvious?
* Is the section easy to scan?

### Spacing

* Is there enough breathing room?
* Are elements too cramped?
* Are cards, buttons, and text aligned?

### Typography

* Are font sizes consistent?
* Is the text readable on desktop and mobile?
* Are headings and body text clearly separated?

### Responsiveness

* Does the section work on mobile?
* Does it avoid horizontal overflow?
* Are buttons usable on smaller screens?

### Product Feel

* Does it look intentional?
* Does it avoid a cheap AI-generated look?
* Does it match the brand direction?

---

## Required Loop

Claude must follow this loop:

1. Inspect the current UI section
2. Identify the main visual weaknesses
3. Create a short improvement plan
4. Edit only the selected UI area
5. Preserve existing functionality
6. Check desktop and mobile layout
7. Run build if available
8. Report what changed

---

## Verification

Run:

```bash
npm run build
```

If available, also run:

```bash
npm run lint
npm run typecheck
```

Manual UI checklist:

```text
Desktop layout checked
Mobile layout checked
CTA visible
No broken spacing
No horizontal overflow
No unrelated functionality changed
```

---

## Stop Condition

Stop when:

* the selected UI section is improved
* functionality is preserved
* responsive behavior is checked
* build passes, if build is available
* changes are summarized
* remaining risks are reported

---

## Final Report Format

Claude must finish with:

```md
## Done

- Improved the selected UI section.

## Changed

- File path: short reason for the change.

## Verified

- Build/check command.
- Manual UI checks.

## UI Improvements

- Layout:
- Spacing:
- Typography:
- CTA:
- Mobile:

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
Improve the hero section so it looks more premium and less generic.

Scope:
Only edit the hero section and related styling.

Do not:
Do not change backend logic.
Do not change routing.
Do not change authentication.
Do not redesign the whole app.
Do not touch unrelated sections.

Verification:
Run npm run build.
Check desktop and mobile layout manually.

Stop condition:
Stop when the hero is visually improved, responsive, build passes, and a final report is provided.
```
