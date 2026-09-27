# Reasoning, Feedback, and Intentional Mistakes — Lesson Update

## Why this update exists

Repetition was central to the instructor's own progression through Carpentries as a learner, helper, and then teacher. The workshop should reproduce that movement deliberately: learners first hear the reasoning, then recognize it, contribute to it, act with less scaffolding, and eventually help another person reason through the work.

This is not repetition for memorization. It is repetition that gradually transfers responsibility.

## Governing rhythms

### Normal work

**CHANGE → INSPECT → CHOOSE → RECORD → REVIEW → SHARE**

### Reasoning and recovery

**EXPECT → OBSERVE → EXPLAIN → TEST → ACT → VERIFY**

### Instructor case design

**WHY → WHAT → HOW → HANDOFF**

### Community practice

**PRACTICE → DOCUMENT → SHARE → QUESTION → REFLECT → REFINE → REUSE**

## Questions belong inside the action

Questions should not appear as separate discussion breaks. Build them into the technical work.

The instructor may ask and answer the question when the class is small or quiet. The point is to make reasoning audible while leaving an opening for the room.

Example:

> “What did I expect? I expected GitHub to accept the push. What happened? Git rejected it. So what do I need to know before I try another command?”

Pause briefly. If somebody contributes, use it. If not, continue the reasoning.

## Feedback belongs inside the action

Use short feedback loops during the work:

> “Was that enough explanation, or did I jump a step?”

> “Who noticed something I did not mention?”

> “Would somebody say that differently?”

> “Helpers, what are you seeing around the room?”

> “Has anybody solved this differently?”

The workshop itself should behave like a small community of practice: observations can move from learner to helper to instructor and back to the group.

## Mistakes become cases

Preserve the real mistakes that occurred while building the lesson and, when useful, reproduce safe versions intentionally during instruction.

The instructor should know the purpose of the mistake even when it appears organic to learners.

For every case record:

- **WHY:** why this situation is worth encountering;
- **WHAT:** the concept it exposes;
- **HOW:** how to inspect, recover, and verify; and
- **HANDOFF:** what learners should be able to do independently afterward.

Cases already available from the project include:

1. Git command entered in the R Console.
2. Working from the wrong directory.
3. Mistyped directory name.
4. `git log --online` instead of `git log --oneline`.
5. Incorrect remote address.
6. Wiki clone initially returning `Repository not found`.
7. Using `git ls-remote` to isolate access from cloning.
8. Push rejected because remote history changed.
9. Pasted terminal control characters becoming commands.
10. Generated and local files appearing as untracked.
11. Deciding whether a file should be tracked, ignored, or investigated.
12. Distinguishing a clone from a file or ZIP download.

## Performance note

The instructor can use humor and zest, but the learner is never the joke.

Useful tone:

> “Git is not being mysterious. Git is being extremely literal.”

> “Before I start throwing commands at it, what did I expect to happen?”

> “The computer says this place does not exist. Before we accuse the computer, let’s establish where we actually are.”

The performance makes uncertainty safe while keeping the investigation rigorous.

## End-state

The workshop succeeds when learners can do more than reproduce a command sequence. They should be able to inspect an unfamiliar repository, formulate a useful question, reason from Git's evidence, choose and verify an action, ask for help, contribute what they notice, and help another person without taking over the keyboard.

The repository they leave with should provide evidence of that practice.
