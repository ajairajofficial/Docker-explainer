# How Docker Really Works — and How to Actually Port Your Containers

A first-principles explainer on what a container *actually is* at the kernel level, why "moving a container" is the wrong mental model, and the exact, repeatable way to lift a running service onto another host **without losing your data**.

**🔗 Read it live:** https://ajairajofficial.github.io/Docker-explainer



---

## What's inside

Built from the ground up, no assumed knowledge, serving a newcomer and an expert on the same page:

- **What a container really is** — one host process wrapped in Linux **namespaces** (what it can see), **cgroups** (what it can use), and an **overlay filesystem** (what files it sees). No VM, no guest OS.
- **The daemon chain** — what `docker run` actually sets in motion, from the CLI down to `runc` and the kernel.
- **Why your data isn't in the image** — copy-on-write, the writable layer, and why named volumes are the thing you carry by hand.
- **`save` vs `export` vs `commit`** — the commands everyone conflates, laid out side by side.
- **A full worked migration** — a live `postgres:16` container moved host-to-host with a real pass/fail test, including the `pg_dump` escape hatch for version/architecture jumps.
- **Edge cases with teeth** — torn snapshots, the `/var/lib/docker` footgun, bind mounts, anonymous volumes, arch mismatches.
- Plus exercises, a command cheat sheet, a glossary, and primary-source links.

---
---

## Author

Written by **Ajai Raj**.
A product of **[iolinked.com](https://iolinked.com)**.

© 2026 Ajai Raj · iolinked.com — all rights reserved.
