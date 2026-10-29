# Developing the plugin

[Back to the README](../README.md) · [Usage guide](usage.md)

This repository contains one instruction package for Codex, OpenCode v2 Desktop
and standalone Antigravity IDE, plus Codex, OpenCode v2 and Antigravity CLIs. Its behavior is defined by
the skill entrypoints, shared references, and output templates. There is no
application runtime to build.

## Source ownership

| Concern | Canonical source |
| --- | --- |
| Incremental conversion, QA coordination, continuation, and response | [Incremental planning](../skills/incremental-plan/SKILL.md) |
| Standalone QA design and its output boundary | [Test design](../skills/test-design/SKILL.md) |
| Approvals, independent reviews, evidence, and retention | [Gate and review policy](../skills/incremental-plan/references/gates-and-reviews.md) |
| Check selection, expected outcomes, and certification design | [Verification design](../references/verification-design.md) |
| Incremental document structure | [Plan template](../skills/incremental-plan/assets/plan-template.md), [handoff template](../skills/incremental-plan/assets/handoff-template.md), and [orchestration prompt template](../skills/incremental-plan/assets/orchestration-prompt-template.md) |
| QA document structure | [QA template](../skills/test-design/assets/qa-plan-template.md) |
| Host capabilities and invocation identities | [Host compatibility](../references/host-compatibility.md) |
| Package identity and native metadata | [Codex manifest](../.codex-plugin/plugin.json) and [Antigravity manifest](../plugin.json) |

Change the canonical owner first, then update affected consumers. The README and
usage guide explain the current behavior to users; they should link to detailed
policy instead of maintaining another copy of it. Historical decisions belong
in the [development records](incremental-and-test-plans/README.md).

## Package contents

The runtime selection is exactly the twelve files in `paths` below. Keep relative
paths intact: the two canonical skills share templates and references. Source
checkouts and development records are not distribution artifacts. No executable
runtime, dependency installation, hooks, MCP server or third-party skill is required.

### Allowlisted export

This is an explicit development export, not an installer. Run from the source
root with Python's standard library. Replace the output argument with an unused
absolute directory outside source and installed paths, under an existing owned
parent. Do not use an installed cache as the source or destination. The recipe
refuses symlinked/escaping selections and occupied output, creates only the named
export, and checks staged and extracted content independently from source bytes.
It leaves failed/partial exports for inspection; cleanup requires its own authority.

```sh
rtk proxy python3 -B - "$PWD" "/absolute/unused/export" <<'PY_EXPORT'
from pathlib import Path
import os
import shutil
import stat
import sys
import zipfile

source = Path(sys.argv[1])
destination = Path(sys.argv[2])
paths = """.codex-plugin/plugin.json
plugin.json
skills/incremental-plan/SKILL.md
skills/incremental-plan/assets/plan-template.md
skills/incremental-plan/assets/handoff-template.md
skills/incremental-plan/assets/orchestration-prompt-template.md
skills/incremental-plan/references/gates-and-reviews.md
skills/test-design/SKILL.md
skills/test-design/assets/qa-plan-template.md
references/verification-design.md
references/third-party-notices.md
references/host-compatibility.md""".splitlines()
allowed = set(paths)
if not source.is_absolute() or source.resolve() != source:
    raise ValueError("Use a canonical absolute source root")
if not destination.is_absolute() or destination.parent.resolve() != destination.parent:
    raise ValueError("Use a canonical absolute destination parent")
if not destination.parent.is_dir() or os.path.lexists(destination):
    raise ValueError("Destination must be unused under an existing parent")
if destination == source or source in destination.parents or destination in source.parents:
    raise ValueError("Export must be outside the source tree")
for name in paths:
    selected = source / name
    if any(part.is_symlink() for part in [selected, *selected.parents]):
        raise ValueError(f"Symlinked selection: {name}")
    if not stat.S_ISREG(selected.stat().st_mode):
        raise ValueError(f"Not a regular file: {name}")
    selected.read_bytes()  # Prove readability before any export writes.

def inspect(root):
    entries = list(root.rglob("*"))
    if any(p.is_symlink() or not (p.is_file() or p.is_dir()) for p in entries):
        raise ValueError("Non-regular export entry")
    actual = {p.relative_to(root).as_posix() for p in entries if p.is_file()}
    expected_dirs = {str(parent) for name in allowed for parent in Path(name).parents if str(parent) != "."}
    actual_dirs = {p.relative_to(root).as_posix() for p in entries if p.is_dir()}
    if actual != allowed or actual_dirs != expected_dirs:
        raise ValueError(f"Unexpected or missing paths: {actual ^ allowed}; directories: {actual_dirs ^ expected_dirs}")
    for name in paths:
        if (root / name).read_bytes() != (source / name).read_bytes():
            raise ValueError(f"Source-byte mismatch: {name}")

destination.mkdir()
staged = destination / "bundle"
staged.mkdir()
for name in paths:
    output = staged / name
    output.parent.mkdir(parents=True, exist_ok=True)
    shutil.copyfile(source / name, output)
inspect(staged)
archive = destination / "bundle.zip"
with zipfile.ZipFile(archive, "x", zipfile.ZIP_DEFLATED) as bundle:
    for name in paths:
        bundle.write(staged / name, name)
with zipfile.ZipFile(archive) as bundle:
    if len(bundle.namelist()) != len(allowed) or set(bundle.namelist()) != allowed:
        raise ValueError("Unexpected archive members")
    if bundle.testzip() is not None:
        raise ValueError("Archive CRC failure")
    for name in paths:
        if bundle.read(name) != (source / name).read_bytes():
            raise ValueError(f"Archive-byte mismatch: {name}")
    extracted = destination / "extracted"
    extracted.mkdir()
    bundle.extractall(extracted)  # Only the verified exact relative allowlist.
inspect(extracted)
print(f"Verified {len(allowed)} files in {staged}, {archive}, and {extracted}")
PY_EXPORT
```

Before distribution, inspect the actual extracted file contents for private/local
planning material, personal paths, credentials, VCS metadata and undeclared
dependencies. Exact membership and byte correspondence are separate checks:
matching a contaminated source alone is insufficient. Validate resource links and
anchors against this selection, with generated-output placeholders distinguished.
Do not distribute this guide, evaluation data or the rest of the checkout.

On disposable synthetic copies, prove that a missing
`references/verification-design.md` fails resource closure; a forbidden
`docs/internal-note.md` present in both staging and archive fails allowed-content
validation despite byte correspondence; and an altered extracted skill byte fails
correspondence. The intact bundle must pass all three checks. These are package
contract controls, not live-model results or prose-matching tests.

## Static checks

Run these from the repository root, following the host's shell conventions.
Locate Skill Creator in the active host inventory and replace
`<skill-creator-directory>` with its actual path before running the validators:

```sh
rtk proxy python3 -B "<skill-creator-directory>/scripts/quick_validate.py" skills/incremental-plan
rtk proxy python3 -B "<skill-creator-directory>/scripts/quick_validate.py" skills/test-design
rtk proxy git --no-optional-locks -c diff.autoRefreshIndex=false diff --check
```

Skill Creator is a development tool, not a runtime dependency. If its validator
or a required dependency is unavailable, report the missing check rather than
silently installing tooling or treating a substitute as equivalent.

Also check the contracts that skill frontmatter validation does not cover:

- Parse both manifests and skill frontmatter; confirm identity/version/description
  agreement, exactly two entrypoints and unchanged discovery descriptions/implicit
  invocation policy. Validate root `plugin.json` against the current official
  [Antigravity schema](https://antigravity.google/schemas/v1/plugin.json); the
  selected four fields are strings and omit Codex-only UI metadata. Preserve the
  Codex manifest and skill metadata byte-for-byte for this compatibility change.
- Resolve component paths, resource links, and anchors within the package.
  Distinguish shipped resources from placeholders for generated output.
- Inspect the complete proposed change, including relevant new files, for stale
  consumers, unsupported claims, privacy leaks, and unintended dependencies.
- For discovery-metadata changes, compare the skill catalog and descriptions,
  and desk-check intended, excluded, adjacent, and ambiguous requests.

Run focused checks while editing and the full relevant deterministic checks once
on the settled candidate. Repeat checks only when their inputs change or new
evidence requires it. These checks establish source structure and consistency;
they do not prove model behavior or installed usability.

## Behavioral evaluation and installation evidence

[tests/scenarios.md](../tests/scenarios.md) defines fresh-agent behavioral
exercises. It is not an automated test suite, and the presence of a scenario is
not a passing result.

The controller-only [native acceptance runbook](../tests/native-acceptance.md)
selects the desktop and three CLI surfaces, producer/receiver dependencies,
authorization, effective isolation/capture and recovery. It is outside the runtime
bundle; its scenario definitions are not results. Do not include private local
plans, machine paths or evaluation records in a public change.

Live-model evaluations require explicit authorization. Use synthetic inputs,
keep evaluator expectations out of the subject's context, and inspect actual
actions and saved outputs. Preserve the candidate, conditions, results, failures,
and untested scope in local evidence outside tracked source. Reuse applicable
results and renew only affected cases.

Keep these kinds of evidence separate:

| Evidence | What it can establish |
| --- | --- |
| Static validation | Metadata, resource structure, and checked source contracts |
| Source-based evaluation | Observed actions and outputs for the supplied instructions and fixture |
| Native installation and discovery | Delivered-file correspondence and skills exposed by that host |
| Installed invocation and desktop use | Behavior actually exercised through the installed entrypoint or UI |
| Executor or provider results | The particular implementation or external outcome that was observed |

A successful install or discovery result does not establish automatic routing.
An old evaluation applies only where its candidate and conditions still match.
Do not turn historical observations into a current general acceptance claim.

## Maintaining the documentation

Keep the README focused on choosing a skill, getting started, expected outputs,
and the next step. Put recurring user tasks in the usage guide and contributor
checks here. Explain an option where a reader needs to choose it, and keep
commands, identifiers, defaults, permission boundaries, and limitations aligned
with the canonical sources.

Review examples against the current skills. Keep development history out of the
getting-started path, and label archived records as history. When polishing the
prose, preserve technical meaning, conditions, and exact commands.

Selected execution-guidance practices are adapted from Superpowers. Attribution
and its license notice are retained in
[third-party notices](../references/third-party-notices.md#superpowers).
