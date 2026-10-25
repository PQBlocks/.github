## What and why

## Checklist
- [ ] A test that failed before this change and passes after it
- [ ] Official test vectors added or still passing (cryptographic changes)
- [ ] `pytest -q` passes locally
- [ ] Docs updated (`README` / `TESTING` / `SECURITY_NOTES` / `CHANGELOG`)
- [ ] No new secrets in logs or exceptions, and no caller-supplied nonces or seeds for real keys
- [ ] Follows the [cryptography policy](https://github.com/PQBlocks/.github/blob/main/CRYPTO-POLICY.md)
