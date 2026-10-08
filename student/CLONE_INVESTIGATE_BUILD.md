## Start or return to the workshop project

**WHY:** Git Bash starts in a local folder, not automatically in your project. GitHub is the shared website, not a directory on this computer.

**DO:** `cd /c/Users/Carpentries` then `pwd` and `ls`. **EXPECT:** the folder `GitHubCarpentries-Examples` if this computer has a copy. **IF PRESENT:** `cd GitHubCarpentries-Examples`, `git status`, `git remote -v`. **IF ABSENT:** `git clone https://github.com/RebekahZipp/GitHubCarpentries-Examples.git`, then enter it. **ASK:** Why can't `cd https://github.com/...` work? Because `cd` only enters local folders. **VERIFY:** `git status` names the branch and `git remote -v` identifies `origin`. **NEXT:** inspect or change a file.

## Return to our work after a reboot: two places, one project

**Why this is in the course:** Last week's files may still be on this computer, but opening Git Bash does not automatically put us inside them. GitHub keeps the shared repository; Git Bash operates in a folder on this computer. We find the local copy before deciding whether to clone. This is a reusable skill whenever we change computers, restart, or return to research.

**Two places to name aloud:**

- **LOCAL, on the Digital Scholarship Center Windows computer:** `C:\Users\Carpentries\GitHubCarpentries-Examples`. In Git Bash, Windows `C:\` is written `/c/`.
- **SHARED, on GitHub:** https://github.com/RebekahZipp/GitHubCarpentries-Examples . The local copy can be connected to this address through a remote called `origin`.
- **Teams:** course links, policies, slides, chat, and help. Teams is not where Git commits live.

**Start in Git Bash. Type one command, read its output, then continue.**

```bash
pwd
ls
```

**Expect:** `pwd` prints the current folder; `ls` lists what is in it. Neither command changes anything.

```bash
cd /c/Users/Carpentries
ls
```

**Expect:** a folder named `GitHubCarpentries-Examples`. If `cd` says **No such file or directory**, stop and inspect the path with File Explorer; do not guess or create a second repository.

```bash
cd GitHubCarpentries-Examples
pwd
git status
```

**Expect:** `pwd` ends in `/GitHubCarpentries-Examples`; `git status` reports a branch and any local changes. A modified file is not a failure; do not discard it.

```bash
git remote -v
```

**Expect:** `origin` with GitHub URL(s) for fetch and push. **This reads the saved connection; it does not contact GitHub.** If the URL differs, stop and check the repository before pushing.

**Only when `git status` shows a clean working tree:**

```bash
git pull origin main
git status
```

**Expect:** Git contacts GitHub and either reports `Already up to date.` or brings in newer work; status then shows the resulting state. A clean local tree does not guarantee a pull will succeed; authentication, connectivity, branch configuration, or divergent histories can require help. Do not reset, force-push, or delete anything to fix it.

**If the repository folder is truly absent:** use Teams **Links** to open the GitHub repository, choose **Code → HTTPS → Copy**; in Git Bash go to `/c/Users/Carpentries` (if it exists), type `git clone ` followed by the pasted HTTPS URL, then `cd GitHubCarpentries-Examples` and `git status`. **Clone only when absent.** If the parent folder is missing, ask the helper to establish the approved workspace location first.

**Read errors literally:**

| Evidence | What it means | Safe next move |
| --- | --- | --- |
| `not a git repository` | You are probably outside the project | `pwd`, `ls`, enter the repository |
| `No such file or directory` | That path/name is not present here | `pwd`, `ls`, check spelling/location |
| `modified: ...` | A file has uncommitted edits | Inspect `git diff`; do not overwrite |
| `Already up to date.` | Pull found no newer changes to integrate | Continue with the lesson |
| Authentication or permission denied | GitHub access is not established | Ask helper; never share passwords/tokens |
| `rejected` on push | Shared history may have moved or permission is missing | Read full error; do not force-push |

**Five commands, five questions:** `pwd` = Where am I? `ls` = What is here? `cd FOLDER` = Enter that folder. `git status` = What is my local Git state? `git remote -v` = Which shared address is saved? `git pull origin main` = What work can I receive from GitHub?

**Remember:** bare `cd` sends you home; `cd ..` moves up one folder; `cat FILE` reads a file. `COMMITTED != PUSHED`. A reboot != a reason to reclone.


---



## Start here: open the Teams workshop space

Keep the **Git & GitHub Workshop | OSU Libraries** Teams space open during class. It is the workshop front door.

Use Teams to:

- get the workshop and repository links;
- review the Notes;
- open the Slides;
- keep the Cheat Sheet available;
- add questions, comments, and ideas to the chat; and
- return to the course material after the live demonstration moves on.

```text
TEAMS              people + course materials + conversation
GITHUB             shared versioned project
LOCAL CLONE        your working copy on your computer
```

A message in Teams does not change the Git repository. A local Git commit does not automatically appear in Teams.

When invited to participate, you may answer aloud or add an observation to the workshop chat.

If you share an error message in chat, check that it contains no password, token, authentication code, private data, or sensitive research information.

From the Teams **Links** area, open the shared GitHub example repository. Then continue with the clone and investigation steps below.

# Clone → Collaborate → Investigate → Build

## Your mission

A GitHub repository is not only code. It can be a research record, dataset, lesson, documentation site, analysis, or professional portfolio.

This lesson continues the Software Carpentry **Version Control with Git** sequence. You already know the local cycle of changing, inspecting, staging, committing, and reviewing history. Now we connect that record to other people and places.

Our rhythm remains:

**CHANGE → INSPECT → CHOOSE → RECORD → REVIEW → SHARE**

## How we work together

This workshop follows [The Carpentries Code of Conduct](https://docs.carpentries.org/policies/coc/) in class, Teams, and GitHub collaboration.

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
- **BUILD:** work in a shared class example repository.
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



## BUILD project: Books I Have Read

For the shared class repository, use a reading log you can keep after class.

The shared example already contains:

```text
build-example/README.md
build-example/books.md
```

Starter `books.md`:

```markdown
# Books I Have Read

| Title | Author | Date Finished | Publisher | Rating | Notes |
| --- | --- | --- | --- | --- | --- |
| Such Sharp Teeth | Rachel Harrison | 2022-10-03 | Penguin Publishing Group | | |
| I, Medusa | Ayana Gray | 2025-11-17 | Random House Publishing Group | | |
| The Penelopiad | Margaret Atwood | 2014-10-22 | Faber & Faber | | |
```

This project is intentionally simple. The content can grow all year while the Git history records when and why the reading list changed.

Use the normal rhythm:

**PULL -> CHANGE -> INSPECT -> CHOOSE -> RECORD -> REVIEW -> PUSH**

Do not put passwords, access tokens, private reading information you do not want shared, or sensitive personal data in the repository.


## 3. Collaborate: pull before new shared work

The canonical Carpentries lesson uses Owner/Collaborator pairs. Our small class keeps the same Git workflow while adapting the mechanics: everyone clones the same public example repository, then receives collaborator access live in class.

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
git commit -m "Add first books to reading list"
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


## Shared-repository distinction

A **rejected push is not automatically a merge conflict**. A rejection commonly means GitHub has commits the local clone does not yet contain. Pull first and read the integration result. A merge conflict occurs only when Git cannot automatically reconcile overlapping changes. Preserve that distinction in explanations and recovery prompts.


## Research workflow reference: why this matters now

OSF Project workflows are changing. New OSF Projects and child Components stop on **November 16, 2026**. Existing OSF Projects become read-only on **February 19, 2027**. OSF Registrations, preregistrations, and Preprints continue.

GitHub is one research repository option for appropriate work that changes over time, including plain-text documentation, code, scripts, methods, metadata, configuration, and small data files.

GitHub is not the right home for every research dataset. Large files, sensitive or restricted data, long-term preservation, DOI needs, disciplinary expectations, or institutional rules may require another repository or storage system.

Read this literally:

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

Before adding research material, ask:

```text
WHAT is the material?
SHOULD it be versioned with Git?
MAY it be shared here?
IS it small and appropriate for a Git repository?
DOES it need preservation, a DOI, restricted access, or a disciplinary repository?
```

**Rule:** Git noticing a file does not mean GitHub is the right place for that file.

Keep using the same class pattern:

```text
DO one action
STOP
READ what happened
SAY what it means
VERIFY
NEXT action
```


## First meaningful change: make the list mean what you intend

Before adding something just to practice Git, read `build-example/books.md` and ask:

> **What is one small thing I would change that would mean something to me?**

The instructor example changes the table from:

```text
Title | Author | Date Finished | Publisher | Rating | Notes
```

to:

```text
Title | Author | Publication Date | Publisher | Rating | Date Finished | Notes
```

The reason matters: the existing dates were interpreted as publication dates, so the field is clarified and a separate Date Finished field is added.

After making a meaningful change:

```bash
git status
git diff
git add build-example/books.md
git diff --staged
git commit -m "Clarify publication and finished dates"
git log --oneline
```

Your change does not have to match the instructor's. Change something you can explain: a label, a useful field, a book, a rating, or a note.

**Key point:** Git does not decide what the information means. People make that decision. Git records the change.


---

## Executable live lab: every action has a command and a check

**Instructor says:** "We will not skip from 'edit' to 'commit'. First we make a change, then we read what Git actually saw." **Learners:** run one line at a time in **Git Bash** or **RStudio Terminal**, never the R `>` Console.

**0. Locate and inspect, without overwriting work.**
```bash
pwd
ls
git status
git remote -v
```
**Expected:** a local folder containing `guacamole.md`; Git status names a branch; `origin` shows a GitHub URL. If `not a git repository`, find the existing clone before cloning again. `git remote -v` is a saved address, not proof of live authentication.

**1. Read and edit the guacamole recipe using Nano.**
```bash
cat guacamole.md
nano guacamole.md
```
**In Nano:** move with arrow keys; add one meaningful ingredient or instruction; press **Ctrl+O**, **Enter** to save, then **Ctrl+X** to exit. If the file opens empty, stop without saving and inspect `pwd` and `ls`. If Nano is unavailable, edit `guacamole.md` in RStudio's file editor and save.

**2. Inspect, stage, record, verify.**
```bash
git status
git diff -- guacamole.md
git add guacamole.md
git diff --staged
git commit -m "Improve guacamole recipe"
git log -1 --oneline
git show HEAD
```
**Expected:** modified file before staging; added line prefixed `+` in diff; new commit in log. **Ask:** "Which command edited the file? Which command recorded it?" **Answer:** Nano edits; Git commits. If Git says "nothing to commit", verify the file was saved and whether that exact change already exists. Do not fabricate a change to force a commit.

**3. Share and receive only when permission and network state permit.**
```bash
git status
git pull origin main
git push origin main
git status
```
**Expected:** pull reports incoming work or "Already up to date"; push reports success if authenticated and authorized. **Caution:** inspect any uncommitted work before pulling. If rejected, stop and read the message; do not force-push. If access is unavailable, the verified local commit is a valid learner checkpoint.

**4. Make metadata meaning visible in the reading list.**
```bash
cat build-example/books.md
nano build-example/books.md
```
**Task:** correct the existing publication-date values currently under `Date Finished` by renaming that header `Publication Date`; add a *separate* `Date Finished` column after `Rating`; update the Markdown separator and every row. **Check**:
```bash
git diff -- build-example/books.md
git add build-example/books.md
git diff --staged
git commit -m "Separate publication and finish dates in book list"
git log -1 --oneline
```
**Expected:** column count matches across header, separator, and all data rows. **Ask:** "Did we change a value, or clarify the meaning of a field?"

**5. RStudio: three interfaces, one existing repository.** Open the **existing local folder** as an RStudio project. At the **R Console `>`**:
```r
getwd()
list.files()
readLines("README.md", n = 5)
visits <- c(12, 15, 18)
mean(visits)
```
**Expected:** R prints the path, files, README lines, and `15`. To make this reproducible, save the two analysis lines in `workshop-analysis.R`; unsaved Console commands are not automatically tracked. In the **RStudio Terminal**:
```bash
git status
git log --oneline -3
```
In the **Git pane**, select a changed file → **Diff** → stage only the intended file → **Commit** → **History**; push only if appropriate. **Do not automatically stage** `.Rproj` or optional analysis files. **Ask:** "Are these three different Git histories?" **Answer:** No: Console runs R, Terminal runs Git commands, Git pane provides Git controls on the same repository.

**Recovery checkpoint:** At every surprising result use **EXPECT → OBSERVE → EXPLAIN → TEST → ACT → VERIFY**. Helpers ask learners to read the *exact* error, identify which interface is active, and verify the directory before suggesting a command. Never use `reset --hard`, `push --force`, or deletion to catch up.
