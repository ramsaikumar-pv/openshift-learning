# NetworkPolicies

> Phase 07 · Networking · ⏱️ 60 min · Status lives in `PROGRESS.md`

## 🎯 What you'll learn

- Default: all pods can talk to all pods
- Default-deny ingress, then allow what's needed
- podSelector, namespaceSelector, ports
- Allowing the OpenShift router and monitoring namespaces
- AdminNetworkPolicy (cluster-scoped) — version-dependent

## 🧩 Key ideas

- **NetworkPolicy** — A firewall rule set selected by labels. Once any policy selects a pod, only allowed traffic gets in.

## 🔀 OpenShift vs plain Kubernetes

Implemented by OVN-Kubernetes. Forgetting to allow the router's namespace is a classic 'Route suddenly 503' cause.

## 🍔 Zomato app tie-in

Only the order service may reach the DB; only the frontend is reachable from the router.

## 🧪 Lab environment

- ☁️ Developer Sandbox (free, namespace-level, no cluster-admin)
- 💻 OpenShift Local / CRC on Windows (16 GB+ RAM, cluster-admin)

## 📚 Official docs

- [Network policies](https://kubernetes.io/docs/concepts/services-networking/network-policies/)

> Docs are version-dependent — match the docs version to the cluster you're on (`oc version`).

## ✅ Done when

Every item under *What you'll learn* has been run **hands-on** and ticked in `PROGRESS.md`,
and you can explain it back without notes. Then move up the ladder in `CHALLENGE.md`.

## 📁 In this folder

- `README.md` — this outline (expanded as we go)
- `CHALLENGE.md` — ladder ideas + write-back from your sessions
- `manifests/` — YAML / Containerfiles you write (created when you write the first one)
- `scenario.sh` → `TICKET.md` — incident lab, added when built (TICKET.md is git-ignored)
