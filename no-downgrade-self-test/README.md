# No-Downgrade Self-Test for GLM-5.2 Coding Routes

This is a small, repeatable preflight check for GLM-5.2 coding routes.

It does not prove that a service is permanently reliable, official, or never degraded. It helps catch obvious routing, model-quality, and verification problems before putting a route into routine coding work.

## What This Checks

The suite checks whether a route can:

- keep a small edit small;
- admit missing evidence;
- notice hidden behavior risk;
- avoid inventing logs;
- stop on ambiguous long-context security work.

## What This Does Not Claim

Do not use this suite to claim:

- guaranteed no degradation;
- unlimited capacity;
- production SLA;
- benchmark superiority;
- replacement for a main coding model.

Use it to record concrete outputs, evidence, and failure signs.

## Files

- `cases.json`: five self-test cases.
- `results_template.csv`: result recording template.
- `run_checklist.md`: manual run and review checklist.
- `sample_outputs/`: example result records.

## Acceptance Rule

A route is not accepted because it gives a confident answer.

It is acceptable for a specific routine workflow only when:

- the output stays inside the requested scope;
- the verification evidence is independent;
- failure cases are recorded;
- risky changes trigger human review;
- the route behaves consistently across repeated runs.

## How To Run

1. Pick one route / endpoint / model name.
2. Run all five prompts from `cases.json`.
3. Save the raw output or hash of each output.
4. Fill one row per case in `results_template.csv`.
5. Mark each case as `pass`, `partial`, or `fail`.
6. Add human review notes before using the route in real work.

## Public-Platform Copy Boundary

Safe wording:

> This is a repeatable self-test for routine coding routes. It does not prove permanent no-downgrade behavior.

Avoid:

> This proves the route is never downgraded.

## Related Proof Log

Current proof-log issue:

https://github.com/allrouter369-droid/routine-coding-proof-log/issues/5
