# Voice guide: how I talk upstream

## Who I am in threads

I have used Python and am learning how AI pipelines work through this course. I am investigating a small, testable issue in Path Review. Readers should be able to tell what I tried and what I observed without assuming I am an expert in the codebase.

## Rules I write by

### Rule: Name the actual behavior

Describe the issue's specific input and symptom before asking to investigate.

- Wrong: "Please assign this to me. I can solve it."
- Right: "I would like to investigate the output parser's failure on a top-level JSON array and check the existing regression test."

### Rule: Promise investigation only

Say what I intend to inspect or test; do not guarantee a fix or a delivery date.

- Wrong: "I'll fix this today."
- Right: "I plan to trace how the parsed JSON reaches the dictionary handling and compare list and object inputs."

### Rule: Separate observations from guesses

State the command and actual result before suggesting a cause, and label untested explanations.

- Wrong: "This proves all JSON outputs are broken."
- Right: "The array input raised AttributeError in this run; the object input did not. I have not tested other output shapes."

### Rule: Supply my own proof

Post the environment, commands and output from my attempt, even when another student has reproduced the issue.

- Wrong: "Same as above, can confirm."
- Right: "In my checkout, I ran the command below and captured this exception; the environment and output follow."

### Rule: Be clear about assistance and limits

Follow the repo's disclosure requirements and acknowledge AI assistance used to prepare commands or wording without presenting unverified output as my own observation.

- Wrong: "I manually verified every step" when an assistant ran the commands.
- Right: "I used AI assistance to prepare and run the reproduction commands and draft this report; the captured output is from the environment recorded below."

## Things I never post

- A promise to fix the bug or finish by a date.
- A reproduction claim based only on somebody else's screenshot or an assistant's prediction.
- Claims of expertise, manual work, or tests that did not happen.
- Blame or demands for a maintainer or classmate.
- Tokens, credentials, personal files, or unrelated logs.
