# Canonical ADR references

ADRs that define ports, the kernel, or composition stay in the `platform`
repo. They are referenced here, never copied (ADR-0129 §2/§7).

| ADR | title | where |
|---|---|---|
| 0098 | One Language, Multiple Interpreters | platform `project/adrs/` |
| 0128 | Target Repos | platform `project/adrs/` |
| 0129 | Project-docs Topology | platform `project/adrs/` |

## ADRs this repo owns

None — the harness is a measurement tool with no decisions of its own. It was
split out of `platform/bench` in ADR-0128.

Note: `crates/bench` (the `handl-bench` criterion suite) is a **different**
thing and stays in `host`; it is a Cargo bench target, not this harness.
