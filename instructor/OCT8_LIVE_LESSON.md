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
| 2:45-2:53 | Learner contribution | A class contribution in shared history |\n| **2:53-3:00** | **Break** | Clean shared checkpoint |
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

## 1:10 teaching cue: recover last week's work, not just the window

**SAY:** "Kevin showed us how to change our thing and see the change. First, we have to find our thing again. A reboot changes the window, not necessarily the project. There is a local copy on this computer and a shared copy on GitHub. Let's prove where we are before doing anything."

**ASK:** "Does opening Git Bash automatically open the project?" **EXPECTED:** No.

**DEMO + DO:** Follow the exact commands and expected evidence below. Pause after each pair. If the path is missing, use the safe clone fallback, not a guessed fix.

**TRANSITION:** "Now we know where the work lives and how to return to it. We can use Kevin's tools to make a change we can see."

## Return to our work after a reboot: two places, one project

**Why this is in the course:** Last week's files may still be on this computer, but opening Git Bash does not automatically put us inside them. GitHub keeps the shared repository; Git Bash operates in a folder on this computer. We find the local copy before deciding whether to clone. This is a reusable skill whenever we change computers, restart, or return to research.

**Two places to name aloud:**

- **LOCAL, on the Digital Scholarship Center Windows computer:** `C:\Users\Carpentries\GitHubCarpentries-Examples`. In Git Bash, Windows `C:\` is written `/c/`.
- **SHARED, on GitHub:** https://github.com/RebekahZipp/GitHubCarpentries-Examples . The local copy can be connected to this address through a remote called `origin`.
- **Teams:** course links, policies, slides, chat, and help. Teams is not where Git commits live.

**Start in Git Bash. Type one command, read its output, then continue.**

```bash
pwd
ls
```

**Expect:** `pwd` prints the current folder; `ls` lists what is in it. Neither command changes anything.

```bash
cd /c/Users/Carpentries
ls
```

**Expect:** a folder named `GitHubCarpentries-Examples`. If `cd` says **No such file or directory**, stop and inspect the path with File Explorer; do not guess or create a second repository.

```bash
cd GitHubCarpentries-Examples
pwd
git status
```

**Expect:** `pwd` ends in `/GitHubCarpentries-Examples`; `git status` reports a branch and any local changes. A modified file is not a failure; do not discard it.

```bash
git remote -v
```

**Expect:** `origin` with GitHub URL(s) for fetch and push. **This reads the saved connection; it does not contact GitHub.** If the URL differs, stop and check the repository before pushing.

**Only when `git status` shows a clean working tree:**

```bash
git pull origin main
git status
```

**Expect:** Git contacts GitHub and either reports `Already up to date.` or brings in newer work; status then shows the resulting state. A clean local tree does not guarantee a pull will succeed; authentication, connectivity, branch configuration, or divergent histories can require help. Do not reset, force-push, or delete anything to fix it.

**If the repository folder is truly absent:** use Teams **Links** to open the GitHub repository, choose **Code → HTTPS → Copy**; in Git Bash go to `/c/Users/Carpentries` (if it exists), type `git clone ` followed by the pasted HTTPS URL, then `cd GitHubCarpentries-Examples` and `git status`. **Clone only when absent.** If the parent folder is missing, ask the helper to establish the approved workspace location first.

**Read errors literally:**

| Evidence | What it means | Safe next move |
| --- | --- | --- |
| `not a git repository` | You are probably outside the project | `pwd`, `ls`, enter the repository |
| `No such file or directory` | That path/name is not present here | `pwd`, `ls`, check spelling/location |
| `modified: ...` | A file has uncommitted edits | Inspect `git diff`; do not overwrite |
| `Already up to date.` | Pull found no newer changes to integrate | Continue with the lesson |
| Authentication or permission denied | GitHub access is not established | Ask helper; never share passwords/tokens |
| `rejected` on push | Shared history may have moved or permission is missing | Read full error; do not force-push |

**Five commands, five questions:** `pwd` = Where am I? `ls` = What is here? `cd FOLDER` = Enter that folder. `git status` = What is my local Git state? `git remote -v` = Which shared address is saved? `git pull origin main` = What work can I receive from GitHub?

**Remember:** bare `cd` sends you home; `cd ..` moves up one folder; `cat FILE` reads a file. `COMMITTED != PUSHED`. A reboot != a reason to reclone.


## TODAY'S REAL RECOVERY LESSON: A WEB ADDRESS IS NOT A FOLDER

**SAY:** "We just experienced a common, useful mistake. I tried `cd https://...` to connect to GitHub. Git Bash could not do that because `cd` moves into folders **on this computer**. A GitHub URL is a web address, not a local folder. This is why we always ask what place we are in and what action we actually want."

**ASK:** "Am I trying to enter a folder I already have, download a repository I do not have, or contact GitHub from a repository I already have?"

| Intention | Use | Why |
| --- | --- | --- |
| Find my location | `pwd` | Shows my current local folder |
| See folders and files | `ls` | Shows what exists here |
| Enter a local folder | `cd FOLDER` | Changes local directory only |
| Get a repository not yet on this computer | `git clone HTTPS_URL` | Downloads files/history and sets up `origin` |
| See the saved GitHub connection | `git remote -v` | Displays the `origin` URL; does not contact GitHub |
| Contact GitHub for updates | `git pull origin main` | Fetches/integrates shared work |
| Share a local commit | `git push origin main` | Sends local commits, if authorized |

**DEMO + DO.** Start with the real Digital Scholarship Center path:

```bash
cd /c/Users/Carpentries
pwd
ls
```

**EXPECTED:** `pwd` says `/c/Users/Carpentries`. If `GitHubCarpentries-Examples` is listed, **do not clone again**:

```bash
cd GitHubCarpentries-Examples
git status
git remote -v
```

**EXPECTED:** `git status` names the branch; `git remote -v` displays `origin` pointing to `https://github.com/RebekahZipp/GitHubCarpentries-Examples.git` (or equivalent URL).

**ONLY IF THE FOLDER IS ABSENT:** Copy the HTTPS URL from GitHub **Code → HTTPS → Copy**, then type `git clone ` followed by the pasted address. For this workshop the complete command is:

```bash
git clone https://github.com/RebekahZipp/GitHubCarpentries-Examples.git
cd GitHubCarpentries-Examples
git status
```

**EXPECTED:** Clone creates the folder and retrieves the recorded history. It does not create a new empty project.

**IF THE COMPUTER REBOOTED:** Start with `pwd`, `ls`; a reboot alone is not a reason to clone. If `cd` alone sends you home, use the full path above. If `cat Carpentries` says **is a directory**, use `cd Carpentries` to enter it; `cat` is for reading files. If you accidentally type Git's printed output as a command, stop: output is evidence, not a new instruction.

**IF AN ERROR APPEARS:** Do not delete, reset, force-push, or keep guessing. Read the exact error, then check `pwd`, `ls`, `git status` as appropriate. Ask the helper to help locate the smallest correct state.

**SAY:** "The mistake is part of today's lesson because it reveals an important distinction: LOCAL FOLDER != GITHUB WEBSITE. A saved remote address != a live connection. COMMITTED != PUSHED. We can return to our work by checking evidence, not memorizing where we left off."

**TRANSITION:** "Now that we know how to find our project and recognize its GitHub address, we can return to Kevin's change-and-record cycle and make something happen."


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

# 3:45-3:55 | SAME GIT, ANOTHER WAY: RSTUDIO

**DEMO + DO**

**SAY**

> "We have done the work in Git Bash because the commands make the states visible. Many of us also work in RStudio. I want you to leave knowing this is not a second kind of Git."

Open this repository in RStudio and show the **Git** pane.

> "Look for the same things we have been reading all afternoon: changed files, staged files, commit, pull, push, and history."

Make one useful README addition:

```text
Workshop: OSU Libraries Git & GitHub, October 8, 2026
```

Save it.

**ASK**

> "What changed in the Git pane?"

Open the RStudio diff.

> "Where is our diff now?"

Stage the README.

> "What state did we just move into?"

Commit in RStudio:

```text
Record Oct 8 workshop
```

Push from RStudio.

Return to Git Bash:

```bash
git status
git log --oneline
```

**EXPECTED OUTPUT**

The working tree is clean and the RStudio-created commit appears at the top of the same history.

**ASK**

> "If I commit in RStudio and then open Git Bash, did I create two histories?"

Pause.

**SAY**

> "No. Different interface, same repository, same history, same lifecycle."

```text
CHANGE -> INSPECT -> CHOOSE -> RECORD -> REVIEW -> SHARE
```

**COMMON MISTAKE CUE**

> "The R Console is not the Terminal. A Git command typed at the R `>` prompt is being given to R. Use the Git pane or Terminal for Git work."

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
