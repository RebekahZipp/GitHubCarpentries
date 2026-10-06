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

**DEMO + DO** = I model one small move; you make the same move with me.  
**TRY** = we pause after a move so you can inspect, predict, or repeat it in the safe class example.  
**BUILD** = we use the same hands-on rhythm in a learner-owned or partner-owned repository.  
**TALK** = we stop typing long enough to explain what the evidence means aloud or in Teams.

**Default workshop rhythm:** **WATCH ONE MOVE -> DO THE MOVE -> STOP -> READ THE OUTPUT -> ASK WHAT IT MEANS -> CONTINUE.**

Do not demonstrate a long command sequence and then ask learners to reproduce it from memory. Commands are taught in small synchronized chunks.

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

## Hands-on facilitation rule

The Carpentries lesson is taught by doing. Mirror that flow here.

For every technical sequence:

1. **SAY** what question the next move answers.
2. **ASK** learners to predict when useful.
3. **DEMO + DO** one command or one small command pair.
4. **STOP** typing.
5. **READ** the output together.
6. **ASK** what the output tells us.
7. **SAY** the conclusion and connect it to the next move.

The instructor and learners should usually be at the same checkpoint. Use helpers to recover learners to the current checkpoint rather than letting the class become two separate tracks.

# Run of show

| Time | Phase | Learner checkpoint |
| --- | --- | --- |
| 1:00-1:10 | Setup + Code of Conduct | Git/GitHub/terminal ready; knows how we work together |
| 1:10-1:20 | Re-enter Git | Can locate terminal, repo, state, history |
| 1:20-1:33 | Clone and inspect | TRY repo cloned and recognized as Git |
| 1:33-1:43 | Remote and origin | Can explain local vs remote and origin |
| 1:43-1:53 | Pair setup | BUILD repo and roles ready |
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

# 1:00-1:10 | SETUP + CODE OF CONDUCT

**Goal:** Get every learner to a usable starting point while establishing how we will learn and collaborate.  
**Mode:** SETUP + TALK

## Say

> "Welcome. Before Git can track our work, we need to make sure Git can find us. Use these first ten minutes to get your computer, terminal, and GitHub account ready. If you are already set up, help us verify rather than racing ahead."

> "While we get everyone connected, I also want to name how we will work together. This workshop follows [The Carpentries Code of Conduct](https://docs.carpentries.org/policies/coc/). It applies here in the room and in the online spaces we use, including Teams and GitHub. The short version is: use welcoming and inclusive language, respect different viewpoints and experience levels, accept constructive feedback, and show courtesy to one another."

> "That matters technically, too. Today we will look at each other's work, ask questions, encounter errors, and sometimes disagree about what a file should say. We critique the work and the evidence, not the person. Ask before touching someone else's keyboard. Do not share passwords, tokens, private repository information, patron information, or other sensitive data."

> "You will see four labels. **DEMO** means I show a move and we read the result together. **TRY** means you experiment in our safe class example. **BUILD** means you make something in a repository you can keep. **TALK** means you can answer aloud or in Teams. You do not need to be the fastest person in the room. You do need to stay curious about what the computer is telling us."

## Setup

Learners verify:

```bash
git --version
```

Then confirm:

- Git Bash or another terminal is available;
- GitHub account can be opened;
- GitHub authentication/2FA is complete if required;
- workshop Teams chat is open;
- student lesson and cheat sheet are available.

If Git is not installed, use the Carpentries setup instructions:  
https://carpentries.github.io/workshop-template/install_instructions/#git

If GitHub account setup is incomplete, pair the learner with a working partner for the first activity while a helper assists. Do not hold the whole room on account recovery.

## Ask

> "What do you need in place before you can participate: a terminal, Git, GitHub, or all three? Which parts are local to your computer, and which part is on the web?"

Give learners time to answer.

## Expected learner evidence

- `git --version` returns a Git version for learners who are configured;
- terminal is open;
- GitHub is reachable;
- learners know where to ask for setup help;
- learners can state that Git is local software and GitHub is a web service used later for sharing/collaboration.

## Helper cue

Frances and Dani split setup support. One helper handles installation/account blockers while the other scans for terminal, directory, or authentication problems.

Do not ask a learner to expose a password, token, recovery code, or authentication secret.

## Common mistake

A learner opens the R Console instead of a terminal. Identify the interpreter before troubleshooting Git.

## Transition Say

> "Now we have the room, the tools, and the rules of collaboration in place. Our next question is not 'What command do I type?' It is 'What do I want to know before I act?' That question will carry us through the rest of the workshop."

---

# 1:10-1:20 | ORIENT: Re-enter Git before GitHub

**Goal:** Reconnect today's work to the previous Carpentries session and establish the five reusable questions.  
**Mode:** TALK + DEMO

## Say

> "Last time, Git learned to remember our work. Today we are going to ask where that memory lives, what state it is in, and how to move it without losing the story."

> "I will demonstrate first. You will read the evidence with me. Then you will try the same reasoning yourself. Before every action, we are going to ask what we need to know."

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

# 1:20-1:33 | CLONE AND INSPECT

**Goal:** Distinguish Git from GitHub and understand clone as a repository relationship.  
**Mode:** DEMO + DO -> STOP + READ -> TALK

## Say

> "We know Git can remember a project locally. Now we are going to make a second copy without turning it into an emailed attachment. I will make one move, then you will make the same move. We will stop and read what Git tells us before moving on."

```text
MY COMPUTER             GITHUB              SOMEONE ELSE
local repository  <-->  remote repository  <--> local repository
```

Open the TRY repository together:

https://github.com/RebekahZipp/GitHubCarpentries-Examples

> "Do not edit yet. Investigate first."

## Ask before typing

> "Where is this repository right now?"

> "Where on your computer do you want the local copy to live?"

> "What do you predict clone will bring with it: only the visible files, or something more?"

Take one or two answers. Then begin the synchronized hands-on sequence.

## DEMO + DO 1: locate ourselves

Instructor runs:

```bash
pwd
```

Learners run:

```bash
pwd
```

## Stop and read

**Expected evidence:** each person sees the directory where the shell is currently located.

## Ask

> "If we clone now, where will Git create the new repository folder?"

If someone is in the wrong parent directory, fix location now, before cloning.

## Say

> "Good. We know where the copy will land. Now we can clone intentionally instead of hunting for it afterward."

## DEMO + DO 2: clone

Instructor runs:

```bash
git clone https://github.com/RebekahZipp/GitHubCarpentries-Examples.git
```

Learners run the same command.

## Stop and read

Do not immediately type the next command.

Ask:

> "What did Git say it was doing?"

Look for language about **cloning**, **receiving objects**, or completion.

Then:

```bash
ls
```

Learners run `ls`.

**Expected evidence:** `GitHubCarpentries-Examples` now appears as a local directory.

## Say

> "We asked Git for another repository, and now we have a new local directory. But a directory alone does not prove that its Git history came with it. Let's go inside and ask."

## DEMO + DO 3: enter and establish repository scope

Instructor:

```bash
cd GitHubCarpentries-Examples
pwd
git rev-parse --show-toplevel
```

Learners do the same.

## Stop and read

**Expected evidence:**

- `pwd` ends in `GitHubCarpentries-Examples`;
- `git rev-parse --show-toplevel` identifies that directory as the repository root.

## Ask

> "What did `pwd` tell us?"

Take an answer.

> "What did Git tell us that `pwd` could not?"

## Say

> "`pwd` tells us where the shell is. Git tells us where the repository begins. Now that we know where we are, we can ask what state and history came with the clone."

## DEMO + DO 4: inspect state

Instructor:

```bash
git status
```

Learners run it.

## Stop and read

**Expected evidence:** branch information and a clean or otherwise described working-tree state.

## Ask

> "What state does Git think this repository is in right now?"

Do not translate the output before learners have a chance to read it.

## DEMO + DO 5: inspect history

Instructor:

```bash
git log --oneline
```

Learners run it.

## Stop and read

**Expected evidence:** commits exist from before anyone in the room cloned the repository.

## Ask

> "Did we create those commits just now?"

> "So what came with the clone besides the visible files?"

## Say

> "That is our first important piece of evidence: clone brought the project's recorded history with it."

## DEMO + DO 6: inspect the remote relationship

Instructor:

```bash
git remote -v
```

Learners run it.

## Stop and read

**Expected evidence:** `origin` appears with the GitHub URL for fetch and push.

## Ask

> "We have a local repository. What evidence tells us it still knows about the GitHub repository it came from?"

Take an answer pointing to `origin` and the URL.

## DEMO + DO 7: inspect the files

```bash
ls
```

Learners locate `guacamole.md`.

## Ask

> "What familiar file do you see?"

Use guacamole to connect this session to the earlier Carpentries Git work.

## Build the concept together

Ask:

> "Based on the evidence we just collected, finish this sentence: cloning gave me ______."

Listen for **files**, **history**, **repository**, and **remote/origin relationship**.

Then summarize:

> "Exactly. Clone did not just download files. It created a local Git repository with recorded history and a configured relationship back to GitHub."

## Concept check

**Clone != ZIP download**

A clone gives us:

```text
FILES + GIT HISTORY + LOCAL REPOSITORY + REMOTE RELATIONSHIP
```

## Helper cue

Stay synchronized with the room. If one learner fails at a step, a helper works only to the current checkpoint. Check:

1. terminal;
2. `pwd`;
3. whether the target folder already exists;
4. exact error text.

Do not run later commands for them while the room moves ahead.

## Common mistake

Cloning in an unintended directory or inside another project.

Ask:

> "Where did the shell say we were before we cloned?"

## Catch-up

Learner can rejoin when:

```bash
cd GitHubCarpentries-Examples
git status
```

works.

## Transition Say

> "We have proved that clone brought history with it and left a relationship back to GitHub. Next we are going to inspect that relationship more closely. The name Git gives us for it is `origin`."

---

# 1:33-1:43 | REMOTE AND ORIGIN

**Goal:** Separate local repository, remote repository, commit, push, and pull.  
**Mode:** DEMO + TRY

## Say

> "The clone gave us more than files. It also gave this local repository an address book entry called `origin`. We are going to read that relationship before we use it."

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

# 1:43-1:53 | BUILD SETUP AND PAIRS

**Goal:** Move from the shared example to learner-owned collaboration.  
**Mode:** BUILD

## Say

> "We have inspected someone else's repository. Now we change responsibility. BUILD is where you create a reading record you can keep, make a decision worth recording, and then let another person collaborate with you."

## Build

Each learner creates or chooses a small repository they can keep after class. Use a **Books I Have Read** reading list as the default BUILD artifact. This gives every learner a useful, low-risk document that can continue growing after the workshop. Keep `guacamole.md` in the TRY repository as the familiar Carpentries specimen for continuity, but move substantive learner work into the reading-list repository.

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
# edit books.md
git status
git diff
git add books.md
git diff --staged
git commit -m "Add first books to reading list"
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

> "Six months from now, will this commit message tell another person what changed and why this version exists?"

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

Use `guacamole.md` for the instructor's controlled conflict demonstration. Then give learners the same reasoning challenge in their reading-list repository: both partners edit the same book entry or the same `Notes` line differently.

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
git add FILE
git status
git commit -m "Resolve conflicting reading-list edit"
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
books.md
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

# Practice challenge: Books I Have Read

**Purpose:** Give learners something personally useful to keep, revisit, and grow after class.

Create:

```text
books-i-have-read/
├── README.md
└── books.md
```

Suggested `books.md` starter:

```markdown
# Books I Have Read

| Title | Author | Date Finished | Publisher | Rating | Notes |
| --- | --- | --- | --- | --- | --- |
| Such Sharp Teeth | Rachel Harrison | 2022-10-03 | Penguin Publishing Group | | |
| I, Medusa | Ayana Gray | 2025-11-17 | Random House Publishing Group | | |
| The Penelopiad | Margaret Atwood | 2014-10-22 | Faber & Faber | | |
```

Suggested `README.md` starter:

```markdown
# Books I Have Read

A personal reading log I can keep updating over time.

## How I use this repository

- Add each finished book to `books.md`.
- Commit meaningful updates.
- Use the Git history to see how the list changed over time.
```

## Challenge 1: What state are we in?

Give learners 2 minutes before discussing.

```bash
pwd
git rev-parse --show-toplevel
git status
git branch --show-current
git remote -v
```

**Answer / instructor workaround**

- `pwd` answers: where is my shell?
- `git rev-parse --show-toplevel` answers: where does this repository begin?
- `git status` answers: what branch and file state does Git see?
- `git branch --show-current` answers: what branch am I on?
- `git remote -v` answers: where can this local repository fetch from or push to?

If `not a git repository` appears, do not start fixing Git. Check `pwd`, then move to the repository directory.

## Challenge 2: Add a book without blindly staging everything

Ask learners to add one real or fictional book to `books.md`.

Before showing the answer, ask:

> "What changed? What does Git say? What should we inspect before recording it?"

**Answer / instructor workaround**

```bash
git status
git diff
git add books.md
git diff --staged
git commit -m "Add The Left Hand of Darkness to reading list"
git log --oneline
```

**Expected evidence**

- before `git add`: `books.md` appears modified;
- `git diff` shows the new row;
- after `git add`: the change is staged;
- `git diff --staged` shows exactly what the commit will preserve;
- after commit: a new commit appears in `git log --oneline`.

**Common wrong turn**

```bash
git add .
```

Workaround: ask whether every visible file belongs to the same decision. Prefer `git add books.md` for this exercise.

## Challenge 3: Commit versus push

Ask:

> "I committed my new book. Can my partner see it on GitHub yet?"

Give them time to answer before running anything.

**Answer**

Not necessarily. A commit records locally. A push shares recorded commits with the remote.

```bash
git status
git log --oneline
git push origin main
```

**Verify**

Open GitHub and confirm the commit and changed `books.md` are visible.

## Challenge 4: Partner collaboration

Partner A adds one book and pushes. Partner B does not edit yet.

Ask Partner B:

> "What should we do before starting new shared work?"

**Answer**

```bash
git pull origin main
git status
git log --oneline
```

Then Partner B adds another book, inspects, stages, commits, reviews, and pushes.

**Concept answer:** pull brings shared history into the local repository. It does not replace the need to inspect local state.

## Challenge 5: Rejected push or conflict?

Have both partners begin from the same version.

- Partner A changes the Notes cell for one book, commits, and pushes.
- Partner B changes the **same Notes cell** differently, commits locally, and tries to push.

Ask:

> "What happened first: a rejected push or a merge conflict?"

**Answer**

First, the push is rejected because the remote contains history Partner B does not have.

Then:

```bash
git pull origin main
```

If the edits overlap, Git may produce a merge conflict.

**Concept answer**

- **Rejected push:** remote history is ahead of this local branch.
- **Merge conflict:** after trying to combine histories, Git finds incompatible content choices that require a human decision.

If conflict markers appear:

```text
<<<<<<< HEAD
my version
=======
their version
>>>>>>> commit
```

Resolve the intended text, then:

```bash
git add books.md
git status
git commit -m "Resolve conflicting reading-list note"
git push origin main
git status
git log --oneline
```

**Instructor line:** Git can preserve both proposed notes. It cannot decide which interpretation belongs in the final reading record.

## Challenge 6: History and recovery

Ask learners to make a harmless uncommitted edit to one rating or note.

Ask:

> "How can we inspect before deciding whether to keep it?"

**Answer**

```bash
git diff
git log --oneline
git show HEAD
```

If they decide to discard the uncommitted change:

```bash
git restore books.md
git status
```

**Concept answer:** decide which state you intend to keep before choosing a recovery command.

## Challenge 7: Track, ignore, or investigate?

Create or point to a harmless temporary file such as `scratch.txt`.

Ask:

> "Should this become part of the durable reading record?"

Give learners three choices:

**TRACK -> IGNORE -> INVESTIGATE**

**Possible answer**

If it is temporary and not useful to future readers, ignore it.

Add to `.gitignore`:

```text
scratch.txt
```

Then verify:

```bash
git status --ignored
git check-ignore -v scratch.txt
```

If learners are unsure whether a file matters, choose **investigate** before staging or ignoring.

## Challenge 8: Make the repository useful six months from now

Ask learners to improve `README.md` so another person can understand the project without asking the instructor.

A strong answer includes:

- what the repository is;
- what year or period it covers;
- how books are added;
- what the fields mean;
- whether ratings are personal;
- what a future update should look like.

**Verification question**

> "Could someone who was not in this workshop add the next book correctly?"

## Answer bank: the questions you ask repeatedly

**What changed?**  
Use `git status` and `git diff`.

**What state are we in?**  
Use `git status`, `git branch --show-current`, and when needed `git diff --staged`.

**What does Git say?**  
Read the exact output before choosing another command.

**What should we do next?**  
Choose the smallest action supported by the evidence.

**How will we verify?**  
Use `git status`, `git log --oneline`, `git show HEAD`, the remote view on GitHub, or the collaborator's pull.

## Instructor rule for challenges

Give learners quiet time first. Then ask for one explanation aloud or in Teams. Only after they have reasoned should you reveal the answer/workaround.

The teaching sequence is:

**PREDICT -> TRY -> READ THE EVIDENCE -> EXPLAIN -> REVEAL WORKAROUND -> VERIFY**

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
