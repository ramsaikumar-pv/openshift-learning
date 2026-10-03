# Projects and namespaces

> Phase 02 · OpenShift core · ⏱️ 30 min · Status lives in `PROGRESS.md`

## 🎯 What you'll learn

- Namespaces isolate names, quotas, permissions and network policy
- A Project = namespace + OpenShift metadata + request workflow
- `oc new-project`, `oc project`, `oc projects`
- Why the Sandbox gives you fixed projects you can't create

## 🧩 Key ideas

- **Namespace** — A folder for objects. Two pods may share a name only in different namespaces.
- **Project request** — Normal users ask for a Project; OpenShift creates the namespace and gives them admin on it via a template.

## 🔀 OpenShift vs plain Kubernetes

Plain Kubernetes users need cluster permissions to create namespaces. OpenShift lets ordinary users self-serve Projects (if the admin allows).

## 🍔 Zomato app tie-in

Plan projects: `zomato-dev` and `zomato-prod` on CRC. In the Sandbox, use the one you're given.

## 🧪 Lab environment

- ☁️ Developer Sandbox (free, namespace-level, no cluster-admin)
- 💻 OpenShift Local / CRC on Windows (16 GB+ RAM, cluster-admin)

## 📚 Official docs

- [Kubernetes namespaces](https://kubernetes.io/docs/concepts/overview/working-with-objects/namespaces/)
- [OCP docs → Building applications → Projects](https://docs.redhat.com/en/documentation/openshift_container_platform/)

> Docs are version-dependent — match the docs version to the cluster you're on (`oc version`).

## ✅ Done when

Every item under *What you'll learn* has been run **hands-on** and ticked in `PROGRESS.md`,
and you can explain it back without notes. Then move up the ladder in `CHALLENGE.md`.

## 📁 In this folder

- `README.md` — this outline (expanded as we go)
- `CHALLENGE.md` — ladder ideas + write-back from your sessions
- `manifests/` — YAML / Containerfiles you write (created when you write the first one)
- `scenario.sh` → `TICKET.md` — incident lab, added when built (TICKET.md is git-ignored)
