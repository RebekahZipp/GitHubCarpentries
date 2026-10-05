# GitHub Carpentries: Oct. 8 Live Lesson

## From Local Git to Shared, Inspectable Work

**Time:** 1:00–4:00 PM  
**Instructor:** Rebekah Silverstein  
**Helpers:** Frances and Dani  
**Setting:** Digital Scholarship Center  
**Canonical foundation:** Software Carpentry, *Version Control with Git*  
**TRY repository:** https://github.com/RebekahZipp/GitHubCarpentries-Examples

This page is the **running teaching script**. Teach from top to bottom. Commands, learner practice, prompts, helper cues, catch-up points, common mistakes, review questions, and cheat-sheet reminders are embedded where they are needed.

The Carpentries sequence remains the technical backbone. Our added layer is deliberate repetition, prediction, evidence, discussion, safe intervention, and transfer into learner-owned work.

---

## Questions

- How does a local Git repository connect to GitHub?
- What do clone, remote, pull, and push actually move?
- How do two people work on the same repository without guessing?
- What should we do when Git rejects a push or reports a conflict?
- How do we decide what belongs in a durable repository?
- How can we use Git evidence to ask better technical questions?

## Objectives

By 4:00, learners should be able to:

- distinguish Git, GitHub, local, and remote;
- locate themselves and the repository before acting;
- clone and inspect an unfamiliar repository;
- explain what `origin` means;
- pull, change, inspect, stage, commit, review, and push;
- collaborate with another person;
- read a rejected push or conflict as evidence;
- inspect history and recover deliberately;
- decide whether a file should be tracked, ignored, or investigated;
- identify the roles of README, license, citation, and provenance;
- recognize the same Git states in RStudio; and
- explain a Git decision using evidence rather than memorized commands.

> **Course refrain:** The commands may change. The reasoning should become familiar.

---

# Instructor dashboard: keep this visible

## Four activity labels

**DEMO** = watch, predict, discuss.  
**TRY** = work in a local clone of the class example.  
**BUILD** = work in a learner-owned or partner-owned repository.  
**TALK** = answer aloud or add a thought to Teams.

Say often:

> "Say it out loud, or put your thought in Teams."

## Three recurring reasoning strips

### Normal Git work
**CHANGE → INSPECT → CHOOSE → RECORD → REVIEW → SHARE**

### Something unexpected
**EXPECT → OBSERVE → EXPLAIN → TEST → ACT → VERIFY**

### Before risky intervention
**LOCATE → DEFINE → SCOPE → PREDICT → ACT → VERIFY → HAND OFF**

## The board

Keep these visible for the entire lesson:

**WHERE AM I?**  
**WHAT CHANGED?**  
**WHAT IS THE EVIDENCE?**  
**WHAT SHOULD WE DO NEXT?**  
**DID IT WORK?**

Underneath:

**UNTRACKED/MODIFIED ≠ STAGED ≠ COMMITTED ≠ PUSHED**

---

# Run of show

| Time | Pace |
| --- | --- |
| 1:00–1:10 | Welcome, Code of Conduct, re-entry |
| 1:10–1:25 | Local vs GitHub, clone the TRY repo |
| 1:25–1:40 | Remotes, origin, push/pull mental model |
| 1:40–1:53 | Begin learner BUILD repositories and pairs |
| **1:53–2:00** | **7-minute break** |
| 2:00–2:18 | First full collaboration cycle |
| 2:18–2:33 | Switch roles and repeat with less support |
| 2:33–2:53 | Rejected push and controlled conflict |
| **2:53–3:00** | **7-minute break** |
| 3:00–3:15 | History, recovery, errors as evidence |
| 3:15–3:27 | Track / Ignore / Investigate |
| 3:27–3:40 | README, provenance, license, citation, review |
| 3:40–3:50 | RStudio transfer; Pages only if time |
| 3:50–4:00 | Learner artifact, explain-back, close |

**If behind:** protect both breaks, collaboration, conflict reasoning, verification, and final explain-back. Cut or shorten Pages, RStudio extension, or extra mystery-repository work.

---

# 1:00–1:10 | BEGINNING: Re-enter Git before GitHub

**MODE: TALK + DEMO**

## Say

> "Welcome back. Last time we taught Git how to remember our work. Today we make that record travel."

> "This is not a speed class. The goal is to make our work understandable, inspectable, recoverable, and reusable."

> "You will see four labels today. DEMO means watch and predict. TRY means use our safe example. BUILD means work in your own repository. TALK means say it aloud or put it in Teams."

Briefly remind learners that the Carpentries Code of Conduct applies in the room, Teams, and GitHub collaboration.

> "Mistakes, questions, rejected pushes, and conflicts are learning material. We review the work and the evidence, not the person."

## Ask before typing

> "Before I touch a repository, what do I want to know?"

Pause. Take answers aloud and from Teams.

If needed, guide toward **location, repository, branch, state, history**.

## DEMO

```bash
pwd
git rev-parse --show-toplevel
git status
git log --oneline
```

## Think aloud

> "`pwd` tells me where my shell is. `git rev-parse --show-toplevel` tells me where Git thinks this repository begins. Those are related questions, but they are not the same question."

## TALK

> "What did `git status` tell us that `pwd` could not?"

> "What did `git log` tell us that `git status` could not?"

### Teams prompt

**Add one word or phrase:** location, state, history, branch, or another thing you think we should check before acting.

### Helper cue

Frances/Dani: look for learners in the wrong console or directory. Do not fix silently. Ask:

> "What does Git think the repository root is?"

### Common mistake

**R Console vs Terminal.** If a learner types Git commands at an R `>` prompt, stop and identify the interpreter before diagnosing Git.

### CHEAT SHEET REMINDER 1: ORIENT

```bash
pwd
git rev-parse --show-toplevel
git status
git log --oneline
```

**Catch-up point:** A learner can rejoin if they know which terminal they are in, which directory they are in, and can run `git status`.

---

# 1:10–1:25 | GitHub adds another repository

**MODE: DEMO → TRY + TALK**

## Say

> "Git and GitHub are related, but they are not the same thing."

Draw:

```text
MY COMPUTER                GITHUB                 SOMEONE ELSE
local repository    <-->   remote repository <--> local repository
```

> "Git records change. GitHub gives us a place on the web to connect repositories and people."

## Ask

> "If GitHub disappeared for five minutes, would the commits already stored in my local repository disappear?"

Let the group reason it out.

## Transition to the class example

Open:

https://github.com/RebekahZipp/GitHubCarpentries-Examples

Say:

> "This is our TRY repository. You can inspect it and experiment in your own local clone. Your substantive workshop work will happen later in a repository you own."

Before cloning:

> "Where is this repository now?"

> "Where do we want another copy?"

> "What do you predict cloning will give us?"

## TRY: clone

Learners move to the parent directory where they want the new project folder, then:

```bash
git clone https://github.com/RebekahZipp/GitHubCarpentries-Examples.git
cd GitHubCarpentries-Examples
```

Immediately:

```bash
pwd
git rev-parse --show-toplevel
git status
git log --oneline
git remote -v
ls
```

## Say

> "Do not edit yet. Investigate first."

## TALK

> "What arrived besides the visible files?"

> "What evidence tells you this is a Git repository rather than a downloaded folder?"

> "What happened in this repository before you arrived?"

> "Say one observation aloud or put it in Teams."

### Helper cue

Before helping with a failed clone, establish:

1. terminal;
2. current directory;
3. whether a folder with that name already exists;
4. exact error text.

### Common mistakes

**Cloning from the wrong location:** learner does not know where the new folder went. Use `pwd` before cloning.

**Literal placeholder:** learner copies `REPOSITORY-URL` from generic notes. Ask what Git interpreted literally.

**Clone inside another project:** stop and locate both repository roots before changing anything.

### CHEAT SHEET REMINDER 2: CLONE AND VERIFY

```bash
git clone URL
cd REPOSITORY
git status
git log --oneline
git remote -v
```

**Memory line:** **Clone gives me a repository relationship, not just a folder of files.**

**Catch-up point:** If someone falls behind, they only need the example repo cloned and `git status` working. A helper can bring them to this exact point.

---

# 1:25–1:40 | Remotes are relationships

**MODE: DEMO + TRY + TALK**

The Carpentries remote lesson connects a local repository to another repository and uses `origin` as the conventional local name for that remote.

## DEMO

```bash
git remote -v
```

Point to the fetch and push URLs.

## Say

> "`origin` is a nickname stored in this local repository. It answers: where can this copy fetch from, and where would it try to push?"

> "Origin is conventional. It is not a magical GitHub location."

Draw:

```text
LOCAL REPO
   |
   | origin
   v
GITHUB REPO
```

## Ask

> "If I remove the nickname `origin` from my local repository, have I deleted GitHub?"

Pause.

> "No. I changed a local relationship."

Show for recognition, not memorization:

```bash
git remote add NAME URL
git remote set-url NAME NEW-URL
git remote rename OLD NEW
git remote remove NAME
```

## Push and pull concept

Write:

```text
LOCAL COMMIT  --push-->  GITHUB
LOCAL REPO    <--pull--  GITHUB CHANGES
```

Ask:

> "What moves when we push: my whole computer, my working file, or recorded Git history?"

> "What should we check before we send anything?"

## TRY

Learners run only:

```bash
git remote -v
```

and complete:

> "My local example repository calls ______ its remote, and that remote points to ______."

### Teams prompt

**In one sentence:** What does `origin` mean on your machine?

### Common mistake

**Push ≠ commit.** A commit records locally. A push shares recorded commits with a remote.

### CHEAT SHEET REMINDER 3: REMOTE

```bash
git remote -v
git push origin main
git pull origin main
```

**Memory line:** **Commit records here. Push shares there. Pull brings shared work here.**

---

# 1:40–1:53 | Move from TRY to BUILD

**MODE: BUILD**

## Say the transition clearly

> "We are finished using the example as our main workspace. TRY taught us how to inspect. BUILD is where you do the real work."

Put on screen:

```text
TRY = class example, local experimentation
BUILD = your repository, your decisions, your collaboration
```

## BUILD: create learner repository

Each learner creates or chooses a small repository they control. Keep the project small enough to understand today.

Minimum starting artifact:

```text
README.md
```

Pair learners as **Owner** and **Collaborator**.

Owner grants Collaborator access. Collaborator accepts and clones the Owner repository.

Before anybody edits, put this rhythm on screen:

**PULL → CHANGE → INSPECT → CHOOSE → RECORD → REVIEW → PUSH**

## Ask

> "Why might we pull before starting new shared work?"

> "Which of these steps changes the file? Which changes staging? Which creates history? Which shares history?"

### Helper cue

Confirm each pair can answer:

- whose repository is this?
- who is Owner right now?
- who is Collaborator?
- what remote does this clone point to?

Do not let access problems consume the class. If one account is blocked, pair the learner with a functioning partner and continue the reasoning exercise.

### CHEAT SHEET REMINDER 4: SHARED WORK

```text
PULL → CHANGE → INSPECT → CHOOSE → RECORD → REVIEW → PUSH
```

**Catch-up point before break:** Learner has a BUILD repository or partner repository available and knows whether they are Owner or Collaborator.

---

# 1:53–2:00 | BREAK 1

**Seven minutes. Stop teaching.**

Say:

> "Seven-minute break. Step away. If you want, leave a question in Teams and we will use those when we return."

### Instructor reset

Ask helpers quietly:

- What question are you hearing more than once?
- Are people confused about location, remote, access, or vocabulary?
- Who needs a catch-up hand at 2:00?

Write the top recurring issue on your instructor notes. Do not use the break for a mini-lecture.

---

# 2:00–2:18 | First complete collaboration cycle

**MODE: BUILD + TALK**

## Re-entry

Say:

> "Before we touch anything: where are we, whose repository is this, and what state is it in?"

Collaborator:

```bash
git status
git remote -v
git pull origin main
```

## CHANGE

Make one small, meaningful Markdown change.

## INSPECT

```bash
git status
git diff
```

Ask:

> "Git sees a change. Does that mean it automatically belongs in our next commit?"

## CHOOSE

```bash
git add FILE
git diff --staged
```

Ask:

> "What did we choose?"

> "Does the staged diff match what we intend to preserve?"

## RECORD

```bash
git commit -m "Describe the change"
```

Ask:

> "What exists now that did not exist before the commit?"

## REVIEW

```bash
git log --oneline
git show HEAD
```

## SHARE

```bash
git push origin main
```

Ask before Enter:

> "Where is this commit right now?"

> "Where are we asking Git to send it?"

## Owner receives the change

Owner:

```bash
git pull origin main
git status
git log --oneline
git show
```

### TALK

> "What can the Git record tell us about this change?"

Then:

> "What can Git not tell us by itself?"

### Teams prompt

Post **one state transition** in plain language. Example: "git add moved my chosen change into staging."

### Common mistakes

**`git add <file>`:** angle brackets are instructional notation, not part of the filename.

**`git add file .md`:** the shell sees two arguments. Check the exact filename with `ls`.

**Output pasted as input:** `new file: example.md` is Git speaking to you, not a shell command.

### CHEAT SHEET REMINDER 5: THE LOCAL CYCLE

```bash
git status
git diff
git add FILE
git diff --staged
git commit -m "message"
git log --oneline
git push origin main
```

**Memory line:** **Change. Inspect. Choose. Record. Review. Share.**

**Catch-up point:** A learner may rejoin once one commit is visible on GitHub. They do not need to reproduce every earlier keystroke.

---

# 2:18–2:33 | Switch roles: repeat with less help

**MODE: BUILD + TALK**

## Say

> "First pass: follow. Second pass: recognize and explain."

Switch Owner and Collaborator.

Do not narrate every command.

Ask:

> "What is our next move, and why?"

Let the group supply the sequence.

If needed, reveal only the rhythm:

**PULL → CHANGE → INSPECT → CHOOSE → RECORD → REVIEW → PUSH**

### Instructor restraint

When someone asks "What command next?", answer first with:

> "What state are you trying to change?"

or:

> "What evidence do you have about the current state?"

Then supply syntax if syntax is the actual barrier.

### Helper prompt

> "Show me the evidence that you are ready for the next step."

### Teams prompt

**What step feels most natural now? What step still feels easy to skip?**

### CHEAT SHEET REMINDER 6: DON'T MEMORIZE BLINDLY

```text
Need current shared work? → pull
Changed a file? → status + diff
Choose it? → add
Check the choice? → diff --staged
Preserve it? → commit
Check history? → log/show
Share it? → push
```

---

# 2:33–2:53 | Controlled conflict: Git refuses to guess

**MODE: BUILD + TALK**

## Set up

Both partners edit the **same clearly identified line** in the same small Markdown file.

Person A commits and pushes first.

Person B commits locally and tries:

```bash
git push origin main
```

## STOP at the rejection

Say:

> "Good. Do not fix it yet."

> "What did we EXPECT?"

> "What did we OBSERVE?"

Invite the exact non-sensitive rejection message into Teams.

> "What explanation fits the evidence?"

Guide toward: GitHub has history this local repository does not yet contain.

Put up:

**EXPECT → OBSERVE → EXPLAIN → TEST → ACT → VERIFY**

## Safety line

> "Nobody type `--force`. A rejected push is not permission to overwrite shared history."

## ACT: bring in shared work

```bash
git pull origin main
```

If Git asks how to reconcile divergent branches, pause and read the message. For this lesson, use the workshop's merge-based path rather than turning the moment into a rebase lesson.

When the conflict appears, inspect the file:

```text
<<<<<<< HEAD
local version
=======
incoming version
>>>>>>> commit
```

Ask:

> "Which one is correct?"

Wait.

> "Git cannot know. This is a human decision."

Resolve the intended text and remove the markers.

```bash
git add FILE
git status
git commit -m "Resolve conflicting changes"
git push origin main
```

## VERIFY

```bash
git status
git log --oneline
```

Have the partner pull and verify too.

## Say

> "CONFLICT does not mean DAMAGE. It means Git refused to invent human intent."

### Helper prompts

> "What changed remotely that this local copy did not know yet?"

> "What evidence tells you Git is still waiting for a decision?"

> "After the fix, what evidence tells you the conflict is over?"

### Common mistake

Learner edits the conflict but forgets `git add`. Ask what tells Git the human decision is complete.

### CHEAT SHEET REMINDER 7: REJECTED PUSH / CONFLICT

```text
EXPECT
  ↓
OBSERVE the exact message
  ↓
EXPLAIN before changing anything
  ↓
PULL shared history
  ↓
READ conflict markers
  ↓
DECIDE intended content
  ↓
ADD → STATUS → COMMIT → PUSH
  ↓
VERIFY
```

**Catch-up point before break:** It is enough to understand why the push was rejected and what the conflict represents. A helper can finish mechanical cleanup with the learner after the break if necessary.

---

# 2:53–3:00 | BREAK 2

**Seven minutes. Stop teaching.**

Say:

> "Second seven-minute break. When we come back, we move from collaboration problems into investigation, recovery, and making a repository understandable to somebody else."

### Instructor/helper pulse

Ask:

- Are rejected push and conflict conceptually different to learners?
- Who is still mid-conflict?
- What error message deserves a whole-room explanation?
- Is anyone working in the wrong repository?

Helpers can prepare catch-up learners at the exact checkpoint. Do not erase their evidence before they understand it.

---

# 3:00–3:15 | History, recovery, and errors as evidence

**MODE: DEMO → TRY + TALK**

Return to the safe TRY repository when useful.

## Say

> "Git history is useful because we can inspect what happened before deciding what to do next."

## DEMO / TRY

```bash
git log --oneline
git show HEAD
git diff HEAD~1
```

Ask:

> "What does HEAD mean here?"

> "Which command shows a commit? Which compares states?"

Make a harmless uncommitted change.

```bash
git diff
```

Ask:

> "Do we want this change?"

Only after deciding no:

```bash
git restore FILE
git status
```

## Say

> "Recovery begins with the state we intend to keep, not with an undo command."

## Authentic mistake mini-cases

Use one or two, not all.

### Mistyped option

```bash
git log --online
```

Ask:

> "Is the repository broken, or is the command malformed?"

### Output is not input

If Git prints:

```text
new file: example.md
```

say:

> "The computer is talking to us. That does not make its sentence shell syntax."

### Wrong place

If Git says "not a git repository":

```bash
pwd
git rev-parse --show-toplevel
```

### Instructor refrain

> "Git is being extremely literal."

Variation:

> "Git is being annoyingly literal again. Which, for version control, is actually a feature."

### Teams prompt

Post one error or surprise from today and complete:

> "I expected ___. I observed ___. The evidence suggests ___."

### CHEAT SHEET REMINDER 8: INVESTIGATE BEFORE RECOVERY

```bash
git status
git log --oneline
git show HEAD
git diff
git diff HEAD~1
```

Then decide. Do not reach for a destructive command first.

---

# 3:15–3:27 | Track, Ignore, Investigate

**MODE: TRY → BUILD + TALK**

In the TRY repository, inspect:

```bash
cat .gitignore
git status --ignored
```

If testing a path:

```bash
git check-ignore -v PATH
```

Ask:

> "Git noticed a file. Does that mean the file belongs in our durable record?"

Put up:

**TRACK → IGNORE → INVESTIGATE**

Use the example rule `*.png`.

Ask:

> "Does that mean all images are ignored?"

No. Git is literal.

## BUILD transfer

Learners look at their own repository and identify one thing that should be:

- tracked;
- ignored; or
- investigated before deciding.

### Helper prompt

> "What rule do you think applies? How can we verify instead of guessing?"

### Common mistake

Adding an ignore pattern does not stop tracking a file that is already tracked. First establish whether Git already tracks it.

### CHEAT SHEET REMINDER 9: IGNORE

```bash
git status
git status --ignored
git check-ignore -v PATH
```

**Question before `git add .`:** "Do all of these files belong in the same decision?"

---

# 3:27–3:40 | Make the repository understandable and reusable

**MODE: BUILD + TALK**

Open the TRY repository's:

- `README.md`
- `LICENSE`
- `CITATION.cff`
- `notes/analysis-notes.md`

## Ask

> "What can another person understand from the repository itself?"

> "What is still missing?"

> "Does public mean reusable?"

Explain the distinctions:

```text
VISIBLE ≠ PERMISSION TO REUSE
RECORDED ≠ CORRECT
DATA ≠ INTERPRETATION
HISTORY ≠ COMPLETE CONTEXT
```

Learners improve their own README with at least:

- what the project is;
- why it exists;
- where its material came from;
- what another person needs to understand it.

Discuss license/citation as decisions, not decorations.

## GitHub review prompt

Model:

> "I see this line changed from ___ to ___. What were you trying to accomplish?"

> "What evidence would help us decide between these approaches?"

Avoid "you did this wrong."

### Teams prompt

**What is one thing your repository needs so another person can understand it six months from now?**

### CHEAT SHEET REMINDER 10: REPOSITORY CONTEXT

```text
README      → what / why / how
.gitignore  → intentional exclusions
LICENSE     → reuse terms
CITATION    → attribution
notes       → decisions / provenance / limits
Git history → recorded change
```

---

# 3:40–3:50 | Same states, another interface

**MODE: DEMO + TRANSFER**

If learners use RStudio, show the Git pane briefly.

Do not reteach Git as buttons.

Say:

> "The interface changed. The repository states did not."

Before clicking anything, use:

**READ → LOCATE → PREDICT → ACT → VERIFY**

Ask:

> "What repository is this project connected to?"

> "What is staged?"

> "What exactly am I saying yes to?"

> "How will I verify what happened?"

## Optional GitHub Pages extension

Only if the class is on time.

Explain:

```text
REPOSITORY → PUBLISHING SOURCE → ENTRY FILE → PUBLIC SITE
```

Use a learner-owned or prepared repository, never the production OSU workshop site.

Ask:

> "Just because GitHub can publish this, should it be public?"

Reinforce privacy, permission, provenance, licensing, and institutional constraints.

### CHEAT SHEET REMINDER 11: GUI DOES NOT REMOVE SCOPE

**READ → LOCATE → PREDICT → ACT → VERIFY**

---

# 3:50–4:00 | END: explain, transfer, keep

**MODE: BUILD + TALK**

## Learner artifact

Learners finish with a repository they can continue developing.

Minimum useful state:

```text
README.md
one meaningful tracked artifact
a readable commit history
a known remote
an intentional next step
```

## Final explain-back

Pair learners.

Person A explains one repository decision or diagnoses one small Git situation. Person B may ask questions but should not take the keyboard. Switch.

Use:

> "I expected ___. I observed ___. The evidence showed ___. I did ___. I verified it by ___."

## Whole-room close

Ask:

> "What is one thing you can now explain that you could only follow at the beginning?"

Invite spoken answers or Teams.

Then ask:

> "What question do you still have?"

Helpers surface one recurring question if useful.

## Final script

> "Version control is not simply saving files. We observed change, decided what it meant, preserved a decision, checked the record, and shared it."

> "Git can record change. It cannot decide whether the change is meaningful, accurate, ethical, or appropriate. That remains human work."

> "The commands may change. The reasoning should become familiar."

---

# Final learner cheat sheet

## Where am I?

```bash
pwd
git rev-parse --show-toplevel
git status
```

## What happened?

```bash
git log --oneline
git show HEAD
git diff
git diff --staged
```

## Where is this connected?

```bash
git remote -v
```

## Normal work

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

## Something unexpected

**EXPECT → OBSERVE → EXPLAIN → TEST → ACT → VERIFY**

## File decision

**TRACK → IGNORE → INVESTIGATE**

## Help sentence

> "I expected ___, but I observed ___. I think ___ may explain it. I can test that by ___."

---

# Helper quick strip

Helpers use:

**LOCATE → OBSERVE → ASK → VERIFY → HAND OFF**

At each transition, ask:

> "What question are you hearing from more than one person?"

Do not silently fix repeated problems. Surface the pattern so the room can learn from it.

Escalate when credentials/private information appear, repository scope is unclear, a command could delete/overwrite files, institutional/shared equipment needs cleanup, or force-pushing/history rewriting appears necessary.

---

# Instructor common-mistake index

Use mistakes only when they expose a durable concept.

| Symptom | First question | Concept |
| --- | --- | --- |
| `not a git repository` | "Where are we?" | location/scope |
| command typed at `>` | "Which interpreter received this?" | console vs terminal |
| `git log --online` | "What did we actually type?" | literal syntax |
| `git add <file>` | "Is that a placeholder or filename?" | examples vs values |
| output pasted as command | "Who is speaking here?" | OUTPUT ≠ INPUT |
| wrong filename/pathspec | "What does `ls` show exactly?" | literal paths |
| rejected push | "What changed remotely?" | shared history |
| merge conflict | "What human decision is Git refusing to make?" | intent |
| ignored file surprises learner | "Which rule applies?" | literal patterns |
| no error but wrong result | "How will we verify?" | success ≠ intended state |

---

# Teaching design notes

This script intentionally follows the Carpentries pattern of **narrative → command → output/evidence → callout → challenge/practice → review/key point**, but makes the instructor's spoken transitions explicit.

Repetition changes responsibility:

1. **follow**;
2. **recognize**;
3. **predict**;
4. **explain**;
5. **act independently**;
6. **help someone else reason**.

Questions are invitations, not tests. If nobody answers, pause, model your reasoning, and continue. Silence is not failure.

Teams is a shared learning notebook. Learners may contribute one observation, command, non-sensitive error message, question, explanation, or takeaway. Helpers watch for patterns and bring them back to the room.

The course follows the Software Carpentry Git progression and adds an OSU Libraries reasoning, troubleshooting, collaboration, safety, and professional-practice layer. The example repository supports TRY. Learner-owned repositories support BUILD.


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
