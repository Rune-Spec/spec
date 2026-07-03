# AGENTS.md - Project Context for AI Coding Agents

Single source of durable project context. Codex reads this file directly;
Claude Code imports it via the `@AGENTS.md` line in `CLAUDE.md`. Keep it lean
and self-contained (no imports); edit this file, not `CLAUDE.md`, when project
context changes.

## What this repo is

The Rune specification (Runespec): an open specification for packaging AI
agents as reusable, deployable units. Public repository under the Apache-2.0
license (`LICENSE`).

## Current state

Early-stage: the specification text has not landed in the tree yet, and
`LICENSE` is the only tracked content file. No schema or validator exists yet;
if either lands, it may live here or in a sibling implementation repository -
that decision is not made.

## Build / test / lint

None. This is a prose/markdown specification repo with no build system, test
suite, or linter. If a schema or validator implementation lands in this repo,
record its single canonical `check` command here.

## Conventions

- Spec prose is markdown. Use hyphens, never em dashes; do not use markdown
  blockquotes (`>` prefix).
- Conventional Commits 1.0.0 on every commit (`docs:`, `feat:`, `fix:`,
  `chore:`, ...), subject imperative, lowercase, <= 72 chars. Branch names
  follow `<type>/<kebab-summary>`.
- SemVer 2.0.0 for releases; tags `v<X.Y.Z>` are immutable.
- Public repo: tracked files carry zero personal, company, or
  infrastructure-specific context. Use generic placeholders (example.com,
  `<your-agent>`) in all examples.

## Escape hatches (never tracked)

`CLAUDE.local.md` (Claude Code; loads in addition to `CLAUDE.md`) and
`AGENTS.override.md` (Codex; replaces `AGENTS.md` entirely when present, so
copy anything still needed into it) are personal, per-machine files. Both are
gitignored and must stay untracked.
