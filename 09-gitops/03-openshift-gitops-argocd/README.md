# OpenShift GitOps (ArgoCD)

> Phase 09 · GitOps · ⏱️ 2 sessions · Status lives in `PROGRESS.md`

## 🎯 What you'll learn

- Install the OpenShift GitOps operator
- Application: repo, path, destination, sync policy
- Sync, self-heal, prune; drift detection
- This repo as the source of truth
- App-of-apps / ApplicationSet (concept)

## 🧩 Key ideas

- **GitOps** — Git holds desired state; a controller continuously makes the cluster match Git.

## 🔀 OpenShift vs plain Kubernetes

OpenShift GitOps is Red Hat's supported Argo CD distribution, installed via OLM.

## 🍔 Zomato app tie-in

Argo CD deploys Zomato from `ramsaikumar-pv/openshift-learning`.

## 🧪 Lab environment

- 💻 OpenShift Local / CRC on Windows (16 GB+ RAM, cluster-admin)

## 📚 Official docs

- [OCP docs → OpenShift GitOps](https://docs.redhat.com/en/documentation/red_hat_openshift_gitops/)
- [Argo CD](https://argo-cd.readthedocs.io/)

> Docs are version-dependent — match the docs version to the cluster you're on (`oc version`).

## ✅ Done when

Every item under *What you'll learn* has been run **hands-on** and ticked in `PROGRESS.md`,
and you can explain it back without notes. Then move up the ladder in `CHALLENGE.md`.

## 📁 In this folder

- `README.md` — this outline (expanded as we go)
- `CHALLENGE.md` — ladder ideas + write-back from your sessions
- `manifests/` — YAML / Containerfiles you write (created when you write the first one)
- `scenario.sh` → `TICKET.md` — incident lab, added when built (TICKET.md is git-ignored)
