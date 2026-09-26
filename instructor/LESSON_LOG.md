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
