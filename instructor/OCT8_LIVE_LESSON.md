# GitHub Carpentries: Oct. 8 Live Lesson

## From Local Git to Shared, Inspectable Work

**Time:** 1:00-4:00 PM  
**Instructor:** Rebekah Silverstein  
**Helpers:** Frances and Dani  
**Setting:** Digital Scholarship Center  
**Foundation:** Software Carpentry, *Version Control with Git*  
**TRY repository:** https://github.com/RebekahZipp/GitHubCarpentries-Examples

This is the **day-of teaching script and instructor safety net**. Teach it top to bottom. You should not need another document or a live assistant to know what to say, what to type, what output to expect, or how to recover from the common mistake at that point.

The class builds one lasting artifact: a small shared **book-list repository** with understandable fields, contributions, documentation, and history. We recover Kevin's local Git lifecycle, extend it through GitHub collaboration, archive the work, ask the workshop for advice, and finish by showing the same Git lifecycle in RStudio.

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
- [ ] GitHub collaborator invitations are ready or learner GitHub usernames can be collected.
- [ ] Teams workshop chat is open for questions and end-of-class advice.
- [ ] A second clean clone is available for the controlled rejected-push/conflict demonstration.
- [ ] The final class repository will remain on GitHub as the archived workshop artifact.

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

| Time | We do | We leave behind |
| --- | --- | --- |
| 1:00-1:10 | Open Teams, policies, tools | Room ready and shared working rules |
| 1:10-1:20 | Find last week's work | Everyone back inside the repository |
| 1:20-1:33 | Recap Kevin by changing guacamole | A new local commit |
| 1:33-1:43 | Find origin and contact GitHub | Local/remote relationship understood |
| 1:43-1:53 | Find and read the book list | A real data decision waiting for us |
| **1:53-2:00** | **Break** | Clean checkpoint |
| 2:00-2:25 | Fix book-list meaning | Better schema + shared commit |
| 2:25-2:45 | Pull the instructor change | Everyone receives file + history |
| 2:45-2:53 | Learner contribution | One meaningful local commit; push if access is ready |
| **2:53-3:00** | **Break** | Clean shared checkpoint |
| 3:00-3:18 | Read a rejected push | Collaboration problem understood |
| 3:18-3:33 | Resolve one conflict | Human decision recorded |
| 3:33-3:45 | Document + archive | README + lasting GitHub record |
| 3:45-3:55 | Same Git in RStudio | Another practical workflow |
| 3:55-4:00 | Advice + takeaway | Sweet book list + next questions |

**If behind:** protect the guacamole recap, meaningful book-list change, push/pull, one learner contribution, README/archive, RStudio transfer, and closing advice. Demonstrate rather than reproduce the conflict if time is tight.

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

## 1:10 instructor recovery cue: make the distinction visible

**SAY:** "A reboot changes our window, not necessarily our project. Git Bash starts in a local folder. GitHub is the shared website. We must decide whether to enter an existing folder or clone a missing repository."

**ASK:** "Does `cd https://github.com/...` open GitHub?" **EXPECTED:** No. `cd` enters a local folder, never a web address.

**DEMO + DO:** Type each line, pause, and read the evidence:

```bash
pwd
ls
cd /c/Users/Carpentries
pwd
ls
```

**EXPECTED:** The local folder is `/c/Users/Carpentries`. **IF** `GitHubCarpentries-Examples` is listed, continue:

```bash
cd GitHubCarpentries-Examples
git status
git remote -v
```

**EXPECTED:** Git reports a branch and `origin` identifies the GitHub repository. `git remote -v` only reads the saved address; it does not contact GitHub.

**IF THE FOLDER IS MISSING:** Return to `/c/Users/Carpentries` and run:

```bash
git clone https://github.com/RebekahZipp/GitHubCarpentries-Examples.git
cd GitHubCarpentries-Examples
git status
```

**COMMON MISTAKE / RECOVER:** `cd https://...` fails because the URL is not a folder. Bare `cd` returns home; `cat Carpentries` fails because `cat` reads files, not directories. Use `pwd` and `ls` before changing anything. Never delete or reclone over existing work.

**VERIFY:** `git status` shows a branch and `git remote -v` shows the expected remote. If files are modified, inspect them rather than resetting. Only pull when local changes are understood and the integration is safe.

**SAY / TRANSITION:** "LOCAL FOLDER != GITHUB WEBSITE. COMMITTED != PUSHED. Now we can return to Kevin's change-and-record cycle."

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
/c/Users/Carpentries
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
git clone https://github.com/RebekahZipp/GitHubCarpentries-Examples.git
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

# 1:20-1:33 | RECAP KEVIN'S LESSON -> USE THE TOOLS

**TALK + TRY + BUILD**

**SAY**

> "We found our work, we have reviewed how we are going to work together, and we are all at the same starting point. Before we add GitHub collaboration, I want to reconnect us to what Kevin gave us in the first lesson."

> "Last time, we learned how to make something happen in a project and then use Git to see and record that change."

**DO TOGETHER**

```bash
git status
git log --oneline
ls
```

**EXPECTED OUTPUT**

Git shows our current state and existing history. The file list includes `guacamole.md`.

**ASK**

> "What do you remember doing with Git last time?"

Take answers from the room.

**SAY**

> "The important part was not memorizing a list of commands. We learned a working cycle."

```text
MAKE A CHANGE
      ↓
SEE THE CHANGE
      ↓
CHOOSE THE CHANGE
      ↓
RECORD THE CHANGE
      ↓
LOOK BACK AT THE RECORD
```

> "In Git, that looked like edit, `status` and `diff`, `add`, `commit`, and then `log` or `show`."

> "Kevin's lesson gave us the tools to change our thing and see what happened. Today we are going to use those same tools and make the record travel between people."

**ASK**

> "Before we make it travel, should we prove we can still use that cycle?"

Pause.

**SAY**

> "Let's find something familiar."

```bash
cat guacamole.md
```

**EXPECTED OUTPUT**

The guacamole recipe prints in the terminal.

**ASK**

> "There it is. What is one thing we could add to our recipe?"

Use a real suggestion from the room.

**SAY**

> "Perfect. Let's make something happen."

Open `guacamole.md`, add the class suggestion, and save.

```bash
git status
```

**EXPECTED OUTPUT**

```text
modified: guacamole.md
```

**ASK**

> "What does Git notice?"

**SAY**

> "The file changed. Modified != recorded. We made something happen; now we inspect it."

```bash
git diff -- guacamole.md
```

**EXPECTED OUTPUT**

The class addition appears in the diff with `+`.

**ASK**

> "Can you find what we added?"

> "Is that the change we intended?"

**SAY**

> "Yes. We changed our thing and used Git to see the change. Now we choose what the next commit will remember."

```bash
git add guacamole.md
git status
git diff --staged
```

**EXPECTED OUTPUT**

`guacamole.md` appears under **Changes to be committed**, and the staged diff shows the class addition.

**ASK**

> "Did the recipe change again when we used `git add`?"

**SAY**

> "No. Its Git state changed. We chose this change for the next record."

```bash
git commit -m "Add class suggestion to guacamole recipe"
git log --oneline
git show HEAD
```

**EXPECTED OUTPUT**

A new commit appears at the top of the history, and `git show HEAD` displays the change we just recorded.

**ASK**

> "Can you see the whole cycle we used last time?"

**SAY**

> "Change. Inspect. Choose. Record. Review. That is where Kevin's lesson leaves us."

```text
CHANGE -> INSPECT -> CHOOSE -> RECORD -> REVIEW
```

> "And that gives us today's question: this commit is here on my computer. How do I get this work to you?"

**TRANSITION**

> "We are not starting over with Git. We are extending the lifecycle. Kevin gave us local change and local history. Today we add SHARE, RECEIVE, COLLABORATE, and EXPLAIN."

```text
CHANGE -> INSPECT -> CHOOSE -> RECORD -> REVIEW
                                      ↓
                                SHARE -> RECEIVE
```

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

# 2:45-2:53 | MAKE A CONTRIBUTION

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

# 2:53-3:00 | BREAK

**SAY**

> "Take seven minutes. Leave your repository where it is. When we come back, we are going to deliberately make collaboration messy and learn how to read what Git tells us."

---

# 3:00-3:18 | WHAT HAPPENS WHEN GITHUB MOVES FIRST?

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

# 3:18-3:33 | WHEN GIT CANNOT DECIDE

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

# 3:33-3:45 | DOCUMENT -> SHARE -> ARCHIVE

**BUILD + TALK**

**SAY**

> "We have changed the data, shared contributions, and made decisions about competing changes. Before we leave it, we need to make the project understandable to somebody who was not in this room."

```bash
cat build-example/README.md
```

**ASK**

> "Does this explain what Publication Date means?"

> "Does it explain what Date Finished means?"

> "Could someone who missed today's workshop add the next book correctly?"

Use the answers to improve `build-example/README.md`. Keep it short and useful. Save it.

**DO TOGETHER**

```bash
git status
git diff
git add build-example/README.md
git diff --staged
git commit -m "Document reading list fields and workflow"
git push origin main
```

**EXPECTED OUTPUT**

A new README commit is created and pushed to the shared GitHub repository.

**SAY**

> "The table holds information. The README preserves enough context for another person to interpret and continue the work."

Point to `LICENSE` and `CITATION.cff`.

**ASK**

> "Does being visible on GitHub automatically tell somebody how they may reuse the work?"

> "Does visibility automatically tell them how to credit it?"

**SAY**

> "No. Git history, documentation, licensing, and citation answer different parts of the reuse question."

Open the GitHub repository.

> "This is also how we archive today's work. We are not ending with a worksheet that disappears after class. The example, its README, and the history of how we built it stay together in the workshop repository."

**VERIFY**

```bash
git pull origin main
git status
git log --oneline
cat build-example/books.md
```

**EXPECTED OUTPUT**

The local repository is current, the working tree is clean, the class commits appear in history, and the final book list contains today's work.

**COMMON MISTAKE CUE**

> "A successful push is not the same thing as understanding what we archived. We verify the file, the history, and the documentation."

---

# 3:45-3:55 | SAME GIT, THREE RSTUDIO WORKSPACES

**PURPOSE:** Learners should distinguish the R Console, Terminal, and Git pane, and understand that RStudio uses the *same local repository* as Git Bash.

**SAY:** "RStudio is a place to write and run R code, manage project files, and work with Git and GitHub. We have not created a new Git history by opening the same folder here. We have changed interfaces."

**DEMO + DO: OPEN THE EXISTING PROJECT.** In RStudio choose **File → New Project → Existing Directory**. Browse to `C:\Users\Carpentries\GitHubCarpentries-Examples` and create/open the project. If a project file already exists, open that instead. **STOP:** In the Files pane, find `README.md`, `guacamole.md`, and `build-example`. **ASK:** "Did we clone a second copy?" **EXPECTED:** No, this is the same local folder. If `.Rproj` appears as an untracked file, do not stage it automatically.

**THREE WORKSPACES, THREE JOBS**

| RStudio place | What it is for | What to type or click | Expected evidence |
| --- | --- | --- | --- |
| **Console** with `>` prompt | Execute R expressions, analysis, and scripts | `getwd()`, `list.files()`, `readLines("README.md", n = 5)` | R prints the current working directory, file names, or README text |
| **Terminal** with a shell prompt such as `$` | Execute shell commands, including Git | `pwd`, `git status`, `git log --oneline -3` | Shell path, Git branch/status, and commit history |
| **Git pane** | Inspect and operate Git through buttons | View changes; Diff; Stage; Commit; Pull; Push; History | Same repository states as Git Bash |

**SAY:** "The Console speaks R. The Terminal speaks shell commands. The Git pane gives us buttons for Git. GitHub is the remote repository that Git can contact. None of these is the same thing."

**ASK / PREDICT:** "What happens if I type `git status` at the R `>` prompt?" **EXPECTED:** R will not run it as a Git command. **RECOVER:** Do not type Git commands directly at the R prompt; switch to the Terminal or Git pane.

**DEMO + DO IN THE CONSOLE** (enter separately at the `>` prompt):

```r
getwd()
list.files()
readLines("README.md", n = 5)
```

**STOP / INTERPRET:** `getwd()` shows the current R working directory; `list.files()` lists files; `readLines()` reads the README. These are R commands, not Git operations. If the README is not found, inspect `getwd()` and the Files pane before changing directories.

**DEMO + DO IN THE TERMINAL** (open **Tools → Terminal → New Terminal**, if available):

```bash
pwd
git status
git log --oneline -3
```

**STOP / INTERPRET:** These are shell/Git commands. The Terminal may use a different shell from Git Bash; check the prompt and directory. If Git reports `not a git repository`, navigate to the existing clone instead of recloning.

**DEMO + DO IN THE GIT PANE:** Open `README.md` and add a short, useful line:

```text
Workshop: OSU Libraries Git & GitHub, October 8, 2026
```

Save. **ASK:** "What changed?" **EXPECTED:** `README.md` appears modified. Select it and click **Diff** to inspect the line. Stage only `README.md`; check staged content. Click **Commit** and enter `Record Oct 8 workshop`. Verify the new commit in **History**. **If permission and remote state allow**, click **Push**. If the push is rejected, stop and inspect; do not force-push.

**VERIFY IN GIT BASH OR RSTUDIO TERMINAL:**

```bash
git status
git log --oneline -3
```

**EXPECTED:** The RStudio commit appears in the same local history. The working tree may contain an untracked `.Rproj` or other files; do not promise a clean tree until these are inspected. A local commit does not prove it was pushed; check the remote response or GitHub history separately.

**ASK:** "If I commit in RStudio and inspect in Git Bash, did I create two histories?" **EXPECTED:** No. Same repository, same commits, different interfaces.

**COMMON MISTAKES:** Opening the wrong folder, using `git status` in the R Console, assuming `getwd()` is always the repository root, staging an unintended `.Rproj`, and mistaking a local commit for a GitHub push. Recover by identifying the interface, locating the project, inspecting Git status, and choosing the next safe action.

**TIME GATE:** Ten minutes is enough for the interface comparison and an instructor-led demonstration, but not a guaranteed independent learner push. If running behind, demonstrate the Console, Terminal, and Git pane and let learners complete the README commit afterward.

**TRANSITION:** "We can do our analysis in R, inspect our files in RStudio, and use Git to record and share the work. The tools are connected by the same project, not by magic."

---

# 3:55-4:00 | READ OUR BOOK LIST -> ASK THE WORKSHOP -> TAKE IT WITH YOU

**TALK + VERIFY**

**SAY**

> "We are going to end with the thing we made, not another command."

Open `build-example/books.md` and the GitHub repository.

> "This is our book list. It started as an example. We clarified what its data means, added to it, moved those changes between people, handled competing work, documented it, and archived the history."

**ASK**

> "Show me one change we made today."

> "Show me where Git recorded why it happened."

> "Show me evidence that somebody else's work reached your computer."

> "Show me where another person can learn what these fields mean."

**SAY**

> "Kevin gave us the tools to make a change and see the change. Today we made that record travel."

```text
CHANGE -> INSPECT -> CHOOSE -> RECORD -> REVIEW
                                      |
                                      v
                              SHARE -> RECEIVE
                                      |
                                      v
                         COLLABORATE -> EXPLAIN
                                      |
                                      v
                              ARCHIVE -> REUSE
```

> "Before we go, I want one piece of advice from you for this workshop. What should we keep, change, explain better, or practice more next time? You can say it aloud or leave it in the Teams workshop chat."

Give them a moment.

> "And leave one question or one thing you want to try next. That becomes part of the workshop record too."

**TAKEAWAY**

> "You leave with a sweet little book list you helped build, a GitHub repository you can return to, and another way to do the same Git work from RStudio."

> "Git records change. People decide what the change means."

> "The commands may change. The reasoning should become familiar."

---
