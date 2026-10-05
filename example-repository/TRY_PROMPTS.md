# TRY prompts

Use these prompts after cloning the example.

## 1. Locate

```bash
pwd
git rev-parse --show-toplevel
```

**TALK:** What is the difference between those two answers?

## 2. Observe

```bash
git status
git log --oneline
git remote -v
```

**TALK:** What does each command tell us that the others do not?

## 3. Investigate the files

Read the README, data, notes, ignore rules, license, and citation file.

**TALK:** Add one observation to Teams or say it aloud.

## 4. Test an ignore rule locally

Create a harmless PNG-named placeholder or use an instructor-provided generated file, then inspect:

```bash
git status
git status --ignored
git check-ignore -v PATH
```

**TALK:** What evidence tells you why Git is ignoring the path?

## 5. Transfer

Before making substantive changes, move to your **BUILD repository**.

Finish this sentence:

> "The example repository helped me inspect ___. My own repository is where I will build ___."


## Workshop continuity: keep the Carpentries thread

Oct. 8 continues the earlier Carpentries Git session. Keep the same conceptual object and vocabulary as responsibility moves from local Git into GitHub collaboration.

**Session 1 foundation:** version control benefits -> Git vs. GitHub -> repository -> modify/add/commit -> meaningful commit messages -> history/HEAD -> ignore -> remotes/collaboration.

**Oct. 8 continuation:** orient -> clone/investigate -> BUILD -> pull/change/inspect/add/commit/review/push -> rejected push/conflict -> human decision -> history/recovery -> documentation -> explain-back.

### Guacamole is the running specimen

Keep `guacamole.md` visible across the handoff instead of replacing it with disconnected exercises. Use it to recognize prior history, make and record a meaningful change, share with a partner, create and resolve a same-line conflict, and review the result with `HEAD`, `HEAD~1`, log, show, and diff.

**Teaching line:** Git can tell us that two versions of guacamole exist. Git cannot tell us which guacamole tastes better.

**Commit-message prompt:** "Six months from now, will this message tell another person why this version exists?"

The responsibility progression is **FOLLOW -> RECOGNIZE -> PREDICT -> EXPLAIN -> ACT -> HELP OTHERS.**
