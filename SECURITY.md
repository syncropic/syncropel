# Security policy

Thank you for helping keep Syncropel and its users safe. If you've
found a security issue, please **don't open a public GitHub issue or
discussion** — coordinate with us privately first.

---

## How to report

Email **security@syncropic.com** with:

- A description of the issue and its potential impact.
- The minimal steps to reproduce.
- The component affected (the protocol, a specific SDK, the hosted
  product, the documentation site, etc.) and the version where
  applicable.
- Any proof-of-concept material — please don't post it publicly.

If you need to encrypt sensitive material, mention that in your
first message and we'll coordinate a key exchange.

---

## What to expect

- **Acknowledgement within 72 hours.** We'll confirm receipt and let
  you know who's looking at it.
- **A status update within 7 days.** Either with a fix in progress, a
  request for more information, or a reasoned position that it isn't
  a vulnerability.
- **Coordinated disclosure.** We prefer to publish a fix and an
  advisory together. We'll agree on a disclosure timeline with you;
  the default is 90 days from the date you reported it, sooner when a
  fix lands first.
- **Credit.** With your permission, we'll credit you in the advisory.
  Anonymous reports are also welcome.

When a fix ships, we publish an advisory through GitHub's Security
Advisory mechanism on the affected repository.

---

## Scope

In scope:

- The Syncropel protocol implementations (the `spl` binary, official
  SDKs).
- Hosted Syncropel instances (`syncropel.com`, customer instances at
  `*.syncropel.app`).
- Official documentation and installer (`docs.syncropel.com`,
  `get.syncropic.com`).

Out of scope:

- Third-party integrations and community-built adapters (report
  those to their respective maintainers).
- Vulnerabilities that require a compromised host or local privileged
  access to exploit.
- Social-engineering attacks against Syncropic personnel.
- Denial-of-service issues that depend on volumetric flooding.

---

## What we won't do

We don't pursue legal action against security researchers who:

- Engage in good-faith vulnerability research.
- Avoid harming users or their data.
- Respect privacy and don't exfiltrate data beyond what's needed to
  demonstrate the issue.
- Coordinate disclosure with us before going public.

If you're unsure whether your research falls within these
guidelines, ask first.
