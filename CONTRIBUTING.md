# Contributing to PQBlocks

Thank you for helping build post-quantum infrastructure. Please read the [cryptography policy](CRYPTO-POLICY.md) first.

## Before you start
- **Security issues:** do not open an issue. Follow the [security policy](SECURITY.md).
- **Bugs:** open an issue with a minimal reproduction, the package version and your Python version.
- **Features:** open an issue to discuss it before writing a large change.

## Pull requests
1. Fork the repository and create a branch from `main`.
2. Install with test extras: `pip install -e ".[test]"`.
3. **Write a failing test first**, then the fix. Cryptographic changes must include official test vectors where they exist.
4. Run the full suite: `pytest -q`. All tests must pass.
5. Update the relevant documentation (`README.md`, `TESTING.md`, `SECURITY_NOTES.md`, `CHANGELOG.md`).
6. Keep pull requests focused: one logical change each.
7. Sign your commits where possible.

## What reviewers check
- Correctness against the standard and official vectors.
- No new secret-dependent branches, no secrets in logs or exceptions, no caller-supplied nonces or seeds for real keys.
- Hostile-input handling: length checks before use, bounded recursion and size.
- Honest documentation: no claims beyond what the tests prove.

## Licence
By contributing you agree that your contribution is licensed under the Apache License 2.0.
