## TODAY'S REAL RECOVERY LESSON: A WEB ADDRESS IS NOT A FOLDER

**SAY:** "We just experienced a common, useful mistake. I tried `cd https://...` to connect to GitHub. Git Bash could not do that because `cd` moves into folders **on this computer**. A GitHub URL is a web address, not a local folder. This is why we always ask what place we are in and what action we actually want."

**ASK:** "Am I trying to enter a folder I already have, download a repository I do not have, or contact GitHub from a repository I already have?"

| Intention | Use | Why |
| --- | --- | --- |
| Find my location | `pwd` | Shows my current local folder |
| See folders and files | `ls` | Shows what exists here |
| Enter a local folder | `cd FOLDER` | Changes local directory only |
| Get a repository not yet on this computer | `git clone HTTPS_URL` | Downloads files/history and sets up `origin` |
| See the saved GitHub connection | `git remote -v` | Displays the `origin` URL; does not contact GitHub |
| Contact GitHub for updates | `git pull origin main` | Fetches/integrates shared work |
| Share a local commit | `git push origin main` | Sends local commits, if authorized |

**DEMO + DO.** Start with the real Digital Scholarship Center path:

```bash
cd /c/Users/Carpentries
pwd
ls
```

**EXPECTED:** `pwd` says `/c/Users/Carpentries`. If `GitHubCarpentries-Examples` is listed, **do not clone again**:

```bash
cd GitHubCarpentries-Examples
git status
git remote -v
```

**EXPECTED:** `git status` names the branch; `git remote -v` displays `origin` pointing to `https://github.com/RebekahZipp/GitHubCarpentries-Examples.git` (or equivalent URL).

**ONLY IF THE FOLDER IS ABSENT:** Copy the HTTPS URL from GitHub **Code → HTTPS → Copy**, then type `git clone ` followed by the pasted address. For this workshop the complete command is:

```bash
git clone https://github.com/RebekahZipp/GitHubCarpentries-Examples.git
cd GitHubCarpentries-Examples
git status
```

**EXPECTED:** Clone creates the folder and retrieves the recorded history. It does not create a new empty project.

**IF THE COMPUTER REBOOTED:** Start with `pwd`, `ls`; a reboot alone is not a reason to clone. If `cd` alone sends you home, use the full path above. If `cat Carpentries` says **is a directory**, use `cd Carpentries` to enter it; `cat` is for reading files. If you accidentally type Git's printed output as a command, stop: output is evidence, not a new instruction.

**IF AN ERROR APPEARS:** Do not delete, reset, force-push, or keep guessing. Read the exact error, then check `pwd`, `ls`, `git status` as appropriate. Ask the helper to help locate the smallest correct state.

**SAY:** "The mistake is part of today's lesson because it reveals an important distinction: LOCAL FOLDER != GITHUB WEBSITE. A saved remote address != a live connection. COMMITTED != PUSHED. We can return to our work by checking evidence, not memorizing where we left off."

**TRANSITION:** "Now that we know how to find our project and recognize its GitHub address, we can return to Kevin's change-and-record cycle and make something happen."


---

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
# edit a file
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

## 6. Shared work

A useful collaboration rhythm:

**PULL → CHANGE → INSPECT → CHOOSE → RECORD → REVIEW → PUSH**

```bash
git pull origin main
# edit
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
