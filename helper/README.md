## DSC recovery: helper intervention

Ask the learner: **Are you trying to enter a local folder, clone a missing repository, or contact GitHub?** Start with `pwd`, `ls`, `cd /c/Users/Carpentries`, `ls`. If `GitHubCarpentries-Examples` exists, enter it and run `git status` and `git remote -v`. If absent, clone only once using `git clone https://github.com/RebekahZipp/GitHubCarpentries-Examples.git`. **Do not use `cd https://...`**, erase work, or take over the keyboard. Ask the learner to interpret each result. A reboot is not a reason to clone.

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



## Teams workshop-space checkpoint

At arrival, help learners open **Git & GitHub Workshop | OSU Libraries** in Teams and keep it available.

The distinction is:

```text
TEAMS       course links, notes, slides, cheat sheet, questions, ideas
GITHUB      shared versioned project history
LOCAL       learner working copy
```

If a learner cannot find a workshop resource, help them return to the Teams tabs before sending them through another route. Encourage learners to use chat for questions, ideas, observations, and non-sensitive error messages.

Do not ask learners to put credentials, tokens, authentication codes, private data, or sensitive research information in chat.

During teaching prompts, watch both spoken participation and chat contributions. Surface useful patterns to Rebekah without requiring every learner to speak aloud.

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
- Is this the shared class clone or another project?

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

## Whole-room discourse

Learners can answer aloud or contribute when invited. Treat both as participation.

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

When useful, invite a learner to read or show the **exact non-sensitive error message** so the group can reason from the same evidence.

At the 7-minute breaks around 2:00 and 3:00, stop active troubleshooting unless a learner specifically asks to continue. Use the break to collect patterns for the instructor and let learners step away.

## Training-day cue sheet

Use these as place points so you know what the room should be doing without needing to follow every instructor sentence.

| Time | Learner state | Helper priority |
| --- | --- | --- |
| **1:00–1:10** | Re-entry | Console, directory, repository root, status |
| **1:10–1:25** | TRY clone | Clone location, exact error, verify remote/history |
| **1:25–1:40** | Remotes | Help learners explain `origin`; do not overteach remote commands |
| **1:40–1:53** | BUILD setup | GitHub username only, collaborator invitation accepted, correct shared clone |
| **1:53–2:00** | **BREAK** | Stop active troubleshooting; give Rebekah pattern report |
| **2:00–2:18** | First collaboration | State transitions: modified → staged → committed → pushed |
| **2:18–2:33** | Shared push/pull | Reduce help; ask learner for next move and evidence |
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


---

## Helper live command reference

Use the same executable commands learners see. Prompt the learner to type, predict, and explain; do not take their keyboard.

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
