# Code Review Checklist

## PR: [Title]
**Author:**
**Reviewer:**
**Date:**

---

## Correctness
- [ ] Does it do what it's supposed to do?
- [ ] Are edge cases handled?
- [ ] Are error conditions handled gracefully?
- [ ] No off-by-one errors or boundary issues?

## Readability
- [ ] Clear naming (variables, functions, classes)?
- [ ] Code is self-documenting or well-commented?
- [ ] No unnecessarily clever code?
- [ ] Consistent style with the codebase?

## Architecture
- [ ] Follows existing patterns and conventions?
- [ ] Appropriate abstraction level (not too much, not too little)?
- [ ] No unnecessary coupling between components?
- [ ] Changes are in the right layer/module?

## Security
- [ ] Input validated?
- [ ] No secrets in code?
- [ ] Auth/authz properly handled?
- [ ] SQL injection / XSS / other injection prevented?

## Testing
- [ ] Tests cover the happy path?
- [ ] Tests cover edge cases and error cases?
- [ ] Tests are readable and well-named?
- [ ] No flaky tests introduced?

## Performance
- [ ] No obvious N+1 queries?
- [ ] No unnecessary computation in hot paths?
- [ ] Large data sets handled appropriately?
- [ ] Caching considered where appropriate?

## Deployment
- [ ] Backward compatible?
- [ ] Migration needed? (reversible?)
- [ ] Feature flag needed?
- [ ] Documentation updated?

## Overall
- **Approve / Request changes / Comment**
- **Summary:**
