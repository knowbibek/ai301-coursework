# Unit 2 progress — saved October 26, 2026

This is unfinished assignment work saved for continuation. It is not ready for
submission yet. Assignment 1 is unchanged.

## Saved work

- The completed initial `repro-check` skill is in `../../tools/repro-check/`.
- `reproduction.md` contains the GitHub username, draft claim and reproduction
  comments, the run history so far, and initial check rationale and trade-offs.
- `drafts/claim.md` and `drafts/repro.md` are the standalone comment drafts.
- `checks/claim-verdict.md` and `checks/repro-verdict.md` are the actual Claude
  Code live skill responses. Both returned `accept`.
- `evidence/` preserves the parser test and direct-control output captured from
  the fork, plus the original failed evaluation result JSON files.
- The required Path Review fork was created:
  https://github.com/knowbibek/pathreview-ai301-fa26-s1

The bug was reproduced at commit
`f89c06fc3ff292df2a04a39ac51319d32a76b779`. With `--runxfail`, the parser suite
reported **1 failed, 18 passed**, exposing the exact array-related
`AttributeError` from issue #69. No fix was implemented.

## Remaining work

1. Restore access for the command-line `claude -p` client used by the official
   evaluator. The signed-in desktop app ran the live skill successfully, but
   the evaluator's subprocess reported `OAuth session expired and could not be
   refreshed`. Both saved evaluation JSON files contain errors, not scores.
2. Run the unmodified official Unit 2 evaluator against the installed rubric
   and evidence guide. Aim for at least 18/20 agreement and a match in every
   category. Review disagreements, make any needed rubric revisions, and use
   targeted reruns before a confirming full run. Save a successful full run
   with `--save-run eval-run.txt` and replace this folder's **existing template
   placeholder** with that harness-written file; do not hand-edit it.
3. Finish `reproduction.md`'s Run history, Package analysis, Check rationale and
   Trade-offs using the actual successful results and final rubric wording.
   Re-check the comments if their wording or the skill changes.
4. Review the accepted drafts, post the claim and reproduction as separate
   comments on https://github.com/codepath/pathreview-ai301-fa26-s1/issues/69,
   then put each actual comment permalink and its exact posted text in the
   corresponding field in `reproduction.md`.
5. Upload the finished files to this same coursework repository. Submit
   https://github.com/knowbibek/ai301-coursework in the Assignment 2 portal.

No issue comments have been posted and no portal submission has been made.

## Continuing on this computer

The installed skill is at `~/.claude/skills/repro-check/`. The starter materials,
coursework checkout, fork checkout, and original drafts are under:

`/Users/biz/Documents/Codex/2026-10-26/so-i-have-opened-up-safari/work/`

From `ai301-unit2-starter/eval/`, the full-run command is:

```bash
python3 run_eval.py \
  --rubric ~/.claude/skills/repro-check/rubric.md \
  --evidence ~/.claude/skills/repro-check/references/evidence-guide.md \
  --save-run eval-run.txt \
  --out results.json
```
