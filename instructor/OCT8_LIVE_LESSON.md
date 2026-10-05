# GitHub Carpentries: Oct. 8 Live Lesson

## From Local Git to Shared, Inspectable Work

**Time:** 1:00-4:00 PM  
**Instructor:** Rebekah Silverstein  
**Helpers:** Frances and Dani  
**Setting:** Digital Scholarship Center  
**Foundation:** Software Carpentry, *Version Control with Git*  
**TRY repository:** https://github.com/RebekahZipp/GitHubCarpentries-Examples

This is the **day-of teaching script**. Teach it top to bottom. Each phase uses the same structure so you can find the next move quickly.

> **Course refrain:** The commands may change. The reasoning should become familiar.

---

# Before class

## Instructor setup checklist

- [ ] Git is installed on the teaching computer.
- [ ] Git Bash or another terminal is open and readable on the projector.
- [ ] GitHub is signed in.
- [ ] TRY repository opens in the browser.
- [ ] TRY repository is cloned locally.
- [ ] `guacamole.md` is present.
- [ ] Teams workshop chat is open.
- [ ] Student lesson and whole-class cheat sheet are open.
- [ ] RStudio is available for the transfer demo.
- [ ] Pair plan is ready.
- [ ] Owner/Collaborator access can be granted.
- [ ] One fallback BUILD repository is available if an account is blocked.
- [ ] Frances and Dani know the catch-up checkpoints and escalation rule.

## Accessibility and inclusion

- Give quiet think time before taking answers.
- Accept spoken or Teams responses.
- Let pairs reason before whole-room correction.
- Treat mistakes as evidence about the work, never as evidence about a learner.
- Ask before touching another person's keyboard.
- Do not require public disclosure of errors, credentials, private repositories, or sensitive data.

## Activity labels

**DEMO** = watch, predict, discuss.  
**TRY** = use the local class example.  
**BUILD** = work in a learner-owned or partner-owned repository.  
**TALK** = speak or contribute to Teams.

## Standard prompts

Use these instead of inventing a new evidence question each time:

1. **What changed?**
2. **What state are we in?**
3. **What does Git say?**
4. **What should we do next?**
5. **How will we verify?**

## Instructor language bank

Use these when useful, not in every section.

> "Git is literal. It does exactly what we tell it, not what we mean."

> "The commands may change. The reasoning should become familiar."

> "Say it out loud, or put your thought in Teams."

> "Commit records here. Push shares there. Pull brings shared work here."

> "A conflict is Git refusing to invent human intent."

## State strip

Keep this visible:

**UNTRACKED/MODIFIED != STAGED != COMMITTED != PUSHED**

Normal work:

**CHANGE -> INSPECT -> CHOOSE -> RECORD -> REVIEW -> SHARE**

When surprised:

**EXPECT -> OBSERVE -> EXPLAIN -> TEST -> ACT -> VERIFY**

---

# Run of show

| Time | Phase | Learner checkpoint |
| --- | --- | --- |
| 1:00-1:10 | Re-enter Git | Can locate terminal, repo, state, history |
| 1:10-1:25 | Clone and inspect | TRY repo cloned and recognized as Git |
| 1:25-1:40 | Remote and origin | Can explain local vs remote and origin |
| 1:40-1:53 | Pair setup | BUILD repo and roles ready |
| **1:53-2:00** | **Break** | |
| 2:00-2:18 | Collaboration cycle | One meaningful commit shared |
| 2:18-2:33 | Switch roles | Repeat with less instructor support |
| 2:33-2:53 | Rejection and conflict | Can distinguish rejection from conflict |
| **2:53-3:00** | **Break** | |
| 3:00-3:15 | History and recovery | Can inspect before restoring |
| 3:15-3:27 | Track/Ignore/Investigate | Can justify one file decision |
| 3:27-3:40 | Repository context | README improved for another reader |
| 3:40-3:50 | RStudio transfer | Recognizes same Git states in GUI |
| 3:50-4:00 | Explain-back | Can explain one decision and verification |

**If behind:** protect collaboration, conflict reasoning, both breaks, verification, and explain-back. Cut Pages first, then shorten RStudio.

---

# Role cards

## Owner

- owns or controls the BUILD repository;
- grants Collaborator access;
- pulls and reviews the collaborator's work;
- discusses intent before resolving shared changes.

## Collaborator

- accepts access;
- clones the Owner repository;
- pulls before shared work;
- changes, inspects, stages, commits, reviews, and pushes.

## Both

- know whose repository they are in;
- use `status`, diff, and history as evidence;
- discuss intent rather than guessing;
- verify after every shared-state change.

---

# 1:00-1:10 | ORIENT: Re-enter Git before GitHub

**Goal:** Reconnect today's work to the previous Carpentries session and establish the five reusable questions.  
**Mode:** TALK + DEMO

## Say

> "Welcome back. Last time we taught Git how to remember our work. Today we make that record travel."

> "Today we are learning how to make work understandable, safe to recover, and easy to share."

Briefly name DEMO, TRY, BUILD, and TALK. Remind learners that the Carpentries Code of Conduct applies in the room, Teams, and GitHub.

## Ask

> "Before we act, what do we want to know?"

Guide toward location, repository, branch, state, and history.

## Demo

```bash
pwd
git rev-parse --show-toplevel
git status
git log --oneline
```

## Expected learner evidence

- `pwd`: current shell directory.
- `git rev-parse --show-toplevel`: repository root.
- `git status`: branch plus working/staging state.
- `git log --oneline`: recorded history.

**Concept check:** `pwd` and repository root answer different questions.

## Helper cue

If a learner is lost, identify the interpreter and directory before diagnosing Git.

## Common mistake

Git command entered at an R `>` prompt.

## Catch-up

Learner can rejoin when `git status` works in the intended repository.

---

# 1:10-1:25 | CLONE AND INSPECT

**Goal:** Distinguish Git from GitHub and understand clone as a repository relationship.  
**Mode:** DEMO -> TRY + TALK

## Say

> "Git records change. GitHub gives repositories and people a place to connect."

```text
MY COMPUTER             GITHUB              SOMEONE ELSE
local repository  <-->  remote repository  <--> local repository
```

Open the TRY repository.

> "Do not edit yet. Investigate first."

## Ask

> "Where is the repository now? Where do we want another copy? What do you predict clone will bring with it?"

## Try

```bash
git clone https://github.com/RebekahZipp/GitHubCarpentries-Examples.git
cd GitHubCarpentries-Examples
pwd
git rev-parse --show-toplevel
git status
git log --oneline
git remote -v
ls
```

## Expected learner evidence

- repository directory exists locally;
- `git status` identifies a branch and working-tree state;
- `git log --oneline` shows history from before the clone;
- `git remote -v` shows `origin` with fetch and push URLs;
- `guacamole.md` is visible.

**Concept check:** clone is not a ZIP download. It brings Git history and configures a remote relationship.

## Helper cue

For a failed clone, check terminal, `pwd`, existing folder, then exact error.

## Common mistake

Cloning in an unintended directory or inside another project.

## Catch-up

TRY repo exists locally and `git status` works.

---

# 1:25-1:40 | REMOTE AND ORIGIN

**Goal:** Separate local repository, remote repository, commit, push, and pull.  
**Mode:** DEMO + TRY

## Say

> "`origin` is a local nickname for a remote repository. It is conventional, not magical."

> "Commit records here. Push shares there. Pull brings shared work here."

## Demo

```bash
git remote -v
```

```text
LOCAL COMMIT --push--> GITHUB
LOCAL REPO   <--pull-- GITHUB CHANGES
```

## Ask

> "What is local? What is remote? What has been committed? What has actually been shared?"

## Expected learner evidence

`git remote -v` shows `origin` twice, normally once for fetch and once for push.

**Concept check:** committed is not pushed. Removing a local remote nickname does not delete GitHub.

## Common mistake

Treating commit and push as the same action.

---

# 1:40-1:53 | BUILD SETUP AND PAIRS

**Goal:** Move from the shared example to learner-owned collaboration.  
**Mode:** BUILD

## Say

> "TRY was for inspection. BUILD is where your decisions and collaboration become the record."

## Build

Each pair chooses or creates a small repository. Keep `guacamole.md` as the familiar Carpentries specimen so the object stays constant while the collaboration gets harder.

Owner grants access. Collaborator accepts and clones.

```text
PULL -> CHANGE -> INSPECT -> CHOOSE -> RECORD -> REVIEW -> PUSH
```

## Ask

> "Whose repository is this? What role are you in? What remote does this clone point to?"

## Expected learner evidence

Each pair can identify Owner, Collaborator, repository, branch, and remote.

## Helper cue

If account access fails, use the fallback BUILD repository or pair with a functioning account. Do not let permissions consume the lesson.

## Catch-up

A BUILD repository is available and each learner knows their role.

---

# 1:53-2:00 | BREAK 1

Seven minutes. Stop teaching.

Helpers identify only the highest-value pattern to surface after break.

---

# 2:00-2:18 | FIRST COLLABORATION CYCLE

**Goal:** Connect file state, staging, commit history, and remote sharing.  
**Mode:** BUILD + TALK

## Say

> "Before we act: what state are we in?"

## Demo / Build

Collaborator:

```bash
git status
git remote -v
git pull origin main
# edit guacamole.md
git status
git diff
git add guacamole.md
git diff --staged
git commit -m "Clarify guacamole instructions"
git log --oneline
git show HEAD
git push origin main
```

Owner:

```bash
git pull origin main
git status
git log --oneline
git show HEAD
```

## Expected learner evidence

- after edit: `guacamole.md` is modified;
- after `git add`: change is staged;
- `git diff --staged` shows exactly what will be recorded;
- after commit: new commit appears in log;
- after push: GitHub shows the commit;
- after Owner pulls: both copies include the commit.

## Ask

> "What changed? What state are we in? What should we do next? How will we verify?"

> "Six months from now, will this commit message tell another person why this version exists?"

## Common mistake

Typing `git add <file>` literally or staging the wrong filename.

## Catch-up

One meaningful commit is visible on GitHub.

---

# 2:18-2:33 | SWITCH ROLES

**Goal:** Move from following to predicting and explaining.  
**Mode:** BUILD + TALK

## Say

> "First pass: follow. Second pass: explain."

Switch roles. Do not narrate the command sequence.

## Ask

Use only:

> "What state are we in?"

> "What should we do next?"

> "How will we verify?"

If syntax is the barrier, provide syntax. If reasoning is the barrier, ask for the state first.

## Expected learner evidence

Learners can reconstruct:

```text
PULL -> CHANGE -> INSPECT -> CHOOSE -> RECORD -> REVIEW -> PUSH
```

## Helper cue

Ask: "What is the smallest state we need so you can rejoin the group?"

---

# 2:33-2:53 | REJECTED PUSH AND CONFLICT

**Goal:** Distinguish a rejected push from a merge conflict and make the human decision visible.  
**Mode:** BUILD + TALK

## Setup

Both partners change the same line in `guacamole.md` differently.

For example:

```text
Mash until smooth.
```

versus:

```text
Mash, leaving it slightly chunky.
```

Person A commits and pushes. Person B commits locally and attempts:

```bash
git push origin main
```

## Say

> "Stop. Read before fixing."

## Ask

> "What changed? What state are we in? What does Git say?"

A **rejected push** means the remote contains history this local branch does not yet contain. It is not yet the same thing as a merge conflict.

## Act

```bash
git pull origin main
```

If overlapping edits conflict, inspect:

```text
<<<<<<< HEAD
local version
=======
incoming version
>>>>>>> commit
```

## Ask

> "Can Git tell us which guacamole tastes better?"

No. Git can preserve competing versions. People decide intended content.

Resolve the wording, remove markers, then:

```bash
git add guacamole.md
git status
git commit -m "Resolve guacamole wording conflict"
git push origin main
git status
git log --oneline
```

Partner pulls and verifies.

## Expected learner evidence

- rejected push message appears before pull;
- after pull, conflict markers appear only if overlapping changes require a human decision;
- after resolution and `git add`, Git recognizes the conflict as resolved;
- after commit/push/pull, both copies contain the agreed wording.

**Concept check:** rejected push != merge conflict.

## Helper cue

Do not jump to force push. Ask what changed remotely and what Git is waiting for.

## Common mistake

Editing conflict markers correctly but forgetting `git add`.

## Catch-up

Learner can explain the difference between the rejection and the conflict. Mechanical cleanup can finish later.

---

# 2:53-3:00 | BREAK 2

Seven minutes. Stop teaching.

Helpers identify learners still mid-conflict and prepare them for the 3:00 checkpoint without erasing the evidence.

---

# 3:00-3:15 | HISTORY AND RECOVERY

**Goal:** Inspect intended state before using a recovery command.  
**Mode:** DEMO -> TRY

## Demo

```bash
git log --oneline
git show HEAD
git diff HEAD~1
```

Make a harmless uncommitted change.

```bash
git diff
```

Only after deciding it should be discarded:

```bash
git restore FILE
git status
```

## Expected learner evidence

- `HEAD` identifies the current commit;
- `git show HEAD` displays that commit;
- `git diff HEAD~1` compares states;
- after deliberate restore, the unwanted working-tree change disappears.

## Ask

> "Which version are we trying to keep?"

## Common mistake

Using an undo command before identifying intended state.

## Helper cue

If `not a git repository` appears, use the emergency pathway below before doing anything else.

---

# 3:15-3:27 | TRACK, IGNORE, INVESTIGATE

**Goal:** Decide deliberately what belongs in the repository.  
**Mode:** TRY -> BUILD

## Demo

```bash
cat .gitignore
git status --ignored
git check-ignore -v PATH
```

## Expected learner evidence

`git check-ignore -v PATH` identifies the matching ignore rule when one applies.

## Ask

> "Git noticed a file. Does that mean it belongs in the record?"

Use:

**TRACK -> IGNORE -> INVESTIGATE**

## Common mistake

Assuming a new ignore pattern stops tracking a file that Git already tracks.

---

# 3:27-3:40 | REPOSITORY DOCUMENTATION

**Goal:** Make the repository understandable to someone who was not in the room.  
**Mode:** BUILD + TALK

Inspect:

- `README.md`
- `.gitignore`
- `LICENSE`
- `CITATION.cff`
- provenance/notes
- Git history

## Ask

> "What can another person understand from this repository six months from now?"

Learners improve README with:

- what the project is;
- why it exists;
- where material came from;
- how to understand or reproduce it;
- the next known step.

## Expected learner evidence

README communicates purpose and context without requiring the instructor to explain it.

**Concept check:** visible != permission to reuse; recorded != correct; data != interpretation.

---

# 3:40-3:50 | RSTUDIO TRANSFER

**Goal:** Recognize the same Git states in a different interface.  
**Mode:** DEMO

## Say

> "The interface changed. The repository states did not."

Show the Git pane. Map GUI actions to status, diff, stage, commit, pull, push, and history.

## Ask

> "What is staged? What will this control change? How will we verify?"

## Expected learner evidence

Learners can name the Git state or action represented by the GUI instead of treating the button as a new concept.

**If behind:** skip this section before sacrificing explain-back.

---

# 3:50-4:00 | EXPLAIN-BACK AND CLOSE

**Goal:** Transfer responsibility from instructor prompts to learner explanation.  
**Mode:** BUILD + TALK

Minimum repository state:

```text
README.md
guacamole.md or another meaningful tracked artifact
readable commit history
known remote
intentional next step
```

Pair learners. Each explains one repository decision or diagnoses one small Git situation without taking the other's keyboard.

Use:

> "I expected ___. I observed ___. I did ___. I verified it by ___."

## Ask

> "What can you explain now that you could only follow at the beginning?"

> "What question do you still have?"

## Close

> "Version control is more than saving files. We observed change, made a decision, recorded it, checked the record, and shared it."

> "Git records change. People decide what the change means."

> "The commands may change. The reasoning should become familiar."

---

# Emergency pathway: if learners are lost

Use the smallest diagnostic that answers the immediate question.

## Cannot find the repository

```bash
pwd
git rev-parse --show-toplevel
```

## Cannot identify the branch

```bash
git branch --show-current
```

## Cannot see the remote

```bash
git remote -v
```

## Cannot tell whether a change is staged

```bash
git status
git diff
git diff --staged
```

## Cannot tell what was recorded

```bash
git log --oneline
git show HEAD
```

## Cannot tell why a path is ignored

```bash
git check-ignore -v PATH
```

If scope is unclear or a command could overwrite/delete work, stop and ask a helper or instructor before acting.

---

# Helper quick strip

**LOCATE -> OBSERVE -> ASK -> VERIFY -> HAND OFF**

Helpers:

- establish terminal, directory, repository, branch, and remote as needed;
- read the exact message before fixing;
- do not take the keyboard unless invited and necessary;
- surface repeated questions to the instructor;
- protect credentials and private data;
- stop destructive or history-rewriting interventions until scope is understood.

Ask:

> "What is the smallest state we need so you can rejoin the group?"

---

# Common mistakes index

| Symptom | First move | Concept |
| --- | --- | --- |
| `not a git repository` | `pwd` / repo root | location |
| Git command at `>` | identify interpreter | terminal vs R console |
| `git log --online` | read literal command | syntax |
| `git add <file>` | use actual filename | placeholder vs value |
| output pasted as command | identify who is speaking | output != input |
| wrong filename/pathspec | `ls` | literal paths |
| rejected push | read remote-state message | shared history |
| merge conflict | identify human content decision | intent |
| ignored-file surprise | `git check-ignore -v` | ignore rules |
| no error but wrong result | verify intended state | success != intent |

---

# Teaching design: seven rules

1. Use **narrative -> command -> evidence -> practice -> review**.
2. Reuse the same concepts in new contexts rather than introducing new slogans.
3. Increase responsibility: **FOLLOW -> RECOGNIZE -> PREDICT -> EXPLAIN -> ACT -> HELP OTHERS**.
4. Ask questions as invitations, not tests. Quiet thinking and Teams responses count.
5. Keep `guacamole.md` as the familiar specimen while the collaboration complexity changes.
6. Treat errors as evidence. Diagnose before acting.
7. Preserve the Carpentries foundation while adding OSU Libraries collaboration, troubleshooting, safety, and professional practice.
