# ARCHIVED — superseded, do not build on this fork

This fork of [`browser-use/browser-harness`](https://github.com/browser-use/browser-harness)
is **archived and carries zero patches worth keeping.**

## Why

Audited 2026-07-12. This fork was:

- **46 commits BEHIND** upstream (which had shipped `v0.1.5`), and
- **5 commits AHEAD** — all five adding *only markdown*: 583 insertions, **zero code**.

We were paying the maintenance cost of a fork in order to hold five markdown files.
That was the entire divergence. There was never anything to maintain.

## Where everything went

- **The domain skills** (`instagram/`, `tiktok/`, `facebook/`, `mastodon/` engagement
  playbooks) now live **in-tree in SmartSocial** at `agents/bob/domain-skills/`, where
  Bob's `HarnessRunner` mounts them for the harness via `BH_AGENT_WORKSPACE`. They are
  no longer coupled to a fork of somebody else's repo.
- **The harness itself** is now consumed as a **pinned upstream release** — currently
  `browser-harness==0.1.5`, installed as a CLI (`uv tool install browser-harness==0.1.5`).
  Staying current is a version bump + a smoke test, not a merge.

Upstream owns the primitives; SmartSocial owns the brand / audit / approval layer.
("Vercel-on-Next.js" — see upstream issue #356.)

## If you need to patch the harness

**Do not re-fork pre-emptively.** Open an upstream PR. If upstream will not take it and
we genuinely need it, *then* fork — and eat the cost knowingly, with a written reason.

## Open upstream PRs from this account

- **#348** (LinkedIn domain skills) — left open upstream. Its `send-connection-request.md`
  has been brought in-tree to SmartSocial regardless, so upstream's decision no longer
  blocks us either way.
