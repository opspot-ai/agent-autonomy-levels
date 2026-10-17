# Evidence scorecard

Use one scorecard per named domain and configured review window. This is a manual evidence summary, not an automated evaluator. Record the policy version and keep source evidence in an approved private location; do not put secrets or private source material in a shared record.

## Evaluator review

- Evaluator identity or role:
- Independence from evaluated agent: confirmed / not independent / unknown
- Review status: pending / completed

| Dimension | Record | Result |
| --- | --- | --- |
| Evidence coverage | Samples observed, required sample count, dimensions covered, and gaps | unknown / insufficient / meets configured threshold |
| Documented preference alignment | Whether each applicable, recorded preference was followed; cite only an approved evidence reference | unknown / insufficient / meets configured threshold |
| Decision accuracy | Whether decisions matched the stated criteria or authorized review verdict | unknown / insufficient / meets configured threshold |
| Observed real outcomes | Whether actual work was held, shipped, successful, mixed, negative, or reversed, with evidence | unknown / insufficient / meets configured threshold |
| Cost and reversibility | Observed cost, reversibility method, and reversal or recovery evidence | recorded / unknown |
| Restrictions | Any current restriction or owner-reserved decision affecting the proposed scope | none found / restriction present / unknown |

## Interpretation

- No samples, missing evidence, or insufficient coverage means unknown and no advancement. Do not infer a perfect result from an empty window.
- Every evaluation recommendation requires review by an evaluator independent of the evaluated agent; the evaluated agent cannot serve as its own evaluator. Unset identity or role, pending review, or unset, unknown, or not-independent status cannot support a positive promotion recommendation.
- Coverage and preference alignment describe what was observed and whether documented preferences were followed. They do not establish decision accuracy or successful outcomes.
- Decision accuracy requires an applicable criterion or authorized review. Real outcome status requires evidence that the outcome actually occurred.
- Apply the configurable thresholds from the policy. Do not invent a threshold or claim the thresholds are scientifically validated.
- Negative evidence triggers the policy's configured hold or downgrade-review action. Any explicit restriction takes precedence over high scores or a high level.
- An adequate clean evidence window can support a recommendation only. Evaluation or review does not update the active level, scoring rules, tool credentials, or permissions.
- Record one recommendation: no change; hold and gather evidence; consider promotion; or review a downgrade. State the evidence and uncertainty behind it.
- Independent evaluation review is separate from scope-change approval. Only the explicitly authorized owner/reviewer or a specifically preapproved policy can approve an actual scope change. No agent may approve its own promotion or change its own scoring rules.
