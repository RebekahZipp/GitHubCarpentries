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
- [ ] Student lesson and whole-class cheat sheet are open.
- [ ] RStudio is available for the transfer demo.
- [ ] `build-example/books.md` is present in the TRY repository on GitHub.
- [ ] Frances and Dani know the catch-up checkpoints and escalation rule.

## Accessibility and inclusion

- Give quiet think time before taking answers.
- Accept spoken responses and give learners time to think before whole-room correction.
- Treat mistakes as evidence about the work, never as evidence about a learner.
- Ask before touching another person's keyboard.
- Do not require public disclosure of errors, credentials, private repositories, or sensitive data.

## Activity labels

**DEMO + DO** = I model one small move; you make the same move with me.  
**TRY** = we pause after a move so you can inspect, predict, or repeat it in the safe class example.  
**BUILD** = we make meaningful local changes in each learner's clone of the class repository.  
**TALK** = we stop typing long enough to explain what the evidence means aloud.

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
| 1:43-1:53 | From TRY to BUILD | Reading-list artifact located; clean local clone ready for first change |
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

# 1:00-1:10 | SETUP + CODE OF CONDUCT

**Goal:** Get every learner to a usable starting point while establishing how we will learn and collaborate.  
**Mode:** SETUP + TALK

## Say

> "Welcome. Before Git can track our work, we need to make sure Git can find us. Use these first ten minutes to get your computer, terminal, and GitHub account ready. If you are already set up, help us verify rather than racing ahead."

> "While we get everyone connected, I also want to name how we will work together. This workshop follows [The Carpentries Code of Conduct](https://docs.carpentries.org/policies/coc/). It applies here in the room and in the GitHub spaces we use. The short version is: use welcoming and inclusive language, respect different viewpoints and experience levels, accept constructive feedback, and show courtesy to one another."

> "That matters technically, too. Today we will look at each other's work, ask questions, encounter errors, and sometimes disagree about what a file should say. We critique the work and the evidence, not the person. Ask before touching someone else's keyboard. Do not share passwords, tokens, private repository information, patron information, or other sensitive data."

> "You will see four labels. **DEMO + DO** means I make one small move and you make the same move with me. **TRY** means we pause to inspect, predict, or repeat something safely. **BUILD** means we make meaningful changes in the local clone you already have. **TALK** means we stop typing and explain what the evidence means aloud. You do not need to be the fastest person in the room. You do need to stay curious about what the computer is telling us."

## Setup

Learners verify:

```bash
git --version
```

Then confirm:

- Git Bash or another terminal is available;
- GitHub account can be opened;
- GitHub authentication/2FA is complete if required;
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

# 1:33-1:43 | REMOTE, ORIGIN, AND PULL

**Goal:** Separate the local repository from the GitHub remote and use evidence to explain what `origin`, fetch/push addresses, commit, and pull mean.  
**Mode:** DEMO + DO -> STOP + READ -> TALK

## Say

> "The clone gave us more than files and history. It also gave this local repository an address-book entry called `origin`. Before we use that relationship, we are going to read it."

> "The question is not 'What Git command comes next?' The question is 'What relationship does this local repository already know about?'"

## DEMO + DO 1: read the remote relationship

Instructor and learners run:

```bash
git remote -v
```

## Stop and read

Expected evidence resembles:

```text
origin  https://github.com/RebekahZipp/GitHubCarpentries-Examples.git (fetch)
origin  https://github.com/RebekahZipp/GitHubCarpentries-Examples.git (push)
```

## Ask

> "What name did Git give this remote relationship?"

Listen for **origin**.

> "What repository does that name point to?"

> "Why do we see the address twice?"

## Say

> "`origin` is a local nickname for this remote repository. It is conventional, not magical. One line is the address Git can fetch from and one is the address it can push to."

Draw or point to:

```text
MY LOCAL CLONE                         GITHUB
GitHubCarpentries-Examples  <------>  RebekahZipp/GitHubCarpentries-Examples
                         origin
```

> "Commit records a version in my local repository. Push attempts to share my local commits with the remote. Pull brings remote work into this existing local clone. Those are different actions."

## ASK: predict before contacting GitHub

> "Our working tree is clean. Does that prove GitHub has nothing newer than our local clone?"

Take answers before running anything.

## DEMO + DO 2: inspect local state

```bash
git status
```

## Stop and read

If Git reports the branch as up to date, ask:

> "What does this tell us about the state our local Git currently knows? Has this command contacted GitHub to discover brand-new work?"

## Say

> "Status is evidence about our local repository and its locally stored knowledge of the remote-tracking branch. To ask GitHub for newer work, we need to contact the remote."

## DEMO + DO 3: pull

```bash
git pull origin main
```

## Stop and read

Do not type the next command yet.

If the prepared BUILD update has not already been pulled, learners should see Git contact GitHub and bring in the `build-example` files. Read the output together. Look for:

- `From https://github.com/...`;
- `main -> origin/main`;
- `Fast-forward` when applicable;
- `build-example/README.md`;
- `build-example/books.md`.

If a learner already has the newest version, Git may instead report **Already up to date.** That is also valid evidence.

## Ask

> "What did `pull` do that `status` did not?"

> "If files arrived, what evidence tells us exactly what arrived?"

## Say

> "Pull contacted the remote. In our prepared example, it can bring the reading-list material into a clone that existed before those files were added. We did not clone again. We updated the clone we already had."

### Teaching moment: output is not input

If someone copies a line such as:

```text
From https://github.com/RebekahZipp/GitHubCarpentries-Examples
```

back into Bash and receives `command not found`, use it.

> "That line was Git talking to us. It was output, not another command. Part of terminal literacy is learning which text we type and which text we read."

## Concept check

```text
COMMIT = record here
PUSH   = attempt to share there
PULL   = bring remote work here
```

**Committed != pushed.**

## Helper cue

If a pull does not behave as expected, first check `pwd`, `git status`, and `git remote -v`. Do not reclone as the first repair.

## Catch-up

Learner can rejoin when they are inside `GitHubCarpentries-Examples`, `git status` works, and `git remote -v` identifies the class repository as `origin`.

## Transition Say

> "We now know where this clone came from and how later shared work can arrive. Everything so far has been observation. Next we are going to find the reading-list example and prepare to make our first local change."

---

# 1:43-1:53 | FROM TRY TO BUILD: FIND THE READING LIST

**Goal:** Move from investigating the class repository to meaningful work inside each learner's own local clone.  
**Mode:** BUILD

**Important:** Learners do **not** create a second repository here. They already have a complete local Git repository because they cloned `GitHubCarpentries-Examples`. Before the collaboration exercise, invite each learner as a collaborator on the public example repository. Their local commits remain local until they push, but collaborator access lets the class practice the complete Carpentries workflow against one shared `origin`.

## Say

> "Everything we have done so far has been observation. Now we are going to make this clone ours locally. Each of you has your own local copy of the same starting repository. That means we can begin from the same history and make different local changes without changing the person sitting next to us."

> "Our BUILD artifact is a simple reading record called **Books I Have Read**. The content is intentionally uncomplicated. I want us thinking about what Git sees when a meaningful file changes, not spending the Git lesson learning a complicated dataset."

> "The reading list gives us decisions a human can make: add a book, add a rating, or add a note. Git can record that a rating changed. Git cannot decide whether your opinion of the book is correct."

## DEMO + DO 1: find what arrived

Instructor and learners run:

```bash
ls
```

## Stop and read

Expected evidence includes:

```text
build-example/
```

## Ask

> "What do you see now that gives us something new to work with?"

Do not type `build-example/` by itself. If that happens and Bash says `Is a directory`, use the output:

> "Bash is telling us this is a directory name, not a command. What command have we already used to look inside a directory?"

## DEMO + DO 2: inspect the BUILD directory

```bash
ls build-example
```

## Stop and read

Expected:

```text
books.md  README.md
```

## Ask

> "What two files do we have to work with?"

## DEMO + DO 3: read before changing

```bash
cat build-example/books.md
```

## Stop and read

Learners should see:

```markdown
# Books I Have Read

| Title | Author | Date Finished | Publisher | Rating | Notes |
| --- | --- | --- | --- | --- | --- |
| Such Sharp Teeth | Rachel Harrison | 2022-10-03 | Penguin Publishing Group | | |
| I, Medusa | Ayana Gray | 2025-11-17 | Random House Publishing Group | | |
| The Penelopiad | Margaret Atwood | 2014-10-22 | Faber & Faber | | |
```

## Ask

> "What do you notice about this file?"

Give learners time to inspect the table.

Then:

> "What is one small change you could make that would actually mean something to you?"

Listen for adding a book, rating, or note.

## Say

> "Those are content decisions. Git does not decide what you should read, what rating a book deserves, or what your note should say. Git helps us see and record the change we decide to make."

> "Before we change anything, we need a baseline. If we know the starting state, the next status message will have something meaningful to compare against."

## DEMO + DO 4: establish the clean baseline

```bash
git status
```

## Stop and read

Expected evidence:

```text
nothing to commit, working tree clean
```

## Ask

> "Have we changed the reading list yet?"

> "What exact evidence supports your answer?"

## DEMO + DO 5: verify the relationship and history one last time

Run one move at a time:

```bash
git remote -v
```

Stop and ask:

> "Where did our common starting repository come from?"

Then:

```bash
git log --oneline
```

Stop and ask:

> "Does this clone already have a history? Which commits existed before we make our own change?"

## Build the next workflow together

Show:

```text
PULL -> CHANGE -> INSPECT -> CHOOSE -> RECORD -> REVIEW -> PUSH
```

## Say

> "We have already experienced the first word: **PULL** brought later shared work into the clone we already had. After the break, each of us will make one real change to `build-example/books.md`. Then we will follow that change through Git one state at a time, commit it locally, and use our collaborator access to try to share it back to the common GitHub repository."

> "Do not memorize this line. We are going to build its meaning by doing it. Change first. Then inspect what actually changed. Choose what belongs in the next version. Record it with a commit. Review what we recorded. Only then do we ask what sharing with the remote means."

## Ask before break

> "Right now, before we edit, what state are we in?"

Expected answer: clean working tree in a local clone with existing history and a known `origin`.

> "After we edit `books.md`, what do you predict `git status` will say?"

Do **not** test the prediction yet. Preserve it for the first move after break.

## Expected learner evidence

By the break, each learner can show:

- a local clone of `GitHubCarpentries-Examples`;
- branch `main`;
- `build-example/books.md`;
- a clean working tree;
- `origin` pointing to the class GitHub repository;
- existing Git history;
- one predicted meaningful change they can make after break.

## Helper cue

Frances and Dani recover learners only to the common checkpoint:

> "Get the learner to a clean clone where they can see `build-example/books.md`. Stop there."

Check, in order:

1. terminal;
2. `pwd`;
3. repository root if needed;
4. `git status`;
5. `ls build-example`.

Do not create another repository, reclone unnecessarily, or make the learner's first reading-list edit for them.

## Common teaching moments from rehearsal

**Cloned inside another repository:** the clone may be healthy even if its location was unintended. Locate it before deciding to delete or reclone.

**Repeated `cd GitHubCarpentries-Examples` while already inside it:** read the prompt and verify with `pwd` before moving again.

**Misspelled path:** compare the typed path with `ls` output. Bash is literal.

**Git output pasted as a command:** identify who is speaking. Output is evidence to read, not necessarily input to type.

## Catch-up checkpoint

```text
[ ] GitHubCarpentries-Examples is the current repository
[ ] main is the current branch
[ ] build-example/books.md is visible
[ ] working tree is clean
[ ] origin is known
[ ] existing history is visible
[ ] no reading-list change has been made yet
```

## LIVE COLLABORATOR SETUP BEFORE BREAK

**This happens during class.** Learners are asked in advance to create a GitHub account, but the instructor does not need or collect passwords, tokens, recovery codes, or other authentication secrets.

### Reminder prompt: ask for GitHub usernames

Before the break, pause and say:

> "Before we go to break, I need one piece of GitHub information from each of you so that we can collaborate after the break: your **GitHub username**. Please do not give me your password, token, recovery code, or any other login credential. I only need the public username attached to your GitHub account."

If useful, ask learners to open GitHub and verify the username shown on their profile rather than guessing it.

### Say: public access versus collaborator access

> "You were able to clone this repository before I gave you any special access because the repository is public. Public means you can read and clone it. It does not mean everyone on the internet can push changes into it."

> "You can also make commits in your local clone without my permission because those commits happen on your computer. What we are changing now is your permission to contribute those commits back to our shared GitHub repository."

Show:

```text
CLONE       local copy       public access is enough
COMMIT      local history    happens on your computer
PUSH        shared history   GitHub write permission is required
```

### DEMO + DO: collaborator invitation

On the instructor's projected GitHub repository, open:

`RebekahZipp/GitHubCarpentries-Examples`

Then use the repository's collaborator/access settings to invite each learner by **GitHub username**.

As each invitation is sent, have that learner open their GitHub notifications or invitation page and accept it.

**Helper role:** Frances and Dani help learners locate their GitHub username, find the invitation, sign in to their own account, and accept. Helpers never ask learners to reveal a password or token and never type a learner's credentials for them.

### Ask

> "Before I invited you, could you clone this repository?"

Expected: **Yes.**

> "Before I invited you, could you make a local commit?"

Expected: **Yes.**

> "So what did the collaborator invitation actually change?"

Give learners time to answer.

### Say

> "It changed what GitHub will allow your account to do when you try to share work back. Your clone did not become a different repository. Your relationship to the shared GitHub repository gained write permission."

### Verify before break

Ask each learner to confirm only:

> "Invitation accepted?"

Do **not** have learners test `push` yet. Preserve that as the post-break teaching event.

If someone has not completed GitHub account setup, do not hold the local Git lesson. A helper can assist with account setup while the learner continues with the local clone. They can still inspect, edit, stage, and commit locally; collaborator access is needed when we reach the shared push.

### Before-break collaboration checkpoint

```text
[ ] GitHub account is available
[ ] instructor has the learner's GitHub USERNAME only
[ ] collaborator invitation was sent
[ ] learner accepted the invitation
[ ] public repository is already cloned locally
[ ] origin is understood
[ ] build-example/books.md is visible
[ ] working tree is clean
[ ] no learner BUILD change has been made yet
[ ] no learner push has been attempted yet
```

## Transition to break

> "Before the break, we learned to locate and read a repository, follow its relationship back to GitHub, and find the file we are going to work on. When we come back, we are going to change one thing and follow that change from the working directory into local history and then try to share it back to our common repository."

> "Because we are now collaborators on one shared repository, somebody else's successful push can change what GitHub knows before your turn. That is not a problem to avoid. It is the collaboration behavior we are here to learn."

---

# Carpentries alignment notes for this workshop

This lesson is a continuation of the Software Carpentry Git curriculum, not a replacement for it. Keep the **observable outputs, sequence logic, and terminology** aligned with the Carpentries Git lesson wherever we teach the same concept.

For this workshop:

- **Clone** should still mean: create a local repository from a remote repository, with `origin` configured automatically.
- **Collaborative workflow** should still be taught as: `pull -> change -> add -> commit -> push`.
- **Push rejection** should still be distinguished from a **merge conflict**. A rejected push means the remote has history the local branch does not yet have. A merge conflict appears only when Git cannot automatically reconcile overlapping changes during integration.
- **Conflict markers** should keep the Carpentries interpretation: local `HEAD`, separator `=======`, incoming version after `>>>>>>>`.
- **Open work** should preserve the Carpentries framing of version control as a shareable, inspectable record of computational or project history.
- **LICENSE** and **CITATION.cff** should be used as concrete repository-context examples, consistent with the Carpentries licensing and citation episodes.
- **RStudio** should be taught as a different interface over the same Git states: status, diff, stage, commit, pull, push, and history.

Where our workshop differs, state the difference explicitly rather than silently changing the model:

- the class is small;
- learners work from clones of the instructor's example repository rather than pairing as Owner/Collaborator for the first BUILD activity;
- learners make local commits in their own clones;
- during the live workshop, learners share their GitHub **usernames only**, the instructor invites them as collaborators to the public example repository, and learners accept before the collaboration exercise so they can practice the full pull -> change -> add -> commit -> push workflow;
- `build-example/books.md` replaces `hummus.md` as the low-risk learner content example, while `guacamole.md` remains the continuity object for conflict reasoning.

The teaching target is still the Carpentries mental model, with our local example substituted for the Carpentries example where useful.

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

Give learners quiet time first. Then ask for one explanation aloud. Only after they have reasoned should you reveal the answer/workaround.

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


## PLAIN-TEXT TEACHING RULE

Carpentries teaching and Git both work best when we are literal. Keep the explanation next to the action.

```text
SAY what we are doing
ASK what we expect
DO one action
STOP
READ what Git or GitHub says
SAY what that means
VERIFY the state
MOVE to the next action
```

Use short sentences. Name the file, repository, branch, and state. The student lesson should follow the same actions in the same order. The instructor lesson adds timing, expected evidence, prompts, recovery, and helper cues.

## WHY THIS MATTERS NOW: OSF PROJECTS ARE CHANGING

Use this immediately before the repository-context and open-science section.

### Say

> "Here is a current reason this matters for research. OSF Project workflows are being phased out. Starting November 16, 2026, new OSF Projects and child Components cannot be created. Starting February 19, 2027, existing OSF Projects become read-only. Registrations, preregistrations, and Preprints continue."

> "That means researchers who used OSF Projects as an active workspace need to decide where changing research materials should live. GitHub is one research repository option for appropriate versionable work: plain-text documentation, code, scripts, configuration, methods, metadata, and small data files."

> "GitHub is not a one-for-one replacement for OSF, and it is not the right repository for every research dataset. Large files, sensitive or restricted data, preservation requirements, DOI needs, disciplinary expectations, and institutional policy can point somewhere else."

### Read this map together

```text
Git history       What changed, when, and by whom?
README.md         What is this project? How do I use it?
.gitignore        What should NOT enter this Git record?
LICENSE           What may another person reuse?
CITATION.cff      How should this work be credited?
GitHub repository Where can appropriate active research files be versioned and shared?
GitHub remote     Where can collaborators exchange recorded Git work?
Data repository   Where should research data be deposited and preserved?
Registration      Where can a fixed study plan or research record be registered?
```

### Ask

> "If an OSF Project became read-only tomorrow, which parts of an active research workflow would need somewhere new to live?"

Let learners name code, documentation, data, collaboration, provenance, citation, preservation, preregistration, and sensitive information. Sort the answers rather than treating them all as GitHub material.

### Say

> "Git noticing a file does not mean GitHub is the right place for that file."

Connect this directly to:

```text
TRACK -> IGNORE -> INVESTIGATE
```

Then ask:

```text
WHAT is the material?
SHOULD it be versioned with Git?
MAY it be shared here?
IS it small and appropriate for a Git repository?
DOES it need preservation, a DOI, restricted access, or a disciplinary repository?
```

### Teaching conclusion

GitHub can be an active research collaboration and version-control repository for appropriate material. Repository choice is still a research-data-management decision.

Use this final open-science rhythm:

```text
PRACTICE -> DOCUMENT -> SHARE -> PRESERVE -> REUSE
```


## TEAMS IS THE WORKSHOP FRONT DOOR

Open the Teams workshop space at the beginning and keep it available during the session. Teams is the class communication and course-material space. GitHub is the versioned project collaboration space.

```text
TEAMS
  open workshop space
  get LINKS
  review NOTES
  open SLIDES
  open CHEAT_SHEET
  add comments, questions, and ideas in CHAT
  contribute to the course conversation

GITHUB
  clone repository
  inspect history
  make project changes
  commit
  pull and push
  collaborate on versioned work
```

### Opening prompt

**Say**

> "Please open our Git & GitHub Workshop space in Teams. Keep it open today. This is our workshop front door."

> "Across the top you will see the materials we use together: Notes, Slides, Links, and the Cheat Sheet. The chat is also part of the workshop. Add questions, observations, ideas, and non-sensitive error messages there as we work."

> "You do not have to remember every command. The reference material stays with the course so you can return to the steps."

### Ask

> "Where would you look if you need today's repository link?"

Answer: the workshop Links area in Teams.

> "Where would you put an idea or question for the group?"

Answer: the workshop chat.

> "Where would you review the teaching notes or slides?"

Answer: the corresponding Teams tabs.

> "If you make a Git commit, does that commit live in Teams?"

Answer: No. Teams supports the people and course conversation. Git/GitHub records the versioned project work.

### Transition to GitHub

**Say**

> "Now we are going to follow a link from our people-and-course space into our versioned project space."

Learners open the GitHubCarpentries-Examples link from Teams, then continue with the clone sequence already in this lesson.

### Contribution prompt during class

After a teaching stop, invite either spoken or chat participation:

> "What did you notice? You can say it aloud or put the observation in our workshop chat."

For a useful error:

> "If the message is not sensitive, paste the exact error into the workshop chat. We can read the same evidence together."

Never ask learners to post passwords, access tokens, authentication codes, private data, or sensitive research information.

### End-of-class return

Return to Teams before the final explain-back.

**Say**

> "We started here because this is the course space, and we are returning here because the workshop should remain usable after today. The links, notes, slides, cheat sheet, questions, and ideas give us a course record. GitHub gives us the versioned project record."

Invite learners to leave one final comment or idea about something they want to practice next.


## START FROM THE LAST PLAY SANDBOX OR CLONE A FRESH COPY

Do not assume every learner begins from the same computer state.

### Path A: returning to the computer used in the earlier Carpentries session

**Say**

> "If you are on the computer where you did our last Git practice, start by finding that play sandbox. We are continuing from work that already exists."

**Do + read**

```bash
pwd
ls
git status
```

If Git recognizes the repository, use that existing work to reconnect the earlier lesson to today's collaboration lesson.

### Path B: loaner computer or Digital Scholarship Center computer

**Say**

> "If you are on a loaner or lab computer, your old local repository may not be here. That is okay. A remote repository lets us make a new local copy."

Open **Teams -> Links -> GitHubCarpentries-Examples**.

On GitHub:

```text
Code -> HTTPS -> Copy
```

Return to Git Bash. Type `git clone ` with a space, then paste the copied HTTPS address. Do not manually retype the long URL.

```bash
git clone [PASTE THE HTTPS ADDRESS HERE]
cd GitHubCarpentries-Examples
git status
git remote -v
```

### Stop and ask

> "Before the clone, why could Git know my name and email but not show my old Git work?"

Read the distinction:

```text
GIT CONFIGURATION       name/email Git can write on new commits
LOCAL REPOSITORY        files + .git history stored on this computer
GITHUB REMOTE           another copy of repository/history hosted elsewhere
GITHUB AUTHENTICATION   proves which GitHub account is connecting
```

**Say**

> "My name and email are configuration. They are not my repository history. Git can know what author name to put on a commit without having any of my old repositories on this computer."

> "My earlier Git work lived inside the .git directories of the repositories on the computer where I made it. A different lab computer does not automatically receive those local repositories."

> "If that work was pushed to GitHub, I can clone the GitHub repository onto this computer and receive the shared history. If it was never pushed anywhere, my name and email cannot reconstruct it."

### Evidence check

After cloning:

```bash
git status
git log --oneline
git remote -v
```

Ask:

> "What changed? Did Git suddenly remember me, or did we bring a repository and its history onto this computer?"

Answer: the repository and its recorded history were cloned onto this computer.

### Teaching conclusion

```text
IDENTITY != HISTORY
CONFIGURATION != REPOSITORY
COMMITTED != PUSHED
CLONE = NEW LOCAL COPY OF SHARED REPOSITORY/HISTORY
```




### Transition before 1:33: read `origin` in plain language

Use this immediately before the **1:33 Remote, Origin, Pull** section.

```bash
git remote -v
```

**Do not begin with:** "The name Git gives us for the remote is origin."

**Ask**

> "What GitHub address do you see?"

Pause and let learners locate the HTTPS address.

Then ask:

> "What short word appears beside it?"

Learners: `origin`.

**Say**

> "`origin` is a short name for the GitHub repository we cloned from."

Point to the screen while reading it:

```text
origin   https://github.com/.../GitHubCarpentries-Examples.git   (fetch)
origin   https://github.com/.../GitHubCarpentries-Examples.git   (push)

origin = the GitHub repository this copy came from
fetch  = get work from GitHub
push   = send work to GitHub
```

Use the visual:

```text
MY COMPUTER  <---- origin ---->  GITHUB
                  short name
```

**Say**

> "When we see `origin` today, read it as: the GitHub repository this copy came from."

Do not introduce `remote-tracking reference`, `remote alias`, or other advanced vocabulary here.

**Transition into 1:33**

> "Now we know where our local copy is and what GitHub repository it is connected to. Next we will use that connection to bring shared work here and later send our recorded work back."

## CLASS ENTRY POINT: DIGITAL SCHOLARSHIP CENTER INSTRUCTOR COMPUTER

Use this as Rebekah's normal Oct. 8 starting point. The expected machine is the same Digital Scholarship Center computer used for rehearsal, but verify the state rather than assuming a restart preserved it.

### Say

> "Before we do Git work, I want to know where this computer and this repository actually are. I am going to read the state before I change the state."

### Demo + do: locate the existing class clone

```bash
pwd
ls
```

Expected starting location:

```text
/c/Users/libpatron/Carpentries
```

Expected directory:

```text
GitHubCarpentries-Examples
```

If it exists, do **not** clone another copy.

```bash
cd GitHubCarpentries-Examples
pwd
git status
ls
```

Expected repository root:

```text
/c/Users/libpatron/Carpentries/GitHubCarpentries-Examples
```

Expected lesson objects include:

```text
CITATION.cff
LICENSE
README.md
TRY_PROMPTS.md
build-example/
guacamole.md
```

### Stop + read

Ask:

> "What changed between 'not a Git repository' and Git recognizing this repository?"

Answer: our location changed. We entered the directory that contains the repository.

If `git status` says the branch is up to date with `origin/main`, ask:

> "Has this command just contacted GitHub, or is Git reporting the remote-tracking information it already has locally?"

Then verify shared state:

```bash
git pull origin main
```

If the result ends with:

```text
Already up to date.
```

say:

> "Now we have contacted the remote. We did not assume the shared state; we checked it."

Then inspect the relationship:

```bash
git remote -v
```

### Instructor checkpoint

```text
LOCATE             pwd
LOOK               ls
ENTER REPOSITORY   cd GitHubCarpentries-Examples
VERIFY LOCAL       git status
CHECK SHARED       git pull origin main
SEE RELATIONSHIP   git remote -v
```

This is the normal class entry point.

### Restart/fallback

A computer restart does not by itself mean the repository must be cloned again. First repeat `pwd` and `ls`. If `GitHubCarpentries-Examples` is still present, enter it and verify it.

Only if the class clone is actually absent, use the fresh-machine path:

```text
Teams -> Links -> GitHubCarpentries-Examples
GitHub -> Code -> HTTPS -> Copy
Git Bash -> git clone [paste copied HTTPS address]
cd GitHubCarpentries-Examples
git status
git pull origin main
git remote -v
```

### Teaching connection

```text
GIT KNOWS MY NAME/EMAIL
        !=
THIS COMPUTER HAS MY REPOSITORY

REPOSITORY EXISTS
        !=
I AM CURRENTLY INSIDE IT

STATUS SAYS UP TO DATE WITH origin/main
        !=
I JUST CONTACTED GITHUB

PULL
        =
CHECK REMOTE + BRING SHARED WORK HERE
```

**Transition**

> "We have located our local copy and verified its relationship to the shared repository. Now we can investigate what is in it before we change anything."
