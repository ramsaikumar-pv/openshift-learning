# Challenge — Git refresh for manifests

> Escalation material. Sessions stay improvised and Socratic; this file records
> what happened and holds the next rung of the ladder. Never drive a session from it.

## 🪜 Ladder

- **L1 — mechanic works:** everything in README *What you'll learn*, hands-on.
- **L2 — edge cases / "what happens if…":**
  - You committed a kubeconfig by accident but haven't pushed — what are your options? What if you had pushed?
  - Why does adding a file to `.gitignore` not stop Git tracking it if it was already committed?
- **L3 — incident ticket (no hints):** "`git status` shows a secret file as 'to be committed' even though it's in .gitignore" — built by `scenario.sh` when ready.
  How the scenario is built is deliberately not written here.
- **Boss:** combines this module with earlier phases — designed when we get here.

## From Ram's sessions

### 2026-10-03 — git init on the course repo
- **Q (predict):** after `git init -b main`, what will `git status` show — all 126 files? Will
  `.gitignore` appear?
- **Ram:** "all 126 files since I didn't track anything." (Didn't answer the .gitignore part.)
- **Actual:** 16 entries — 4 top-level files + 12 folders. Correction: with untracked files in
  a folder, Git shows just the folder (`--untracked-files=normal`). `.gitignore` shows as
  untracked and *should* be committed so clones share the rules.
- **Open question (unanswered, resume here):** an ignored kubeconfig inside an untracked
  folder — does `git status` still show only the folder? Would `git add .` stage it?
- **Next command pending:** predict, then `git status --untracked-files=all | wc -l`.
