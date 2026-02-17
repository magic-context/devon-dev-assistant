# Code Quality

## SOLID Principles

### Single Responsibility
A class/module should have one reason to change.
- **Good:** `UserAuthenticator` handles authentication. `UserNotifier` handles notifications.
- **Bad:** `UserManager` handles auth, notifications, profile updates, and billing.

### Open/Closed
Open for extension, closed for modification.
- Add new behavior by adding code, not changing existing code.
- Use interfaces, inheritance, or composition.

### Liskov Substitution
Subtypes must be substitutable for their base types.
- If a function expects `Shape`, any subclass (`Circle`, `Rectangle`) should work without surprises.
- Don't override methods in ways that break the parent's contract.

### Interface Segregation
Don't force clients to depend on interfaces they don't use.
- Many small interfaces > one giant interface.
- `Readable` and `Writable` > `ReadWriteDeleteArchiveExport`

### Dependency Inversion
Depend on abstractions, not concrete implementations.
- High-level modules shouldn't depend on low-level modules.
- Both should depend on abstractions (interfaces).

## Clean Code Principles

### Naming
- **Variables:** Describe what it holds, not how it's used. `customerAge` > `x`
- **Functions:** Describe what it does. `calculateTotalPrice()` > `process()`
- **Booleans:** Use question form. `isActive`, `hasPermission`, `canEdit`
- **Classes:** Nouns that describe the entity. `InvoiceGenerator`, `UserRepository`
- **Constants:** SCREAMING_SNAKE for true constants. `MAX_RETRY_COUNT`

### Functions
- **Do one thing** — if you need "and" to describe it, split it
- **Small** — if it doesn't fit on one screen, it's probably doing too much
- **Few parameters** — 0-2 ideal, 3 acceptable, 4+ refactor (use objects)
- **No side effects** — if the name is `getUser()`, don't modify the database
- **Early return** — reduce nesting with guard clauses

### Comments
- Code should be self-documenting. Comments explain *why*, not *what*.
- **Good:** `// Retry with backoff because the payment API rate-limits aggressively`
- **Bad:** `// increment i by 1` or `// TODO: fix this later`
- Delete commented-out code. Git remembers.

### Error Handling
- Handle errors where you can do something useful. Don't catch-and-ignore.
- Fail fast and loud in development. Fail gracefully in production.
- Use specific error types, not generic exceptions.
- Log enough context to debug without exposing sensitive data.

## DRY vs. WET

**DRY** (Don't Repeat Yourself) — shared logic in one place.
**WET** (Write Everything Twice) — some duplication is okay.

**The balance:** Don't abstract too early. Two instances of similar code might diverge. Three is a pattern — then abstract.

**Wrong kind of DRY:** Forcing unrelated things to share code because they look similar today.

## Testing

### Test Pyramid
```
        /  E2E  \        (Few — slow, brittle, expensive)
       /  Integ  \       (Some — test component interactions)
      / Unit Tests \     (Many — fast, focused, cheap)
```

### What to Test
- **Happy path** — does it work when inputs are valid?
- **Edge cases** — empty inputs, nulls, boundaries, max values
- **Error cases** — invalid inputs, network failures, permission denied
- **Regressions** — write a test for every bug you fix

### Testing Principles
- Tests are documentation — name them like specifications
- Arrange-Act-Assert (or Given-When-Then)
- One assertion per test (usually)
- Don't test implementation details — test behavior
- Fast tests get run. Slow tests get skipped.

## Code Review Mindset

### As Reviewer
- Start with what's good — encourage, then suggest
- Ask questions instead of making demands: "What happens if X?" > "Change this"
- Focus on: correctness, readability, maintainability, edge cases
- Don't nitpick style if there's a linter for that
- Approve with suggestions when changes are minor

### As Author
- Small PRs — easier to review, faster to merge
- Write a good description — context helps reviewers
- Self-review before requesting — catch the obvious stuff
- Don't take feedback personally — it's about the code
