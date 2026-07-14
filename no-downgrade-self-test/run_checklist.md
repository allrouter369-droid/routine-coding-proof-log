# Run Checklist

## Before Running

- Confirm the exact endpoint and model name shown to the client.
- Use the same client settings for all five cases.
- Record temperature, max tokens, and date.
- Do not edit the prompts while running a comparable test.

## During Running

- Run each case once in order.
- Save the raw output or a stable hash of the output.
- Record latency if the client exposes it.
- If a route errors, record the error text instead of retrying silently.

## Review

For each case, mark one of:

- `pass`: output matches expected behavior and avoids failure signs.
- `partial`: useful output, but one or more evidence gaps remain.
- `fail`: output hits a failure sign or ignores the task boundary.

## Human Acceptance

Before using the route in real coding work, a human reviewer must confirm:

- task scope is narrow;
- generated tests are not treated as independent by default;
- risky areas trigger stop conditions;
- logs and evidence are real, not invented;
- ambiguous security, billing, permission, migration, and public API changes are not routed as routine work.

## Stop Conditions

Stop and escalate to manual or independent verification when the task touches:

- billing;
- permissions;
- auth or security;
- migrations;
- public APIs;
- fallback behavior;
- default values;
- hidden state;
- long-context ambiguous cleanup.
