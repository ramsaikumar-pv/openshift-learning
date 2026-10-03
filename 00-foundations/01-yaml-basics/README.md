# YAML basics

> Phase 00 · Foundations · ⏱️ 60 min · Status lives in `PROGRESS.md`

## 🎯 What you'll learn

- Key/value pairs and why indentation (spaces, never tabs) is the syntax
- Maps (dictionaries) vs lists (sequences) — and lists of maps
- Scalars and types: strings, numbers, booleans, null — and when to quote
- Multi-line strings with `|` (keep newlines) and `>` (fold)
- Multiple documents in one file with `---`, and comments with `#`
- Validate YAML with `yamllint` / `python3 -c 'import yaml...'` and read it with `yq`
- The 4 top-level fields of every Kubernetes object: apiVersion, kind, metadata, spec

## 🧩 Key ideas

- **Indentation is structure** — YAML has no braces. Two spaces deeper = 'belongs to the line above'. One wrong space changes the meaning or breaks parsing.
- **Map** — Unordered `key: value` pairs. Keys are unique within the same map.
- **List** — Items starting with `- `. A list item can itself be a map — this is how `containers:` works in a Pod.
- **Type surprises** — `version: 1.10` becomes the number 1.1. `country: NO` can become boolean false in YAML 1.1 parsers. Quote anything that must stay a string.
- **Block scalars** — `|` keeps line breaks (scripts, config files inside a ConfigMap); `>` folds lines into one.
- **Kubernetes shape** — apiVersion = which API group/version; kind = what object; metadata = name/labels; spec = what you want. The cluster adds `status` = what is.

## 🍔 Zomato app tie-in

Describe one Zomato restaurant (name, cuisine list, menu items with prices, open hours) in YAML. Later this same skill writes the Deployment for the order service.

## 🧪 Lab environment

- 🐧 Ubuntu on WSL (your laptop)

## 📚 Official docs

- [YAML 1.2.2 spec](https://yaml.org/spec/1.2.2/)
- [yamllint](https://yamllint.readthedocs.io/)
- [yq](https://mikefarah.gitbook.io/yq/)

> Docs are version-dependent — match the docs version to the cluster you're on (`oc version`).

## ✅ Done when

Every item under *What you'll learn* has been run **hands-on** and ticked in `PROGRESS.md`,
and you can explain it back without notes. Then move up the ladder in `CHALLENGE.md`.

## 📁 In this folder

- `README.md` — this outline (expanded as we go)
- `CHALLENGE.md` — ladder ideas + write-back from your sessions
- `scenario.sh` → `TICKET.md` — incident lab, added when built (TICKET.md is git-ignored)
