## Start on the Digital Scholarship Center computer

The workshop local folder is `C:\Users\Carpentries` (Git Bash: `/c/Users/Carpentries`). **First check `pwd` and `ls`**, then `cd /c/Users/Carpentries` and `ls`. Enter `GitHubCarpentries-Examples` if present. Clone from [the shared example repository](https://github.com/RebekahZipp/GitHubCarpentries-Examples) only if absent. **`cd` cannot open a GitHub HTTPS URL.** For the complete spoken recovery lesson, use [the master instructor script](instructor/OCT8_LIVE_LESSON.md).

# GitHub Carpentries

# START HERE: OCT. 8 LIVE LESSON

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



This repository is the course front door. **You should not have to hunt through folders to find the lesson.**

## Training-day map

| I am... | Start here | What it is for |
| --- | --- | --- |
| **Instructor** | **[OPEN THE OCT. 8 LIVE TEACHING LESSON](instructor/OCT8_LIVE_LESSON.md)** | The 1:00–4:00 running script: what to say, ask, demonstrate, practice, review, breaks, catch-up points, common mistakes, helper cues, and cheat-sheet reminders. |
| **Learner** | **[OPEN THE STUDENT LESSON](student/CLONE_INVESTIGATE_BUILD.md)** | Follow-along GitHub lesson, catch-up checkpoints, collaboration, conflict, recovery, and BUILD work. |
| **Helper** | **[OPEN THE HELPER CUE SHEET](helper/README.md)** | Timed room cues, learner checkpoints, common problems, collaboration support, and safe handoff. |
| **Everyone** | **[OPEN THE GIT & GITHUB CHEAT SHEET](GIT_CHEAT_SHEET.md)** | Commands and reasoning in lesson order. Keep this open during class. |
| **TRY practice** | **[OPEN / CLONE THE EXAMPLE REPOSITORY](https://github.com/RebekahZipp/GitHubCarpentries-Examples)** | Safe shared example to clone and investigate locally. After live collaborator setup, use it for the shared BUILD and collaboration exercise. |

## The course in one map

```text
                         OCT. 8 WORKSHOP
                               |
                +--------------+--------------+
                |              |              |
           INSTRUCTOR       STUDENT         HELPER
          running script   follow-along     cue sheet
                |              |              |
                +--------------+--------------+
                               |
                         WHOLE-CLASS
                         CHEAT SHEET
                               |
                    +----------+----------+
                    |                     |
                   TRY                  BUILD
          class example repo      shared class repo
          clone + investigate     change + collaborate
                    |                     |
                    +----------+----------+
                               |
                            EXPLAIN
                     evidence + reasoning
```

## Training-day rhythm

**DEMO** — watch, predict, discuss.  
**TRY** — use your local clone of the class example.  
**BUILD** — make meaningful work in the shared class repository.  
**TALK** — speak up, ask a question, or share an observation.

### 1:00–1:53 — Beginning
**WHERE AM I? → WHERE CAN THE WORK GO?**

Git/GitHub → clone → inspect → remotes → move from TRY to BUILD.

### 1:53–2:00 — 7-minute break

### 2:00–2:53 — Middle
**HOW DOES WORK MOVE BETWEEN PEOPLE?**

Collaboration → repeat → rejected push → conflict → human decision → verify.

### 2:53–3:00 — 7-minute break

### 3:00–4:00 — End
**HOW DO I UNDERSTAND, RECOVER, AND LEAVE GOOD WORK BEHIND?**

History → recovery → ignore decisions → documentation/provenance → transfer → explain-back.

## Git records the work. GitHub makes the work visible.

This repository is a companion to the OSU Libraries Git and GitHub workshop.

## Read the workflow

**CHANGE → INSPECT → CHOOSE → RECORD → REVIEW → SHARE**

We are not learning commands just to memorize commands.

We are learning to ask:

- Where am I?
- What did I expect?
- What actually happened?
- What changed?
- What does Git know?
- What do I need to know next?
- What belongs in the project?
- What should be recorded?
- How will I verify the result?
- Who else can help us understand the work?
- Can another person understand what we did?

When something unexpected happens, use a second rhythm:

**EXPECT → OBSERVE → EXPLAIN → TEST → ACT → VERIFY**

## Questions are part of the practice

Questions in this workshop are invitations, not quizzes. They give learners and helpers room to contribute, but they also help the instructor make reasoning visible. In a small or quiet class, the instructor may ask and answer the prompt while thinking aloud.

Feedback is not saved for the end. Learners, helpers, and instructors can notice something, ask a question, suggest another interpretation, test it against the evidence, and make that knowledge available to the group.

See [PEDAGOGY_RUBRIC.md](PEDAGOGY_RUBRIC.md) for the reasoning, mistake-as-teaching-case, feedback, repetition, and community-of-practice rubric used throughout the lesson.

## Git is not GitHub

**Git** records the history of work.

**GitHub** provides a place to share, document, review, and collaborate on that work.

We start with Git. Then we add GitHub.

## This repository has three jobs

### 1. Learn Git and GitHub

Follow a small project from local files through version control, troubleshooting, and collaboration.

### 2. Teach Git and GitHub

Instructor notes document teaching choices, questions, mistakes, recovery, feedback, and lessons learned while building the workshop.

### 3. Show the work

The repository itself becomes evidence of project organization, documentation, collaboration, technical practice, and reasoning.

That means the history matters.

We are building the lesson with the tools and community practices the lesson teaches.



## Course files and design documentation

The role-specific links above are the training-day paths. Supporting design and community documents remain in this repository, including [PEDAGOGY_RUBRIC.md](PEDAGOGY_RUBRIC.md), [CONTRIBUTING.md](CONTRIBUTING.md), and the instructor/student/helper folders.

The Software Carpentry lesson remains the canonical Git foundation. This repository adds the OSU Libraries teaching, reasoning, troubleshooting, collaboration, and professional-practice layer.


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


## Plain-text teaching and research repository context

The lesson is written to be followed literally. Instructor and learner materials use the same sequence and vocabulary:

```text
SAY -> ASK -> DO -> STOP -> READ -> EXPLAIN -> VERIFY -> NEXT
```

OSF Project workflows are changing in 2026-2027. This makes active research workflow choices timely. GitHub is one research repository option for appropriate versionable materials such as documentation, code, methods, metadata, configuration, scripts, and small data files. It is not a one-for-one replacement for OSF or the right data repository for every project.

The training now connects Git history, README, .gitignore, LICENSE, CITATION.cff, GitHub repositories/remotes, data repositories, and registrations as different parts of a research record.

**Rule:** Git noticing a file does not mean GitHub is the right place for that file.


---

## Run the workshop, not just its outline

The timed instructor lesson and student workbook contain live commands and evidence checks. This runnable quick-start prevents unexecutable 'edit a file' gaps.

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


---

## October 8 live-teaching corrections: retain in every future edition

This section records what actually had to be taught during the workshop. **Do not remove the executable commands, Nano editing steps, expected output, or conditional recovery paths when revising or exporting this curriculum.** The original shared example repository is the learners' working specimen, not a place to pre-complete their exercise.

**In Git Bash, inside the existing `GitHubCarpentries-Examples` clone:**

```bash
pwd
git status
cat guacamole.md
nano guacamole.md
```

In Nano, use arrow keys to edit, **Ctrl+O**, **Enter** to save, **Ctrl+X** to exit. Then:

```bash
git diff -- guacamole.md
git add guacamole.md
git diff --staged
git commit -m "Improve guacamole recipe"
git log -1 --oneline
```

**Book-list correction, with an actual editor command:**

```bash
cat build-example/books.md
nano build-example/books.md
```

Change the mislabeled `Date Finished` column to `Publication Date`; add a *separate* `Date Finished` column after `Rating`; adjust the Markdown separator and all rows; preserve original dates. **Ctrl+O**, **Enter**, **Ctrl+X**.

```bash
git diff -- build-example/books.md
git add build-example/books.md
git status
git diff --staged
git commit -m "Separate publication and finished dates"
git log -1 --oneline
git show HEAD
```

**Share and receive, with state checks:**

```bash
git status
git remote -v
git push origin main
```

Push only if the learner has permission and their local work is ready. On another collaborator's clean working tree:

```bash
git status
git pull origin main
cat build-example/books.md
git log --oneline -- build-example/books.md
```

**If collaborators see different files:** check `git remote -v`, `git status`, the branch, and whether the original push succeeded. A public repo and collaborator invitation do **not** synchronize local working copies.

**If `git status` shows `Unmerged paths`:** stop pulling and pushing. Inspect the exact paths, then edit the *conflicted* file with Nano:

```bash
git status
nano build-example/books.md
```

Read `<<<<<<<`, `=======`, `>>>>>>>` as two competing versions. Preserve valid work from both sides, remove markers, **Ctrl+O**, **Enter**, **Ctrl+X**. For a **merge** in progress:

```bash
git add build-example/books.md
git status
git commit -m "Resolve book list merge conflict"
git status
```

Only commit if `git status` says all conflicts are fixed and a **merge** is in progress. If it says **rebase**, follow the rebase procedure instead; do not issue the merge commit command. Once clean and complete, `git push origin main` can share the result. Never use force-push, hard reset, or deletion as a catch-up shortcut.

**History lesson after resolution:**

```bash
git log --oneline
git show HEAD
git log --oneline -- build-example/books.md
```

A merge commit may not display a conventional single-parent diff in `git show HEAD`. Use the path-specific log to trace the book-list history. **Instructor asks:** "Which commits represent the metadata correction and the human resolution? How can we tell the difference between a local commit and a shared commit?"

**Teaching contract for each future module:** **SAY → PREDICT → TYPE THE REAL COMMAND → OBSERVE EXPECTED OUTPUT → INTERPRET → VERIFY → RECOVER → CONTINUE**. Never substitute `# edit`, `FILE`, or "save the file" for the first time a novice must perform an action. RStudio **Console** runs R; **Terminal** runs Git Bash commands; **Git pane** offers Git controls. Keep these distinctions visible.
