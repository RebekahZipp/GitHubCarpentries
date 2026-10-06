# GitHub Carpentries — Live Lesson Log and Teaching Script

This document is both a project log and a reusable instructor script.

It records not only successful commands, but also decisions, mistakes, recovery, and the concepts those moments exposed. That history is part of the teaching evidence.

## How to read this log

The learner workflow is:

**CHANGE → INSPECT → CHOOSE → RECORD → REVIEW → SHARE**

The instructor watches:

**ACTION → RESULT → CONCEPT → TEACHING MOMENT → RECOVERY**

The community of practice adds:

**PRACTICE → DOCUMENT → SHARE → QUESTION → REFLECT → REFINE → REUSE**

---

## Teaching Moment 1 — Start with a project

**Action:** Create the RStudio project `GitHubCarpentries`.

**Result:** The work has a defined local project location.

**Concept:** Project structure gives the work a boundary.

**Instructor line:** “Before we version anything, we need to know what the project is.”

---

## Teaching Moment 2 — Git can exist before GitHub

**Action:** Initialize and inspect the local Git repository before creating the repository on GitHub.

**Result:** Git reports a local `main` branch even though no GitHub repository exists yet.

**Concept:** Git and GitHub are related, but they are not the same thing.

**Instructor line:** “Git is already recording locally. GitHub has not entered the story yet.”

---

## Teaching Moment 3 — Use the correct console

**Action:** Git commands such as `git status` were initially entered in the R Console.

**Result:** R returned errors such as `unexpected symbol`.

**Concept:** R and the shell interpret different languages.

**Recovery:** Move Git commands to RStudio’s **Terminal** tab.

**Instructor line:** “The command was not necessarily wrong. We were speaking it to the wrong interpreter.”

---

## Teaching Moment 4 — Inspect before changing

**Action:** Run:

```bash
git status
```

**Result:** Git shows the current branch and untracked files.

**Concept:** `git status` is an inspection command. It answers: What does Git see right now?

**Instructor line:** “Before we tell Git to do something, ask Git what it sees.”

---

## Teaching Moment 5 — Build the README as part of the lesson

**Action:** Create and preview `README.md` in RStudio.

**Result:** The Markdown source renders as a readable HTML preview.

**Concept:** Source and rendered output are different representations of the same teaching content.

**Teaching decision:** Add `README.html` to `.gitignore`; the Markdown source is the versioned artifact we need.

---

## Teaching Moment 6 — `.gitignore` is a decision about the record

**Action:** Inspect the `.gitignore` created with the RStudio project and add:

```text
README.html
```

**Result:** Git stops presenting the rendered HTML as a file to track.

**Concept:** `.gitignore` defines what should remain outside the project history.

**Instructor line:** “Version control is not only deciding what to keep. It is also deciding what not to keep.”

---

## Teaching Moment 7 — Stage deliberately

**Action:** Add selected files rather than blindly adding everything.

```bash
git add README.md
git add .gitignore
```

Later:

```bash
git add student/README.md
git add instructor/README.md
```

**Result:** `git status` separates staged work from untracked work.

**Concept:** Staging is a choice about what belongs in the next recorded change.

**Instructor line:** “A working directory can contain more than the change I am ready to record.”

---

## Teaching Moment 8 — The first commit creates history

**Action:** Commit the initial teaching project.

```bash
git commit -m "Start GitHub Carpentries teaching project"
```

**Result:** Git creates the root commit.

**Concept:** A commit is a named point in project history, not merely a save button.

---

## Teaching Moment 9 — Errors are inspectable evidence

Two useful mistakes occurred while reading the history:

```bash
git log --online
```

and an earlier mistyped `git commit` command.

**Result:** Git reported the problem instead of silently doing something else.

**Recovery:** Read the error, inspect the command, and correct it:

```bash
git log --oneline
```

**Concept:** Error messages are part of the workflow.

**Instructor line:** “Recovery is not outside the lesson. Recovery is one of the skills we are learning.”

---

## Teaching Moment 10 — Separate student and instructor paths

**Action:** Create:

```text
student/README.md
instructor/README.md
```

**Result:** The same project now exposes two views of the learning process.

**Concept:** Students need the path through the work; instructors also need the reasoning, pacing, troubleshooting, and teaching decisions behind that path.

---

## Teaching Moment 11 — Record a coherent unit of work

**Action:** Stage and commit both learning paths together.

```bash
git add student/README.md
git add instructor/README.md
git status
git commit -m "Add student and instructor learning paths"
```

**Result:** One commit represents one meaningful development in the lesson.

**Concept:** Commit boundaries communicate reasoning.

---

## Teaching Moment 12 — GitHub enters the workflow

**Action:** Create an empty public `GitHubCarpentries` repository on GitHub without creating another README or `.gitignore` there.

**Result:** The local project and remote repository exist separately.

**Concept:** Creating a GitHub repository does not automatically connect an existing local Git repository to it.

---

## Teaching Moment 13 — A remote is an address

**Action:** Add and inspect `origin`.

```bash
git remote add origin https://github.com/RebekahZipp/GitHubCarpentries.git
git remote -v
```

An initial remote used the wrong repository path, producing `Repository not found` during push.

**Recovery:** Correct the remote address and inspect it again before pushing.

**Concept:** `origin` is a local name for the remote repository address. The name does not guarantee that the address is correct.

---

## Teaching Moment 14 — Push makes local history shared history

**Action:**

```bash
git push -u origin main
```

**Result:** The commits, README, student path, and instructor path become visible on GitHub. The local `main` branch is configured to track `origin/main`.

**Concept:** Commit and push are different actions. Commit records locally; push shares recorded history with the remote.

**Instructor line:** “Now we can see the same history from two places.”

---

## Teaching Moment 15 — The remote can change too

**Action:** Add peer-review documentation on GitHub so that instructor review can begin.

**Result:** GitHub now contains a commit that the local RStudio project does not yet have.

**Next recovery/action:** Before editing locally again, run:

```bash
git pull
```

**Concept:** Once collaboration begins, changes can originate somewhere other than your current machine.

**Instructor line:** “Someone changed the shared repository. Before I continue local work, I bring that history back to my machine.”

---

## Teaching Moment 16 — Review is not the same as surrendering authorship

**Decision:** Carpentries instructors are being invited primarily to provide rigorous peer review, insight, questions, and validation—not to rewrite the lesson.

Review should examine:

- pedagogical rigor;
- technical accuracy;
- novice accessibility;
- sequencing and pacing;
- hidden assumptions;
- troubleshooting and recovery;
- reproducibility and provenance;
- accessibility and inclusive teaching; and
- alignment with Carpentries practice.

**Concept:** GitHub collaboration can support deliberation before modification. Issues can hold review and reasoning; a Pull Request can follow when a specific change is discussed or invited.

---

## Teaching Moment 17 — Community of practice is part of the architecture

The project now has three connected rhythms.

### Student

**CHANGE → INSPECT → CHOOSE → RECORD → REVIEW → SHARE**

### Instructor

**ACTION → RESULT → CONCEPT → TEACHING MOMENT → RECOVERY**

### Community

**PRACTICE → DOCUMENT → SHARE → QUESTION → REFLECT → REFINE → REUSE**

The student learns the workflow.

The instructor makes the pedagogy visible.

The community examines and strengthens the practice.

**Instructor line:** “Git records changes. GitHub supports conversation around changes. A community of practice gives those conversations meaning.”

---

## Current review question

**Can another instructor understand, evaluate, and teach from these materials without reconstructing the reasoning that produced them?**

That question should remain visible as the lesson develops.

---

## Project-log principle

Do not clean the history until it stops looking like real work.

Mistyped commands, wrong consoles, an incorrect remote, inspection steps, and recovery decisions are not embarrassing debris. When documented carefully, they are evidence of how the workflow actually behaves and where learners need conceptual support.

The log therefore serves four purposes:

1. instructor script for the live lesson;
2. provenance for teaching decisions;
3. evidence of iterative lesson development; and
4. a record that can support later reflection on teaching and professional/CV documentation.


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
