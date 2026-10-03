# Git refresh for manifests

> Phase 00 · Foundations · ⏱️ 30 min · Status lives in `PROGRESS.md`

## 🎯 What you'll learn

- Initialise this course repo and push it to GitHub (ramsaikumar-pv)
- `.gitignore` for kubeconfigs, pull secrets, keys and install state
- Verify ignores with `git status` and `git check-ignore -v`
- Commit YAML manifests in small, meaningful commits

## 🧩 Key ideas

- **Repo as source of truth** — Phase 9's GitOps (ArgoCD) watches this repo and makes the cluster match it. Good habits now = smooth Phase 9.
- **Secrets never in Git** — Once pushed, assume a secret is leaked forever — history keeps it even after deletion.

## 🍔 Zomato app tie-in

The `manifests/` folders across modules become the Zomato app's deployable source.

## 🧪 Lab environment

- 🐧 Ubuntu on WSL (your laptop)
- 🐙 GitHub + your openshift-learning repo

## 📚 Official docs

- [git-scm docs: gitignore](https://git-scm.com/docs/gitignore)

> Docs are version-dependent — match the docs version to the cluster you're on (`oc version`).

## ✅ Done when

Every item under *What you'll learn* has been run **hands-on** and ticked in `PROGRESS.md`,
and you can explain it back without notes. Then move up the ladder in `CHALLENGE.md`.

## 📁 In this folder

- `README.md` — this outline (expanded as we go)
- `CHALLENGE.md` — ladder ideas + write-back from your sessions
- `scenario.sh` → `TICKET.md` — incident lab, added when built (TICKET.md is git-ignored)
