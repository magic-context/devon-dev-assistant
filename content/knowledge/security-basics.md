# Security Basics

## OWASP Top 10 (Developer Summary)

### 1. Broken Access Control
Users accessing things they shouldn't.
- **Fix:** Check permissions on every request. Deny by default. Test authorization paths.

### 2. Cryptographic Failures
Sensitive data exposed through weak crypto or no encryption.
- **Fix:** HTTPS everywhere. Encrypt sensitive data at rest. Use bcrypt/scrypt for passwords. Never roll your own crypto.

### 3. Injection
Untrusted input executed as code (SQL, NoSQL, OS commands, LDAP).
- **Fix:** Parameterized queries. Never concatenate user input into queries. Use ORMs safely.

### 4. Insecure Design
Flawed architecture that can't be fixed with implementation alone.
- **Fix:** Threat modeling during design. Secure defaults. Principle of least privilege.

### 5. Security Misconfiguration
Default credentials, unnecessary features enabled, missing hardening.
- **Fix:** Remove defaults. Disable unused features. Automate configuration. Review regularly.

### 6. Vulnerable Components
Using libraries with known vulnerabilities.
- **Fix:** `npm audit` / `pip audit` / Dependabot. Keep dependencies updated. Minimize dependencies.

### 7. Authentication Failures
Broken auth: weak passwords, credential stuffing, session hijacking.
- **Fix:** Strong password policies. MFA. Rate limiting. Secure session management. Use proven auth libraries.

### 8. Data Integrity Failures
Untrusted data assumed to be valid (deserialization, unsigned updates).
- **Fix:** Verify signatures. Validate all data. Use integrity checks.

### 9. Logging & Monitoring Failures
Can't detect breaches because logging is insufficient.
- **Fix:** Log auth events, access failures, input validation failures. Monitor and alert.

### 10. Server-Side Request Forgery (SSRF)
Server fetches attacker-controlled URLs.
- **Fix:** Validate and sanitize URLs. Allowlist destinations. Don't trust user-supplied URLs.

## Authentication Patterns

### Password-Based
- Hash with bcrypt (cost factor 12+) or Argon2
- Never store plaintext passwords
- Implement rate limiting on login endpoints
- Support MFA (TOTP, WebAuthn)

### Token-Based (JWT)
- Short-lived access tokens (15-60 minutes)
- Longer-lived refresh tokens (stored securely)
- Include only necessary claims
- Validate signature and expiration on every request
- Don't store sensitive data in JWT payload (it's base64, not encrypted)

### OAuth 2.0 / OpenID Connect
- Use for "Sign in with Google/GitHub/etc."
- Use Authorization Code flow (not Implicit)
- Validate tokens with the provider
- Don't implement from scratch — use a proven library

### Session-Based
- Generate cryptographically random session IDs
- Store sessions server-side (Redis, database)
- Set secure cookie flags: `HttpOnly`, `Secure`, `SameSite`
- Rotate session ID on login (prevents session fixation)

## Secrets Management

### Rules
1. **Never commit secrets to git** — not even in private repos
2. **Use environment variables** for configuration
3. **Use a secrets manager** for production (AWS Secrets Manager, HashiCorp Vault, Doppler)
4. **Rotate secrets regularly** — especially after any potential exposure
5. **Use `.env` files locally** — add `.env` to `.gitignore` immediately

### If You Accidentally Commit a Secret
1. Rotate the secret immediately (generate a new one)
2. Remove from git history (`git filter-branch` or BFG Repo-Cleaner)
3. Force push (coordinate with team)
4. Check for unauthorized usage
5. Don't just delete the file — the commit history still has it

## Quick Security Checklist

- [ ] HTTPS everywhere (no exceptions)
- [ ] Input validation on all user input
- [ ] Parameterized queries (no string concatenation in SQL)
- [ ] Passwords hashed with bcrypt/Argon2
- [ ] Authentication on all protected endpoints
- [ ] Authorization checks (not just authentication)
- [ ] Secrets in environment variables, not code
- [ ] Dependencies audited and updated
- [ ] Security headers set (CSP, HSTS, X-Frame-Options)
- [ ] Error messages don't leak internal details
- [ ] Logging for security events
- [ ] Rate limiting on auth endpoints
