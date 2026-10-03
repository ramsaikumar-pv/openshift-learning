# Web console and the oc CLI

> Phase 02 · OpenShift core · ⏱️ 60 min · Status lives in `PROGRESS.md`

## 🎯 What you'll learn

- Install `oc` and log in (`oc login` with a token)
- `oc whoami`, `oc whoami --show-console`
- `oc get`, `oc describe`, `oc explain`, `-o yaml`, `-o wide`
- `oc api-resources` — what object kinds exist
- `oc` vs `kubectl` — same core, OpenShift extras
- Navigating the web console (views/perspectives are version-dependent)

## 🧩 Key ideas

- **oc** — A superset of kubectl: all kubectl verbs plus OpenShift ones (`new-project`, `new-app`, `start-build`, `adm`…).
- **oc explain** — Built-in field documentation: `oc explain deployment.spec.strategy`. Your best friend when writing YAML.
- **kubeconfig** — File (`~/.kube/config`) holding cluster URLs and your credentials. Never commit it.

## 🔀 OpenShift vs plain Kubernetes

`kubectl` works against OpenShift too, but `oc` adds login via OAuth, project switching and build/image commands.

## 🍔 Zomato app tie-in

Find your Sandbox project in both the console and `oc`; list everything already in it.

## 🧪 Lab environment

- ☁️ Developer Sandbox (free, namespace-level, no cluster-admin)

## 📚 Official docs

- [OpenShift CLI (oc) — OCP docs → CLI tools](https://docs.redhat.com/en/documentation/openshift_container_platform/)
- [Developer Sandbox](https://developers.redhat.com/developer-sandbox)

> Docs are version-dependent — match the docs version to the cluster you're on (`oc version`).

## ✅ Done when

Every item under *What you'll learn* has been run **hands-on** and ticked in `PROGRESS.md`,
and you can explain it back without notes. Then move up the ladder in `CHALLENGE.md`.

## 📁 In this folder

- `README.md` — this outline (expanded as we go)
- `CHALLENGE.md` — ladder ideas + write-back from your sessions
- `manifests/` — YAML / Containerfiles you write (created when you write the first one)
- `scenario.sh` → `TICKET.md` — incident lab, added when built (TICKET.md is git-ignored)
