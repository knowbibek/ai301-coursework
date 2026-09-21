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
| Maintainer activity | Repo facts: last 5 default-branch commits and their authors | At least one human-authored commit, or a bot merge of a human PR, within 90 days of the capture date (today in live mode) | required |
| Repository in use | Repo facts: archived flag, latest release date, and last push date | Repository is not archived, and has either a release within 365 days or a push within 90 days of the capture date (today in live mode) | required |
| Manageable scope | Issue body and comment thread; issue age and linked PR history in Repo facts | A concrete contribution with a defined outcome. Related edits across multiple files or documentation pages can count as one task. Reject explicit umbrella/tracking issues intended to be split into separate tasks, pure usage questions, unresolved implementation-design debates, or work explicitly requiring core-internals changes. Reject issues older than 2 years with at least 2 abandoned PRs. Missing reproduction steps alone do not cause rejection. | required |
| Available to work on | Repo facts: assignees and linked PRs; comment thread for claims and PR updates | No active assignee, open competing PR, or unresolved claim within 30 days. Explicit withdrawal clears a claim. In live mode, follow scope.md's Path Review exceptions for shared issues. | required |
| AI contribution policy | Repo facts: contribution policy; in live mode CONTRIBUTING.md, linked contributor docs, AI policy files, and PR templates | No outright ban on AI-assisted contributions. Disclosure, testing, understanding, or human-review requirements are acceptable conditions to follow. No stated AI policy passes. | required |

## Verdict rule

<!-- State how the grades above combine into accept or reject, and how
unclear is treated. Example shape (write your own): "accept if every
required check passes; preferred checks never change the verdict, they
rank accepted issues; unclear counts as fail." -->
Accept only if every required check passes. A failed or unclear required check means reject. Preferred checks only rank accepted issues and never change the verdict. Measure dates against the bundle's capture date in eval mode and today's date in live mode.