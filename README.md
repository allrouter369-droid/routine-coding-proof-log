# allrouter-routine-coding-proof-log

A small public proof log for routine AI coding tasks.

What this repo records:

- Task input (small, well-scoped).
- Model used (main or routine lane).
- Output diff or patch.
- Test / lint / local run result.
- Manual review notes.
- Failure cases as boundary examples.

Why:

- Most "AI saves cost" claims do not survive a code review.
- This log only counts routine work that passes tests, lint, or a runnable example.
- Failure cases are kept on purpose. They show where routine routing should stop.

How to use this repo:

- One issue per task.
- Use the `routine-task` issue template.
- Keep prompts and outputs short and concrete.

Public experiments:

- [Model Fingerprint Lab](model-fingerprint-lab/README.md): fixed protocol,
  decision thresholds, public report schema, and result-card template.

## 2026-06-27 note: small refactors are not always routine

Today’s proof log update:

- README cleanup: safe enough because the diff is mostly wording.
- Issue template: useful as a draft, but generic placeholder text still needs review.
- Request-routing helper refactor: risky. The patch looked cleaner, but changed a fallback path and missed an empty-config edge case.

Current routing rule:

1. The task can be explained in one sentence.
2. The diff should stay small.
3. There is a test or clear manual check.
4. Review is cheaper than rewriting.

If two of those are false, keep it on the stronger model or split the task.

Related write-ups:

- DEV.to: https://dev.to/zephyre-labs/keep-coding-after-claude-code-limits-route-routine-tasks-by-risk-5871
- Hashnode: https://routine-coding-notes.hashnode.dev/keep-coding-after-claude-code-limits-route-routine-tasks-by-risk
- Medium: https://medium.com/@allrouter369/three-routine-coding-tasks-i-would-route-differently-next-time-3e75ec65b954
