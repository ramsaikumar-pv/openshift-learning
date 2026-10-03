# Routes

> Phase 02 · OpenShift core · ⏱️ 60 min · Status lives in `PROGRESS.md`

## 🎯 What you'll learn

- Route = external hostname → Service, served by the OpenShift router (HAProxy)
- `oc expose service`, and the equivalent Route YAML
- Route vs Kubernetes Ingress (OpenShift supports both)
- TLS termination types at a glance: edge, passthrough, re-encrypt
- Reading router 503s: no endpoints vs wrong port vs not ready

## 🧩 Key ideas

- **Router** — HAProxy pods run by the Ingress Operator. They watch Routes and reconfigure automatically.
- **Host** — The public hostname, usually `<name>-<project>.apps.<cluster-domain>` by default.

## 🔀 OpenShift vs plain Kubernetes

Routes are OpenShift-native and predate Ingress. OpenShift turns Ingress objects into Routes under the hood. Gateway API support is arriving in newer versions (version-dependent).

## 🍔 Zomato app tie-in

Expose the frontend with a Route and open it in your browser — the Zomato app is live 🎉

## 🧪 Lab environment

- ☁️ Developer Sandbox (free, namespace-level, no cluster-admin)

## 📚 Official docs

- [OCP docs → Networking → Routes](https://docs.redhat.com/en/documentation/openshift_container_platform/)
- [Kubernetes Ingress (for comparison)](https://kubernetes.io/docs/concepts/services-networking/ingress/)

> Docs are version-dependent — match the docs version to the cluster you're on (`oc version`).

## ✅ Done when

Every item under *What you'll learn* has been run **hands-on** and ticked in `PROGRESS.md`,
and you can explain it back without notes. Then move up the ladder in `CHALLENGE.md`.

## 📁 In this folder

- `README.md` — this outline (expanded as we go)
- `CHALLENGE.md` — ladder ideas + write-back from your sessions
- `manifests/` — YAML / Containerfiles you write (created when you write the first one)
- `scenario.sh` → `TICKET.md` — incident lab, added when built (TICKET.md is git-ignored)
