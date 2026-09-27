# Evidence guide: where proof lives in a reproduction package

<!--
THIS IS THE PART YOU WRITE (new this week: week 1 handed you this file
finished; the scaffolding fades). The skill uses this guide as its map:
for every kind of proof a rubric check names, this file says WHERE to
find it in a package and WHAT GOOD LOOKS LIKE when you do.

Under each family heading below, write:

- Where it lives: the exact places to look. In an eval bundle (which
  section of the package: the issue context, the repo-facts block, the
  claim comment, the repro report and its parts). In live mode (where
  on GitHub or in the draft: the issue thread, the repo's docs, the
  student's draft comment).
- What good looks like: one or two sentences someone else could apply.
  Prefer observable conditions ("the versions named match what the
  issue targets, or the difference is called out") over adjectives
  ("environment is thorough").

A rubric check whose evidence this guide cannot locate is a check
nobody else can execute; your operator swap showed you what that feels
like. Write the map you wish your executor had.
-->

## Environment

Where it lives: The Environment line at the top of the repro report. Compare it with the issue's stated Environment.
What good looks like: It names the tool version, OS, and commit hash the repo's bug template asks for, and matches the issue's version or clearly states why it differs.

## Steps

Where it lives: The steps section of the repro report.
What good looks like: The steps are complete and minimal, starting from a fresh clone or setup, including exact commands so a stranger can copy and paste to re-run them.

## Behavior shown

Where it lives: The artifacts section (terminal logs, screenshots, output blocks) of the repro report.
What good looks like: The artifact explicitly shows the expected vs actual delta, matching the exact failure (e.g., exit code 101, panic message) described in the issue. It must be shown, not just asserted.

## Honesty

Where it lives: The conclusion or summary of the repro report, compared to the evidence shown above it.
What good looks like: The report states exactly what happened. If the bug could not be reproduced, it honestly reports a "cannot reproduce" with a full control run. It never claims more than the attached artifacts prove.

## Comms

Where it lives: The claim comment in the issue thread, and the repro report's adherence to repo guidelines (like AGENTS.md or CONTRIBUTING.md).
What good looks like: The communication is specific, names the version and behavior, flags if it is a first contribution, and never promises timelines. It follows any required disclosure rules (e.g., AI assistance) from the repo.
