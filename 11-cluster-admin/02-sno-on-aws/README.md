# Single Node OpenShift on AWS

> Phase 11 · Cluster admin · ⏱️ 2–3 sessions · Status lives in `PROGRESS.md`

## 🎯 What you'll learn

- SNO requirements and limits
- Cost estimate and Budget alerts before you start
- Install into the project's selected Region only
- Create → practice → `openshift-install destroy cluster`
- Verify nothing is left billing (EC2, EBS, ELB, NAT, EIPs, Route 53)

## 🧩 Key ideas

- **SNO** — Control plane and workloads on one node — great for labs and edge, no HA.

## 🍔 Zomato app tie-in

Deploy Zomato via GitOps onto a fresh SNO, then destroy it.

## 🧪 Lab environment

- 🟧 AWS Single Node OpenShift (Paid plan, billed hourly — create → practice → destroy)

> 💸 **AWS cost safety:** state the hourly cost first, check Budget alerts,
> use only the project's selected Region, and destroy everything at session end.
> NAT gateways, load balancers, EBS volumes and public IPs bill even when instances are stopped.

## 📚 Official docs

- [OCP docs → Installing on a single node](https://docs.redhat.com/en/documentation/openshift_container_platform/)
- [OCP docs → Installing on AWS](https://docs.redhat.com/en/documentation/openshift_container_platform/)

> Docs are version-dependent — match the docs version to the cluster you're on (`oc version`).

## ✅ Done when

Every item under *What you'll learn* has been run **hands-on** and ticked in `PROGRESS.md`,
and you can explain it back without notes. Then move up the ladder in `CHALLENGE.md`.

## 📁 In this folder

- `README.md` — this outline (expanded as we go)
- `CHALLENGE.md` — ladder ideas + write-back from your sessions
- `manifests/` — YAML / Containerfiles you write (created when you write the first one)
- `scenario.sh` → `TICKET.md` — incident lab, added when built (TICKET.md is git-ignored)
