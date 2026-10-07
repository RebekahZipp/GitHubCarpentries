# GitHub Carpentries: Oct. 8 Live Lesson

## From Local Git to Shared, Inspectable Work

**Time:** 1:00-4:00 PM  
**Instructor:** Rebekah Silverstein  
**Helpers:** Frances and Dani  
**Setting:** Digital Scholarship Center  
**Foundation:** Software Carpentry, *Version Control with Git*  
**TRY repository:** https://github.com/RebekahZipp/GitHubCarpentries-Examples

This is the **day-of teaching script**. Teach it top to bottom. Each phase uses the same structure so you can find the next move quickly.

> **Course refrain:** The commands may change. The reasoning should become familiar.

---

# Before class

## Instructor setup checklist

- [ ] Git is installed on the teaching computer.
- [ ] Git Bash or another terminal is open and readable on the projector.
- [ ] GitHub is signed in.
- [ ] TRY repository opens in the browser.
- [ ] TRY repository is cloned locally.
- [ ] `guacamole.md` is present.
- [ ] Student lesson and whole-class cheat sheet are open.
- [ ] RStudio is available for the transfer demo.
- [ ] `build-example/books.md` is present in the TRY repository on GitHub.
- [ ] Frances and Dani know the catch-up checkpoints and escalation rule.

## Accessibility and inclusion

- Give quiet think time before taking answers.
- Accept spoken responses and give learners time to think before whole-room correction.
- Treat mistakes as evidence about the work, never as evidence about a learner.
- Ask before touching another person's keyboard.
- Do not require public disclosure of errors, credentials, private repositories, or sensitive data.

## Activity labels

**DEMO + DO** = I model one small move; you make the same move with me.  
**TRY** = we pause after a move so you can inspect, predict, or repeat it in the safe class example.  
**BUILD** = we make meaningful local changes in each learner's clone of the class repository.  
**TALK** = we stop typing long enough to explain what the evidence means aloud.

**Default workshop rhythm:** **WATCH ONE MOVE -> DO THE MOVE -> STOP -> READ THE OUTPUT -> ASK WHAT IT MEANS -> CONTINUE.**

Do not demonstrate a long command sequence and then ask learners to reproduce it from memory. Commands are taught in small synchronized chunks.

## Standard prompts

Use these instead of inventing a new evidence question each time:

1. **What changed?**
2. **What state are we in?**
3. **What does Git say?**
4. **What should we do next?**
5. **How will we verify?**

## Instructor language bank

Use these when useful, not in every section.

> "Git is literal. It does exactly what we tell it, not what we mean."

> "The commands may change. The reasoning should become familiar."

> "Commit records here. Push shares there. Pull brings shared work here."

> "A conflict is Git refusing to invent human intent."

## State strip

Keep this visible:

**UNTRACKED/MODIFIED != STAGED != COMMITTED != PUSHED**

Normal work:

**CHANGE -> INSPECT -> CHOOSE -> RECORD -> REVIEW -> SHARE**

When surprised:

**EXPECT -> OBSERVE -> EXPLAIN -> TEST -> ACT -> VERIFY**

---

## Hands-on facilitation rule

The Carpentries lesson is taught by doing. Mirror that flow here.

For every technical sequence:

1. **SAY** what question the next move answers.
2. **ASK** learners to predict when useful.
3. **DEMO + DO** one command or one small command pair.
4. **STOP** typing.
5. **READ** the output together.
6. **ASK** what the output tells us.
7. **SAY** the conclusion and connect it to the next move.

The instructor and learners should usually be at the same checkpoint. Use helpers to recover learners to the current checkpoint rather than letting the class become two separate tracks.

# Run of show

| Time | Phase | Learner checkpoint |
| --- | --- | --- |
| 1:00-1:10 | Setup + Code of Conduct | Git/GitHub/terminal ready; knows how we work together |
| 1:10-1:20 | Re-enter Git | Can locate terminal, repo, state, history |
| 1:20-1:33 | Clone and inspect | TRY repo cloned and recognized as Git |
| 1:33-1:43 | Remote and origin | Can explain local vs remote and origin |
| 1:43-1:53 | From TRY to BUILD | Reading-list artifact located; clean local clone ready for first change |
| **1:53-2:00** | **Break** | |
| 2:00-2:18 | Collaboration cycle | One meaningful commit shared |
| 2:18-2:33 | Switch roles | Repeat with less instructor support |
| 2:33-2:53 | Rejection and conflict | Can distinguish rejection from conflict |
| **2:53-3:00** | **Break** | |
| 3:00-3:15 | History and recovery | Can inspect before restoring |
| 3:15-3:27 | Track/Ignore/Investigate | Can justify one file decision |
| 3:27-3:40 | Repository context | README improved for another reader |
| 3:40-3:50 | RStudio transfer | Recognizes same Git states in GUI |
| 3:50-4:00 | Explain-back | Can explain one decision and verification |

**If behind:** protect collaboration, conflict reasoning, both breaks, verification, and explain-back. Cut Pages first, then shorten RStudio.

---

# 1:00-1:10 | OPEN THE WORKSHOP AND CHECK OUR TOOLS

**TALK + DEMO + DO**

**SAY**

> "Welcome. Please open our Git & GitHub Workshop space in Teams and keep it open. This is our workshop front door. Notes, Slides, Links, and the Cheat Sheet are across the top. You can also put questions, observations, ideas, and non-sensitive error messages in the chat."

> "Today we are going to work the way Git works: make one move, stop, read the evidence, decide what it means, and then make the next move."

> "Our rhythm is CHANGE, INSPECT, CHOOSE, RECORD, REVIEW, SHARE. When something surprises us, we EXPECT, OBSERVE, EXPLAIN, TEST, ACT, and VERIFY."

> "One symbol before we begin: `!=` means is not equal to, or is not the same as. I will define it once. After this, we will use it as shorthand."

```text
!= = IS NOT THE SAME AS
```

> "This workshop follows the Carpentries Code of Conduct. We critique the work and the evidence, not the person. Ask before touching someone else's keyboard. Never put passwords, tokens, authentication codes, patron information, or sensitive research data into our chat or example repository."

**DEMO + DO**

```bash
git --version
```

**EXPECTED OUTPUT**

Something beginning with:

```text
git version ...
```

**ASK**

> "What did we just prove?"

Pause.

**SAY**

> "Git is installed on this computer. Git is local software. GitHub is the web service we will use to share Git work."

**COMMON MISTAKE CUE**

> "If your prompt begins with `>`, you may be in the R Console rather than a terminal. Git commands go in Git Bash or another terminal."

**TRANSITION**

> "Our tools are ready. Before Git can tell us anything useful, we need to know where we are."

---

# 1:10-1:20 | LOCATE -> OBSERVE

**DEMO + DO**

**SAY**

> "I am teaching from a shared Digital Scholarship Center computer. I am not going to assume it remembers where I worked. I am going to ask."

```bash
pwd
ls
```

**EXPECTED OUTPUT**

On the teaching computer, we expect to find the class work under:

```text
/c/Users/libpatron/Carpentries
```

and a directory named:

```text
GitHubCarpentries-Examples
```

**SAY**

> "`pwd` asks, Where am I? `ls` asks, What files and folders are here?"

**ASK**

> "Do we see `GitHubCarpentries-Examples`?"

If yes:

```bash
cd GitHubCarpentries-Examples
pwd
git status
```

**EXPECTED OUTPUT**

`pwd` ends with:

```text
/GitHubCarpentries-Examples
```

and `git status` identifies the branch and working-tree state.

**ASK**

> "What changed between being outside the repository and Git recognizing it?"

Pause.

**SAY**

> "Our location changed. The repository was already on the computer; we entered it."

**COMMON MISTAKE CUE**

> "If I type `cd` by itself, Git Bash sends me home. `cd FOLDER` enters a folder. `cd ..` goes up one folder. If Git suddenly says 'not a git repository,' I check `pwd` before I fix anything else."

**FALLBACK IF THE REPOSITORY IS ABSENT**

**SAY**

> "If the folder is not here, we do not have the local copy on this computer. We will make one from the shared GitHub repository."

Open **Teams -> Links -> GitHubCarpentries-Examples**, then on GitHub choose **Code -> HTTPS -> Copy**.

In Git Bash type `git clone ` with a space and paste the copied address.

```bash
git clone [PASTE HTTPS ADDRESS]
cd GitHubCarpentries-Examples
git status
```

**EXPECTED OUTPUT**

Git reports cloning/receiving objects, the new directory appears, and `git status` recognizes the repository.

**SAY**

> "Git knowing my name and email != this computer having my repository. Configuration is identity information. The repository carries the files and history."

**TRANSITION**

> "Now we are inside the repository. We can investigate what clone or our existing local copy actually contains."

---

# 1:20-1:33 | INVESTIGATE THE CLONE

**TRY + DEMO + DO**

**SAY**

> "Do not edit yet. Investigate first. We want evidence that this is more than a folder full of downloaded files."

```bash
git status
git log --oneline
ls
```

**EXPECTED OUTPUT**

- `git status` names the current branch and state.
- `git log --oneline` shows commits that existed before today's work.
- `ls` shows repository files including `guacamole.md` and `build-example`.

**ASK**

> "Did we create those older commits just now?"

Pause.

> "So what came with this repository besides the visible files?"

Pause.

**SAY**

> "The recorded history came with it."

**DO**

```bash
git rev-parse --show-toplevel
```

**EXPECTED OUTPUT**

The repository root ending in:

```text
GitHubCarpentries-Examples
```

**ASK**

> "What did `pwd` tell us earlier, and what did Git tell us now?"

**SAY**

> "`pwd` tells us where the shell is. Git tells us where this repository begins."

**COMMON MISTAKE CUE**

> "A folder name is not a command. `cat Carpentries` fails if Carpentries is a directory. `cd` enters directories; `cat` reads files."

**SAY**

> "We have proved that the repository contains files and recorded history. Next we are going to inspect its connection back to GitHub."

---

# 1:33-1:43 | REMOTE -> ORIGIN -> PULL

**DEMO + DO + TALK**

**SAY**

> "We have proved that clone brought history with it and a connection back to GitHub. Next we are going to inspect that relationship more closely."

> "Where did these files originate? Git tells us with `origin`."

```bash
git remote -v
```

**EXPECTED OUTPUT**

```text
origin  https://github.com/RebekahZipp/GitHubCarpentries-Examples.git (fetch)
origin  https://github.com/RebekahZipp/GitHubCarpentries-Examples.git (push)
```

**ASK**

> "What GitHub address do you see?"

Pause.

> "What short word appears beside it?"

Pause.

**SAY**

> "`origin` is a short name for the GitHub repository this copy came from. Fetch means get work from GitHub. Push means send recorded work to GitHub."

```text
MY COMPUTER  <---- origin ---->  GITHUB
```

**SAY**

> "Now I want to know whether GitHub has work my local copy does not have."

```bash
git status
```

**ASK**

> "If status says we are up to date with `origin/main`, did this command just contact GitHub?"

Pause.

**SAY**

> "No. Status reports what this local repository currently knows. To check the shared repository, we contact it."

```bash
git pull origin main
```

**EXPECTED OUTPUT**

Either new work arrives, or:

```text
Already up to date.
```

**ASK**

> "What did pull do that status did not?"

**SAY**

> "Pull contacted GitHub. Pull brings shared work here."

```text
COMMIT = record here
PUSH   = share there
PULL   = bring shared work here
```

> "Committed != pushed."

**COMMON MISTAKE CUE**

> "If Git prints a line beginning `From https://...`, that is Git talking to us. It is output, not another command. We read output; we do not paste it back into Bash."

**TRANSITION**

> "We know where the repository came from, what history it contains, and how shared work comes back to us. Now let's find the thing we are actually going to improve."

---

# 1:43-1:53 | FIND THE WORK -> READ BEFORE CHANGING

**BUILD + TALK**

```bash
ls
ls build-example
cat build-example/books.md
```

**EXPECTED OUTPUT**

We see `build-example/books.md` and its reading-list table.

**SAY**

> "Everything so far has been observation. Now read this as information, not as a Git exercise."

**ASK**

> "What does this table mean to you?"

Pause.

> "What is one small thing you would change that would mean something to you?"

Pause.

**SAY**

> "I notice something I actually want to fix. I read these existing dates as publication dates, but the heading says Date Finished. That tells me the structure is communicating something different from what I understood."

> "After the break, this becomes our work. I am going to change Date Finished to Publication Date and add a separate Date Finished field after Rating."

**EXPECTED CHANGE**

```text
BEFORE
Title | Author | Date Finished | Publisher | Rating | Notes

AFTER
Title | Author | Publication Date | Publisher | Rating | Date Finished | Notes
```

**ASK**

> "Before we change it, what state should we leave the repository in for break?"

```bash
git status
```

**EXPECTED OUTPUT**

A clean working tree.

**SAY**

> "Good. We know what we want to change, but we have not changed it yet. We are leaving a clean checkpoint."

---

# 1:53-2:00 | BREAK

**SAY**

> "Take seven minutes. When we come back, we are going to stop observing Git and use it to improve this project."

---

# 2:00-4:00 | BUILD ONE USEFUL REPOSITORY

By the end of class, we will have improved the shared reading-list repository, recorded why it changed, moved work between computers through GitHub, solved one collaboration problem, and left documentation another person can understand.

# 2:00-2:25 | FIX THE READING LIST

**SAY**

> "Before the break, we learned where this repository came from and how our local copy is connected to GitHub. Now we are going to use Git to do actual work. By the end of class, this repository should be better than when we opened it."

**DO TOGETHER**

```bash
pwd
git status
git pull origin main
cat build-example/books.md
```

**ASK**

> "What does this table mean to you as you read it?"

> "What is one small thing you would change that would mean something to you?"

Pause.

**SAY**

> "I noticed something I actually want to fix. I read these existing dates as publication dates, but the heading says Date Finished. That means the structure is telling me something different from what I understood."

> "I am going to change Date Finished to Publication Date. Then I am going to add a separate Date Finished field after Rating."

**CHANGE**

```text
BEFORE
Title | Author | Date Finished | Publisher | Rating | Notes

AFTER
Title | Author | Publication Date | Publisher | Rating | Date Finished | Notes
```

Edit `build-example/books.md`. Update the separator row and each existing row so the table has seven columns. Keep the existing dates under `Publication Date`. Leave `Date Finished` empty unless we actually know it.

Save the file.

**SAY**

> "I made a change. I am not going to record it yet. First I want Git to show me what I actually did."

**DO TOGETHER**

```bash
git status
git diff -- build-example/books.md
```

**ASK**

> "What changed?"

> "Does the diff show the change I intended?"

> "Did I change the values, the structure, the meaning, or more than one?"

**SAY**

> "Git can show me the difference. Git cannot decide what these fields mean. That decision is ours."

**DO**

```bash
git add build-example/books.md
git status
git diff --staged
```

**ASK**

> "What changed when I used `git add`?"

**SAY**

> "The change is staged. I have chosen it for the next commit. Staged != committed."

**DO**

```bash
git commit -m "Clarify publication and finished dates"
git log --oneline
git show HEAD
```

**ASK**

> "Where does that commit exist right now?"

Pause.

**SAY**

> "It is recorded here in my local repository. Committed != pushed."

> "If I want this change to become part of our shared GitHub repository, what do I need to do?"

**DO**

```bash
git push origin main
```

Open the GitHub repository and find the commit.

**ASK**

> "What evidence tells us the change is now on GitHub?"

**SAY**

> "We changed the meaning deliberately, inspected the evidence, recorded why, and shared the record."

---

# 2:25-2:45 | RECEIVE MY CHANGE

**SAY**

> "My change is on GitHub. It is not automatically in your local copy. Let's prove that by bringing it to you."

**DO TOGETHER**

```bash
git pull origin main
cat build-example/books.md
git log --oneline
```

**ASK**

> "Did you make my change?"

Pause.

> "Is it on your computer now?"

Pause.

> "Where do you see the change?"

> "Where do you see the record of the change?"

**SAY**

> "That is collaboration. I changed and committed something here. I pushed it to GitHub. You pulled it into your repository. The file and its recorded history traveled."

```text
MY COMPUTER             GITHUB             YOUR COMPUTER
change
commit
push -----------------> shared
                           |
                           +--------------> pull
                                            file + history
```

**ASK**

> "This repository is public. You were able to see it, clone it, and pull from it. Should everyone on the internet also be allowed to push changes into it?"

Pause.

**SAY**

> "No. Public means people can read and clone it. GitHub still controls who can contribute back."

> "For today's exercise, I have added you as collaborators. A collaborator is someone who has permission to contribute to this repository."

If anyone still needs access, handle the invitation now. Ask only for a GitHub username.

**SAY**

> "Being able to read a repository != having permission to change the shared repository."

---

# 2:45-3:05 | MAKE A CONTRIBUTION

**SAY**

> "Now you are going to improve the project. Do not make a disposable change just because I told you to type something. Make one small change you can explain."

> "You can add a book you have read, add a rating or useful note to your own entry, improve a field label, or improve one sentence in the README."

**DO TOGETHER BEFORE EDITING**

```bash
git pull origin main
git status
```

Make one change and save it.

**DO**

```bash
git status
git diff
```

**STOP.**

**TALK TO A PARTNER**

> "I changed ___ because ___."

**SAY**

> "If you cannot explain the change yet, do not commit it yet."

Stage the file you actually changed:

```bash
git add build-example/books.md
```

or:

```bash
git add build-example/README.md
```

Then:

```bash
git diff --staged
git status
```

**ASK**

> "Is this exactly what you want the next commit to remember?"

Write a short commit message that describes your actual change.

```bash
git commit -m "YOUR MESSAGE"
git log --oneline
```

**SAY**

> "Everyone has now made and recorded a meaningful contribution locally. We are going to send one contribution through the shared repository together so we can see the whole collaboration cycle."

Choose one ready learner.

**LEARNER DOES**

```bash
git pull origin main
git push origin main
```

**EVERYONE ELSE DOES**

```bash
git pull origin main
```

Open `build-example/books.md` or `build-example/README.md`.

**ASK THE CONTRIBUTOR**

> "What did you change and why?"

**ASK THE ROOM**

> "Who can find that change on their own computer?"

> "Who can find its commit in the history?"

**SAY**

> "That contribution started on one person's computer and is now part of our shared project."

---

# 3:05-3:25 | WHAT HAPPENS WHEN GITHUB MOVES FIRST?

**SAY**

> "So far our collaboration has been orderly: pull, work, commit, push. Real shared work is not always that tidy."

> "I am going to show you a situation you will eventually see. Do not fix anything yet. Your job is to read what Git tells us."

Use two prepared clones, or work with a helper. Both begin from the same shared history.

In the first copy, make a small change, commit it, and push it.

In the second copy, without pulling that new commit, make a different small change and commit it.

**ASK BEFORE PUSHING THE SECOND COPY**

> "GitHub now has work that this copy does not have. What do you predict will happen if I try to push?"

**DO**

```bash
git push origin main
```

**STOP. READ THE MESSAGE.**

**ASK**

> "Did Git say my local work disappeared?"

> "Did Git say merge conflict?"

> "What is Git refusing to do?"

**SAY**

> "Git is refusing to let this copy overwrite shared history it does not have."

> "This is a rejected push. Rejected push != merge conflict."

**ASK**

> "What does this copy need before it can safely share its work?"

**DO**

```bash
git pull origin main
```

If the two changes are on different lines, let Git combine them.

Then:

```bash
git status
git log --oneline
```

**ASK**

> "What did pull bring into this copy?"

> "Do we still have our local commit?"

If the history is integrated:

```bash
git push origin main
```

**SAY**

> "The rejection was useful evidence. It told us the shared history had moved and we needed to receive that work before sharing ours."

---

# 3:25-3:40 | WHEN GIT CANNOT DECIDE

**SAY**

> "The last example could be combined because the changes did not require us to choose between two meanings. Now we are going to make Git face a decision it cannot make for us."

Open `guacamole.md`.

Use two copies to change the same line differently. Commit both changes. Push the first change. In the second copy, pull.

**STOP when the conflict appears.**

Open the file and read:

```text
<<<<<<< HEAD
local version
=======
incoming version
>>>>>>> commit
```

**ASK**

> "What is Git showing us?"

> "Which version is ours?"

> "Which version came from the other history?"

> "Can Git decide which guacamole we intended?"

**SAY**

> "No. Git can preserve both pieces of evidence. A person has to decide the final meaning."

Ask the room what the final wording should be. Edit the file to that decision and remove the conflict markers.

**DO**

```bash
git status
git add guacamole.md
git status
git commit -m "Resolve guacamole wording"
git push origin main
```

**ASK**

> "What did `git add` mean this time?"

Guide toward: we are telling Git that we resolved the file.

**SAY**

> "Conflict != failure. A conflict is Git refusing to invent human intent."

---

# 3:40-3:52 | EXPLAIN THE PROJECT TO SOMEONE WHO WAS NOT HERE

**SAY**

> "We have changed the data, shared contributions, and made decisions about competing changes. But right now we know more about this project than the files may tell the next person."

> "Imagine someone finds this repository six months from now. None of us are standing beside them. What would they need to know?"

**DO**

```bash
cat build-example/README.md
```

**ASK**

> "Does this README explain what Publication Date means?"

> "Does it explain what Date Finished means?"

> "Does it tell someone how to add another entry?"

As a class, improve the README so it explains the reading list and the fields we changed today.

Save it.

**DO TOGETHER**

```bash
git status
git diff
git add build-example/README.md
git diff --staged
git commit -m "Document reading list fields and workflow"
git push origin main
```

**SAY**

> "The table holds information. The README helps another person interpret that information."

Point briefly to `LICENSE` and `CITATION.cff`.

**ASK**

> "If something is visible on GitHub, does that automatically tell us how we may reuse it?"

> "Does visibility automatically tell us how to credit the people who made it?"

**SAY**

> "No. That is why research repositories also need reuse and citation information. Git history tells us how the project changed. Documentation, licensing, and citation tell other people how to understand, reuse, and credit it."

---

# 3:52-4:00 | READ WHAT WE BUILT

**SAY**

> "We are not going to end by adding another command. We are going to read the thing we built."

**DO TOGETHER**

```bash
git pull origin main
git status
git log --oneline
cat build-example/books.md
cat build-example/README.md
```

Open the GitHub repository.

**ASK**

> "Show me one change we made today."

> "Show me where Git recorded why a change happened."

> "Show me evidence that somebody else's work reached your computer."

> "Show me where we documented what our fields mean."

> "What is the difference between commit and push?"

> "What is the difference between a rejected push and a conflict?"

**SAY**

> "At the beginning, we had a repository somebody else had prepared. Now we have a shared project that we actually changed."

> "We read the information. We noticed a meaning problem. We changed it. We inspected the change. We recorded why. We shared it. We received somebody else's work. We solved a collaboration problem. And we documented enough of the project for another person to understand it."

> "Git records change. People decide what the change means."

> "The commands may change. The reasoning should become familiar."

---

