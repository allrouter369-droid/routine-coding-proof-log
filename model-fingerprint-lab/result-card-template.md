# Public Model Fingerprint Result

- Run ID: `{{run_id}}`
- Collected at: `{{collected_at}}`
- Declared model: `{{declared_model}}`
- Test set: `{{test_set_version}}`
- Verdict: **{{match / uncertain / mismatch / insufficient}}**
- Mean JSD: `{{mean_jsd}}`
- Comparable cells: `{{comparable_cells}}`
- Split-half JSD: `{{split_half_jsd}}`
- Latency P50 / P95: `{{latency_p50}} / {{latency_p95}}`
- Error rate: `{{error_rate}}`

Reproduction command: `{{reproduction_command}}`

Full redacted report: {{report_url}}

This result is statistical evidence, not proof of provider intent. Model
updates, quantization, system prompts, and routing changes may affect the
fingerprint. Repeat a mismatch result on another day before drawing a strong
conclusion.
