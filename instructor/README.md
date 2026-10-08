## Instructor orientation: use the master script

The authoritative October 8 teaching sequence is [OCT8_LIVE_LESSON.md](OCT8_LIVE_LESSON.md). Recover from reboot with `cd /c/Users/Carpentries`, `ls`, enter the existing example repository, then `git status` and `git remote -v`. Use `git clone HTTPS_URL` only if the local folder is absent; `cd https://...` is not valid. Teach **PURPOSE → PREDICT → ACT → OBSERVE → INTERPRET → VERIFY → CONTINUE**.

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

# Instructor Path

## Teach Git by making the lesson with Git

This repository is both the teaching material and the teaching example.

Students see the project being built while learning how Git records that work.

The instructor follows the same workflow as the students:

**CHANGE → INSPECT → CHOOSE → RECORD → REVIEW → SHARE**

When something is uncertain or goes wrong, model:

**EXPECT → OBSERVE → EXPLAIN → TEST → ACT → VERIFY**

The instructor watches one additional layer:

**ACTION → RESULT → CONCEPT → TEACHING MOMENT → RECOVERY → HANDOFF**

Read the full [Teaching Rubric](../PEDAGOGY_RUBRIC.md) before teaching.

---

## Teaching objective

Students should leave understanding the workflow, not simply remembering commands.

Git is the record.

GitHub is the shared location for that record.

RStudio is one place where we can work with both.

The deeper objective is that learners can inspect an unfamiliar situation, explain what they observe, choose a test or action for a reason, verify the result, ask for useful help, and eventually help another person reason through the same work.

---

## Prompts are invitations, not quizzes

Questions in this guide are prompts for the instructor as much as for the room.

Pause briefly after a prompt. If a learner or helper contributes, use the contribution and test it against the evidence when practical. If nobody answers, continue naturally by thinking aloud.

Do not create an artificial question-and-answer routine in a small class.

For example:

> “What did I expect? I expected the push to work. What actually happened? Git rejected it. So before I try another command, what do I need to know?”

The learner hears both the question and the reasoning process.

Useful recurring prompts:

- Where am I?
- What did I expect?
- What actually happened?
- What changed?
- What does Git know?
- What do I need to know next?
- What evidence could answer that?
- What should we do next?
- How will we verify it?
- Who knows something we do not?

---

## Use mistakes intentionally, but let them feel like work

Safe mistakes can be planned. Perform them organically rather than announcing an “error demonstration.”

For every intentional mistake, know:

- **WHY** — why learners need this case;
- **WHAT** — what concept it exposes;
- **HOW** — how you will investigate, recover, and verify; and
- **HANDOFF** — what learners should be able to do afterward without you.

Do not make the learner the joke. The zest belongs in the instructor’s relationship with the computer and the evidence.

A useful line is:

> “Git is not being mysterious. Git is being extremely literal.”

---

## Feedback is part of the lesson

Do not wait until the final survey.

Use short openings:

> “Was that enough explanation, or did I jump a step?”

> “Who noticed something I did not mention?”

> “Would somebody say that differently?”

> “Helpers, what are you seeing around the room?”

> “Has anybody solved this differently?”

If nobody answers, keep teaching. The opening still models that technical knowledge can be questioned and improved.

Helpers are knowledge conduits, not only emergency support. Ask them to surface repeated questions and useful observations from around the room.

---

## Repetition removes scaffolding

Repeat the reasoning, not just the keystrokes.

1. Instructor models the reasoning aloud.
2. Learners participate when ready.
3. Learners begin supplying the reasoning.
4. Learners act with less prompting.
5. Learners explain or help another person without taking over the keyboard.

The same `git status` can deepen from “What changed?” to “What state am I in?” to “Before I act, what does Git currently believe?”

---

## Live teaching moments

### Teaching Moment 1 — Start with a project

We created an RStudio project.

The project gave our work a defined local location.

**Concept:** project structure.

**Prompt:** “Before we version anything, where is this project and what belongs to it?”

### Teaching Moment 2 — Git can exist before GitHub

The local project became a Git repository before the GitHub repository existed.

**Concept:** Git and GitHub are related, but they are not the same thing.

**Prompt:** “If GitHub does not exist yet, what is Git recording?”

### Teaching Moment 3 — Inspect before changing

Use:

```bash
git status
```

**Concept:** inspection before action.

**Think aloud:** “I could start trying commands, but first I want to know what Git thinks is happening.”

### Teaching Moment 4 — Wrong console

A Git command entered in the R Console produces an R error.

**WHY:** novices need to distinguish interpreters.

**WHAT:** the command may be reasonable but spoken to the wrong program.

**HOW:** identify the prompt, move to Terminal, retry, verify.

**HANDOFF:** learner can decide whether an R or Git/shell command belongs in the Console or Terminal.

### Teaching Moment 5 — Untracked and generated files

When Git reports new files, do not immediately `git add .`.

**Prompt:** “Git noticed these files. Does that mean they all belong in our record?”

Discuss **TRACK → IGNORE → INVESTIGATE**.

**Concept:** Git reports state; humans decide what constitutes the project record.


---

## Oct. 8 lesson sequence: Carpentries foundation plus reasoning layer

This workshop continues the Software Carpentry **Version Control with Git** lesson rather than replacing it. Kevin's first session establishes the local Git foundation. This session picks up with GitHub, collaboration, conflicts, professional repository practice, and transfer into RStudio and the learner's own work.

For each segment, teach three layers:

1. **Carpentries foundation** — the canonical Git concept and workflow.
2. **Reasoning layer** — the question or mental model learners can transfer.
3. **Live move** — the action, prompt, mistake, or verification learners experience.

### A. Re-orient to the local cycle

**Carpentries foundation:** modify → add → commit; use status, diff, and history.

**Reasoning layer:** **CHANGE → INSPECT → CHOOSE → RECORD → REVIEW → SHARE**

**Live move:** begin with `git status`, not a lecture. Ask what state Git reports and what evidence supports that reading.

### B. Clone and remotes

**Carpentries foundation:** `git clone` creates a local repository and configures `origin`.

**Reasoning layer:** cloning is a relationship, not just a download.

**Live move:** predict what will arrive, clone into an explicitly chosen location, then verify with `git status`, `git log --oneline`, and `git remote -v`.

### C. Shared class collaborators

**Carpentries foundation:** collaborator access, clone, change, add, commit, push; owner pulls the shared change.

**Reasoning layer:** **PULL → CHANGE → INSPECT → CHOOSE → RECORD → REVIEW → PUSH**

**Live move:** use the small class as collaborators on one shared public example repository. Collect GitHub usernames only during class, invite learners live, and have them accept before the first push. Helpers watch repository identity and location rather than taking over keyboards.

### D. Review shared work

**Carpentries foundation:** inspect changes from the command line and GitHub; comment on diffs.

**Reasoning layer:** a commit records a change, but the record does not automatically establish meaning, correctness, or intent.

**Live move:** ask, "What can I know from this record? What can I not know from Git alone?"

### E. Create and resolve a conflict

**Carpentries foundation:** two people make overlapping changes; push is rejected; pull exposes a merge conflict; human reconciles; stage, commit, and push the resolution.

**Reasoning layer:** **EXPECT → OBSERVE → EXPLAIN → TEST → ACT → VERIFY**

**Live move:** preserve the rejected push long enough to read it. Do not jump directly to a fix. Read the conflict markers as evidence and make the content decision explicit.

### F. History and recovery

**Carpentries foundation:** HEAD, commit identifiers, `git show`, `git diff`, `git restore`, and the distinction between restoring working files and reversing shared committed work.

**Reasoning layer:** recovery starts by identifying the intended state.

**Live move:** ask, "Which version are we trying to keep?" before using a recovery command.

### G. Ignore intentionally

**Carpentries foundation:** `.gitignore` records patterns for files that should not be tracked.

**Reasoning layer:** **TRACK → IGNORE → INVESTIGATE**

**Live move:** let generated files appear. Ask whether Git noticing a file means it belongs in the durable record.

### H. License, cite, and host

**Carpentries foundation:** public work needs explicit reuse terms; citation metadata makes work easier to credit; hosting choices do not remove institutional or sensitive-data obligations.

**Reasoning layer:** making work visible, reusable, citable, and appropriate to share are separate decisions.

**Live move:** inspect a real repository for README, LICENSE, CITATION, provenance, and hosting context.

### I. RStudio translation

**Carpentries foundation:** RStudio's Git pane exposes common staging, commit, diff, history, pull, and push operations.

**Reasoning layer:** the interface changes; Git state does not.

**Live move:** before clicking a GUI control, use **READ → LOCATE → PREDICT → ACT → VERIFY**. Ask, "What exactly am I saying yes to?"

### J. Portfolio handoff

**Carpentries foundation:** version control supports work that changes over time and collaboration beyond software.

**Reasoning layer:** the repository is evidence of technical decisions, documentation, provenance, and collaboration.

**Live move:** learners improve a repository they can keep, then explain one decision or diagnose one small Git situation without another person taking over their keyboard.

---

## Safety rule for repository scope

Before any destructive or difficult-to-reverse intervention, use:

**LOCATE → DEFINE → SCOPE → PREDICT → ACT → VERIFY → HAND OFF**

Do not casually demonstrate recursive deletion as repository cleanup. Prefer reversible moves, explicit paths, and verification. On institutional, shared, or borrowed equipment, stop and involve the responsible support staff when the scope extends beyond the learner's project.

See the [Helper Path](../helper/README.md) for the workshop support protocol.


---

## Instructor principle

Do not rescue every error immediately.

When an error is safe and instructive, make the thinking visible:

> “I expected X. I observed Y. Before changing anything, what evidence would help me distinguish the possible explanations?”

Then investigate.

The lesson is not: **experts type commands without mistakes.**

The lesson is: **we can inspect the state of our work, reason from evidence, ask for help, make the next decision deliberately, and share what we learn.**


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

## Required no-gap teaching protocol

Every module must show SAY → ASK/PREDICT → DEMO + DO → EXPECTED OUTPUT → INTERPRET → COMMON MISTAKE → RECOVER → VERIFY → TRANSITION. Do not present a placeholder such as '# edit a file' as a runnable step. Use the authoritative timed script for full dialogue.

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
