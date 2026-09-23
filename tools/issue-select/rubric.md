# Rubric: is this a good first issue?

<!--
THIS IS THE PART YOU WRITE. The skill in SKILL.md executes whatever checks
you define here. It ships empty on purpose: the judgment is your work.

A filled rubric must contain:

1. At least one row in the checks table. Each row needs all four columns:
   - Check: a short name (used in the output JSON).
   - Evidence: exactly what to look at, and where. Name the source
     (repo-facts block, issue body, comment thread, or the locations in
     references/evidence-guide.md). "The repo" is not a source; "the last
     5 default-branch commit dates" is.
   - Pass condition: a condition someone else could apply and get your
     answer. Prefer thresholds with numbers ("a maintainer commented
     within 30 days") over adjectives ("maintainer is responsive").
   - Weight: `required` (a fail here rejects the issue) or `preferred`
     (never changes the verdict; a nice-to-have that helps rank the
     issues you accept).

2. A verdict rule below the table: how the check grades combine into
   accept or reject, including how `unclear` is treated. The verdict
   space is binary. If you write no rule for `unclear`, the skill treats
   it as fail.

Cover what actually kills first contributions. The lecture named four
families: the maintainer is alive, the repo is in use, the scope fits a
newcomer, and nobody else is already on it. A rubric that ignores a family
will fail eval issues designed around that family.
-->

## Checks

| Check | Evidence | Pass condition | Weight |
|---|---|---|---|
| maintainer_alive | The issue's comment thread, or recent PR activity in the repo | A maintainer has commented on the issue OR merged a PR within the last 30 days | required |
| repo_in_use | The last 5 default-branch commit dates | There is at least one commit on the default branch in the last 6 months | required |
| scope_fits | Issue labels and issue body/description | The issue has a "good first issue" or "help wanted" label, OR it describes a single actionable task/bug that a newcomer could understand without massive architectural changes. | required |
| issue_unclaimed | Issue assignees and the comment thread | The issue has no assignee AND no active/recent claim comment from another contributor (claims from years ago or stale claims do not count as active). Note: ignore claim comments in Path Review repos. | required |
| policy | Repo facts / contribution policy | The repository's contribution policy must NOT explicitly forbid or ban the use of AI or generative AI tools for new code/documentation. | required |

## Verdict rule

Accept if every required check passes; preferred checks never change the verdict, they only rank accepted issues; unclear counts as fail.
