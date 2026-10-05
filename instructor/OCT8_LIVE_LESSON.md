# GitHub Carpentries: Live Teaching Lesson

## Oct. 8 | From Local Git to Shared, Inspectable Work

This is the **actual live lesson** for the second workshop session. It continues the Software Carpentry *Version Control with Git* lesson rather than replacing it.

Kevin's first session establishes the local Git foundation. This session moves learners from a local repository into GitHub collaboration, review, recovery, professional repository practice, and transfer into their own work.

The instructor teaches from this page. Students use the linked Student Path. Helpers use the linked Helper Path.

**Instructor:** Rebekah Silverstein  
**Helpers:** Frances and Dani  
**Setting:** in person, Digital Scholarship Center

---

## What learners should leave able to do

By the end, learners should be able to:

- distinguish Git, GitHub, a local repository, and a remote repository;
- establish where they are before acting;
- clone and inspect a repository;
- explain what `origin` means;
- collaborate using pull, change, stage, commit, review, and push;
- read a rejected push or merge conflict as evidence;
- inspect history and recover deliberately;
- decide what should be tracked, ignored, documented, licensed, and cited;
- recognize the same Git states in RStudio and GitHub interfaces;
- ask a useful technical question and help another learner without taking over; and
- leave with a repository that can become evidence of their work.

The commands may change. **The reasoning should become familiar.**

## How we work together

This workshop follows **The Carpentries Code of Conduct** in the room and in our GitHub collaboration spaces.

We will make mistakes, ask questions, review one another's work, and sometimes create conflicts on purpose. Treat those moments as evidence, not embarrassment.

- Use welcoming and inclusive language.
- Respect different viewpoints, experiences, technical choices, and experience levels.
- Accept constructive feedback gracefully.
- Focus review on the work and the evidence, not on the person.
- Help without taking over.
- Ask before touching another learner's keyboard or files.
- Do not publish another person's private communication, credentials, or project material without permission.

Instructor framing:

> "The goal is not to be the fastest person in the room. The goal is to make the work understandable, inspectable, and reusable."

During collaboration and review, model questions such as:

> "Can you walk me through what you expected this change to do?"

> "What does the diff show us?"

> "How can we ask about this change without assuming the other person made a mistake?"

If a Code of Conduct concern arises, stop the technical exercise and follow the workshop's Carpentries reporting and response process.

---

# The recurring language

## Normal work

**CHANGE → INSPECT → CHOOSE → RECORD → REVIEW → SHARE**

- **CHANGE:** make one intentional change.
- **INSPECT:** ask what Git sees.
- **CHOOSE:** decide what belongs in the next version.
- **RECORD:** commit that decision.
- **REVIEW:** inspect the resulting history.
- **SHARE:** move recorded work beyond this computer when it is ready.

## When something is unexpected

**EXPECT → OBSERVE → EXPLAIN → TEST → ACT → VERIFY**

> "I expected ___. I observed ___. I think ___ may explain it. I can test that by ___."

## Before risky intervention

**LOCATE → DEFINE → SCOPE → PREDICT → ACT → VERIFY → HAND OFF**

## When Git notices files

**TRACK → IGNORE → INVESTIGATE**

---

# 0. Re-entry: What did Git already teach us?

### Carpentries foundation

Learners already encountered repositories, `.git`, `git status`, changes, staging, commits, history, and ignoring files.

### Instructor move

Do not begin with a command list. Begin with the repository.

Say:

> "Last time we taught Git how to remember our work. Today we make that record travel."

Then:

> "Before I touch anything, what do I want to know?"

Pause. Accept learner answers. Then establish location and state:

```bash
pwd
git rev-parse --show-toplevel
git status
git log --oneline
```

### Student ask

- Where am I?
- What repository am I in?
- What branch am I on?
- What has already happened here?

### Helper ask

> "What does Git think the repository root is?"

### Tangible teaching moment

Put **WHERE AM I?** on the board. Keep it visible for the whole lesson.

Explain that `pwd` and `git rev-parse --show-toplevel` answer different questions: current directory versus repository root.

---

# 1. Git is not GitHub

### Carpentries foundation

Git records repository history locally. GitHub is a hosting and collaboration service for Git repositories.

### Instructor move

Draw three boxes:

```text
MY COMPUTER        GITHUB        SOMEONE ELSE'S COMPUTER
local repo   <-->  remote  <-->  local repo
```

Ask:

> "If GitHub disappeared for five minutes, would my local commits disappear?"

Then answer from the model: no. The local repository contains its own history.

### Student ask

> "What exists locally, and what exists on GitHub?"

### Helper watch

If a learner uses "Git" and "GitHub" interchangeably, do not merely correct the vocabulary. Ask which location they mean.

### Tangible teaching moment

Use a physical gesture or point to the three locations every time work moves. Make **local** and **remote** spatial.

---

# 2. Clone is not Download

### Carpentries foundation

`git clone` creates a local repository from a remote repository and automatically establishes a remote named `origin`.

### Instructor move

Before cloning, ask:

> "What do you predict will arrive on this computer?"

Also ask:

> "Before I click or type anything, where will Git put it?"

This is the first **READ → LOCATE → PREDICT → ACT → VERIFY** GUI/command moment.

Choose the destination deliberately, then clone an approved workshop repository:

```bash
git clone REPOSITORY-URL NEW-DIRECTORY
cd NEW-DIRECTORY
```

Immediately investigate:

```bash
git status
git log --oneline
git remote -v
ls
```

Translate:

- `ls`: What is here?
- `git status`: What state is this working copy in?
- `git log --oneline`: What happened before I arrived?
- `git remote -v`: Where is this copy connected?

### Controlled practice

Learners clone the assigned repository into a location they can identify.

They must be able to finish:

> "I cloned ___ into ___. Git says the repository came from ___."

### Student ask

> "What did cloning give me that downloading a ZIP would not?"

### Helper ask

> "Show me where you are going to put the clone before you run the command."

### Intentional mistake

Use a placeholder literally once, safely:

```bash
git clone REPOSITORY-URL NEW-DIRECTORY
```

Read the error.

Ask:

> "Did Git break, or did Git do exactly what I asked?"

Explain that instructional placeholders must be replaced with real values.

**WHY:** learners routinely paste examples literally.  
**WHAT:** syntax can be valid while the requested object does not exist.  
**HOW:** read the command and error as evidence.  
**HANDOFF:** learners identify placeholders before executing examples.

---

# 3. Remotes are relationships

### Carpentries foundation

A remote is another repository Git can fetch from or push to. `origin` is a conventional local alias, automatically created by clone. It is not an intrinsic GitHub object.

### Instructor move

Run:

```bash
git remote -v
```

Say:

> "Origin is a nickname this local repository knows. We could have called it something else."

Show, but do not require learners to execute all of these:

```bash
git remote add NAME URL
git remote set-url NAME NEW-URL
git remote rename OLD-NAME NEW-NAME
git remote remove NAME
```

Ask:

> "If I remove the local nickname, have I deleted the GitHub repository?"

No. We changed a local relationship.

### Student ask

> "Where will `git push origin main` try to send my commits?"

### Helper ask

> "What does `git remote -v` actually show on your machine?"

---

# 4. Owner and Collaborator

### Carpentries foundation

The Carpentries collaboration exercise uses pairs. One learner is the **Owner**, the other the **Collaborator**. The Collaborator receives repository access, clones the Owner's repository, makes and commits a change, and pushes it. The Owner pulls that change. Then roles switch.

### Instructor setup

Pair learners. If necessary, create one trio with a helper participating as observer rather than owner of the keyboard.

Before anybody edits, put this on the board:

**PULL → CHANGE → INSPECT → CHOOSE → RECORD → REVIEW → PUSH**

Explain:

> "This is not a magic sequence. Each arrow is a change in state."

### Owner

Grant Collaborator access through GitHub repository settings.

### Collaborator

Accept access, clone the Owner's repository into a clearly named location, then verify:

```bash
git status
git remote -v
git log --oneline
```

### Controlled practice: one small contribution

Create or edit one small Markdown file.

Then:

```bash
git status
git diff
git add FILE
git diff --staged
git commit -m "Describe the change"
git log --oneline
git push origin main
```

### Instructor prompts

Before `git add`:

> "Git sees the change. Does that mean it automatically belongs in the next commit?"

Before `git commit`:

> "What decision are we preserving?"

Before `git push`:

> "What exists locally right now that does not yet exist on GitHub?"

### Student asks

- What changed?
- What am I staging?
- Does the staged diff match what I intend to record?
- Where will this commit go when I push?

### Helper asks

- "What did `git status` say before you staged it?"
- "Can you show me the staged diff?"
- "Which remote and branch are you about to push to?"

### Tangible teaching moment: staging is a decision

Write:

**UNTRACKED/MODIFIED ≠ STAGED ≠ COMMITTED ≠ PUSHED**

Have learners point to the state their change is currently in.

---

# 5. Owner pulls and reviews the collaborator's work

### Carpentries foundation

The Owner downloads the Collaborator's new commit with:

```bash
git pull origin main
```

Then the local Owner repository, GitHub repository, and Collaborator repository can be brought back into sync.

### Instructor move

Before pulling:

> "What do I expect to change on this computer?"

After pulling:

```bash
git status
git log --oneline
git show
```

Open the commit on GitHub and inspect the diff.

### Student ask

> "What can I know about this change from Git's record?"

Then:

> "What can I *not* know from Git alone?"

### Teaching point

Git can preserve the change, author metadata, time, commit message, and history relationships. It cannot independently establish that the change is meaningful, accurate, ethical, or appropriate.

Documentation and human review supply context.

### GitHub review moment

Show how a change can be discussed in GitHub. The point is not merely that GitHub has comments. The point is that technical review and discussion can become part of the collaborative record.

Model community-centered review:

> "I see this line changed from ___ to ___. What were you trying to accomplish?"

> "What evidence would help us decide between these approaches?"

Avoid person-centered judgments such as "you did this wrong." Review the change, evidence, and intended outcome. Different experience levels and technical choices are expected in the room.

---

# 6. Switch roles

Do the collaboration cycle again with Owner and Collaborator reversed.

This repetition is deliberate.

First pass: **follow**.  
Second pass: **recognize and explain**.

Instructor and helpers reduce prompting on the second pass.

Ask:

> "What is our next move, and why?"

Do not answer immediately.

---

# 7. Controlled conflict: Git refuses to guess

### Carpentries foundation

Create overlapping changes to the same line in the Owner and Collaborator copies. One person pushes first. The other person's later push is rejected because the remote history has changed.

### Instructor setup

Tell learners only that both people will edit the same small line. Do not frame the rejection as failure.

Person A commits and pushes.

Person B commits locally and then tries:

```bash
git push origin main
```

Stop when Git rejects the push.

### Instructor move

Do **not** fix it immediately.

Say:

> "Good. This is evidence."

Then:

> "What did we expect?"

Expected: push succeeds.

> "What did we observe?"

Observed: Git rejected the push.

> "What explanation fits the evidence?"

GitHub has history this local repository does not yet have.

Use:

**EXPECT → OBSERVE → EXPLAIN → TEST → ACT → VERIFY**

### Critical rule

> "Nobody type `--force`."

Explain why: we do not rewrite shared history simply because Git refused an operation.

### Pull the shared work

```bash
git pull origin main
```

Now inspect the conflict.

### Read the markers

```text
<<<<<<< HEAD
our local version
=======
incoming version
>>>>>>> commit
```

Ask:

> "Which line is correct?"

The answer is not "the top one" or "the bottom one." A human must decide what the intended content should be.

Edit deliberately, remove conflict markers, then:

```bash
git add FILE
git status
git commit -m "Resolve conflicting changes"
git push origin main
```

Finally:

```bash
git status
git log --oneline
```

### Student ask

> "How do I know the conflict is actually resolved?"

### Helper ask

> "What evidence tells you Git has stopped waiting for a decision?"

### Tangible teaching moment

Put on the board:

**CONFLICT ≠ DAMAGE**

A conflict is Git refusing to invent human intent.

---

# 8. Error messages are evidence

Use authentic, safe examples when they arise.

## Placeholder as literal input

```bash
git add FILE
```

Possible result: pathspec does not match.

Ask:

> "What did Git think FILE meant?"

## Mistyped option

```bash
git log --online
```

Ask:

> "Is the repository broken, or is the command malformed?"

## Commit message without `-m`

```bash
git commit - "My message"
```

Read the pathspec error.

Then compare with:

```bash
git commit -m "My message"
```

## Output is not input

If Git prints:

```text
new file: example.md
```

do not paste that line as the next command.

Say:

> "The computer is talking to us. That does not make its sentence shell syntax."

### Instructor refrain

> "Git is being extremely literal."

Use occasionally, not after every error.

---

# 9. History and recovery

### Carpentries foundation

Git's history allows learners to inspect earlier states and recover deliberately.

Use:

```bash
git log --oneline
git show HEAD
git diff HEAD~1
```

Explain `HEAD` as the current commit.

### Controlled practice

Make a small uncommitted change. Inspect it:

```bash
git diff
```

Ask:

> "Do we want this change?"

If the class intentionally decides no, demonstrate:

```bash
git restore FILE
git status
```

### Teaching point

Recovery begins with a target state, not with a recovery command.

Ask:

> "Which version are we trying to keep?"

Do not generalize `git restore` into a universal undo button.

---

# 10. Track, Ignore, Investigate

### Carpentries foundation

A `.gitignore` file tells Git which untracked paths should normally stay out of version control.

### Instructor move

Create or expose generated/example files.

Run:

```bash
git status
```

Ask:

> "Git noticed these. Does that mean all of them belong in our record?"

Use:

**TRACK → IGNORE → INVESTIGATE**

Inspect the ignore rules:

```bash
cat .gitignore
git status --ignored
```

If something behaves unexpectedly:

```bash
git check-ignore -v PATH
```

### Tangible teaching moment

Compare:

```text
*.png
pictures/
```

Explain that file extensions and directory rules are literal. A rule for PNG files does not mean "all images."

Also explain that ignore rules do not automatically stop tracking something already committed.

### Student ask

- Can another person regenerate this?
- Does another person need it?
- Is it source, configuration, output, scratch work, or unknown?

### Helper ask

> "What rule do you think applies? How can we verify that instead of guessing?"

---

# 11. License, Citation, Hosting: making a repository usable

### Carpentries foundation

The Carpentries lesson distinguishes making work public from granting permission to reuse it, and recommends explicit licensing. It also introduces citation files, including `CITATION.cff`, and asks learners to consider where work should be hosted.

### Instructor move

Open a real public repository and investigate:

- README
- LICENSE
- CITATION/CITATION.cff
- contributors/history
- source/provenance notes

Ask:

> "I can see this repository. Does that mean I can do anything I want with it?"

No.

Then:

> "If I reuse this work, how does the creator tell me how to credit it?"

### Institutional prompt

> "Can every project we work on at a university simply be made public?"

Discuss intellectual property, sensitive information, human-subjects material, contractual restrictions, and institutional policy at the level supported by the workshop. The lesson is to **check**, not to make learners legal experts.

### Student controlled practice

For their own repository, learners identify:

1. whether the repository should be public or private;
2. whether they know the reuse/license status;
3. what provenance needs to be documented; and
4. whether a citation file would be appropriate.

---

# 11A. Optional extension: publish with GitHub Pages

Use this only if the core collaboration lesson is on time. GitHub Pages is an extension, not a prerequisite.

### Teaching purpose

A repository can become more than a storage location: selected repository content can be published as a static website.

Before publishing, ask:

> "What will become public if I publish this?"

> "Does this repository contain anything that should not be on a public website?"

### Controlled demonstration

Use a **separate learner-owned or instructor-prepared repository**, never the production OSU Carpentry workshop website.

Show the relationship:

```text
REPOSITORY → PUBLISHING SOURCE → ENTRY FILE → GITHUB PAGES SITE
```

Explain that a Pages site needs a publishing source and an entry file such as `index.html`, `index.md`, or `README.md`.

Keep the conceptual lesson:

**VISIBLE ≠ APPROPRIATE TO PUBLISH**

Learners should check privacy, permissions, provenance, licensing, and institutional constraints before publication.

---

# 12. RStudio: same states, different interface

### Carpentries foundation

RStudio exposes common Git operations through its Git integration: status, staging, diff, commit, history, pull, and push.

### Instructor move

Open an existing Git repository as an RStudio Project.

Point to the Git pane.

Do not teach the buttons as a second Git system.

Say:

> "The interface changed. Did Git's states change?"

Use:

**READ → LOCATE → PREDICT → ACT → VERIFY**

Before clicking Commit:

> "What is staged?"

Before Push:

> "Where will these commits travel?"

Before accepting a dialog:

> "What exactly am I saying yes to?"

### Student ask

> "Which command-line concept does this button represent?"

### Helper ask

> "Can you show me the repository state before we click?"

### Teaching point

Friendly interfaces do not remove filesystem scope, repository scope, or consequences.

---

# 13. Mystery repository investigation

Give learners a small approved public or prepared repository without explaining it first.

Mission:

> "What is this thing, where did it come from, and what happened before you arrived?"

Learners use:

```bash
git status
git log --oneline
git remote -v
ls
```

Then inspect README, license, citation/provenance, file types, and selected history.

### Report back

Each learner/pair gives:

- one thing the evidence supports;
- one thing they still do not know;
- one question they would ask the project creator.

This is the transition from following commands to investigating repositories.

---

# 14. Build something worth keeping

Learners now create or improve a repository they own.

Suggested minimum:

```text
my-project/
├── README.md
├── data/ or materials/
├── scripts/ or notes/
├── docs/
└── .gitignore
```

Not every repository needs this exact structure. The point is intentional organization.

The README should answer:

- What is this project?
- Why does it exist?
- Where did its material or data come from?
- What did I do?
- How can another person understand or reproduce the work?
- What skills does this repository demonstrate?

Where appropriate, add licensing and citation information.

### Portfolio framing

Say:

> "This is not a disposable recipe exercise anymore. The repository can become evidence of how you document, reason, collaborate, and preserve your work."

---

# 15. Final transfer: help without taking over

Pair learners one final time.

One learner presents a small Git situation. The other may not take the keyboard.

Use:

- What did you expect?
- What do you observe?
- What evidence would help?
- What is the smallest safe test?
- What action does the evidence support?
- How will you verify it?

Then switch.

### Helper role

Helpers listen for whether learners are reasoning from evidence. Surface recurring questions to the whole room.

### Instructor close

Return to the board:

**CHANGE → INSPECT → CHOOSE → RECORD → REVIEW → SHARE**

Then:

**EXPECT → OBSERVE → EXPLAIN → TEST → ACT → VERIFY**

Close with:

> "Git is not valuable because experts never make mistakes. It is valuable because we can inspect what changed, preserve decisions, recover history, collaborate, and make our reasoning easier for the next person to follow."

---

# Continue practicing after the workshop

Offer these after the core lesson so they extend rather than interrupt the Git/GitHub sequence:

- **Exercism** — free coding-literacy practice.
- **Stack Overflow** — community questions and searchable technical discussions; encourage learners to read context and evaluate answers rather than copy commands blindly.
- **Alliance for Data Science and AI** — continuing education, community events, hackathons, practice, and workshops.
- **sandbox.bio** — interactive practice with Carpentries Programming with Python exercises.

Invite learners to keep using the same reasoning outside this workshop:

**EXPECT → OBSERVE → EXPLAIN → TEST → ACT → VERIFY**

---

# Instructor safety boundaries

Do not use destructive commands casually for demonstrations.

Before cleanup or recovery:

**LOCATE → DEFINE → SCOPE → PREDICT → ACT → VERIFY → HAND OFF**

Stop and escalate when:

- repository scope is unclear;
- credentials or tokens appear;
- personal/private information is visible;
- a command could recursively delete or overwrite files;
- the machine is institutional, shared, or borrowed and cleanup extends beyond the workshop project;
- force-pushing or shared-history rewriting appears necessary.

Prefer reversible moves and inspection.

---

# Helper pulse checks

At natural transitions, ask helpers:

> "What question are you hearing from more than one person?"

> "Where are learners getting stuck: location, Git state, GitHub, or vocabulary?"

> "Did anybody solve this differently?"

Helpers should surface patterns, not silently fix every machine.

---

# Student checkpoints

A learner is ready to continue when they can explain, not merely reproduce:

### Checkpoint 1
"I know where my repository is and what Git says its state is."

### Checkpoint 2
"I can explain the difference between my local repository and GitHub."

### Checkpoint 3
"I can explain what clone and origin gave me."

### Checkpoint 4
"I can inspect a change before staging and inspect the staged change before committing."

### Checkpoint 5
"I can explain why a rejected push is evidence rather than permission to force."

### Checkpoint 6
"I can read a conflict as a human decision Git refused to make."

### Checkpoint 7
"I can decide whether a file should be tracked, ignored, or investigated."

### Checkpoint 8
"I can explain what another person needs in order to understand, reuse, or cite my repository."

### Checkpoint 9
"I can ask for help using evidence."

### Checkpoint 10
"I have a repository I can continue developing after class."

---

# Relationship to the Carpentries lesson

This lesson deliberately retains the Software Carpentry progression and concepts:

- local automated version control;
- repository creation and `.git`;
- tracking changes;
- history and recovery;
- ignoring files;
- GitHub remotes;
- collaboration through clone/pull/push;
- conflicts;
- licensing;
- citation;
- hosting; and
- RStudio integration.

Our added layer makes the reasoning explicit, adds controlled practice and helper behavior, uses authentic mistakes as evidence, strengthens repository-scope safety, and ends with a durable learner artifact.

Use the canonical Software Carpentry lesson for the full reference material and this document for the live Oct. 8 teaching sequence.
