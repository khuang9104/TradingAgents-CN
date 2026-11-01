# PR1 offline test evidence

Tested head: `51aeb6208679077a8c8069661a0fb816fa213e6f`. Upstream baseline: `51060a7682cf51810b4bc3a704829438d18cd8dc`.

| Run | Passed | Business failures | Errors / skips |
|---|---:|---:|---:|
| Full PR1 regression | 95 | 0 | 0 / 0 |
| Same-input upstream comparison | 7 normal controls | 26 expected BusinessMismatch | 0 / 0 |
| Same-input PR1 comparison | 33 | 0 | 0 / 0 |

The 95 regression identities include the original 83 C1/C2/state-merge cases
plus 12 actual task-entry cases. Comparison uses identical test bytes, fake
inputs, and installed package versions on both complete source checkouts.
Only call-phase BusinessMismatch failures are accepted as reproductions.
Complete normal Web reports and 60 business-field equalities are checked.

Models, tools, storage, auth, and configuration boundaries are fakes. Actual
product method bodies, LangGraph 0.4.8 scheduling/reducers, workflow compilation,
node wrappers, and FastAPI serialization execute. Provider-registering startup,
application lifespan, real models, real trades, and real services are not run.
See summary.json for exact dependency/test hashes and zero-attempt guards.

JUnit files and full logs are included for all three runs. Only local workspace
paths and text encoding/line endings were normalized for publication; source
and published SHA256 digests are recorded in summary.json. comparison.json
records each case's equal input digest, baseline outcome and business checks,
and patched outcome and checks. The baseline's nonzero exit is intentional.

Reproduce using the committed runner and README at the tested code SHA:

- [Runner](https://github.com/khuang9104/TradingAgents-CN/blob/51aeb6208679077a8c8069661a0fb816fa213e6f/tests/offline/run_pr1.py)
- [Commands and test boundaries](https://github.com/khuang9104/TradingAgents-CN/blob/51aeb6208679077a8c8069661a0fb816fa213e6f/tests/offline/PR1.md)

These evidence files live on a separate Fork branch. They are not part of the
PR1 code diff. PR1 contains only C1, C2 and necessary state merging; task
cancellation, queue/worker, recovery and resume changes remain separate.
