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

### 2026-10-14 — bringing a remote branch into main
- **Q:** after `git fetch`, why does `git branch` still show only `main`?
- **Actual:** fetch creates remote-tracking branches (`origin/...`), not local ones; `git branch -a`
  shows them.
- **Q (scenario):** you commit "Add YAML notes" on local main without pushing. What does
  `git log --oneline origin/main..main` print?
- **Ram:** "local commit details that's not in main." **Correction:** not in *origin/main* — it lists
  unpushed commits.
- **Q (scenario):** a teammate pushes to GitHub's main; you don't fetch. Does
  `git log main..origin/main` show it?
- **Ram:** "No — local Git has no idea what went to the remote." ✅
- **Q:** after merging and then running `git fetch`, why is `origin/main` still on the old commit?
- **Ram:** "fetch is remote → local, not local → remote." ✅ Then guessed the `origin/claude/...`
  label was on the new commit *because* he merged. **Correction:** it was there since the fetch;
  a merge only moves the current branch (HEAD).
- **Predict → run:** graph shows the claude branch one commit ahead ✅; merge was a fast-forward ✅
  (ran it before predicting); after push, `origin/main..main` prints nothing ✅.
- **Q:** why did `git push` report `Total 0` objects yet still move GitHub's main?
- **Ram:** "nothing to upload because it's already on the remote" ✅; "fetch got the metadata".
  **Correction:** fetch downloads the full objects (commit, trees, blobs), not just metadata — the
  push only had to move the `main` pointer.
