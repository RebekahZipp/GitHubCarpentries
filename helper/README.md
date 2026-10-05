# Helper Path

## Help learners reason without taking over

Helpers are part of the teaching team. Your job is not to type the fastest fix. Your job is to help a learner establish where they are, read the evidence, make a reasoned next move, and verify it.

The Carpentries Code of Conduct applies to the workshop and to collaboration spaces such as GitHub. Technical help should remain welcoming, respectful, and professional across differences in experience, background, viewpoint, and technical choice.

Helper practice:

- address the work and evidence, not the learner's competence;
- do not shame mistakes or make experience-level jokes;
- ask before touching another person's keyboard, files, or account;
- protect credentials and private project information;
- invite questions without turning them into tests;
- accept different valid approaches when the evidence supports them;
- surface patterns to the instructor without identifying or embarrassing a learner.

A useful review question is:

> "What does the evidence show, and what are we still assuming?"

Use this rhythm:

**LOCATE → OBSERVE → ASK → VERIFY → HAND OFF**

### LOCATE

Before changing anything, establish context.

```bash
pwd
git rev-parse --show-toplevel
git status --short --branch
git remote -v
```

You may not need every command. Use the smallest safe check that answers the question.

Ask:

- Which terminal or console are we in?
- What directory are we in?
- What repository does Git think we are in?
- What branch are we on?
- Is this the learner's repository, a collaborator's clone, or another project?

### OBSERVE

Read the message before fixing it.

Ask:

- What did you expect?
- What actually happened?
- What changed?
- What does Git say now?

Treat error messages and unexpected output as evidence.

### ASK

Help the learner explain the situation.

Useful prompts:

- "What do you think Git is being literal about here?"
- "What evidence would distinguish those two explanations?"
- "What is the smallest safe thing we can test?"
- "Before we click Yes, what does the computer think 'here' is?"

Questions are invitations, not quizzes. If the learner does not know, explain your reasoning aloud and keep them involved.

### VERIFY

After an action, inspect again. No error message is not proof that the intended result occurred.

Use `git status`, `git log --oneline`, `git remote -v`, `ls`, or the GitHub repository page as appropriate.

### HAND OFF

Return control to the learner.

A successful helper interaction ends with the learner able to say:

> "I expected ___. I observed ___. The evidence showed ___. I did ___. I verified it by ___."

Do not take the keyboard unless accessibility or another practical need makes that appropriate.

## Common workshop cases

### Wrong console

An R command belongs in the R Console. Git and shell commands belong in a Terminal or Git Bash.

Do not diagnose a Git problem until you know which interpreter received the command.

### Wrong directory

A repository problem may really be a location problem. Check `pwd` and the repository root before changing anything.

### Output pasted as input

Git's output is information. It is not automatically the next command. Help the learner separate what the computer said from what they should type.

### Rejected push

Do not use `--force` as a reflex.

Inspect the local branch, remote, and history. A rejected push often means the remote contains work the local copy does not yet have.

### Merge conflict

A conflict is not repository damage. Git has stopped because overlapping changes require a human decision. Read the conflict markers, reconcile the intended content, stage the resolved file, commit, and verify.

### Untracked or generated files

Do not automatically use `git add .`.

Use:

**TRACK → IGNORE → INVESTIGATE**

Ask whether each file belongs in the durable project record.

### Repository created in the wrong place

Stop before deleting anything.

Use the safe intervention lifecycle:

**LOCATE → DEFINE → SCOPE → PREDICT → ACT → VERIFY → HAND OFF**

On institutional, shared, or borrowed equipment, involve the responsible IT staff when cleanup extends beyond the learner's project.

Never teach `rm -rf` as a casual recovery command. Prefer reversible moves and explicit verification of the target.

## Teams and whole-room discourse

Learners can answer aloud or contribute to the Teams chat. Treat both as participation.

While the instructor is teaching, helpers can watch for:

- repeated questions;
- different results from the same exercise;
- useful error messages;
- learners who have a good explanation but may not want to speak to the whole room; and
- questions that should be brought back to everyone.

Ask permission before quoting or identifying a learner. Prefer summarizing the pattern:

> "A couple of people are seeing a different branch name."

rather than:

> "Jordan did this wrong."

When useful, invite a learner to add the **exact non-sensitive error message** to Teams so the group can reason from the same evidence.

At the 7-minute breaks around 2:00 and 3:00, stop active troubleshooting unless a learner specifically asks to continue. Use the break to collect patterns for the instructor and let learners step away.

## Training-day cue sheet

Use these as place points so you know what the room should be doing without needing to follow every instructor sentence.

| Time | Learner state | Helper priority |
| --- | --- | --- |
| **1:00–1:10** | Re-entry | Console, directory, repository root, status |
| **1:10–1:25** | TRY clone | Clone location, exact error, verify remote/history |
| **1:25–1:40** | Remotes | Help learners explain `origin`; do not overteach remote commands |
| **1:40–1:53** | BUILD setup | Owner/Collaborator identity, access, correct clone |
| **1:53–2:00** | **BREAK** | Stop active troubleshooting; give Rebekah pattern report |
| **2:00–2:18** | First collaboration | State transitions: modified → staged → committed → pushed |
| **2:18–2:33** | Role switch | Reduce help; ask learner for next move and evidence |
| **2:33–2:53** | Conflict | Preserve rejection/conflict evidence; no reflex force push |
| **2:53–3:00** | **BREAK** | Identify learners mid-conflict and recurring misconceptions |
| **3:00–3:15** | History/recovery | Intended target state before recovery command |
| **3:15–3:27** | Ignore decisions | TRACK / IGNORE / INVESTIGATE |
| **3:27–3:40** | Context/reuse | README, provenance, license, citation questions |
| **3:40–3:50** | Interface transfer | Same Git states in RStudio/GitHub |
| **3:50–4:00** | Explain-back | Learner explains; helper does not take over |

### Catch-up rule

If a learner falls behind, do not reconstruct the whole lesson. Bring them to the **next checkpoint**.

Ask:

> "What is the smallest state we need so you can rejoin the group?"

Examples:

- clone exists + `git status` works;
- one commit is visible on GitHub;
- learner can explain the rejected push even if conflict cleanup is unfinished;
- README is open and one meaningful next change is identified.

### Signal Rebekah

Surface a pattern when **two or more learners** are showing the same conceptual problem, or immediately when a safety/privacy issue appears.

Useful handoff:

> "Several people are seeing ___. The common evidence is ___. I think the room may need a 60-second reset on ___."

## Helper checkpoints during the lesson

### Before cloning

Confirm the learner knows where the clone will be created and that they are not accidentally cloning inside another repository.

### After cloning

Have the learner verify:

```bash
git status
git log --oneline
git remote -v
```

### Before a commit

Ask what belongs in this version and whether the staged diff matches that decision.

### Before a push

Ask where the commit is going and whether the learner has the latest shared work.

### During collaboration

Surface repeated questions to the instructor. Helpers are knowledge conduits across the room.

### At the end

Ask the learner to explain one Git situation back to you without giving them the answer first.

## Escalate when

Pause and involve the instructor or appropriate support when:

- the repository scope is unclear;
- credentials, tokens, or private information appear;
- a command could delete or overwrite files;
- the learner is on institutional or shared equipment and cleanup is needed;
- the remote contains work whose ownership or intended history is uncertain;
- the next step would require force-pushing, rewriting shared history, or another destructive action.

The workshop goal is not fast rescue. It is durable reasoning.


## Workshop continuity: keep the Carpentries thread

Oct. 8 is a continuation of the earlier Carpentries Git session, not a replacement lesson. Keep the same conceptual object and vocabulary as responsibility moves from local Git into GitHub collaboration.

**Session 1 foundation:** version control benefits -> Git vs. GitHub -> repository -> modify/add/commit -> meaningful commit messages -> history/HEAD -> ignore -> remotes/collaboration.

**Oct. 8 continuation:** orient -> clone/investigate -> BUILD -> pull/change/inspect/add/commit/review/push -> rejected push/conflict -> human decision -> history/recovery -> documentation -> explain-back.

### Guacamole is the running specimen

Keep `guacamole.md` visible across the handoff instead of replacing it with disconnected exercises.

1. **RECOGNIZE:** inspect the familiar recipe and its recorded history.
2. **RECORD:** make one intentional recipe change and write a commit message that will still explain the decision later.
3. **SHARE:** push the recorded change so another copy can receive it.
4. **COLLABORATE:** a partner pulls, changes, records, and pushes.
5. **CONFLICT:** two people deliberately change the same recipe line differently. Git preserves both claims and stops rather than inventing human intent.
6. **RESOLVE:** people decide the intended wording, record the resolution, and verify it.
7. **REVIEW:** use `HEAD`, `HEAD~1`, commit IDs, log, show, and diff to explain how the recipe became its current version.

**Teaching line:** Git can tell us that two versions of guacamole exist. Git cannot tell us which guacamole tastes better.

**Commit-message prompt:** "Six months from now, will this message tell another person why this version exists?"

This continuity preserves the Carpentries learning progression while increasing learner responsibility: **FOLLOW -> RECOGNIZE -> PREDICT -> EXPLAIN -> ACT -> HELP OTHERS.**
