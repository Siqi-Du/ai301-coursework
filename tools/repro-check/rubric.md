# Rubric: is this reproduction package ready to post?

<!--
THIS IS THE PART YOU WRITE. The skill in SKILL.md executes whatever
checks you define here. It ships empty on purpose: the judgment is your
work.

A filled rubric must contain:

1. At least one row in the checks table. Each row needs all four
   columns:
   - Check: a short name (used in the output JSON).
   - Evidence: exactly what to look at, and where in the package. Name
     the part (the claim comment, the repro report's environment
     record, the artifacts read against the issue's description, the
     repo-facts block) or a location from your
     references/evidence-guide.md. "The report" is not a source; "the
     output excerpt read against the error the issue describes" is.
   - Pass condition: a decision rule about the OUTCOME that someone
     else could apply and get your answer. Judge the thing itself (does
     the artifact show the issue's behavior?), never the write-up's
     shape (how many steps it has, how long it is, whether it uses a
     template's headings). Structure-shaped checks are what make
     graders disagree with themselves.
   - Weight: `required` (a fail here holds the package) or `preferred`
     (never changes the verdict).

2. A verdict rule below the table: how the check grades combine into
   accept (ready) or reject (hold), including how `unclear` is
   treated. The verdict space is binary. If you write no rule for
   `unclear`, the skill treats it as fail.

Cover what actually gets bad packages posted. The lecture named the
proof families: the environment is recorded, the steps are complete
and followable, the behavior shown matches the issue (not an adjacent
one), the outcome is stated honestly (an evidenced cannot-reproduce is
a pass, a confident wrong-target is not), and the words respect the
repo's conventions. A rubric that ignores a family will fail eval
packages designed around that family.
-->

## Checks

| Check | Evidence | Pass condition | Weight |
|---|---|---|---|
| Environment check | the repro report's environment record read against the issue's description | The environment record explicitly names the OS and tool version (commit hash is optional). It matches the issue's environment or explicitly notes the difference. | required |
| Steps followable | the repro report's steps | The steps provide enough detail (e.g., exact commands, code snippets, or clear references to the issue's code) so a stranger can re-run them to reach the reported state. | required |
| Behavior matches | the artifact (logs/output) read against the issue's expected vs actual | The attached log/artifact explicitly shows the expected vs actual behavior. It must match the failure described in the issue, OR faithfully demonstrate an honest cannot-reproduce. | required |
| Claim specific | the claim comment | The claim comment clearly identifies what is being investigated (e.g., naming the specific behavior, not just "this bug"). It promises an investigation or provides it inline, without promising a fix timeline. | required |
| Policy check | the claim comment read against the repo's contribution policy (repo-facts) | The comment adheres to the repo's stated contribution policies, including explicitly disclosing AI usage if the policy requires it. | required |

## Verdict rule

Accept if all `required` checks pass. If any `required` check fails, reject. `unclear` counts as a fail. `preferred` checks never change the verdict.
