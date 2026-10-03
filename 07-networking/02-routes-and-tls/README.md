# Routes and TLS

> Phase 07 · Networking · ⏱️ 60 min · Status lives in `PROGRESS.md`

## 🎯 What you'll learn

- Edge, passthrough and re-encrypt termination
- Custom certificates and keys on Routes (keys never in Git!)
- insecureEdgeTerminationPolicy (Redirect)
- IngressController basics, wildcard cert, router sharding (concept)

## 🧩 Key ideas

- **Edge** — TLS ends at the router.
- **Passthrough** — Router forwards encrypted bytes; the pod terminates TLS.
- **Re-encrypt** — Router terminates, then opens a new TLS connection to the pod.

## 🔀 OpenShift vs plain Kubernetes

Route TLS options are richer than basic Ingress.

## 🍔 Zomato app tie-in

Serve the Zomato frontend on HTTPS with redirect.

## 🧪 Lab environment

- ☁️ Developer Sandbox (free, namespace-level, no cluster-admin)
- 💻 OpenShift Local / CRC on Windows (16 GB+ RAM, cluster-admin)

## 📚 Official docs

- [OCP docs → Networking → Routes](https://docs.redhat.com/en/documentation/openshift_container_platform/)

> Docs are version-dependent — match the docs version to the cluster you're on (`oc version`).

## ✅ Done when

Every item under *What you'll learn* has been run **hands-on** and ticked in `PROGRESS.md`,
and you can explain it back without notes. Then move up the ladder in `CHALLENGE.md`.

## 📁 In this folder

- `README.md` — this outline (expanded as we go)
- `CHALLENGE.md` — ladder ideas + write-back from your sessions
- `manifests/` — YAML / Containerfiles you write (created when you write the first one)
- `scenario.sh` → `TICKET.md` — incident lab, added when built (TICKET.md is git-ignored)
