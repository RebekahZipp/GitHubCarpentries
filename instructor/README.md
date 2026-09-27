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

## Instructor principle

Do not rescue every error immediately.

When an error is safe and instructive, make the thinking visible:

> “I expected X. I observed Y. Before changing anything, what evidence would help me distinguish the possible explanations?”

Then investigate.

The lesson is not: **experts type commands without mistakes.**

The lesson is: **we can inspect the state of our work, reason from evidence, ask for help, make the next decision deliberately, and share what we learn.**
