# Third-party notices

## Superpowers

Selected execution practices are adapted from [Superpowers](https://github.com/obra/superpowers), copyright (c) 2025 Jesse Vincent, distributed under the MIT license reproduced below.

The original adaptation's selected source is package version **6.4.2**, inspected on **2026-10-18**. These SHA-256 values identify the inspected package bytes:

| Source | SHA-256 |
| --- | --- |
| [Execution guidance](https://github.com/obra/superpowers/blob/main/skills/executing-plans/SKILL.md) — `skills/executing-plans/SKILL.md` | `f38e8f2ddcf079f65493adc713c1fed78421dfaf5f4dbf6b3a6b2b1d95466e71` |
| [Plan-authoring guidance](https://github.com/obra/superpowers/blob/main/skills/writing-plans/SKILL.md) — `skills/writing-plans/SKILL.md` | `a6c67c1900064347c2a329990dd3c555657c51c3ec53b259a08aa01a2c26139a` |
| [Implementer guidance](https://github.com/obra/superpowers/blob/main/skills/subagent-driven-development/implementer-prompt.md) — `skills/subagent-driven-development/implementer-prompt.md` | `81dd9d5a3fb0b09b96b5829f03b9796842f3199ef7591d1ba1c2db2a515f64d0` |
| [License](https://github.com/obra/superpowers/blob/main/LICENSE) — `LICENSE` | `a37e0e9697144819e1d965176ac4ae5bc3fa02d11e7812036bbcadf6dafe2400` |

The [TDD guidance](https://github.com/obra/superpowers/blob/main/skills/test-driven-development/SKILL.md) additionally informed the portable TDD baseline. The inspected source was package **7.0.1**, on **2026-11-04**, with `skills/test-driven-development/SKILL.md` SHA-256 `64b03fce4aee5a97a93160cea8111f3ba13a17b7c001db4bd5836d67fd10705d`. Local applicability, exceptions and work-preservation rules are maintained in [verification design](verification-design.md#test-driven-implementation); this records source provenance, not a required or guaranteed receiver version.

The upstream URLs use mutable `main` references for discovery; they do not assert an immutable upstream revision. The selected versions and hashes identify the respective adaptation sources. [Upstream package metadata](https://github.com/obra/superpowers/blob/main/.codex-plugin/plugin.json) identifies the project package.

The local adaptation carries exact-brief start/resumption, meaningful execution-deviation records, conditional producer/consumer contract comparison from plan-authoring guidance and executor result self-review from implementer guidance in the [gate policy](../skills/incremental-plan/references/gates-and-reviews.md#execution-discipline-carried-by-a-handoff). Observed-result comparison and mismatch interpretation live in [verification design](verification-design.md#independent-expectations-and-test-sensitivity). The [incremental handoff](../skills/incremental-plan/assets/handoff-template.md), [QA handoff](../skills/test-design/assets/qa-plan-template.md#copy-ready-preparation-handoff) and [orchestration prompt](../skills/incremental-plan/assets/orchestration-prompt-template.md) carry the applicable duties to external executors. Exact future interfaces remain provisional until concrete preparation, and self-review precedes rather than replaces the required independent reports.

These are locally maintained adaptations with existing gates, review obligations, evidence retention and separate action permissions retained. Attribution imposes no Superpowers runtime dependency, scripts or installation requirement, and does not relicense unrelated original repository material. The [optional TDD policy](../skills/incremental-plan/references/gates-and-reviews.md#optional-superpowers-tdd) prefers only a compatible, permitted exposed TDD skill and retains the self-contained fallback. Future adaptations require deliberate source comparison and scoped review; there is no automatic upstream synchronization.

### Upstream MIT license

```text
MIT License

Copyright (c) 2025 Jesse Vincent

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
```
