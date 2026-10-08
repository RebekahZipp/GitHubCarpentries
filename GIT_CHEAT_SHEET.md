## START HERE: choose the right command

| Question | Command | Evidence |
| --- | --- | --- |
| Where am I? | `pwd` | Local path |
| What is here? | `ls` | Folder names |
| How do I reach the DSC workspace? | `cd /c/Users/Carpentries` | `pwd` confirms location |
| How do I enter the existing project? | `cd GitHubCarpentries-Examples` | `git status` reports branch |
| How do I obtain a missing repo? | `git clone https://github.com/RebekahZipp/GitHubCarpentries-Examples.git` | New local folder |
| What GitHub address is saved? | `git remote -v` | `origin` URL; no network check |
| How do I receive shared work? | `git pull origin main` | Integration result, only after checking local state |
| How do I share a commit? | `git push origin main` | Remote response, if authorized |

**Do not type `cd https://...`.** A URL is not a folder. **Do not reclone after a reboot without checking `ls`.**

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

# Git & GitHub Whole-Class Cheat Sheet

Keep this page open during the workshop. It follows the same order as the live lesson.

> **Before acting:** Where am I? What changed? What is the evidence? What should happen next? How will I verify it?

## 1. Orient: where am I?

```bash
pwd
git rev-parse --show-toplevel
git status
git status --short --branch
```

- `pwd` — current shell directory.
- `git rev-parse --show-toplevel` — repository root.
- `git status` — branch and working/staging state.

**Common clue:** `not a git repository` often means **check location first**.

## 2. Inspect before changing

```bash
ls
git status
git diff
git diff --staged
git log --oneline
git show HEAD
```

- `git diff` — unstaged changes.
- `git diff --staged` — what you have chosen for the next commit.
- `git log --oneline` — compact history.
- `git show HEAD` — current commit.

## 3. Clone the class TRY example

```bash
git clone https://github.com/RebekahZipp/GitHubCarpentries-Examples.git
cd GitHubCarpentries-Examples
git status
git log --oneline
git remote -v
```

**TRY** means inspect and experiment in your own local clone.  
**BUILD** means substantive work happens in a shared class example repository.

## 4. Remotes: where can work travel?

```bash
git remote -v
git pull origin main
git push origin main
```

**Memory line:** **Commit records here. Push shares there. Pull brings shared work here.**

`origin` is the conventional local nickname for the remote created by `git clone`.

## 5. Normal work cycle

**CHANGE → INSPECT → CHOOSE → RECORD → REVIEW → SHARE**

```bash
nano guacamole.md  # edit, Ctrl+O, Enter, Ctrl+X
git status
git diff
git add FILE
git diff --staged
git commit -m "Describe the change"
git log --oneline
git push origin main
```

Before `git add`: **Does this change belong in the next version?**  
Before `git commit`: **What decision am I preserving?**  
Before `git push`: **Where is this commit now, and where am I sending it?**

**LEAD → FOLLOW → CHECK: OPEN THE BOOK FILE WITH NANO (DO NOT SKIP)**

**SAY:** "We have read the table. Now we must open the actual file to change it. `cat` displays a file; `nano` edits it. Watch me open the exact book-list file, then follow."

**DEMO + DO** in Git Bash or RStudio **Terminal** (not the R `>` Console):

```bash
pwd
ls build-example
nano build-example/books.md
```

**EXPECTED:** Nano opens the existing Markdown reading list. **CHECK:** learners see the heading `# Books I Have Read` and a six-column table. If Nano is blank, do not save: exit with **Ctrl+X**, inspect `pwd` and `ls build-example`, and correct the directory/path.

**EDIT THE REAL TABLE:** Rename `Date Finished` to `Publication Date`. Add a *new* `Date Finished` column after `Rating`, and add one empty cell to the separator and to **each** existing book row. Preserve the original dates as publication dates. The result should have seven columns:

```markdown
# Books I Have Read

| Title | Author | Publication Date | Publisher | Rating | Date Finished | Notes |
| --- | --- | --- | --- | --- | --- | --- |
| Such Sharp Teeth | Rachel Harrison | 2022-10-03 | Penguin Publishing Group | | | |
| I, Medusa | Ayana Gray | 2025-11-17 | Random House Publishing Group | | | |
| The Penelopiad | Margaret Atwood | 2014-10-22 | Faber & Faber | | | |
```

**SAVE:** Press **Ctrl+O**, then **Enter** to confirm the filename. **EXIT:** Press **Ctrl+X**. If prompted `Save modified buffer?`, press **Y**, then **Enter**. **CHECK:** the shell prompt returns.

**VERIFY, one command at a time:**

```bash
cat build-example/books.md
git status
git diff -- build-example/books.md
```

**EXPECTED:** Seven column headers; `books.md` modified; diff shows the changed heading and added cells. **ASK:** "Did we change the original date values?" **EXPECTED:** No. We corrected their meaning and added a distinct completion-date field.

**RECORD THE CHANGE** only after verifying:

```bash
git add build-example/books.md
git diff --staged
git commit -m "Separate publication and finished dates"
git log -1 --oneline
```

**EXPECTED:** a local commit with the table correction. Do not push until collaborators, permissions, and shared branch state have been checked. If Git says `nothing to commit`, inspect `git status` and `git diff`; the edit may not have been saved or may already be present.

**RECOVER:** `nano: command not found` means use Git Bash with Nano or open the file in RStudio's editor. A `Permission denied` on save indicates local file/folder write permissions, not necessarily GitHub authorization. Do not use `sudo`, force-push, or delete work to get past it.


## 6. Shared work

A useful collaboration rhythm:

**PULL → CHANGE → INSPECT → CHOOSE → RECORD → REVIEW → PUSH**

```bash
git pull origin main
nano guacamole.md  # edit, Ctrl+O, Enter, Ctrl+X
git status
git diff
git add FILE
git diff --staged
git commit -m "Describe the change"
git log --oneline
git push origin main
```

## 7. Rejected push or conflict

Do not reflexively force push.

**EXPECT → OBSERVE → EXPLAIN → TEST → ACT → VERIFY**

Typical workshop path:

```bash
git pull origin main
# read and resolve the conflicting file
git add FILE
git status
git commit -m "Resolve conflicting changes"
git push origin main
git status
git log --oneline
```

Conflict markers:

```text
<<<<<<< HEAD
local version
=======
incoming version
>>>>>>> commit
```

**Memory line:** **CONFLICT ≠ DAMAGE. Git is refusing to invent human intent.**

## 8. History and deliberate recovery

```bash
git log --oneline
git show HEAD
git diff HEAD~1
git diff
```

For an uncommitted working-file change you have **decided to discard**:

```bash
git restore FILE
git status
```

First ask: **Which version am I trying to keep?**

## 9. Track, Ignore, Investigate

```bash
git status
git status --ignored
cat .gitignore
git check-ignore -v PATH
```

Use:

**TRACK → IGNORE → INVESTIGATE**

Do not automatically `git add .` until you know what the files are.

## 10. Repository context

| File/object | Question it helps answer |
| --- | --- |
| `README.md` | What is this? Why does it exist? How do I use it? |
| `.gitignore` | What is intentionally excluded? |
| `LICENSE` | What reuse is permitted? |
| `CITATION.cff` | How should this work be cited? |
| notes/provenance | Where did material come from? What decisions were made? |
| Git history | What recorded changes happened? |

**VISIBLE ≠ PERMISSION TO REUSE**  
**RECORDED ≠ CORRECT**  
**DATA ≠ INTERPRETATION**

## 11. Common mistakes: investigate first

| What you see | Ask first |
| --- | --- |
| `not a git repository` | Where am I? |
| Git command typed at an R `>` prompt | Which interpreter received this? |
| `git log --online` | What option did I actually type? |
| `git add <file>` | Is that a placeholder or the real filename? |
| pathspec error | What does `ls` say the file is actually called? |
| Git output pasted at the shell prompt | Is the computer speaking, or is this a command? |
| rejected push | What changed remotely? |
| conflict | What human decision is Git refusing to make? |
| ignored file surprise | Which ignore rule applies? |
| no error but wrong result | How can I verify the intended state? |

## 12. Asking for help

Use:

> "I expected ___. I observed ___. I think ___ may explain it. I can test that by ___."

If you fall behind:

> "I am at ___. I see ___. I need to get to the next checkpoint."

## 13. The whole lesson in one view

```text
WHERE AM I?
     ↓
CHANGE
     ↓
INSPECT
     ↓
CHOOSE
     ↓
RECORD
     ↓
REVIEW
     ↓
SHARE
     ↓
VERIFY
```

When something surprises you:

```text
EXPECT → OBSERVE → EXPLAIN → TEST → ACT → VERIFY
```

**The commands may change. The reasoning should become familiar.**


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


## Oct. 8 synchronized decisions

- This workshop continues the canonical Software Carpentry Git concepts and observable states while adapting examples and small-class mechanics.
- **DEMO + DO** means instructor and learners make one small move together, then stop and read the evidence.
- **TRY** means inspect, predict, or safely repeat in the local clone.
- **BUILD** means meaningful work in `build-example/books.md` inside each learner's clone of the shared `GitHubCarpentries-Examples` repository.
- There is **no Teams-dependent activity** and no Owner/Collaborator pair setup for the first BUILD.
- Learners are asked in advance to create GitHub accounts. During class, Rebekah collects **GitHub usernames only**, invites learners as collaborators, and learners accept before the first push. Passwords, tokens, recovery codes, and other authentication secrets are never collected.
- Public access explains why learners can clone before invitation. Collaborator access explains why they can later push.
- The class practices the full Carpentries collaboration rhythm: **PULL -> CHANGE -> INSPECT -> ADD -> COMMIT -> REVIEW -> PUSH**.
- Local commits are valid before a push. **COMMITTED != PUSHED**.
- A rejected push and a merge conflict are different states. Read the rejection, integrate remote work, and only call it a conflict when Git reports an unresolved merge.
- `guacamole.md` remains the continuity object for a deliberate conflict demonstration when needed; `books.md` is the common BUILD artifact.
- Helpers recover learners to the current checkpoint rather than creating alternate tracks or taking over keyboards.
- RStudio is another interface over the same Git states, not a separate Git workflow.


## Plain-text research workflow reference

Keep the teaching literal: **say the action, do one action, stop, read the evidence, say what it means, verify, then move on.** The student and instructor paths use the same actions and vocabulary; the instructor path adds timing, prompts, expected evidence, recovery, and helper cues.

OSF Project workflows are being phased out: new Projects and child Components stop on **November 16, 2026**, and existing Projects become read-only on **February 19, 2027**. Registrations, preregistrations, and Preprints continue.

GitHub is one research repository option for appropriate versionable material such as plain-text documentation, code, scripts, methods, metadata, configuration, and small data files. It is not a one-for-one OSF replacement or the right data repository for every project. Large, sensitive, restricted, preservation-focused, DOI-dependent, or disciplinary data may belong elsewhere.

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

Before adding research material:

```text
WHAT is the material?
SHOULD it be versioned with Git?
MAY it be shared here?
IS it small and appropriate for a Git repository?
DOES it need preservation, a DOI, restricted access, or a disciplinary repository?
```

**Rule:** Git noticing a file does not mean GitHub is the right place for that file.


## Research repository reference

OSF Project workflows are changing: new Projects and child Components stop November 16, 2026, and existing Projects become read-only February 19, 2027. Registrations, preregistrations, and Preprints continue.

GitHub can be a research repository for appropriate versionable work such as documentation, code, scripts, methods, metadata, configuration, and small data files. It is not the right repository for every dataset.

```text
Git history       change record
README.md         project explanation
.gitignore        intentional exclusions
LICENSE           reuse terms
CITATION.cff      credit and citation
GitHub repository active versioned research work when appropriate
GitHub remote     shared Git history
Data repository   data deposit and preservation
Registration      fixed study plan or research record
```

Before adding research material ask: What is it? Should Git version it? May it be shared here? Is it appropriate in size and format? Does it need preservation, a DOI, restricted access, or a disciplinary repository?

**Rule:** Git noticing a file does not mean GitHub is the right place for that file.

**Teaching rhythm:** SAY -> ASK -> DO -> STOP -> READ -> EXPLAIN -> VERIFY -> NEXT.


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
