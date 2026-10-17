# Agent Autonomy Levels

A compact, generic skill and set of templates for defining, recording, and reviewing explicit agent decision scope.

These materials describe possible grants. A level is not a trust certificate, a capability switch, or permission that applies everywhere.

## Contents

- The installable skill: [SKILL.md](skills/agent-autonomy-levels/SKILL.md)
- The ten-level scope matrix: [levels.md](skills/agent-autonomy-levels/references/levels.md)
- A configurable policy template: [policy-template.md](skills/agent-autonomy-levels/references/policy-template.md)
- An evidence scorecard: [eval-scorecard.md](skills/agent-autonomy-levels/references/eval-scorecard.md)
- A decision record template: [decision-log.md](skills/agent-autonomy-levels/references/decision-log.md)
- A promotion and demotion review: [scope-review.md](skills/agent-autonomy-levels/references/scope-review.md)

## Install the skill

From the repository root, this copies only the skill folder. Its references stay beside the skill after installation. The command stops if the destination exists, including when it is a dangling symlink.

~~~sh
set -eu
source_dir="./skills/agent-autonomy-levels"
skill_home="${CODEX_HOME:-$HOME/.codex}/skills"
target="$skill_home/agent-autonomy-levels"

if [ ! -d "$source_dir" ]; then
  printf '%s\n' "Skill source directory not found: $source_dir" >&2
  exit 1
fi
if [ -e "$target" ] || [ -L "$target" ]; then
  printf '%s\n' "Refusing to replace existing target: $target" >&2
  exit 1
fi
mkdir -p "$skill_home"
cp -R "$source_dir" "$target"
~~~

Invoke it explicitly with a request such as:

~~~text
$agent-autonomy-levels Help define a bounded, per-domain scope and review its evidence.
~~~

## Manual use

1. Name one domain and record the currently approved actions, exclusions, limits, and reserved decisions.
2. Treat reversible choices separately from hard-to-reverse choices. If classification is uncertain, escalate.
3. Use only documented, relevant preferences. If none are available, record preference alignment as unknown.
4. Log material decisions, cost, reversibility, evidence, and whether work was proposed, held, or actually shipped.
5. Review evidence dimensions separately: coverage, documented preference alignment, decision accuracy, and observed real outcomes.
6. Have each evaluation recommendation reviewed by an evaluator independent of the evaluated agent. Record the evaluator's identity or role and independence in the policy, scorecard, and scope-review records. The evaluated agent cannot serve as its own evaluator; unset or unknown independence cannot support a positive promotion recommendation.
7. Keep independent evaluation review separate from scope-change approval. Only the explicitly authorized owner/reviewer or a specifically preapproved policy may approve an actual scope change. Review or recommendation does not change the active level, tool credentials, or scoring rules.

## Limits

This repository provides written guidance and static templates only. It has no automated evaluator, scoring, enforcement, live autonomy tests, or host-permission validation. It makes no safety guarantee. Thresholds are configurable and have not been scientifically validated. Zero or insufficient evidence stays unknown and cannot support advancement. Even a clean evidence window only supports a recommendation; it grants no publication, spending, account, or other authority. Explicit restrictions and actual host permissions continue to apply at every level, including L10.
