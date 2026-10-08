# October 8 curriculum review and revision record

**Status:** Partial source audit and targeted corrections. This record does not claim a complete historical chat or Teams audit.

## Sources inspected

- Complete default-branch file trees for `RebekahZipp/GitHubCarpentries` (22 files) and `RebekahZipp/GitHubCarpentries-Examples` (8 files).
- Full text of all 22 curriculum repository files and all 8 example repository files.
- Existing 22-slide `Git_GitHub_Oct8_Workshop_Companion.pptx` from conversation files, slide titles and text inspected.
- Workshop files discovered in the file library: printable Bash cheat sheet PDF and DOCX, workshop links DOCX, daily schedule DOCX, `Teaching Git and GitHub.pdf`. The PDF and DOCX source content were not all independently audited page by page.
- Accessible current chat and carried-forward planning decisions. Historical conversations beyond accessible context were not exhaustively retrievable.

## Principles that govern revisions

**PURPOSE → PREDICT → ACT → OBSERVE → INTERPRET → VERIFY → CONTINUE**

**CHANGE → INSPECT → CHOOSE → RECORD → REVIEW → SHARE**

**EXPECT → OBSERVE → EXPLAIN → TEST → ACT → VERIFY**

Every command should answer a question, show evidence, include a safe recovery, and lead to the next meaningful action. Learners commit locally before the first break. Keep the two seven-minute breaks. Preserve book-list metadata ambiguity as the class discovery.

## Findings and actions

| Finding | Reasoning | Action | Validation |
| --- | --- | --- | --- |
| DSC local folder previously described under `libpatron` | Wrong path derails instructor and learners | Corrected to `C:\Users\Carpentries` and Git Bash `/c/Users/Carpentries` in the seven core files | Text check in revised materials |
| `cd https://...` confused with `git clone` | Distinguish local directory from remote URL | Explicit spoken instructor cue and student/helper reference | Static syntax review |
| Identical long instructor dialogue copied into student, helper, README, and cheat sheet | Conflicting audiences and too much scrolling | Removed duplicated blocks; replaced with audience-specific entry points | File update commits |
| Master script had three overlapping setup explanations | Setup was harder to follow during live teaching | Consolidated into one short instructor cue before the existing locate activity | Static content review |
| Run-of-show contained literal `\\n` inside break table | Could break rendering and obscure second break | Corrected Markdown table row | Static text review |
| Example books table uses `Date Finished` but dates resemble publication dates | A meaningful metadata interpretation activity | Retained starting-state ambiguity; documented it in example README | Example file inspected; unchanged |
| Eight-minute learner contribution slot (2:45–2:53) | Too tight for permission, editing, staging, and push | Treat as minimum checkpoint, not a guaranteed full-class push; use pre-invited learners or local commit as safe outcome | Scheduling concern remains |
| Multiple instructor logs exist | Potentially competing sources of truth | Designated `instructor/OCT8_LIVE_LESSON.md` authoritative for live teaching; other logs historical | Repository tree reviewed |
| Existing slide deck predates some setup corrections | Misalignment of live setup and slides | Updated companion copy as separate downloadable revision, not yet uploaded to GitHub | Inspect slide count and text after edit |

## Safety gates

- Do not clone if the local project exists.
- Do not pull over unexamined uncommitted work.
- `git remote -v` is not a live network test.
- A rejected push is not automatically a merge conflict.
- No force-push, reset, or deletion as novice default recovery.
- Do not change `build-example/books.md` on shared `main` until the activity is performed deliberately.
- RStudio should open the existing local clone; cloud-synced `.git` directories and shared-machine account sessions require care.

## Open / unverified

- Complete historical chat audit and Teams tab contents were not available.
- Actual DSC machine filesystem, Git credentials, and live clone were not inspected.
- Actual live Git operations and collaborator permissions were not exercised.
- No live push/pull or merge conflict was performed in the teaching repository.
- The 2:45 learner contribution and 3:45 RStudio handoff remain tight and should have a local-commit fallback.
- Slide and Word revisions produced as downloadable copies need separate publication into the desired shared workspace.

## Authoritative sources

- [Live instructor lesson](OCT8_LIVE_LESSON.md)
- [Student exercise](../student/CLONE_INVESTIGATE_BUILD.md)
- [Cheat sheet](../GIT_CHEAT_SHEET.md)
- [Helper guide](../helper/README.md)
- [Example repository](https://github.com/RebekahZipp/GitHubCarpentries-Examples)
