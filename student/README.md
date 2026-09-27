# Student Path

## Learn Git by watching your work change

Git records changes to files.

GitHub gives those changes a place to be shared.

In this lesson, we learn the workflow by using it, talking through it, making ordinary mistakes, and checking the evidence together.

## Our working rhythm

**CHANGE → INSPECT → CHOOSE → RECORD → REVIEW → SHARE**

### CHANGE

Make a small change to the project.

### INSPECT

Ask Git what changed.

```bash
git status
```

Read the output before choosing another command.

### CHOOSE

Decide what belongs in the next recorded change.

```bash
git add FILE
```

### RECORD

Create a meaningful checkpoint.

```bash
git commit -m "MESSAGE"
```

### REVIEW

Read the history and inspect what was recorded.

```bash
git log --oneline
```

### SHARE

When the work is ready and appropriate to share, synchronize it with the remote repository.

## When something is unexpected

Use this reasoning rhythm:

**EXPECT → OBSERVE → EXPLAIN → TEST → ACT → VERIFY**

You may hear the instructor ask questions such as:

- Where am I?
- What did I expect?
- What actually happened?
- What does Git know right now?
- What do I need to know before acting?
- What could give me that evidence?
- Did the action do what I expected?

These are not quiz questions. Join in when you have an idea. If the room is quiet, listen to the instructor think through the same questions aloud.

The goal is to practice the questions until you can use them on your own.

## Mistakes are usable evidence

A wrong directory, mistyped command, rejected push, unexpected file, or wrong console does not end the workflow.

We will practice reading what happened before trying random fixes.

A useful sentence is:

> “I expected ___, but I observed ___. I think ___ may explain it. I can test that by ___.”

## Help is part of the practice

Technical work is collaborative. A useful question to a partner, helper, instructor, documentation source, or project community is a technical skill.

If you notice something the group has not mentioned, contribute it. If another person explains something differently, compare the explanation with the evidence.

By the end, you should be able to explain part of the workflow to somebody else without taking over their keyboard.

## What you leave with

The goal is not to remember every command.

The goal is to leave able to inspect an unfamiliar repository, understand what Git is telling you, make and verify a reasoned change, recover from ordinary problems, and continue developing a repository that can demonstrate your work.

Continue with [Clone → Investigate → Build](CLONE_INVESTIGATE_BUILD.md).
