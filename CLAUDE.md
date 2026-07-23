# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## What this repository is

This is a **GitHub profile README** repository — the special `ShresthSamyak/ShresthSamyak` repo whose `README.md` renders directly on the owner's GitHub profile page (github.com/ShresthSamyak). There is no application code, build system, or test suite. Editing `README.md` changes what visitors see on the profile.

## Structure

- `README.md` — the profile page. Professional, theme-neutral layout: animated hero banner, portfolio/LinkedIn/X/Email links, an About paragraph written for SEO, `img.shields.io` skill badges, and a GitHub-statistics section (stats card, top languages, streak, activity graph). Does **not** list personal projects and does **not** list open-source contributions (owner's choice). **No emojis anywhere** — the owner wants a clean, emoji-free profile; do not add them.
- `assets/hero.svg` — hand-authored, **self-hosted animated banner** (SMIL animations: shimmering name gradient, cycling role text, blinking cursor, underline reveal, floating dots). Referenced from README by its `blob/main/...?raw=true` URL. It is a self-contained dark card, so it reads as intentional on both light and dark GitHub themes.

## Working notes

- **Animate only via self-hosted SVG.** The animation requirement is met by `assets/hero.svg`, not by third-party services. Use **SMIL** (`<animate>`, `<animateTransform>`) — it animates reliably when an SVG is embedded as an `<img>` on GitHub. Only system fonts are available inside a camo-proxied SVG (no web fonts) — stick to `'Segoe UI'`/`'Courier New'` families.
- **Self-host anything critical.** The banner is self-hosted SVG precisely because third-party render services are unreliable. The stats/streak/activity-graph images (`github-readme-stats`, `streak-stats`, `github-readme-activity-graph`) were re-added at the owner's explicit request despite this — they can show "Error Fetching Resource" when rate-limited through camo. That is a known tradeoff the owner accepted; do not silently remove them, but never make the banner or any load-bearing element depend on such a service. (Also removed for good: readme-typing-svg, capsule-render, and the `Platane/snk` snake Action.)
- **Theme safety is a hard requirement.** Do not hardcode dark-only page backgrounds (an old version used `#000d1a` and looked like a black slab on light theme). Badges use per-tech brand colors; the hero is a self-contained card.
- **No projects section, no forks.** The owner asked not to list projects. If projects are ever re-added, every claim must carry a verifiable number and link to a real repo, and forks must never appear as "shipped" work.
- **Preview only renders correctly on GitHub.** Local markdown preview will not show the hero animation, badges, or centered HTML — verify by pushing and viewing the profile.
- **Absolute URLs are load-bearing.** The hero is referenced by an absolute `blob/main/assets/hero.svg?raw=true` URL tied to the `ShresthSamyak` username + `main` branch. Renaming the repo or default branch silently breaks the banner.
- GitHub sanitizes README HTML — only a whitelisted subset of tags survives (no `<script>`, no `style` attributes). Keep to the badge / `<img>` / `<p align>` patterns already in use.

## SEO (requested feature)

Optimized to be found by name **and** by tech skills:
- The hero banner + the bold About line carry the name and role keywords Google indexes into the search snippet.
- The About paragraph deliberately contains recruiter-queried terms in plain text: LLM inference, RAG, Model Context Protocol (MCP), Computer Vision, PyTorch, JAX.
- Cross-linking the portfolio (shresthsamyak.com) and LinkedIn is what lets Google associate the profiles — keep those links present.
