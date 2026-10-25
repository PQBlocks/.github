<p align="center">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/PQBlocks/.github/main/profile/assets/banner-dark.svg">
    <img alt="PQBlocks: open, verified building blocks for the post-quantum transition" src="https://raw.githubusercontent.com/PQBlocks/.github/main/profile/assets/banner-light.svg" width="100%">
  </picture>
</p>

<p align="center">
  <b>Post-quantum building blocks you can read, test and verify.</b><br>
  Standards-based cryptography, migration tooling and quantum-inspired optimisation for Python.
</p>

<p align="center">
  <img alt="License" src="https://img.shields.io/badge/license-Apache--2.0-0f172a">
  <img alt="Standards" src="https://img.shields.io/badge/standards-FIPS%20203%20%C2%B7%20204%20%C2%B7%20205-22d3ee">
  <img alt="Python" src="https://img.shields.io/badge/python-3.11%20%E2%80%93%203.14-a78bfa">
  <img alt="Status" src="https://img.shields.io/badge/status-0.1%20alpha-f59e0b">
</p>

---

### Why PQBlocks

Large-scale quantum computers will break RSA and elliptic-curve cryptography. Data encrypted today can be recorded now and decrypted later. Moving to post-quantum security takes more than new algorithms: it takes **standard implementations, safe hybrid modes, ways to find what still needs to move, and proof that the change was done correctly.**

PQBlocks builds those pieces as small, focused, independently installable Python packages. Each one does one job, ships its evidence, and states its limits.

### Packages

| Package | What it does | Built on | Status |
|---|---|---|---|
| [**acvp-conformance**](https://github.com/PQBlocks/acvp-conformance) · `pqblocks-acvp` | Runs NIST ACVP test vectors for FIPS 203 / 204 / 205 across implementations and reports every case | NIST ACVP, FIPS 203/204/205 | 0.1 alpha |
| [**cbom-scanner**](https://github.com/PQBlocks/cbom-scanner) · `pqblocks-scan` | Finds classical and post-quantum cryptography in a codebase and emits a CycloneDX 1.6 CBOM and SARIF | CycloneDX 1.6, SARIF 2.1.0 | 0.1 alpha |
| [**pqc-wireformat**](https://github.com/PQBlocks/pqc-wireformat) · `pqblocks-wire` | A small, length-prefixed binary frame for ML-KEM ciphertexts and ML-DSA / SLH-DSA signatures | FIPS 203/204/205 | 0.1 alpha |
| [**hybrid-jwe**](https://github.com/PQBlocks/hybrid-jwe) · `pqblocks-jwe` | A compact wire format and parser for hybrid ML-KEM-768 + X25519 JWE-style tokens | RFC 7516, FIPS 203 | 0.1 alpha |
| [**simulated-bifurcation**](https://github.com/PQBlocks/simulated-bifurcation) · `pqblocks-bifurcation` | Ballistic and discrete Simulated Bifurcation for Ising / QUBO problems (quantum-inspired, classical, **not cryptography**) | Goto et al., *Sci. Adv.* 2019 & 2021 | 0.1 alpha |

More packages covering hybrid file encryption, policy-as-code, TLS interoperability, CSR proof-of-possession and crypto-agility are in review and will appear here once they pass the same checks.

### How we build

- **No new cryptography.** We implement and wrap standardised, peer-reviewed algorithms (ML-KEM, ML-DSA, SLH-DSA) through maintained libraries such as liboqs and pyca/cryptography. We never invent primitives.
- **Official test vectors first.** Correctness is checked against NIST ACVP and Wycheproof vectors wherever they exist, not only against our own tests.
- **Hybrid by default.** We pair post-quantum with classical algorithms where the protocol allows it, and refuse silent fallbacks.
- **Evidence ships with the code.** Every repository carries `TESTING.md`, `BENCHMARKS.md` (losing cases included), `EVIDENCE.md` (standards and the code that implements them), `VERIFICATION_REPORT.md` and `SECURITY_NOTES.md`.
- **Honest limits.** Every package is self-verified and states plainly what is *not* covered: constant-time status, side-channel posture, audit status. Nothing here is FIPS or CMVP validated, and no package claims to be.
- **Reproducible.** Each package is tested by installing the built wheel into a fresh environment on Python 3.11 – 3.14.

### Using PQBlocks with AI coding assistants

Every repository includes an `AGENTS.md` with the correct import, the right call and the mistakes to avoid. Coding assistants can then add post-quantum code that is correct by default.

### Security

Found a vulnerability? Please report it **privately** via GitHub's private vulnerability reporting on the affected repository. Do not open a public issue. See our [security policy](https://github.com/PQBlocks/.github/blob/main/SECURITY.md).

### Contributing

Issues and pull requests are welcome. Read [CONTRIBUTING.md](https://github.com/PQBlocks/.github/blob/main/CONTRIBUTING.md) and our [cryptography policy](https://github.com/PQBlocks/.github/blob/main/CRYPTO-POLICY.md) first.

<sub>PQBlocks · Post-Quantum Building Blocks · Apache-2.0</sub>
