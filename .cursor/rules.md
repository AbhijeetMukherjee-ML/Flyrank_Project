# Flyrank Project — Coding Conventions

This project uses **Python**, **HTML**, **CSS**, and **JavaScript**. Follow these conventions when writing or modifying code.

## General Principles

- **Write readable code** — code is read more often than it is written. Prefer clarity over cleverness.
- **Use meaningful names** — variables, functions, classes, and files should describe their purpose.
- **Keep functions modular** — each function should do one thing well. Extract helpers when logic grows complex.
- **Match existing style** — follow patterns already present in the codebase before introducing new conventions.
- **Keep changes focused** — avoid unrelated refactors in the same change.

## Python

- Follow [PEP 8](https://peps.python.org/pep-0008/) for formatting and style.
- Use 4 spaces for indentation (no tabs).
- Limit lines to 79–88 characters where practical.
- Use `snake_case` for functions, variables, and module names.
- Use `PascalCase` for class names.
- Use `UPPER_SNAKE_CASE` for module-level constants.
- Add docstrings to public modules, classes, and non-trivial functions.
- Prefer explicit imports; group standard library, third-party, and local imports separately.
- Use type hints for function signatures when they improve clarity.
- Handle errors explicitly — avoid bare `except:` clauses.

```python
# Good
def calculate_total_price(items: list[dict]) -> float:
    return sum(item["price"] for item in items)

# Avoid
def calc(x):
    t = 0
    for i in x:
        t += i["price"]
    return t
```

## HTML

- Use semantic elements (`<header>`, `<nav>`, `<main>`, `<section>`, `<footer>`) where appropriate.
- Use 2-space indentation for nested elements.
- Always include meaningful `alt` text on images.
- Use lowercase for tag and attribute names.
- Keep structure (HTML), presentation (CSS), and behavior (JavaScript) separated.
- Prefer accessible markup: labels for inputs, proper heading hierarchy, ARIA only when native HTML is insufficient.

## CSS

- Use consistent naming — prefer descriptive class names (e.g., `.card-title`, `.nav-link`).
- Use 2-space indentation.
- Group related properties (layout, typography, color, spacing).
- Avoid overly specific selectors; prefer classes over deep nesting.
- Use CSS custom properties for repeated values (colors, spacing, fonts).
- Keep styles maintainable — one component or section per logical block of rules.

```css
/* Good */
.card {
  padding: 1rem;
  border-radius: 8px;
  background-color: var(--surface-color);
}

/* Avoid */
div div div .card {
  padding: 1rem;
}
```

## JavaScript

- Use `camelCase` for variables and functions; `PascalCase` for classes and constructors.
- Prefer `const` by default; use `let` when reassignment is needed. Avoid `var`.
- Keep functions small and single-purpose; extract reusable logic into named functions.
- Use meaningful names — avoid single-letter variables except in short loops or callbacks.
- Prefer modern ES6+ syntax (arrow functions, template literals, destructuring) when it improves readability.
- Add comments only for non-obvious logic; the code itself should explain the what and how.
- Validate user input and handle async errors with `try/catch` or `.catch()`.

```javascript
// Good
function formatUserDisplayName(user) {
  return `${user.firstName} ${user.lastName}`.trim();
}

// Avoid
function f(u) {
  return u.fn + " " + u.ln;
}
```

## File Organization

- Place related code together — keep templates, styles, and scripts organized by feature or page.
- Use descriptive file names (e.g., `user_service.py`, `dashboard.js`, `main.css`).
- Remove dead code and unused imports rather than leaving them commented out.

## Before Submitting Changes

- Ensure code runs without errors.
- Remove debug statements (`print`, `console.log`) unless intentionally kept for logging.
- Verify formatting is consistent with the conventions above.
