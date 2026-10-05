# Helper Path

## Help learners reason without taking over

Helpers are part of the teaching team. Your job is not to type the fastest fix. Your job is to help a learner establish where they are, read the evidence, make a reasoned next move, and verify it.

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
