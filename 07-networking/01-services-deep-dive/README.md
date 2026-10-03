# Services in depth

> Phase 07 · Networking · ⏱️ 60 min · Status lives in `PROGRESS.md`

## 🎯 What you'll learn

- ClusterIP, NodePort, LoadBalancer, ExternalName, headless
- sessionAffinity, named ports, multi-port Services
- Services without selectors (pointing outside the cluster)
- DNS search paths inside pods

## 🧩 Key ideas

- **Headless** — `clusterIP: None` — DNS returns pod IPs directly (used by StatefulSets).

## 🔀 OpenShift vs plain Kubernetes

LoadBalancer Services need a cloud or MetalLB; on vSphere you often use MetalLB.

## 🍔 Zomato app tie-in

Point the payment service at an 'external' gateway via ExternalName.

## 🧪 Lab environment

- ☁️ Developer Sandbox (free, namespace-level, no cluster-admin)
- 💻 OpenShift Local / CRC on Windows (16 GB+ RAM, cluster-admin)

## 📚 Official docs

- [Services](https://kubernetes.io/docs/concepts/services-networking/service/)

> Docs are version-dependent — match the docs version to the cluster you're on (`oc version`).

## ✅ Done when

Every item under *What you'll learn* has been run **hands-on** and ticked in `PROGRESS.md`,
and you can explain it back without notes. Then move up the ladder in `CHALLENGE.md`.

## 📁 In this folder

- `README.md` — this outline (expanded as we go)
- `CHALLENGE.md` — ladder ideas + write-back from your sessions
- `manifests/` — YAML / Containerfiles you write (created when you write the first one)
- `scenario.sh` → `TICKET.md` — incident lab, added when built (TICKET.md is git-ignored)
