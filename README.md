# Yuki Takamura

Full-stack engineer working with TypeScript, Go and Rust.

Since June 2026 I've had autonomous coding agents build my own task-management app, [rapitas](https://github.com/takamurayuki/rapitas). I write about what the logs actually show, including the places where my own setup quietly broke.

## What the logs taught me

Over about four and a half months, the agents opened 930 PRs (761 merged) on a codebase that has grown to about 760k lines of TypeScript and Rust. A few findings:

- **A better number that meant nothing.** The fail rate of my multi-model AI code review dropped from 51% to 13%. Over the same period, two of the three reviewer models had stopped returning verdicts, and the gate kept passing diffs on a single vote. [Write-up (Japanese)](https://zenn.dev/taka8823/articles/2df36d66844c15)
- **`unknown` hides the cause.** Timeouts, refused calls, cooldowns and parse errors were all stored as the same `unknown`. Afterwards, there was no way to tell which one had happened.
- **Models disagree more than I expected.** When two or more models answered, they split on 23% of diffs (91 of 393).

My takeaway: check that the review or test actually ran before trusting its pass rate.

## Projects

**[rapitas](https://github.com/takamurayuki/rapitas)**: A local-first workbench where agents research, plan, implement and verify each task in its own git worktree. A lint and type-check gate runs before every commit or PR. Built with Next.js, Bun/Elysia and Tauri.

**[ime-live-converter](https://github.com/takamurayuki/ime-live-converter)**: A Windows IME with macOS-style live conversion, so text becomes kanji as you type, without pressing space. It uses Viterbi search over a dictionary, learns from your confirmed conversions in SQLite, and suggests a fix when conversion fails (`gmennasai` → ごめんなさい). Written in Rust and built on a low-level keyboard hook.

## Working on now

- Making "review incomplete" its own state, separate from fail, and recording why each model didn't answer
- Building the same app in React, Vue and Svelte with Claude Code, then comparing development time, code quality and test coverage (in progress)

## Writing

I publish in Japanese on [Zenn](https://zenn.dev/taka8823).

<!-- BLOG-POST-LIST:START -->
- [AIコードレビューの不合格率が51%→13%に。3モデル中2つは判定していなかった](https://zenn.dev/taka8823/articles/2df36d66844c15)
<!-- BLOG-POST-LIST:END -->

## Stack

TypeScript, React, Vue, Svelte, Next.js / Go, Node.js, Bun, PHP / Rust, Tauri, Electron / AWS, Docker, GitHub Actions
