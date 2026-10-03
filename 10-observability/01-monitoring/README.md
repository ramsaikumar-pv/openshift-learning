# Monitoring

> Phase 10 · Observability · ⏱️ 60 min · Status lives in `PROGRESS.md`

## 🎯 What you'll learn

- Built-in Prometheus, Alertmanager and console dashboards
- PromQL basics
- User workload monitoring and ServiceMonitors
- Writing an alert rule

## 🧩 Key ideas

- **Prometheus** — Scrapes metrics endpoints on a schedule and stores time series.

## 🔀 OpenShift vs plain Kubernetes

OpenShift ships a full monitoring stack managed by the Cluster Monitoring Operator.

## 🍔 Zomato app tie-in

Alert when the order service's error rate spikes.

## 🧪 Lab environment

- 💻 OpenShift Local / CRC on Windows (16 GB+ RAM, cluster-admin)
- ☁️ Developer Sandbox (free, namespace-level, no cluster-admin)

## 📚 Official docs

- [OCP docs → Observability → Monitoring](https://docs.redhat.com/en/documentation/openshift_container_platform/)

> Docs are version-dependent — match the docs version to the cluster you're on (`oc version`).

## ✅ Done when

Every item under *What you'll learn* has been run **hands-on** and ticked in `PROGRESS.md`,
and you can explain it back without notes. Then move up the ladder in `CHALLENGE.md`.

## 📁 In this folder

- `README.md` — this outline (expanded as we go)
- `CHALLENGE.md` — ladder ideas + write-back from your sessions
- `manifests/` — YAML / Containerfiles you write (created when you write the first one)
- `scenario.sh` → `TICKET.md` — incident lab, added when built (TICKET.md is git-ignored)
