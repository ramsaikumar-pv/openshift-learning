# etcd backup and restore

> Phase 11 · Cluster admin · ⏱️ 45 min · Status lives in `PROGRESS.md`

## 🎯 What you'll learn

- Why etcd backup is your last line of defence
- `cluster-backup.sh` on a control plane node
- Restore at a high level (and when not to)

## 🧩 Key ideas

- **etcd snapshot** — A point-in-time copy of all cluster state.

## 🧪 Lab environment

- 🟧 AWS Single Node OpenShift (Paid plan, billed hourly — create → practice → destroy)
- 💻 OpenShift Local / CRC on Windows (16 GB+ RAM, cluster-admin)

> 💸 **AWS cost safety:** state the hourly cost first, check Budget alerts,
> use only the project's selected Region, and destroy everything at session end.
> NAT gateways, load balancers, EBS volumes and public IPs bill even when instances are stopped.

## 📚 Official docs

- [OCP docs → Backup and restore](https://docs.redhat.com/en/documentation/openshift_container_platform/)

> Docs are version-dependent — match the docs version to the cluster you're on (`oc version`).

## ✅ Done when

Every item under *What you'll learn* has been run **hands-on** and ticked in `PROGRESS.md`,
and you can explain it back without notes. Then move up the ladder in `CHALLENGE.md`.

## 📁 In this folder

- `README.md` — this outline (expanded as we go)
- `CHALLENGE.md` — ladder ideas + write-back from your sessions
- `manifests/` — YAML / Containerfiles you write (created when you write the first one)
- `scenario.sh` → `TICKET.md` — incident lab, added when built (TICKET.md is git-ignored)
