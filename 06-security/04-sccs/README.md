# Security Context Constraints (SCCs)

> Phase 06 · Security · ⏱️ 2 sessions · Status lives in `PROGRESS.md`

## 🎯 What you'll learn

- What SCCs control: UID, capabilities, privileged, host access, volumes, SELinux
- `restricted-v2` (default), `nonroot-v2`, `anyuid`, `privileged`
- Arbitrary UIDs and why images expecting root fail
- How a pod gets an SCC (SA permissions, priority) and the `openshift.io/scc` annotation
- Pod Security Admission and how it relates to SCCs

## 🧩 Key ideas

- **SCC** — OpenShift's admission gate on what a pod may do on the node. Older and more detailed than Kubernetes Pod Security Standards.

## 🔀 OpenShift vs plain Kubernetes

OpenShift-only, and the #1 reason 'it works on Docker/K8s but not on OpenShift'. Link back to Phase 1 rootless + Containerfile USER.

## 🍔 Zomato app tie-in

A vendor image for the payment service insists on root — diagnose it and fix it the right way.

## 🧪 Lab environment

- 💻 OpenShift Local / CRC on Windows (16 GB+ RAM, cluster-admin)
- ☁️ Developer Sandbox (free, namespace-level, no cluster-admin)

## 📚 Official docs

- [OCP docs → Authentication and authorization → SCCs](https://docs.redhat.com/en/documentation/openshift_container_platform/)

> Docs are version-dependent — match the docs version to the cluster you're on (`oc version`).

## ✅ Done when

Every item under *What you'll learn* has been run **hands-on** and ticked in `PROGRESS.md`,
and you can explain it back without notes. Then move up the ladder in `CHALLENGE.md`.

## 📁 In this folder

- `README.md` — this outline (expanded as we go)
- `CHALLENGE.md` — ladder ideas + write-back from your sessions
- `manifests/` — YAML / Containerfiles you write (created when you write the first one)
- `scenario.sh` → `TICKET.md` — incident lab, added when built (TICKET.md is git-ignored)
