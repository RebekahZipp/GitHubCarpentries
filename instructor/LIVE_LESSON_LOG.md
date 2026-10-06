# Live Lesson Log and Instructor Script

## Purpose

This log documents both what we build and why we teach it this way. The repository is the lesson, the teaching record, and evidence of a developing community of practice.

Use [PEDAGOGY_RUBRIC.md](../PEDAGOGY_RUBRIC.md) as the governing teaching rubric.

## Memorable lesson arc

Students should leave with more than commands. They should be able to recognize a Git repository as a research and professional object, investigate where it came from, reason from evidence, make an intentional change, record and verify that change, seek useful help, and share work they can continue developing as portfolio evidence.

### Two ways into Git

**LOCAL → Git → GitHub**

A student already has work and decides to record and share it.

**GitHub → CLONE → LOCAL**

A project already exists and the student creates a connected local working copy.

After either entry point, use the same rhythm:

**CHANGE → INSPECT → CHOOSE → RECORD → REVIEW → SHARE**

When the expected path breaks:

**EXPECT → OBSERVE → EXPLAIN → TEST → ACT → VERIFY**

## How to use prompts live

Prompts are invitations, not quizzes. Ask, pause briefly, and continue if the room is quiet. The prompt is also your cue to make expert reasoning audible.

Example:

> “What did I expect? I expected this push to work. What happened instead? Git rejected it. Before I try another command, what do I need to know?”

If somebody contributes, incorporate the idea. Ask what evidence would support it. If nobody contributes, keep reasoning aloud.

Use feedback during the technical work:

> “Was that enough explanation, or did I jump a step?”

> “Who noticed something I did not mention?”

> “Helpers, what are you seeing around the room?”

> “Has anybody solved this differently?”

## Teaching Moment — Clone is not Download

A downloaded file is a file. A ZIP is a snapshot of files. A clone is a local Git repository with project files, history, branches, and a remembered remote.

**OPEN PROMPT:** “Before we clone it, what do you think will arrive on this computer?”

If nobody answers, make your own prediction aloud.

Investigate before changing anything:

```bash
git status
git log --oneline
git remote -v
ls
```

Translate the commands into questions:

- `ls` — What is here?
- `git status` — What state is my working copy in?
- `git log --oneline` — What happened before I arrived?
- `git remote -v` — Where did this repository come from?

Then open History/Diff in GitHub Desktop.

**PROMPT:** “I was not there when this change happened. What can I know anyway?”

**FOLLOW:** “What can Git not tell me?”

If the room is quiet, model both answers. This introduces provenance, documentation, commit messages, review, and the limits of the record.

## Teaching Moment — Wrong console

Let a Git command land in the R Console during a natural transition.

**WHY:** Learners need to recognize that tools interpret different languages.

**WHAT:** A reasonable command can fail because it was sent to the wrong interpreter.

**PERFORM:** “Well, R did not enjoy that. Before I change the command, what else could be wrong?”

**HOW:** Notice the `>` prompt, identify the R Console, move to Terminal, retry, verify.

**HANDOFF:** Learners can use the interface and prompt to decide where R versus shell/Git commands belong.

## Teaching Moment — Wrong directory or typo

Allow an ordinary path typo or work from the wrong location when it arises safely.

**WHY:** Novices often interpret a location error as a broken repository.

**PERFORM:** “The computer says that place does not exist. Before we accuse the computer, let’s establish where we actually are.”

Use `pwd`, `ls`, and then `git status` when appropriate.

**HANDOFF:** Learners check location before escalating the diagnosis.

## Teaching Moment — Error messages are evidence

A typo such as:

```bash
git log --online
```

can remain visible long enough to read the response.

**PERFORM:** “Git is not being mysterious. Git is being extremely literal.”

Ask or model:

- What did we ask for?
- What did Git report?
- Is this evidence of a damaged repository or a malformed command?
- What is the smallest correction we can test?

Then verify the corrected command.

## Teaching Moment — Remote and clone problems

If a remote URL or clone fails, do not repeatedly change commands at random.

**PERFORM:** “I expected Git to reach the repository. It did not. What can I test without doing the whole operation again?”

Use an appropriate diagnostic such as:

```bash
git remote -v
```

or, when testing a remote directly:

```bash
git ls-remote REPOSITORY-URL
```

**CONCEPT:** isolate one uncertainty at a time.

## Teaching Moment — Push rejected

When local and remote history differ, preserve the moment.

**PERFORM:** “GitHub has work I do not have, or my local history is not where GitHub expects it. Nobody type `--force`. What do we need to know before deciding what history is right?”

Inspect before synchronizing.

**HANDOFF:** Learners understand that push is not a universal save button and that remote history matters.

## Teaching Moment — Git noticed files; should we keep them?

When generated or local files appear as untracked, do not immediately stage everything.

**PROMPT:** “Git sees these files. Does that mean they all belong in the project history?”

Use:

**TRACK → IGNORE → INVESTIGATE**

For each file ask:

- What is it?
- Where did it come from?
- Can it be regenerated?
- Does another person need it to understand, reproduce, or continue the work?
- Is it source, configuration, output, scratch work, or something we still need to investigate?

**CONCEPT:** Git reports state; humans establish the record.

## Land-grant artifact investigation

Use authentic public research/teaching repositories when their license and size make them appropriate. Prefer artifacts that let learners recognize land-grant work as data, documentation, teaching, agriculture, environment, or public scholarship rather than only software.

Candidate stations:

1. **OSU Carpentries workshop repository** — inspect a real Oklahoma State workshop repository already visible to instructors. Look at `index.md`, `_config.yml`, history, authorship, and the `gh-pages` branch. Use for provenance and collaborative teaching infrastructure.
2. **NEONForestAGB** — public forest biomass research whose authors include an Oklahoma State University researcher and USDA/NEON collaborators. Its repository documents a data workflow and includes taxonomy/source-data context and R scripts. Use only after checking current size/license and choosing a small, safe path for learners.
3. **Land-Grab Universities source data** — a public CC0 dataset containing CSV, spreadsheet, shapefile, and documentation artifacts about land-grant university history. This is useful for showing that repositories can contain research data and documentation, not merely code. Instructor must frame the subject historically and respectfully and avoid making it the first technical exercise.
4. **The Carpentries workshop template** — useful for demonstrating a real community-maintained repository, but follow its own guidance: create from the template rather than asking learners to fork it directly.

## Mystery repository exercise

Do not explain the repository first. Give learners a small approved public repository or prepared teaching repository.

**PROMPT:** “What is this thing, where did it come from, and what happened before you arrived?”

Learners clone, inspect, read the README, inspect history, identify file types, locate provenance/licensing information, and report what the evidence supports.

If nobody volunteers, model the first inference and leave the next one open.

## Portfolio outcome

The final learner artifact should be a repository they own and can continue using. Suggested structure:

```text
my-project/
├── README.md
├── data/
│   └── example.csv
├── scripts/
│   └── analysis.R
├── docs/
│   └── notes.md
└── .gitignore
```

Their README should answer:

- What is this project?
- Why did I make it?
- Where did its data/material come from?
- What did I change or contribute?
- How can another person understand or reproduce the work?
- What skills does this repository demonstrate?

The learning product is therefore not a disposable exercise. It can become evidence of documentation, version control, provenance awareness, reproducible practice, reasoning, and collaboration for a CV, résumé, portfolio, application, or later research project.

## Final transfer — explain, do not take over

Near the end, stop being the person with the answer.

Ask a learner to explain one situation to a partner or helper. If they are helping someone else, ask them not to take the keyboard.

Useful prompts:

> “What did you expect?”

> “What do you observe?”

> “What evidence would help you decide?”

> “How will you know the next action worked?”

In a very small class, perform both sides of the dialogue and leave openings for correction or contribution.

## Community-of-practice review

Invite Carpentries instructors to review the lesson for rigor rather than silently rewrite it. Ask reviewers to comment on:

- conceptual accuracy;
- novice cognitive load;
- accessibility and recovery paths;
- whether commands are connected to questions and concepts;
- whether prompts work even when nobody answers;
- whether mistakes have a clear WHY, WHAT, HOW, and HANDOFF;
- whether feedback is embedded throughout the technical lesson;
- whether repetition transfers responsibility to learners;
- provenance/reproducibility claims;
- whether the portfolio outcome is authentic and achievable;
- whether example repositories are appropriately licensed, sized, and contextualized; and
- missing teaching moments or likely learner misconceptions.

Record substantive changes in Git history so the development of the lesson remains inspectable.


---

## Decision synchronization: Oct. 5, 2026

The repository was synchronized to the current Oct. 8 workshop design after rehearsal and comparison with the Software Carpentry Git collaboration/conflict sequence.

### Decisions recorded

1. **Carpentries remains the conceptual spine.** The OSU lesson adapts examples, pacing, prompts, and small-class mechanics without redefining clone, origin, pull, commit, push, rejected push, or merge conflict.
2. **Hands-on rhythm is one move at a time.** Use **SAY -> ASK/PREDICT -> DEMO + DO -> STOP -> READ OUTPUT -> ASK WHAT IT MEANS -> SAY THE CONCLUSION -> NEXT MOVE**. Learners normally remain at the same checkpoint as the instructor.
3. **Shared BUILD replaces separate learner repositories.** Everyone clones `RebekahZipp/GitHubCarpentries-Examples`. The common BUILD artifact is `build-example/books.md`.
4. **Collaboration is real, not simulated.** During class, Rebekah asks each learner for their **GitHub username only**, adds them as collaborators to the public example repository, and learners accept the invitation before the first push. No password, token, recovery code, or other authentication secret is requested or shared.
5. **Permission becomes a teaching moment.** Public repository access allows clone/read. A local clone allows local commits. Collaborator write access allows push to the shared GitHub repository.
6. **No Teams-dependent work.** Spoken prompts, helper conversations, terminal/GitHub evidence, and whole-room discussion carry the lesson.
7. **No Owner/Collaborator pair setup for the first BUILD.** The small class collaborates on one shared repository. The canonical Owner/Collaborator lesson is acknowledged as the source pattern, but the class mechanics are adapted.
8. **Pre-break checkpoint.** Learners have a GitHub account, have shared their username only, accepted collaborator access, cloned the repository, identified `origin`, found `build-example/books.md`, and have a clean working tree. No BUILD edit or learner push occurs before the break.
9. **Post-break collaboration rhythm.** **PULL -> CHANGE -> INSPECT -> ADD -> COMMIT -> REVIEW -> PUSH**. The reading list provides the meaningful shared change.
10. **Committed is not pushed.** Learners can make valid local commits independently. A push is a separate sharing operation.
11. **Rejected push is not synonymous with conflict.** A rejected push commonly indicates remote commits missing locally. Learners read the evidence and pull/integrate. A merge conflict is named only when Git cannot automatically reconcile overlapping changes.
12. **Conflict continuity.** `guacamole.md` remains the familiar Carpentries continuity object and can be used for a deliberate same-line conflict if reading-list changes integrate automatically.
13. **Helpers recover to the checkpoint.** Frances and Dani use **LOCATE -> OBSERVE -> ASK -> VERIFY -> HAND OFF**, help with GitHub invitation/account navigation when needed, never request credentials, and do not create alternate learner tracks.
14. **Repository context remains part of Git practice.** README, .gitignore, LICENSE, CITATION.cff, provenance, open/reusable work, and RStudio are taught as later repository decisions or alternate interfaces over the same Git states.
15. **Safety and recovery remain evidence-first.** Do not reflexively force push, reclone, delete, or run destructive recovery commands. Establish location and state first.

### Resulting workshop arc

```text
BEGINNING
orient -> clone -> inspect -> origin -> pull -> find books.md
-> live collaborator invitation -> BREAK

MIDDLE
pull -> edit books.md -> status -> diff -> add -> staged diff
-> commit -> log/show -> push -> read shared-state result
-> rejected push/integration -> controlled conflict when needed -> BREAK

END
history/recovery -> track/ignore/investigate -> README/provenance
-> LICENSE/CITATION/open work -> RStudio transfer -> explain-back
```

### Repository synchronization

The root README, whole-class cheat sheet, pedagogy rubric, instructor path, helper path, student path, student live lesson, and example-repository guidance were updated to use this shared vocabulary and workflow. The live instructor lesson remains the timing authority for Oct. 8.
