# Services

> Phase 02 · OpenShift core · ⏱️ 60 min · Status lives in `PROGRESS.md`

## 🎯 What you'll learn

- Why pods need a stable address (pod IPs change)
- ClusterIP Service: selector, `port` vs `targetPort`
- Endpoints / EndpointSlices — the pods actually behind a Service
- Cluster DNS: `orders.zomato-dev.svc.cluster.local`
- Test from inside the cluster with a debug pod and `curl`

## 🧩 Key ideas

- **Service** — A stable virtual IP + DNS name that load-balances to pods matching its selector.
- **port vs targetPort** — `port` = what clients call; `targetPort` = what the container listens on.
- **Endpoints** — If this list is empty, the Service has nowhere to send traffic — first thing to check.

## 🔀 OpenShift vs plain Kubernetes

Identical to Kubernetes. On OpenShift the data path is implemented by OVN-Kubernetes (Phase 7).

## 🍔 Zomato app tie-in

Create an `orders` Service; the frontend will call `http://orders:8080`.

## 🧪 Lab environment

- ☁️ Developer Sandbox (free, namespace-level, no cluster-admin)

## 📚 Official docs

- [Kubernetes Services](https://kubernetes.io/docs/concepts/services-networking/service/)

> Docs are version-dependent — match the docs version to the cluster you're on (`oc version`).

## ✅ Done when

Every item under *What you'll learn* has been run **hands-on** and ticked in `PROGRESS.md`,
and you can explain it back without notes. Then move up the ladder in `CHALLENGE.md`.

## 📁 In this folder

- `README.md` — this outline (expanded as we go)
- `CHALLENGE.md` — ladder ideas + write-back from your sessions
- `manifests/` — YAML / Containerfiles you write (created when you write the first one)
- `scenario.sh` → `TICKET.md` — incident lab, added when built (TICKET.md is git-ignored)
