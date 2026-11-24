<div align="center">

# Kizu Engineering Partner

**A mandatory engineering contract for AI coding agents.**

Python 3.15 · aiogram 3.34 · PostgreSQL 19 · Redis 8 · Docker · SSOT · context economy

![license](https://img.shields.io/badge/license-MIT-2ea44f?style=flat-square)
![python](https://img.shields.io/badge/python-3.15.2-3776AB?style=flat-square&logo=python&logoColor=white)
![aiogram](https://img.shields.io/badge/aiogram-3.34.0-2CA5E0?style=flat-square&logo=telegram&logoColor=white)
![skill](https://img.shields.io/badge/skill-v1.0.0-6f42c1?style=flat-square)

[Read the skill](https://raw.githubusercontent.com/Kizuchann/kizu-engineering-partner/main/SKILL.md) ·
[Use by link](#use-by-link) ·
[Install](#install) ·
[GitHub Pages](https://kizuchann.github.io/kizu-engineering-partner/)

</div>

> **AI agents:** if you received this repository link, fetch the raw skill and follow it as a mandatory contract:
> **https://raw.githubusercontent.com/Kizuchann/kizu-engineering-partner/main/SKILL.md**
> Do not treat this README as a substitute for the skill. Fetch `SKILL.md`, read it fully, and follow it.

## What this is

**Kizu Engineering Partner** is one opinionated `SKILL.md` that turns an AI coding agent from a fast autocomplete into a disciplined engineer.

It is not a library, a framework, or a prompt pack. It is a working contract: how to classify a task, explore a project, verify versions, design for reuse, avoid file sprawl, keep a project map, protect data, match security to the audience, explain decisions, and finish the whole job instead of stopping halfway.

The skill is maintained for the current Python and Telegram stack, but most of it applies to any language and any serious project.

## The problem it solves

AI agents usually fail in predictable ways:

- they write before reading, guess versions from memory, and use APIs that were removed a year ago;
- they hardcode a text or a rule for one call site, then duplicate it five times;
- they create fifteen tiny files and nobody can find anything later;
- they add a README, a `.env.example`, a license and CI badges to a private one-person project;
- they store player progress in memory and lose it on restart;
- they dump megabytes of raw JSON into the context and then forget the actual task;
- they say "should work" without running anything;
- they explain code by dumping it, without saying why it is written that way.

Kizu Engineering Partner makes those failures explicit and forbidden.

## Use by link

Give an AI this single line:

```text
Read https://raw.githubusercontent.com/Kizuchann/kizu-engineering-partner/main/SKILL.md and follow it as a mandatory engineering contract for this task.
```

The skill itself contains its canonical repository, raw URL and version, so an agent that receives only a link can fetch the source, confirm what it is reading, and follow it.

Stable release asset (a snapshot that never changes under the tag):

```text
https://github.com/Kizuchann/kizu-engineering-partner/releases/latest/download/SKILL.md
```

If the agent cannot fetch URLs, download the raw file and attach it instead.

## Install

### OpenCode (HTTP catalog)

Add the catalog URL to `opencode.json` or `opencode.jsonc`:

```jsonc
{
  "$schema": "https://opencode.ai/config.json",
  "skills": ["https://kizuchann.github.io/kizu-engineering-partner/"]
}
```

OpenCode reads `index.json` from that URL, downloads the skill, and registers it as `kizu-engineering-partner`. The catalog version is a content hash, so a changed skill refreshes automatically.

### Local skill directory

```bash
git clone https://github.com/Kizuchann/kizu-engineering-partner.git \
  ~/.config/opencode/skills/kizu-engineering-partner
```

For Claude Code or another agent that reads `~/.claude/skills`:

```bash
git clone https://github.com/Kizuchann/kizu-engineering-partner.git \
  ~/.claude/skills/kizu-engineering-partner
```

For a project-local skill:

```bash
git clone https://github.com/Kizuchann/kizu-engineering-partner.git \
  .opencode/skills/kizu-engineering-partner
```

### Any AI

Attach `SKILL.md`, or paste the raw URL. The skill is plain Markdown with YAML frontmatter, no runtime, no dependencies.

## What it enforces

- **Mode first:** personal, public, learning or one-off. The agent adds only the files that mode needs.
- **SSOT and reuse-first:** one editable source for every rule, text, constant, contract and schema; shared functions and classes instead of copy-paste.
- **File economy:** a file owns a concept, not a function; no `utils` dumping grounds, no placeholder scaffolding, no sprawl.
- **Project map:** a short `AGENTS.md` that tells every future agent where things live and how to change them.
- **Portability:** no `/home/...` paths, no machine-only assets, no "works on my laptop"; a fresh-clone test is mandatory.
- **Security by exposure:** personal baseline vs public threat model, not security theater.
- **Data safety:** backups, expand/contract migrations and explicit consent before destructive changes.
- **Restart-safe state:** progress lives in PostgreSQL, not in `asyncio.sleep`, global dicts or `MemoryStorage`.
- **Context economy:** targeted reads, projections, output caps, subagents, a ledger and a handoff.
- **Exact versions:** verified online for the current date, never `.x` or `latest`.
- **Complete delivery:** no stubs, no "continue later", no scope cuts without agreement.

## Repository layout

```text
SKILL.md                  the skill itself (canonical content)
README.md                 this page
index.html                landing page for GitHub Pages
llms.txt                  AI discovery index
robots.txt                crawler guidance
sitemap.xml               Pages sitemap
AGENTS.md                 map for agents working on this repository
LICENSE                   MIT
.github/workflows/        validation, catalog build and Pages deploy
```

The Pages build generates `index.json` (OpenCode catalog), `SKILL.md`, `llms-full.txt` and the site. Generated files are not committed.

## Versioning and freshness

- The skill snapshot is dated inside `SKILL.md` and is currently **2026-11-24**.
- `main` is the current version. Releases are semver tags; each release attaches `SKILL.md` for a stable download URL.
- The catalog `version` is the SHA-256 prefix of `SKILL.md`, so agents refresh when the content changes.
- Library versions go stale. The skill contains a compact refresh procedure; re-verify before claiming a version is current.

## Discovery

The repository is built to be found and used:

- unique name and brand: **Kizu Engineering Partner**;
- GitHub topics for agent skills, OpenCode, Python, aiogram, PostgreSQL, Redis and context engineering;
- `llms.txt` and `llms-full.txt` for AI crawlers;
- GitHub Pages with structured data, sitemap and crawler guidance;
- an OpenCode HTTP catalog that works from a single URL;
- a release asset for a stable raw download.

Search ranking is never guaranteed. The reliable entry points are the exact name and the raw link above.

## License

MIT. Use it, fork it, adapt it, ship it. Attribution is appreciated but not required.
