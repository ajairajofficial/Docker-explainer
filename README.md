# How Docker Really Works — and How to Actually Port Your Containers

A first-principles explainer on what a container *actually is* at the kernel level, why "moving a container" is the wrong mental model, and the exact, repeatable way to lift a running service onto another host **without losing your data**.

**🔗 Read it live:** https://YOUR-USERNAME.github.io/REPO-NAME/

> Replace the link above with your own GitHub Pages URL once Pages is enabled (see **Hosting** below).

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

Five inline SVG infographics, a phosphor terminal theme, and everything in **one self-contained HTML file** — no external assets, no build step, no hosting dependencies.

---

## View it locally

Clone the repo and open the file in any browser:

```bash
git clone https://github.com/YOUR-USERNAME/REPO-NAME.git
cd REPO-NAME
open index.html        # macOS
# xdg-open index.html  # Linux
# start index.html     # Windows
```

To save a PDF, open it in a browser and choose **Print → Save as PDF** — the page ships with a print stylesheet that flips to light-on-white for paper.

---

## Hosting (GitHub Pages)

The page is a single static `index.html`, so GitHub Pages serves it with zero configuration:

1. Push `index.html` to the **root** of a **public** repo (see below).
2. Go to **Settings → Pages**.
3. Under **Build and deployment → Source**, choose **Deploy from a branch**.
4. Set **Branch** to `main` and the folder to `/ (root)`, then **Save**.
5. Wait a few minutes. Your page goes live at `https://YOUR-USERNAME.github.io/REPO-NAME/`.

**Custom domain (optional):** add a `CNAME` DNS record pointing to `YOUR-USERNAME.github.io`, then enter the domain in the Pages settings. If you front it with Cloudflare, set that record to **DNS-only** (grey cloud) so Cloudflare's TLS doesn't collide with GitHub's.

---

## Repository layout

```
.
├── index.html    # the explainer — self-contained, all SVGs inline
└── README.md     # this file
```

---

## Author

Written by **Ajai Raj**.
A product of **[iolinked.com](https://iolinked.com)**.

© 2026 Ajai Raj · iolinked.com — all rights reserved.
