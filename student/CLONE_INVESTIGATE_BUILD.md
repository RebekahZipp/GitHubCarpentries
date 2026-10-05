# Clone → Collaborate → Investigate → Build

## Your mission

A GitHub repository is not only code. It can be a research record, dataset, lesson, documentation site, analysis, or professional portfolio.

This lesson continues the Software Carpentry **Version Control with Git** sequence. You already know the local cycle of changing, inspecting, staging, committing, and reviewing history. Now we connect that record to other people and places.

Our rhythm remains:

**CHANGE → INSPECT → CHOOSE → RECORD → REVIEW → SHARE**

## How we work together

This workshop follows The Carpentries Code of Conduct in class and in our GitHub collaboration.

Mistakes, questions, rejected pushes, and conflicts are normal learning material. We review the **work and evidence**, not the person.

- Use welcoming and inclusive language.
- Respect different viewpoints, experience levels, and technical choices.
- Ask before touching another person's keyboard or files.
- Protect credentials and private information.
- Give constructive feedback about the change and intended outcome.
- Help another learner reason rather than simply taking over.

A useful collaboration question is:

> "What did you expect, and what does the evidence show?"

## Know where to work

The lesson uses four simple labels:

- **DEMO:** watch, predict, and discuss.
- **TRY:** work in your own local clone of the class example. You are not changing the instructor's source repository.
- **BUILD:** work in a repository you own or share with your partner.
- **TALK:** answer aloud or add your observation, question, error message, or takeaway to the Teams chat.

If you are unsure where a command belongs, ask before running it.

You will have a **7-minute break at about 2:00 and another at about 3:00**. We will protect those breaks even if an optional activity has to be shortened.

## Stay-with-the-class strip

If you fall behind, do **not** try to recreate every keystroke. Rejoin at the next checkpoint.

| Point in class | You are caught up when... |
| --- | --- |
| Before first break | You can run `git status`, know whether you are in TRY or BUILD, and know your repository/role. |
| After first collaboration | One commit is visible on GitHub and you can explain whether it is local, pushed, or pulled. |
| Before second break | You can explain why a push was rejected and what a conflict asks a human to decide. |
| Final hour | You can inspect history, make one track/ignore/investigate decision, and improve your README. |
| End | You can explain one decision using evidence and name your next step. |

When you need help, tell a helper:

> "I am at ___. I expected ___. I see ___. I need to get to the next checkpoint."

## Pocket cheat sheet

**ORIENT**
```bash
pwd
git rev-parse --show-toplevel
git status
```

**INSPECT**
```bash
git diff
git diff --staged
git log --oneline
git show HEAD
```

**CONNECT**
```bash
git remote -v
git pull origin main
git push origin main
```

**NORMAL WORK**

**CHANGE → INSPECT → CHOOSE → RECORD → REVIEW → SHARE**

**WHEN SURPRISED**

**EXPECT → OBSERVE → EXPLAIN → TEST → ACT → VERIFY**

## 1. Orient before acting

Before a clone, pull, push, or repair, establish where you are.

```bash
pwd
git status
git remote -v
```

Ask:

- Where am I?
- Which repository am I in?
- Which branch am I on?
- What does Git know?
- Where will shared work come from or go to?

Git is being extremely literal. Location and repository identity matter.

## 2. Clone: GitHub → local

Cloning creates a connected local copy of a Git repository.

**GitHub → CLONE → LOCAL**

A clone is not the same as downloading a ZIP. The clone includes the repository history and automatically configures a remote named `origin`.

Before cloning, decide where the new directory should be created. Do not clone a repository inside another copy of the same project.

```bash
git clone https://github.com/RebekahZipp/GitHubCarpentries-Examples.git
cd GitHubCarpentries-Examples
git status
git log --oneline
git remote -v
```

Read those commands as questions:

- What state is my local copy in?
- What happened before I arrived?
- Where did this repository come from?

## 3. Collaborate: pull before new shared work

In the Carpentries Owner/Collaborator exercise, one person owns the GitHub repository and another person works from a clone.

A basic shared workflow is:

```text
PULL → CHANGE → INSPECT → ADD → COMMIT → REVIEW → PUSH
```

Typical commands are:

```bash
git pull origin main
# edit a file
git status
git diff
git add FILE
git diff --staged
git commit -m "Clarify guacamole instructions"
git log --oneline
git push origin main
```

Do not treat these as a magic recipe. At each step, be able to explain what state is changing.

Small, meaningful commits are easier to read, review, recover, and collaborate around.

For continuity with the earlier Carpentries session, use `guacamole.md` as the familiar specimen. Ask: **"Six months from now, will this commit message tell another person why this version exists?"**

## 4. Remotes are relationships

`origin` is a local name for a remote repository. It is not a special place built into Git.

Inspect configured remotes with:

```bash
git remote -v
```

Useful remote operations include:

```bash
git remote add NAME URL
git remote set-url NAME NEW-URL
git remote rename OLD-NAME NEW-NAME
git remote remove NAME
```

Removing a remote removes the local relationship. It does not delete the hosted repository.

## 5. Review somebody else's change

After a collaborator pushes, inspect the record before editing again.

From the command line, use tools such as:

```bash
git status
git log --oneline
git show
git diff
```

On GitHub, inspect the commit and its diff. Comments on a commit or pull request can make review part of the project record.

Ask:

**What can I know about this change from the record?**

Then:

**What can I not know from Git alone?**

Git records change. Documentation, people, and community discussion help explain meaning and decisions.

## 6. When a push is rejected

A rejected push is evidence, not a cue to force the push.

Use:

**EXPECT → OBSERVE → EXPLAIN → TEST → ACT → VERIFY**

Start by reading the rejection. Then inspect the repository and remote state.

A common case is that GitHub contains commits your local branch does not yet contain. Integrate the shared work before trying to publish your own work.

If overlapping changes produce a conflict, Git stops and asks a human to decide the intended content.

Conflict markers look like:

```text
<<<<<<< HEAD
local version
=======
remote version
>>>>>>> commit
```

Resolve the content deliberately, remove the markers, then:

```bash
git add FILE
git status
git commit -m "Merge changes from GitHub"
git push origin main
```

A conflict is not Git failing. It is Git refusing to guess which human decision is correct.

## 7. Inspect and recover history

`HEAD` refers to the current commit. Earlier commits can be inspected with commit IDs or relative names such as `HEAD~1`.

Useful commands include:

```bash
git log --oneline
git show HEAD
git diff HEAD~1
```

For an uncommitted working-file change that you intentionally want to discard, `git restore FILE` can restore the version recorded in `HEAD`.

Do not use recovery commands until you can say which version you intend to keep.

## 8. Decide what belongs in the repository

When Git notices files, do not automatically stage everything.

Use:

**TRACK → IGNORE → INVESTIGATE**

A `.gitignore` file records patterns for files the project intentionally does not track. Track the `.gitignore` itself when collaborators should share those rules.

Remember: ignoring a file does not delete it, and adding a pattern does not automatically stop tracking a file that is already tracked.

## 9. Make the repository reusable

A professional repository should help another person understand whether and how they may use the work.

Consider:

- `README.md` for purpose, context, sources, and instructions;
- `.gitignore` for intentional exclusions;
- `LICENSE` for reuse permissions;
- `CITATION.cff` or another citation file when the work should be cited;
- clear provenance for data and other source material.

Public visibility is not the same as permission to reuse. Institutional, intellectual-property, privacy, human-subjects, and sensitive-data rules still apply wherever a repository is hosted.

## 10. RStudio is another view of the same Git states

RStudio can expose common Git actions through its Git pane: stage, commit, inspect diffs, view history, pull, and push.

The interface changes. The reasoning does not.

Before clicking, ask:

- What repository is this project connected to?
- What is staged?
- What will this button change?
- Where will the result be recorded?
- How will I verify it?

## 11. Build something you keep

Create or develop a repository that represents your own learning or work. It might contain research notes, a small dataset, an R script, documentation, a class project, metadata work, or another appropriate artifact.

Your README should tell another person:

- what the project is;
- why it exists;
- where its material or data came from;
- what you did;
- how to understand or reproduce it;
- what skills the project demonstrates.

## 12. Explain without taking over

Before leaving, explain one repository decision or diagnose one small Git situation aloud with another learner, helper, or instructor.

Use:

**EXPECT → OBSERVE → EXPLAIN → TEST → ACT → VERIFY**

A useful sentence is:

> "I expected ___, but I observed ___. I think ___ may explain it. I can test that by ___."

If you help another person, do not take their keyboard. Help them read the evidence and decide.

## What you should leave able to do

You do not need to memorize every command.

You should be able to:

- locate yourself and the repository before acting;
- distinguish Git from GitHub and local from remote;
- clone and inspect an unfamiliar repository;
- pull, make a reasoned change, stage, commit, review, and push;
- read a rejected push or conflict as evidence;
- inspect and recover history deliberately;
- decide what to track or ignore;
- explain licensing, citation, and hosting as repository decisions;
- recognize the same Git states in RStudio; and
- continue developing a repository that can serve as evidence of your work.

The commands may change. The reasoning should become familiar.

## Continue practicing

After the workshop, you can continue with:

- **Exercism** for free coding-literacy practice;
- **Stack Overflow** for searching and asking technical questions;
- **Alliance for Data Science and AI** for continuing education and community practice opportunities; and
- **sandbox.bio** for interactive Carpentries Programming with Python exercises.

When using community answers or unfamiliar commands, keep the same habit: understand what a command is expected to do, establish its scope, test safely, and verify the result.


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
