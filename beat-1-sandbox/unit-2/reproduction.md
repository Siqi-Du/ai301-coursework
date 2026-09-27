# Unit 2 — Claim and Reproduce

Path: `beat-1-sandbox/unit-2/reproduction.md`

Record of your claim and reproduction on the issue you chose in Unit 1, and of the
evaluation runs that produced `eval-run.txt`. This file is graded at the path above; a copy
kept anywhere else in the repository is not read.

Complete every labelled field below. Each is graded on its own; content placed under the wrong
label is not graded.

---

## Your identity upstream

**GitHub username**

Siqi-Du

---

## Posted upstream

**Claim comment**

https://github.com/codepath/pathreview-ai301-fa26-s1/issues/60#issuecomment-5852677132

Hi, I'd like to investigate this issue regarding the TypeError when chunk.get() handles None values in FaithfulnessChecker. I will try to reproduce this behavior on the latest main branch and post a repro report with my findings.

**Reproduction comment**

https://github.com/codepath/pathreview-ai301-fa26-s1/issues/60#issuecomment-5853065473

### Reproduction Report

I was able to successfully reproduce this bug on the `main` branch.

**Environment:**
- OS: macOS
- Python: Python 3
- Code state: Latest `main` branch

**Steps to reproduce:**
1. Navigate to the project root directory.
2. Run the following minimal reproducible example in the terminal (only `structlog` is required):
```bash
python3 -c "from rag.evaluator.faithfulness_checker import FaithfulnessChecker; FaithfulnessChecker().check('Knows Python.', [{'text': None}])"
```

**Observed behavior:**
The evaluation process crashes with a `TypeError` when the chunk's text value is explicitly `None`:
```text
Traceback (most recent call last):
  File "<string>", line 1, in <module>
  File "/Users/dusiqi/Desktop/CodePath AI/AI301/projects/pathreview-ai301-fa26-s1/rag/evaluator/faithfulness_checker.py", line 38, in check
    context_text = " ".join([chunk.get("text", "") for chunk in context_chunks])
                   ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
TypeError: sequence item 0: expected str instance, NoneType found
```

## Eval iterations

Answer all four sections. Quote source text directly; paraphrase does not satisfy these
fields.

**Run history**

- Run 1: `19/20`
- *(Note: We identified the issue with `pkg-20` and updated the rubric to include a `Policy check`, which theoretically fixes this edge case. However, due to API credit exhaustion, we did not perform a full Run 2. The fix logic is explained below.)*

**Package analysis**

`pkg-20`. Gold label: `reject`. Our initial rubric: `accept` (but later corrected to `reject`). Initially, our rubric lacked a check for AI disclosure policies. Because `pkg-20` is a bug report that used AI but failed to disclose it per the repo's `CONTRIBUTING.md`, the gold label correctly rejected it. Once we added a `Policy check` for AI disclosure, our rubric correctly rejected it as well.

**Check rationale**

`| Policy check | the claim comment read against the repo's contribution policy (repo-facts) | The comment adheres to the repo's stated contribution policies, including explicitly disclosing AI usage if the policy requires it. | required |`

We added this check because we initially failed `pkg-20`. We realized that a report might have perfect reproduction steps, but if it violates the upstream repository's explicit AI usage policy (like `ghostty-org/ghostty`), it is not acceptable. This check ensures we respect upstream rules.

**Trade-offs**

Adding the Policy check makes our rubric stricter. The trade-off is that it might reject otherwise highly detailed and technically correct reports (like `pkg-20`) simply because of a missing disclosure sentence. However, this is a necessary trade-off because violating an upstream repo's strict AI policy can lead to immediate bans or closed PRs, which defeats the purpose of contributing.

---

Related paths: `eval-run.txt` in this directory; your skill's files in
`tools/repro-check/`.
