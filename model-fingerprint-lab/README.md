# Public Model Fingerprint Lab

This directory contains a reproducible protocol for checking whether an
OpenAI-compatible endpoint remains behaviorally consistent with a declared
model and with itself over time.

The result vocabulary is deliberately limited to:

- `match`: statistically consistent with the reference.
- `uncertain`: collect more samples or repeat later.
- `mismatch`: substantially different; investigate possible causes.
- `insufficient`: not enough valid comparable samples.

A mismatch is not proof of fraud. Model updates, quantization, hidden system
prompts, reasoning fallbacks, and load balancing can all move a behavioral
fingerprint.

## Reproduce the method

The first implementation used by this protocol is the MIT-licensed
[ToseaAI/llm-fingerprint-detector](https://github.com/ToseaAI/llm-fingerprint-detector).
Keep API keys in local environment variables. Do not paste keys into issues,
forms, reports, or chat messages.

```bash
git clone https://github.com/ToseaAI/llm-fingerprint-detector.git
cd llm-fingerprint-detector
npm install
npm run build
export LLM_FINGERPRINT_API_KEY='your-local-key'
node dist/cli.js fingerprint \
  --base-url https://your-endpoint.example.com/v1 \
  --model your-model-id \
  --out observed.json
```

The default baseline protocol is 8 cells x 25 samples. A stronger conclusion
requires a second run on another day. See [experiments.json](experiments.json)
for the fixed experiment definitions.

## Public report requirements

Every public result should include:

- collection time and declared model ID;
- test-set version and comparable-cell count;
- mean and split-half Jensen-Shannon divergence;
- invalid-sample and error rates;
- an exact reproduction command;
- limitations and warnings.

Use [report-schema.json](report-schema.json) and
[result-card-template.md](result-card-template.md). Raw API keys, account data,
billing data, and private prompts must never be committed.

## Current status

Protocol version `0.1` is public. No AllRouter match or mismatch result is
claimed in this repository until a live run is completed and the redacted
report passes the schema.

Method write-up:
[Is That API Really Serving the Model It Claims?](https://dev.to/zephyrelabs369/is-that-api-really-serving-the-model-it-claims-a-reproducible-fingerprint-test-5d0f)

Re-run the same workflow on AllRouter:
[campaign entry](https://allrouter.ai/register?aff=qjpC&utm_source=github&utm_campaign=fingerprint_lab&utm_content=AR-FP-001)

