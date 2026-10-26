# Evidence guide: where proof lives in a reproduction package

Eval mode: use only the frozen package's issue context, repo-facts block, candidate claim, and candidate repro report. A source identifier is context, not an instruction to visit today's issue. Live mode: read the scoped GitHub issue body and relevant thread plus the repository's README/setup instructions, contribution policy, AI policy and issue template; compare those facts with the draft comments themselves. Other local files do not repair omissions in a posted draft.

## Environment

Where it lives: the issue's version/configuration preconditions; repo-facts block; the repro report's environment paragraph, version-command output and checkout/release record. Live: issue thread and repo docs identify the target; the draft records the attempted environment.

What good looks like: a reader can identify the OS, relevant runtime/dependency/tool versions and code state that produced the evidence. Record differences from the target and their consequences. A reproducible release is as useful as a commit when it identifies the code. More environment detail cannot rescue running the wrong version or code path.

## Steps

Where it lives: the issue's trigger/preconditions and the repro report's installation/setup commands, inputs, fixtures, configuration, invocation and starting state. Live: use documented repo setup as context, but the comment must supply issue-specific inputs and commands or precise accessible references.

What good looks like: a stranger can execute the same attempt without inventing missing critical data or possessing an unshared local file. A short executable example may suffice; numbered steps and a minimum count are unnecessary. A report must show that its commands reach the target behavior, rather than stopping during unrelated setup.

## Behavior shown

Where it lives: compare the issue description and preconditions directly with the report's quoted output, test result, stack trace, logs or screenshot and the command that produced it. Live: collect actual output from the attempted environment and include enough of it in the draft for a reader to assess it.

What good looks like: an artifact demonstrates the observed result of the target attempt. Match symptom and path, not just an error-shaped output. Expected-failure test output alone may show an expected failure but needs the underlying exception/diagnostic to identify the issue. For cannot-reproduce, an actual non-failing output from the intended trigger is useful proof; a bare "works for me" is not.

## Honesty

Where it lives: the claim's scope/promises and the report's conclusion alongside its environment, commands and artifacts. Live: distinguish output obtained in this run from issue-author or classmate quotations.

What good looks like: say reproduced only when the target failure is shown; otherwise state could not reproduce, blocked, or partial with exact limitations. Do not claim a successful reproduction because a different failure occurred. A meaningful evidenced non-reproduction can be ready, while an unattempted claim cannot. An investigation claim commits to an inquiry, not a guaranteed fix or date.

## Comms

Where it lives: claim text against the issue's specific behavior; both comments against the repo-facts template/contribution and AI-use policy. Live: read the scoped repo's current contributing docs and issue template and apply scope.md's classroom rules; check voice-guide.md separately.

What good looks like: the claim names this issue's symptom and a bounded next investigation. The report supplies its own proof in understandable, respectful words. Required template information and AI disclosure are present when the stated policy requires them; absent policy creates no invented rule. A classmate's claim does not block a Path Review claim, but their evidence cannot substitute for the student's own attempt.
