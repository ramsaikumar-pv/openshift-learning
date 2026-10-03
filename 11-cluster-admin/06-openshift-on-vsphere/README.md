# OpenShift on vSphere / VCF

> Phase 11 · Cluster admin · ⏱️ 60 min · Status lives in `PROGRESS.md`

## 🎯 What you'll learn

- vSphere IPI vs UPI vs Agent-based on vSphere
- Required vCenter permissions and networking (VIPs for API and ingress)
- vSphere CSI and storage policies (link Phase 4)
- Day-2: adding nodes, failure domains/zones (version-dependent)

## 🧩 Key ideas

- **API/Ingress VIPs** — Virtual IPs (keepalived on the nodes) for the API and the apps router on vSphere IPI.

## 🧪 Lab environment

- 🏢 vSphere — your work environment (read-only exploration unless you have a lab)

## 📚 Official docs

- [OCP docs → Installing on vSphere](https://docs.redhat.com/en/documentation/openshift_container_platform/)

> Docs are version-dependent — match the docs version to the cluster you're on (`oc version`).

## ✅ Done when

Every item under *What you'll learn* has been run **hands-on** and ticked in `PROGRESS.md`,
and you can explain it back without notes. Then move up the ladder in `CHALLENGE.md`.

## 📁 In this folder

- `README.md` — this outline (expanded as we go)
- `CHALLENGE.md` — ladder ideas + write-back from your sessions
- `manifests/` — YAML / Containerfiles you write (created when you write the first one)
- `scenario.sh` → `TICKET.md` — incident lab, added when built (TICKET.md is git-ignored)
