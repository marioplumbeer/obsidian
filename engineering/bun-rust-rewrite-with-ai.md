---
title: What Can We Learn from Bun's Rapid Rust Rewrite with AI?
date: 2026-07-16
tags: [engineering, ai-coding, migration, rust, claude-code, agents]
---

# What Can We Learn from Bun's Rapid Rust Rewrite with AI?

## Summary
Bun (the JS/TS runtime with 22M monthly downloads, depended on by Claude Code, OpenCode, and hosted by Vercel/Railway/DigitalOcean) rewrote its entire 535,496-line Zig codebase to Rust in 11 days using Claude and a tool called Fable, orchestrated by creator Jarred Sumner. The rewrite was previously infeasible — Sumner estimated ~1 year of dedicated engineering work with zero user-facing improvements in the meantime — but AI-assisted parallel agent work compressed it into less than two weeks.

Source: [The Pulse: What can we learn from Bun's rapid Rust rewrite with AI?](https://newsletter.pragmaticengineer.com/p/the-pulse-what-can-we-learn-from-07f) (Gergely Orosz & Ivan Klaric, Pragmatic Engineer, 16 July 2026)

---

## Decisions & insights

### Why rewrite at all
Zig isn't memory-safe. Sumner had documented recurring memory leaks, crashes, and heap-out-of-bounds writes despite patching the Zig compiler and adding end-to-end memory leak tests. Rust's compile-time borrow checker offered a way to eliminate use-after-free, double-free, and initialization bugs without runtime failures. Sumner: "Correctly handling the lifetimes of garbage-collected values and manually-managed values has been a major source of stability issues."

### The process (11 days total)
1. **Prep (3 hrs):** Sumner spent 3 hours discussing Zig→Rust pattern mapping with Claude, producing a 600-line `PORTING.md` ground-rules doc (no `tokio`/`rayon`/`hyper`/`async-trait`/`futures`, no async functions — callbacks/state machines instead).
2. **Trial run:** 3 sample files rewritten, each reviewed adversarially in two separate Claude sessions.
3. **Distributed work (~1 day to stabilize):** 64 agents split across independent files; git conflicts from simultaneous commits forced restricting agents to file-specific commits and reorganizing into 4 worktrees × 16 Claude instances.
4. **Parallel execution (~2 days):** 535,496 lines rewritten across 6,500 commits, each passing two adversarial reviews before merge.
5. **Compiler error resolution (~12 hrs):** ~16,000 initial compiler errors fixed crate-by-crate (cargo check → group by file → fix → 2 adversarial reviews → designated fixer applies corrections) — much of this ran overnight unattended.
6. **Local testing (~2 days)** then **CI suite completion (~3 days)** to reach a fully green pipeline.

### Cost
5.9B uncached input tokens + 690M output tokens + 72B cached input reads = **$165,000** at API list pricing. Mitchell Hashimoto's take: "There's absolutely no way an engineer with that salary would've been able to achieve the milestones Claude did in 11 days" — even split across several engineers' salaries, it wouldn't buy equivalent output in 11 days. Cost could drop further via cheaper models for coding/review (reserving expensive models for planning) and better caching.

### Conditions that made it work
1. An engineer with deep codebase knowledge and strong personal motivation (Sumner, the creator).
2. An exceptionally robust existing test suite — the confidence signal that let the team trust the rewrite.
3. Willingness to spend a large token budget without a guaranteed outcome.

---

## Key takeaways
1. AI-assisted rewrites can compress ~1-year efforts into ~2-week ones, but only when paired with strong existing test coverage and a domain expert directing the work — it's not a free lunch for under-tested codebases.
2. Adversarial review (2 independent reviews per commit/crate) was the recurring safety mechanism at every stage, not just a one-time check.
3. Parallel agent work needs explicit guardrails (restricted git commands, worktree isolation) or agents collide with each other.
4. This may make previously-uneconomical rewrites (legacy language migrations, memory-unsafe → memory-safe transitions) newly viable cost/time trade-offs.

## References
- [The Pulse: What can we learn from Bun's rapid Rust rewrite with AI? (Pragmatic Engineer)](https://newsletter.pragmaticengineer.com/p/the-pulse-what-can-we-learn-from-07f)
