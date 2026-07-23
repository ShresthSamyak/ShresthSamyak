# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## What this repository is

This is a **GitHub profile README** repository — the special `ShresthSamyak/ShresthSamyak` repo whose `README.md` renders directly on the owner's GitHub profile page (github.com/ShresthSamyak). There is no application code, build system, or test suite. Editing `README.md` changes what visitors see on the profile.

## Structure

- `README.md` — the profile page. A professional, theme-neutral layout: centered header (name + role + Portfolio/LinkedIn/X/Email links), a bio paragraph written for SEO, a Featured-projects table, an Open-source-contributions section, `img.shields.io` skill badges (each colored with its tech's brand color so it reads on both light and dark GitHub themes), and one `github-readme-stats` card.

## Working notes

- **Purpose is signal, not decoration.** Every project claim must carry a verifiable number and link to a real repo. Do not add aspirational taglines, and never list forks under "shipped" / project sections — forking is one click and reads as padding.
- **Theme safety is a hard requirement.** GitHub renders READMEs in both light and dark themes. Do not hardcode dark-only backgrounds (a previous version used `#000d1a` and rendered as a black slab on light theme). Badges use per-tech brand colors; the stats card is theme-neutral.
- **Avoid flaky third-party render services.** A previous version used readme-typing-svg, streak-stats, capsule-render, and a `Platane/snk` contribution-"snake" Action — all removed. They rate-limit through GitHub's camo proxy and show broken-image icons at exactly the wrong moment (cold outreach). `github-readme-stats` is the one remaining external render dependency; if it rate-limits, self-host or delete the block rather than tolerate a broken image.
- **Preview only renders correctly on GitHub.** Local markdown preview will not show badges/stats or the centered HTML layout — verify by pushing and viewing the profile.
- **Absolute URLs are load-bearing.** README references stats and repos by absolute URLs tied to the `ShresthSamyak` username. Changing the username silently breaks them.
- **Unverified facts are flagged in an HTML comment** at the bottom of `README.md` (repo slugs, PyPI names, inferred project descriptions). Resolve those before treating the profile as final.
- GitHub sanitizes README HTML — only a whitelisted subset of tags survives (no `<script>`, no `style` attributes). Keep to the badge / table / `<img>` / `<p align>` patterns already in use.

## SEO (requested feature)

The profile is optimized to be found by name **and** by tech skills. Keep these intact when editing:
- The H1 is the owner's name and the bold sub-line is the role — Google indexes these into the search snippet.
- The bio paragraph deliberately contains recruiter-queried keywords in plain text: LLM inference, RAG, Model Context Protocol (MCP), Computer Vision, PyTorch, JAX.
- Real open-source contributions (esp. the merged `google/jax` PR) are surfaced because recruiters search for *contributors to known repos*, not just keywords.
- Cross-linking the portfolio (shresthsamyak.com) and LinkedIn to this profile is what lets Google associate them — keep those links present.
