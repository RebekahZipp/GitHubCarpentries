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
**BUILD** means substantive work happens in a repository you own or share with your partner.

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
