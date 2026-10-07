# GitHub Carpentries

# START HERE: OCT. 8 LIVE LESSON

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
