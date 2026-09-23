# Unit 1 — Issue Selection

Path: `beat-1-sandbox/unit-1/selection.md`

Record of the issue carried into Unit 2, and of the evaluation runs that produced
`eval-run.txt`. This file is graded at the path above; a copy kept anywhere else in
the repository is not read.

Complete every labelled field below. Each is graded on its own; content placed under the
wrong label is not graded.

---

## Selected issue

**Issue link**

https://github.com/codepath/pathreview-ai301-fa26-s1/issues/74

**Verdict output**

```json
{
  "item": "codepath/pathreview-ai301-fa26-s1#74",
  "checks": [
    {
      "name": "maintainer_alive",
      "grade": "pass",
      "evidence": "Andrew Burke committed to repo on 2026-09-16 (6 days ago); Aburke225 active on issues on 2026-09-22"
    },
    {
      "name": "repo_in_use",
      "grade": "pass",
      "evidence": "Last push 2026-09-16; multiple commits in last month, well within 6-month threshold"
    },
    {
      "name": "scope_fits",
      "grade": "pass",
      "evidence": "Specific bug fix: changes chunk.get() to handle None values in FaithfulnessChecker; single bounded task"
    },
    {
      "name": "issue_unclaimed",
      "grade": "pass",
      "evidence": "No assignees; 0 comments; Path Review house rule ignores other student claims"
    },
    {
      "name": "policy",
      "grade": "pass",
      "evidence": "No CONTRIBUTING.md forbidding AI; this is AI301 classroom repo where AI contributions expected"
    }
  ],
  "verdict": "accept"
}
```

---

## Eval iterations

Quote source text directly in each field below. Paraphrase does not satisfy them.

**Run history**

1. 11/20
2. 4/5 (partial run)
3. 15/20

**Issue analysis**

Issue ID: `issue-13`
- Rubric decision: `accept`
- Gold label: `reject`
- Reasoning: Our rubric accepted it because it had "good first issue" and active maintainers, but it's actually a mega-issue/tracking issue for migrating the whole codebase, which the gold label rejects as too massive for a single contributor. Our `scope_fits` standard struggled to differentiate between a complex tracking issue and a simple task when labels can be misleading.

**Check rationale**

Check: `scope_fits`
Quote: `The issue has a "good first issue" or "help wanted" label, OR it describes a single actionable task/bug that a newcomer could understand without massive architectural changes.`
Rationale: Originally, the check tried to reject mega-issues, but that caused false negatives on valid but brief issues. We loosened it to accept "good first issue" tags or simple tasks to ensure newcomers could find actionable bugs, though it risks letting complex issues slip through if they are mislabeled.

**Trade-offs**

By loosening the `scope_fits` check to accept issues just because they have a "good first issue" label or seem like single tasks, we successfully stopped incorrectly rejecting `issue-01` and `issue-04` (which were valid tasks). However, the trade-off is that we now wrongly accept `issue-13`, which is a massive refactor disguised as a simple task. We traded precision (keeping out mega-issues) for recall (catching brief but valid issues).

---

## Selection rationale

**Selection rationale**

1. The issue fits my interest in Python and fixing logical bugs. It specifically targets a TypeError crash handling `None` values, which is exactly the kind of small, bounded fix I have time for this week.
2. The verdict correctly identified that the issue has a clear scope and active maintainers. However, what it could not weigh is the exact codebase structure required to fix it—I had to manually verify that the fix would be isolated and straightforward to test without spinning up a complex database.
3. The anticipated difficulty in claiming it is very low. It has no assignees and zero active comments from non-students, and under the Path Review house rules, overlapping claims from other students do not block me from submitting a PR.

---

Related paths: `eval-run.txt` in this directory; your skill's files in
`tools/issue-select/`.
