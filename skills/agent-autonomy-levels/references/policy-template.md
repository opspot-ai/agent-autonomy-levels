# Policy and configurable thresholds

Copy this template into the policy record for one domain, then replace placeholders and null values through the authorized policy owner. Define units or a scoring rubric for any threshold before using it. Thresholds are local configuration choices, not scientifically validated standards.

~~~json
{
  "schema_version": "1",
  "policy_owner": "<role or identifier>",
  "domain": "<one named domain>",
  "review_window": null,
  "current_level": null,
  "allowed_actions": [],
  "limits": {
    "time": null,
    "resource": null,
    "external_effects": null
  },
  "excluded_actions": [],
  "owner_reserved_decisions": [],
  "explicit_restrictions": [],
  "decision_classification": {
    "reversible_criteria": "<define>",
    "hard_to_reverse_criteria": "<define>",
    "uncertain_classification": "escalate"
  },
  "evidence_thresholds": {
    "minimum_sample_count": null,
    "minimum_coverage": null,
    "minimum_documented_preference_alignment": null,
    "minimum_decision_accuracy": null,
    "minimum_successful_real_outcomes": null
  },
  "insufficient_evidence_action": "unknown_no_advance",
  "negative_evidence_action": "hold_or_review_downgrade",
  "scope_change_authority": "<explicitly authorized owner/reviewer or specifically preapproved policy>",
  "evaluation_review": {
    "required": true,
    "evaluator_role_or_identifier": "<role or identifier>",
    "independence_from_evaluated_agent": "<confirmed / not independent / unknown>",
    "independence_requirement": "independent_of_evaluated_agent",
    "independence_must_be_confirmed_for_positive_promotion": true
  },
  "agent_may_change_own_level": false,
  "agent_may_change_own_scoring_rules": false,
  "evaluation_changes_active_scope": false,
  "evaluation_changes_tool_credentials": false,
  "evaluation_changes_scoring_rules": false
}
~~~

## Apply the policy

- A null threshold is undefined. Do not treat it as zero or as a pass; have the policy owner define the measure and required evidence before using it.
- Zero samples, missing evidence, or insufficient coverage are unknown and do not support advancement.
- Each recommendation requires review by an evaluator independent of the evaluated agent. Record evaluator identity or role and confirm independence in the evaluation and scope-review records. An evaluated agent cannot serve as its own evaluator; unset or unknown independence cannot support a positive promotion recommendation.
- Keep coverage and documented preference alignment separate from decision accuracy and observed real outcomes.
- Negative evidence follows the configured hold or downgrade-review rule. An explicit restriction overrides every score and level.
- Independent evaluation review and recommendation do not authorize a scope change or change the active level, tool credentials, or scoring rules. Only the explicitly authorized owner/reviewer or a specifically preapproved policy may approve an actual scope change.
- No agent may promote itself or modify its own scoring rules. Host permissions and current restrictions still apply.
- A clean evidence window does not create publication, spending, account, or other authority.
- These are policy-recording instructions; the template does not automatically enforce evaluator independence or scope approval.
