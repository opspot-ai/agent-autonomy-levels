# Decision log template

Create one record for each material decision. Use null or unknown when a fact is not available. Keep secrets and private source material out of shared records; reference evidence only through an approved location.

~~~json
{
  "decision_id": "<unique local identifier>",
  "timestamp": null,
  "domain": "<named domain>",
  "active_level": null,
  "grant_reference": null,
  "decision": "<one sentence>",
  "classification": "reversible|hard_to_reverse|uncertain",
  "uncertainty_action": "proceed_within_grant|escalate|held",
  "preference_evidence": {
    "reference": null,
    "alignment": "matched|mismatched|unknown"
  },
  "cost": {
    "kind": "time|money|resource|none|unknown",
    "amount": null,
    "unit": null,
    "basis": "observed|estimated|unknown"
  },
  "reversal": {
    "possible": null,
    "method": null
  },
  "work_status": "proposed|held|shipped",
  "observed_outcome": "unknown|successful|mixed|negative|reversed",
  "outcome_evidence": null,
  "scope_change_requested": false,
  "scope_change_approval": null
}
~~~

Use shipped only when evidence shows the work was actually delivered or performed. A held item is not a shipped outcome. Keep unknown outcomes unknown until evidence is available.
