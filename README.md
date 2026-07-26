# allrouter-routine-coding-proof-log

A small public proof log for routine AI coding tasks.

## Model migration and relay verification community

Model IDs, provider defaults, and relay mappings change quickly. A successful HTTP 200 response does not prove that the requested model was preserved end to end.

### Current migration deadlines (verified on 2026-07-26)

- GitHub Models will be fully retired on 2026-07-30, including the model catalog, playground, inference API, and BYOK.
- GitHub Copilot will retire Gemini 3 Pro and Gemini 2.5 Pro on 2026-07-31.
- GitHub Models added a model-catalog endpoint, which is a useful reminder not to hard-code one static model list forever.
- Copilot is expanding automatic model selection, making task-based routing and fallback behavior a mainstream workflow.

Official notices:

- https://github.blog/changelog/2026-07-01-github-models-is-being-fully-retired-on-july-30-2026/
- https://github.blog/changelog/2026-07-01-upcoming-model-retirements-gemini-3-pro-and-gemini-2-5-pro/
- https://github.blog/changelog/2026-07-09-github-models-api-now-supports-model-catalog-endpoint/
- https://github.blog/changelog/2026-07-07-auto-model-selection-is-now-generally-available-in-copilot-in-visual-studio-2022/

Before trusting any compatible API or relay, check:

1. The requested model ID and the model field returned by the API.
2. Whether a retired ID raises a clear error, maps to a documented alias, or silently switches models.
3. Tool calling, structured output, context length, and error boundaries on one fixed test set.
4. Cache behavior and fallback behavior when the preferred route fails.
5. Cost and latency by task class, instead of sending every task to the most expensive model.
6. Whether your application can discover currently available models instead of relying only on hard-coded IDs.

Join the Telegram group for migration alerts, reproducible relay checks, and real AI coding routing tests: https://t.me/+13g2ma9APiU0YjRl

After joining, reply with **GitHub Models + your client or stack** to get the matching migration checklist.

Disclosure: this community is operated by the AllRouter team. Never post API keys, private code, full bills, or sensitive logs. Model IDs shown by a relay may be compatibility aliases and should not be treated as official vendor model names without vendor confirmation.

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

