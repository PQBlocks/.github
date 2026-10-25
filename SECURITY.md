# Security policy

PQBlocks builds security-relevant software, and we treat vulnerability reports as our highest priority.

## Reporting a vulnerability

Please report suspected vulnerabilities **privately**, using GitHub's private vulnerability reporting on the affected repository:
`https://github.com/PQBlocks/<repository>/security/advisories/new`

**Do not open a public issue, discussion or pull request** for a suspected vulnerability.

Please include:
- the affected package and version;
- a description of the issue and its impact;
- a minimal reproduction (code, inputs, or test vector);
- any suggested fix, if you have one.

## What to expect

| Step | Target |
|---|---|
| Acknowledgement | within 3 working days |
| Initial assessment and severity | within 10 working days |
| Fix and coordinated disclosure | normally within 90 days, agreed with the reporter |

We credit reporters in the advisory and release notes unless they ask to remain anonymous. We request a CVE where appropriate.

## Supported versions

Only the latest minor release of each package receives security fixes during the 0.x series.

## Scope

In scope: code in PQBlocks repositories and their published packages. Out of scope: vulnerabilities in upstream dependencies (please report those upstream, e.g. to liboqs or pyca/cryptography), and issues that require a compromised host.

## Our security posture

Every package documents its own posture in `SECURITY_NOTES.md`: constant-time status, side-channel considerations, zeroization, RNG source and audit status. PQBlocks packages are self-verified and have **not** been externally audited, and none is FIPS or CMVP validated unless its notes explicitly say otherwise.
