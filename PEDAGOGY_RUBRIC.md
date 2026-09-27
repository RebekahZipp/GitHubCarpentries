# GitHub Carpentries Teaching Rubric

## The practice we are teaching

This workshop teaches more than commands. It teaches learners how to inspect a technical situation, make their reasoning visible, act deliberately, verify the result, and contribute what they learn back to a community.

The lesson therefore repeats two connected rhythms.

### Working rhythm

**CHANGE → INSPECT → CHOOSE → RECORD → REVIEW → SHARE**

### Reasoning and recovery rhythm

**EXPECT → OBSERVE → EXPLAIN → TEST → ACT → VERIFY**

The commands may change. The reasoning should become familiar.

## Prompts are invitations, not quizzes

Questions in this lesson serve two purposes at once:

1. they invite learners and helpers into the reasoning; and
2. they prompt the instructor to think aloud when the room is quiet.

Pause briefly after a prompt. Accept a contribution if one comes. If nobody answers, continue naturally by modeling the reasoning.

Do not turn a small or quiet class into an interrogation.

Example:

> “What did I expect to happen here? I expected GitHub to accept the push. What actually happened? Git rejected it. So before I try another command, what do I need to know?”

If a learner answers, use the contribution. If not, keep thinking aloud.

## The recurring questions

Work these into the lesson until they become habits rather than a checklist.

- **Where am I?** What directory, repository, branch, console, or remote am I working in?
- **What did I expect?** What did I think this action would do?
- **What actually happened?** What does the screen or Git output say?
- **What changed?** What evidence does Git have?
- **What do I need to know next?** What uncertainty must I resolve before acting?
- **What can tell me that?** Which command, file, history, documentation, helper, or collaborator provides evidence?
- **What should we do next?** What action follows from the evidence?
- **Did it work?** How will we verify the result?
- **Who knows something we do not?** What can another learner, helper, instructor, documentation source, or community contribution add?

## Mistakes are teaching cases

Safe mistakes may be planned by the instructor but should feel like ordinary work rather than staged failure.

Do not perform incompetence. Perform **realistic uncertainty and recovery**.

For each mistake, document:

### WHY
Why is this mistake useful to learners?

### WHAT
What conceptual distinction does it expose?

### HOW
How will the instructor notice, investigate, recover, and verify?

### HANDOFF
What should learners be able to explain or do afterward without the instructor?

Examples already produced while building this lesson include:

| Moment | Concept it exposes |
|---|---|
| Git command entered in the R Console | Commands execute in a context; R and the shell speak different languages. |
| Wrong directory or mistyped directory | Location is state; inspect before assuming a larger problem. |
| `git log --online` instead of `--oneline` | Git is literal; error messages are evidence. |
| Incorrect remote URL | A remote is an address and should be verified. |
| Wiki clone initially fails | Isolate a problem with a smaller diagnostic instead of repeating a failed action. |
| Push is rejected | Local and remote histories can differ; synchronize deliberately rather than forcing. |
| Untracked/generated files appear | Git notices files; humans decide what belongs in the record. |
| Staging is skipped | A changed file is not automatically part of the next recorded change. |

## Instructor performance

Use some zest, but keep the humor attached to reasoning.

Useful lines include:

> “Git is not being mysterious. Git is being extremely literal.”

> “Before I start throwing commands at it, what did I expect to happen?”

> “The computer says this place does not exist. Before we accuse the computer, let’s establish where we actually are.”

> “Git has noticed the file. Git does not know whether it belongs in our scholarly record. That decision is ours.”

The performance should reduce anxiety and expose thought processes. It should never make a learner the joke.

## Feedback is part of the technical workflow

Do not reserve feedback for the end-of-workshop survey.

Use small feedback openings throughout:

- “Was that enough explanation, or did I jump a step?”
- “Who noticed something I did not mention?”
- “Would somebody say that in different words?”
- “What question would you ask tomorrow if an instructor were not here?”
- “Helpers, what are you seeing around the room?”
- “Has anybody solved this differently?”

When a learner or helper offers a useful alternative, test it against the evidence when practical. The contribution should be able to change the conversation.

## Helpers are knowledge conduits

Helpers are not only emergency technical support.

Invite them to surface patterns:

> “What question are you hearing more than once?”

> “What did somebody at your table notice that the rest of us should know?”

This makes knowledge produced around the room available to the whole group.

## Repetition removes scaffolding

The workshop intentionally repeats the workflow while transferring responsibility.

1. **Instructor models** the reasoning aloud.
2. **Learners participate** in the reasoning.
3. **Learners supply** parts of the reasoning.
4. **Learners act** with less prompting.
5. **Learners explain** the workflow to another person.

The same command can deepen over time. Early `git status` means “What changed?” Later it means “What state am I in?” Later still it means “Before I act, what does Git currently believe?”

## Community-of-practice outcome

Knowing how to formulate a useful question, explain what you observe, ask another person for help, test a suggestion, and contribute the result is part of technical practice.

The workshop should end with learners able to say:

> “I can inspect an unfamiliar repository, understand what Git is telling me, make a reasoned change, document why I made it, recover when something goes wrong, and help another person reason through the work.”

The repository they leave with is evidence of that practice, not merely evidence that they typed commands.

## Instructor review check

For every major episode, ask:

- Is the **why** explicit?
- Is the **what** visible in evidence?
- Is the **how** demonstrated?
- Is there room for learner/helper reasoning without requiring participation?
- Is there a verification step?
- Does repetition deepen understanding rather than merely repeat keystrokes?
- Does the episode transfer some responsibility to the learner?
- Can another instructor understand why this teaching choice exists?
