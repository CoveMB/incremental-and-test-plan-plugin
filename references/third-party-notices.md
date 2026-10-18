# Third-party notices

## Superpowers

Selected execution practices are adapted from [Superpowers](https://github.com/obra/superpowers), copyright (c) 2025 Jesse Vincent, distributed under the MIT license reproduced below.

The selected source is package version **6.4.2**, inspected on **2026-10-18**. These SHA-256 values identify the inspected package bytes:

| Source | SHA-256 |
| --- | --- |
| [Execution guidance](https://github.com/obra/superpowers/blob/main/skills/executing-plans/SKILL.md) — `skills/executing-plans/SKILL.md` | `f38e8f2ddcf079f65493adc713c1fed78421dfaf5f4dbf6b3a6b2b1d95466e71` |
| [Plan-authoring guidance](https://github.com/obra/superpowers/blob/main/skills/writing-plans/SKILL.md) — `skills/writing-plans/SKILL.md` | `a6c67c1900064347c2a329990dd3c555657c51c3ec53b259a08aa01a2c26139a` |
| [License](https://github.com/obra/superpowers/blob/main/LICENSE) — `LICENSE` | `a37e0e9697144819e1d965176ac4ae5bc3fa02d11e7812036bbcadf6dafe2400` |

The upstream URLs use mutable `main` references for discovery; they do not assert an immutable upstream revision. The selected version and hashes identify this adaptation's source. [Upstream package metadata](https://github.com/obra/superpowers/blob/main/.codex-plugin/plugin.json) identifies the project package.

The local adaptation carries exact-brief start/resumption and meaningful execution-deviation records in the [gate policy](../skills/incremental-plan/references/gates-and-reviews.md#execution-discipline-carried-by-a-handoff), and observed-result comparison and mismatch interpretation in [verification design](verification-design.md#independent-expectations-and-test-sensitivity). The [incremental handoff](../skills/incremental-plan/assets/handoff-template.md) and [QA handoff](../skills/test-design/assets/qa-plan-template.md#copy-ready-preparation-handoff) carry the applicable duties to external executors. Plan-authoring guidance informed the development plan's task structure.

These are locally maintained adaptations with existing gates, review obligations, evidence retention and separate action permissions retained. Attribution imposes no Superpowers runtime dependency, workflow invocation, scripts or installation requirement, and does not relicense unrelated original repository material. Future adaptations require deliberate source comparison and scoped review; there is no automatic upstream synchronization.

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
