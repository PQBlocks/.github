# Cryptography policy

These rules apply to every PQBlocks package. A contribution that breaks one of them will not be merged.

1. **No novel cryptography.** We implement or wrap only standardised or peer-reviewed algorithms: NIST FIPS 203 (ML-KEM), FIPS 204 (ML-DSA), FIPS 205 (SLH-DSA), and established classical primitives. New primitives, ad-hoc constructions and "improved" variants are out of scope.
2. **Prefer audited implementations.** Where possible we bind to maintained libraries (liboqs, pyca/cryptography) rather than re-implementing primitives.
3. **Hybrid by default.** Where a protocol allows it, post-quantum algorithms are combined with a classical one, so security does not rest on a single assumption. Downgrade to classical-only must be explicit, never silent.
4. **Official vectors are the reference.** Correctness is checked against NIST ACVP / KAT and Wycheproof vectors wherever they exist, vendored byte-for-byte with their source and hash.
5. **Secrets stay secret.** No secret material in logs, exceptions or `repr`. Randomness for keys and nonces comes from the operating system CSPRNG; callers cannot supply seeds or nonces for production key material.
6. **Fail loudly.** Malformed or hostile input is rejected with a typed error before any cryptographic operation. Parsers check lengths before use and bound recursion and size.
7. **No overclaiming.** We never describe a package as "certified", "FIPS-validated", "unbreakable" or "quantum-proof". We say exactly what was verified, against which standard, and what was not.
8. **Disclose limits.** Constant-time behaviour, side-channel posture and audit status are written down per package in `SECURITY_NOTES.md`.
