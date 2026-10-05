# GitHub Carpentries Example Repository

**TRY repository seed: clone, inspect, and experiment locally.**

This material supports the **TRY** parts of the Oct. 8 Git & GitHub workshop.

Learners should not use the instructor's source as their permanent workspace. During the workshop:

- **DEMO:** watch, predict, and discuss.
- **TRY:** inspect or experiment in your own local clone of the example.
- **BUILD:** do meaningful work in a repository you own or share with your partner.
- **TALK:** speak up or add a note, question, observation, or non-sensitive error message to Teams.

## Start by investigating

After cloning the example repository, do not change anything yet.

```bash
pwd
git rev-parse --show-toplevel
git status
git log --oneline
git remote -v
ls
```

Ask:

1. Where am I?
2. What repository am I in?
3. What branch am I on?
4. What happened before I arrived?
5. Where is this local repository connected?
6. What can I learn from the files without changing them?

## What is here?

- `data/library_visits.csv` — a tiny fictional dataset.
- `notes/analysis-notes.md` — a short record of an analytical decision.
- `output/README.md` — explains generated output.
- `.gitignore` — gives us something literal to inspect.
- `CITATION.cff` — a simple citation example.
- `LICENSE` — a teaching example of explicit reuse information.

The data are fictional and contain no patron or personal information.

## Practice rule

You may experiment with your **local clone**. If it becomes confusing, stop, inspect, explain what happened, and decide whether recovery or a fresh clone is the better learning move.

Do not paste credentials, tokens, private project information, or personal data into this repository or Teams.

## Reasoning rhythm

**CHANGE → INSPECT → CHOOSE → RECORD → REVIEW → SHARE**

When something surprises you:

**EXPECT → OBSERVE → EXPLAIN → TEST → ACT → VERIFY**


## Workshop continuity: keep the Carpentries thread

Oct. 8 continues the earlier Carpentries Git session. Keep the same conceptual object and vocabulary as responsibility moves from local Git into GitHub collaboration.

**Session 1 foundation:** version control benefits -> Git vs. GitHub -> repository -> modify/add/commit -> meaningful commit messages -> history/HEAD -> ignore -> remotes/collaboration.

**Oct. 8 continuation:** orient -> clone/investigate -> BUILD -> pull/change/inspect/add/commit/review/push -> rejected push/conflict -> human decision -> history/recovery -> documentation -> explain-back.

### Guacamole is the running specimen

Keep `guacamole.md` visible across the handoff instead of replacing it with disconnected exercises. Use it to recognize prior history, make and record a meaningful change, share with a partner, create and resolve a same-line conflict, and review the result with `HEAD`, `HEAD~1`, log, show, and diff.

**Teaching line:** Git can tell us that two versions of guacamole exist. Git cannot tell us which guacamole tastes better.

**Commit-message prompt:** "Six months from now, will this message tell another person why this version exists?"

The responsibility progression is **FOLLOW -> RECOGNIZE -> PREDICT -> EXPLAIN -> ACT -> HELP OTHERS.**
