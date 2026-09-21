# Unit 1 — Issue Selection

## Selected issue

**Issue link**

https://github.com/codepath/pathreview-ai301-fa26-s1/issues/69

**Verdict output**

All three issues pass every required check. Ranked read-out:

**Accepted, in fit order**

1. **#69 Output parser crashes on top-level JSON array.** Best fit: a bounded Python fix in the RAG generator's LLM output parser, with a covering `xfail` test already in place, so it is small, testable, and directly about how the AI feedback pipeline works. One classmate commented a claim on 2026-09-19 with a reproduction. House rule says that does not block.
2. **#68 Keyword search ZeroDivisionError on empty index.** Same shape: one guard in the BM25 retriever plus removing an `xfail` marker. Also Python, testable, and in the RAG retrieval layer. A classmate claimed it on 2026-09-20 with a repro and plan, and has commits in their own fork. No PR in this repo. House rule applies.
3. **#64 Relevance scorer "partial overlap" fixture.** Smallest task, one test file, exact repro command given, no claims at all. Ranked last only because it is a test-fixture edit and teaches least about the AI features themselves.

**Rejected:** none.

Shared evidence for the repo checks: the last five commits on `main` are all by a human maintainer, dated 2026-08-24 to 2026-09-16. The repo is not archived and was pushed 4 days ago. There is no release, but the push satisfies the rule. The linked contributing doc and PR template state no AI policy, so silence passes.

```json
[
  {
    "item": "https://github.com/codepath/pathreview-ai301-fa26-s1/issues/69",
    "checks": [
      {"name": "Maintainer activity", "grade": "pass", "evidence": "Last 5 main commits authored by Aburke225 (human), newest 2026-09-16, within 90 days of 2026-09-20."},
      {"name": "Repository in use", "grade": "pass", "evidence": "archived=false; pushed_at 2026-09-16 (4 days ago); no releases, but push threshold met."},
      {"name": "Manageable scope", "grade": "pass", "evidence": "Concrete bug: handle list in _parse_json_output; two named files; estimated 2-4 hours; opened 2026-09-10, no PR history."},
      {"name": "Available to work on", "grade": "pass", "evidence": "No assignee, no linked or mentioning PRs; one student claim (jacho15, 2026-09-19) which scope.md's Path Review house rule says does not block."},
      {"name": "AI contribution policy", "grade": "pass", "evidence": "docs/CONTRIBUTING.md and .github/PULL_REQUEST_TEMPLATE.md state no AI policy; no AI_POLICY/AGENTS files exist."}
    ],
    "verdict": "accept"
  },
  {
    "item": "https://github.com/codepath/pathreview-ai301-fa26-s1/issues/68",
    "checks": [
      {"name": "Maintainer activity", "grade": "pass", "evidence": "Last 5 main commits authored by Aburke225 (human), newest 2026-09-16, within 90 days of 2026-09-20."},
      {"name": "Repository in use", "grade": "pass", "evidence": "archived=false; pushed_at 2026-09-16 (4 days ago); no releases, but push threshold met."},
      {"name": "Manageable scope", "grade": "pass", "evidence": "Concrete bug: guard empty corpus in KeywordSearcher.index(); two named files; estimated 2-4 hours; opened 2026-09-10, no PR history."},
      {"name": "Available to work on", "grade": "pass", "evidence": "No assignee, no PRs in this repo; student claim by yulijasso on 2026-09-20 with fork commits, which the Path Review house rule says does not block."},
      {"name": "AI contribution policy", "grade": "pass", "evidence": "docs/CONTRIBUTING.md and .github/PULL_REQUEST_TEMPLATE.md state no AI policy; no AI_POLICY/AGENTS files exist."}
    ],
    "verdict": "accept"
  },
  {
    "item": "https://github.com/codepath/pathreview-ai301-fa26-s1/issues/64",
    "checks": [
      {"name": "Maintainer activity", "grade": "pass", "evidence": "Last 5 main commits authored by Aburke225 (human), newest 2026-09-16, within 90 days of 2026-09-20."},
      {"name": "Repository in use", "grade": "pass", "evidence": "archived=false; pushed_at 2026-09-16 (4 days ago); no releases, but push threshold met."},
      {"name": "Manageable scope", "grade": "pass", "evidence": "Concrete fix to one test fixture in tests/unit/test_relevance_scorer.py with exact repro command; opened 2026-09-10, no PR history."},
      {"name": "Available to work on", "grade": "pass", "evidence": "No assignee, no comments, no linked or mentioning PRs."},
      {"name": "AI contribution policy", "grade": "pass", "evidence": "docs/CONTRIBUTING.md and .github/PULL_REQUEST_TEMPLATE.md state no AI policy; no AI_POLICY/AGENTS files exist."}
    ],
    "verdict": "accept"
  }
]
```

---

## Eval iterations

**Run history**

I ran three evaluations, in this order:

1. Initial three-issue test with `--limit 3`:

   > agreement: 2/3 scored items

2. After revising the Manageable scope check, I reran `issue-01` with `--only issue-01`:

   > agreement: 0/1 scored items

3. Full 20-issue evaluation using the revised rubric, saved with `--save-run eval-run.txt`:

   > agreement: 18/20 scored items  (bar: 18/20: PASS)

The final run matched at least one verdict in every category. Its disagreements were `issue-19` and `issue-20`.

**Issue analysis**

In the final run, my rubric returned `reject` for `issue-19`, while its gold label was `accept`. The evaluator failed only the Manageable scope check and recorded:

> Issue lists two root causes plus three additional suggestions (multi-processing, selective category matching, separate rewrite-application thread) spanning matcher performance and threading architecture — an umbrella of core-internals changes, not one defined-outcome task

The evaluator interpreted the proposed performance and threading changes as broad architectural work. My check therefore rejected it even though the gold label accepted it. This is a limitation of how the rule distinguishes a bounded contribution from a collection of related suggestions.

**Check rationale**

The current check in the uploaded rubric is quoted below without changes:

| Check | Evidence | Pass condition | Weight |
|---|---|---|---|
| Manageable scope | Issue body and comment thread; issue age and linked PR history in Repo facts | A concrete contribution with a defined outcome. Related edits across multiple files or documentation pages can count as one task. Reject explicit umbrella/tracking issues intended to be split into separate tasks, pure usage questions, unresolved implementation-design debates, or work explicitly requiring core-internals changes. Reject issues older than 2 years with at least 2 abandoned PRs. Missing reproduction steps alone do not cause rejection. | required |

The initial version rejected `issue-01`, a documentation task involving several related pages. With AI assistance, I clarified that related edits across files can still count as one task. This wording aims to distinguish a coordinated change from an umbrella issue instead of using file count alone as a reason to reject it. It also avoids treating missing reproduction steps alone as evidence that a task is too large.

**Trade-offs**

The revised check says:

> Related edits across multiple files or documentation pages can count as one task.

This allows coordinated changes but leaves judgment about whether the work has one defined outcome. My targeted rerun of `issue-01` still returned `reject` and reported:

> agreement: 0/1 scored items

The final full run accepted `issue-01` using the same revised wording. That change shows variation in the evaluator's interpretation, rather than proving that the wording guarantees acceptance. The final run also rejected the gold-accepted `issue-19` and accepted the gold-rejected `issue-20`. I kept the rubric after it reached 18/20 with a match in every category, while recognizing that its scope judgments are imperfect.

---

## Selection rationale

**Selection rationale**

1. I have used Python and want to build my AI skills. Issue #69 interests me because it involves handling an AI response when JSON is returned as a list instead of an object. It names the implementation and test files and estimates 2–4 hours. I can spend about 2–4 hours on it, which matches the estimate. I will need to use that time to understand the code, make the fix, and run the tests; unfamiliar setup may take extra time.

2. The verdict identified a specific bug, named files, and an existing test to update. It also applied the Path Review rule that another student's claim does not block the issue. My interest in learning how Python handles AI output is an additional reason for choosing it. Passing the rubric does not establish how quickly I will understand the unfamiliar code.

3. I expect the claim itself to be straightforward under the classroom rules, even though another student has already expressed interest. Before writing my Unit 2 claim comment, I need to understand the problem and describe my own intended approach. The existing claim does not reserve the issue against other students under Path Review's rules.

---

Related paths: `eval-run.txt` in this directory; skill files in `tools/issue-select/`.
