# Live Lesson Log and Instructor Script

## Purpose

This log documents both what we build and why we teach it this way. The repository is the lesson, the teaching record, and evidence of a developing community of practice.

## Memorable lesson arc

Students should leave with more than commands. They should be able to recognize a Git repository as a research and professional object, investigate where it came from, make an intentional change, record that change, and share work they can continue developing as portfolio evidence.

### Two ways into Git

**LOCAL → Git → GitHub**

A student already has work and decides to record and share it.

**GitHub → CLONE → LOCAL**

A project already exists and the student creates a connected local working copy.

After either entry point, use the same rhythm:

**CHANGE → INSPECT → CHOOSE → RECORD → REVIEW → SHARE**

## Teaching Moment — Clone is not Download

A downloaded file is a file. A ZIP is a snapshot of files. A clone is a local Git repository with project files, history, branches, and a remembered remote.

Ask students to investigate before changing anything:

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

Then open History/Diff in GitHub Desktop and ask: **I was not there when this change happened. What can I know anyway? What can Git not tell me?**

This introduces provenance, documentation, commit messages, review, and the limits of the record.

## Land-grant artifact investigation

Use authentic public research/teaching repositories when their license and size make them appropriate. Prefer artifacts that let learners recognize land-grant work as data, documentation, teaching, agriculture, environment, or public scholarship rather than only software.

Candidate stations:

1. **OSU Carpentries workshop repository** — inspect a real Oklahoma State workshop repository already visible to instructors. Look at `index.md`, `_config.yml`, history, authorship, and the `gh-pages` branch. Use for provenance and collaborative teaching infrastructure.
2. **NEONForestAGB** — public forest biomass research whose authors include an Oklahoma State University researcher and USDA/NEON collaborators. Its repository documents a data workflow and includes taxonomy/source-data context and R scripts. Use only after checking current size/license and choosing a small, safe path for learners.
3. **Land-Grab Universities source data** — a public CC0 dataset containing CSV, spreadsheet, shapefile, and documentation artifacts about land-grant university history. This is useful for showing that repositories can contain research data and documentation, not merely code. Instructor must frame the subject historically and respectfully and avoid making it the first technical exercise.
4. **The Carpentries workshop template** — useful for demonstrating a real community-maintained repository, but follow its own guidance: create from the template rather than asking learners to fork it directly.

## Mystery repository exercise

Do not explain the repository first. Give learners a small approved public repository or prepared teaching repository and ask:

**What is this thing, where did it come from, and what happened before you arrived?**

Learners clone, inspect, read the README, inspect history, identify file types, locate provenance/licensing information, and report what the evidence supports.

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

The learning product is therefore not a disposable exercise. It can become evidence of documentation, version control, provenance awareness, reproducible practice, and collaboration for a CV, résumé, portfolio, application, or later research project.

## Community-of-practice review

Invite Carpentries instructors to review the lesson for rigor rather than silently rewrite it. Ask reviewers to comment on:

- conceptual accuracy;
- novice cognitive load;
- accessibility and recovery paths;
- whether commands are connected to questions and concepts;
- provenance/reproducibility claims;
- whether the portfolio outcome is authentic and achievable;
- whether example repositories are appropriately licensed, sized, and contextualized;
- missing teaching moments or likely learner misconceptions.

Record substantive changes in Git history so the development of the lesson remains inspectable.