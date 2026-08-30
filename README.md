# Syncropel

> **Make coordination durable, composable, and trustworthy.**

[![Docs](https://img.shields.io/badge/docs-syncropel.com-black)](https://docs.syncropel.com)
[![npm](https://img.shields.io/npm/v/@syncropel/sdk?label=npm%20%40syncropel%2Fsdk&color=cb3837)](https://www.npmjs.com/package/@syncropel/sdk)
[![PyPI](https://img.shields.io/pypi/v/syncropel?label=PyPI%20syncropel&color=blue)](https://pypi.org/project/syncropel/)
[![This repo: Apache-2.0](https://img.shields.io/badge/this%20repo-Apache--2.0-green)](LICENSE)

---

Syncropel makes the world's knowledge and actions composable,
computable, verifiable, and yours. It is an open protocol for human +
AI teams to coordinate, decide, and govern together, built from
immutable, signed, content-addressed records that compose into
threads, accumulate evidence-based trust, and feed workflows that
learn and replay.

Syncropel is not an AI framework, not a vendor SaaS, and not a
blockchain. It sits alongside your tools and records what they do,
with verifiable provenance and consent-gated sharing.

---

## What's in the protocol

- **Records.** Every coordination event becomes a record: who did it,
  what kind of act (intend, do, know, learn), what content, in what
  thread. Signed by the actor, content-addressed by its hash,
  immutable from the moment it lands.
- **Threads.** Records group into threads, the unit of coordinated
  work. Git-like: fork, merge, close.
- **Actors.** Humans, AI agents, and automations are all first-class
  actors with portable identity. The protocol doesn't distinguish
  them structurally; every record is signed by its actor, and every
  actor accrues trust independently.
- **Trust.** Evidence-based reputation. Trust accumulates from
  execution history, is computed per actor and per domain rather than
  as a single score, and decays over time so old wins don't bank
  forever.
- **Patterns.** Repeated success is captured automatically. When a
  thread succeeds the same way often enough, its shape promotes to a
  reusable pattern; next time something similar appears, the proven
  solution replays. A single dial decides whether each task leans
  into replay (predictable, free) or fresh generation (novel,
  costlier).
- **Workspaces.** A workspace is a record too: versioned, forkable,
  federatable. Specs, dashboards, runbooks, anything you'd put in a
  separate tool, but as records.
- **Federation.** Instances pull from each other selectively,
  consent-gated, with no central registry. Share patterns without
  sharing data: publish what works while keeping the specifics
  private.

For the full specification, see
[docs.syncropel.com](https://docs.syncropel.com).

---

## Two paths to a working instance

**Hosted**, the fastest. Sign up at
[syncropel.com/sign-up](https://syncropel.com/sign-up); a private
Syncropel instance comes up at `<your-label>.syncropel.app` in about a
minute. No install, no machine to maintain. 30-day free trial;
[pricing](https://syncropel.com/pricing).

**Self-hosted**, free: install `spl` on a machine you control.

```bash
# Linux + WSL
curl -sSf https://get.syncropic.com/spl | sh

# Windows (PowerShell)
irm https://get.syncropic.com/spl.ps1 | iex

# Then
spl init && spl serve --daemon
```

Both paths run the same binary, expose the same APIs, and federate
with each other.

If you're integrating from code, use one of the SDKs:

```bash
npm install @syncropel/sdk      # TypeScript / JavaScript
pip install syncropel           # Python
```

Full getting-started flow at
[docs.syncropel.com](https://docs.syncropel.com).

---

## What a thread looks like

```
fix-checkout-timeout                          5 records · 3 actors

● you      INTEND  "Fix checkout timeout before launch"     14m ago
○ agent    DO      Profiled: connection pool saturated      12m ago
○ agent    DO      Patch applied: pool 10 → 50, deployed    9m ago
○ monitor  KNOW    p99 4.2s → 180ms, 340 users unblocked    6m ago
○ agent    LEARN   "Pool sizing must scale with replicas"   now
                   captured · next similar issue replays
```

`●` is a person; `○` is an AI agent or automation. Every record is
immutable, content-addressed, and signed by its actor. The `LEARN` at
the end captures a reusable pattern; the next time the same shape of
issue appears, the solution replays automatically.

---

## Where to go next

- **[docs.syncropel.com](https://docs.syncropel.com)**: guides, API
  reference, integration cookbook, operations runbooks
- **[syncropel.com](https://syncropel.com)**: hosted product, signup,
  the Studio web interface
- **[GitHub Discussions](https://github.com/syncropic/syncropel/discussions)**:
  questions, ideas, use-case sharing
- **[GitHub Issues](https://github.com/syncropic/syncropel/issues)**:
  bug reports and feature requests

---

## Open protocol, open SDKs, a kernel that is free to run

- **The protocol is open.** The Syncropel specification is published
  under CC-BY-SA-4.0 and anyone may implement it.
- **The SDKs are open source.** `@syncropel/sdk` and the Python
  `syncropel` package are Apache-2.0 and will stay that way.
- **The kernel (`spl`) is free to download and run** for any purpose,
  including production and commercial use, locally or on our hosted
  service. Its source is not yet public; we intend to publish it once
  the protocol reaches 1.0. The binary ships under the Business
  Source License 1.1: every release carries a written date on which it
  becomes Apache-2.0, and the one use the license does not permit is
  reselling Syncropel itself as a hosted service, for which a
  commercial license is available.
- **Terms only ever loosen.** No right we have granted is ever
  narrowed, the specification never closes, and the SDKs never leave
  Apache-2.0.
- **You can leave.** `spl export` produces a complete, documented copy
  of your instance; hosted customers can move to self-hosted or to
  another host at any time.

We intend to hold our patents defensively and to publish a
non-assertion pledge, and to move stewardship of the protocol to an
independent foundation. The texts of the charter, the pledge, and the
kernel's license terms are in counsel review and will be published
here when ready.

---

## Status

Syncropel is in active development. It is used in production by early
adopters, and hosted signup is live. Breaking changes are possible,
and when they happen they ship with documented migrations and a
[CHANGELOG](CHANGELOG.md) entry.

---

## License

The documents in this repository are Apache-2.0. See
[LICENSE](LICENSE).

The specification, the SDKs, and the kernel ship under their own
licenses, summarised above.

Syncropel is developed by [Syncropic, Inc.](https://syncropic.com), a
Delaware public-benefit corporation.

---

## Brand

- **Syncropic**: the company that stewards the protocol
- **Syncropel**: the protocol itself
- **Studio**: the browser interface for working with Syncropel
- **`spl`**: the command-line interface and local instance binary
