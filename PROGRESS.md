# 🗂️ OpenShift Learning Progress — Ram (ramsaikumar-pv)

> Tick a box only after doing it **hands-on** in a real terminal or cluster.
> Reading or watching is not doing. 🎯
> Update "Last Session" and the Session Log after every session.

---

## 00 — Foundations

### 01-yaml-basics — YAML basics
- [ ] Key/value pairs and why indentation (spaces, never tabs) is the syntax
- [ ] Maps (dictionaries) vs lists (sequences) — and lists of maps
- [ ] Scalars and types: strings, numbers, booleans, null — and when to quote
- [ ] Multi-line strings with `|` (keep newlines) and `>` (fold)
- [ ] Multiple documents in one file with `---`, and comments with `#`
- [ ] Validate YAML with `yamllint` / `python3 -c 'import yaml...'` and read it with `yq`
- [ ] The 4 top-level fields of every Kubernetes object: apiVersion, kind, metadata, spec

### 02-rhel-linux-for-containers — RHEL Linux for containers
- [ ] Linux namespaces (pid, net, mnt, uts, ipc, user) — what isolates a container
- [ ] cgroups v2 — what limits a container's CPU/memory
- [ ] SELinux basics: modes, contexts (`ls -Z`, `ps -Z`), `container_t`, and why `:Z` exists
- [ ] systemd units and `journalctl` — how services run and log on RHEL/RHCOS
- [ ] `dnf` package management on RHEL and UBI images
- [ ] `firewalld` zones and services (and why OpenShift nodes manage this for you)
- [ ] UIDs, `/etc/subuid` and `/etc/subgid` — the base of rootless containers
- [ ] Network troubleshooting toolkit: `ss`, `ip`, `dig`, `curl -v`

### 03-git-refresh — Git refresh for manifests
- [ ] Initialise this course repo and push it to GitHub (ramsaikumar-pv)
- [ ] `.gitignore` for kubeconfigs, pull secrets, keys and install state
- [ ] Verify ignores with `git status` and `git check-ignore -v`
- [ ] Commit YAML manifests in small, meaningful commits

---

## 01 — Containers with Podman

### 01-what-is-a-container — What is a container
- [ ] Container vs virtual machine (shared kernel vs own kernel)
- [ ] Image vs container (template vs running instance)
- [ ] OCI standard — why Podman, Docker, CRI-O all run the same images
- [ ] Podman vs Docker: daemonless, rootless by default, CLI-compatible
- [ ] `podman run`, `podman ps -a`, `podman logs`, `podman exec`, `podman stop`, `podman rm`
- [ ] Container lifecycle states: created, running, exited

### 02-images-and-registries — Images and registries
- [ ] Image layers and how they're shared/cached
- [ ] Fully-qualified image names: registry/namespace/repo:tag
- [ ] Tags vs digests (`@sha256:...`) — mutable vs immutable
- [ ] Registries: quay.io, registry.redhat.io (login), registry.access.redhat.com, docker.io
- [ ] Short-name resolution and `/etc/containers/registries.conf`
- [ ] Red Hat Universal Base Images (UBI)
- [ ] `podman pull`, `images`, `inspect`, `tag`, `rmi`, `login`, `push`
- [ ] `skopeo inspect` — look at a remote image without pulling

### 03-ports — Ports and container networking
- [ ] Each container gets its own network namespace
- [ ] Publishing ports with `-p hostPort:containerPort`
- [ ] Why the app must listen on 0.0.0.0, not 127.0.0.1
- [ ] Rootless containers can't bind host ports below 1024 by default
- [ ] `podman port`, `curl`, `ss` to verify the path end-to-end

### 04-volumes — Volumes and persistence
- [ ] Container filesystems are ephemeral
- [ ] Bind mounts vs named volumes
- [ ] SELinux relabelling with `:Z` and `:z`
- [ ] Rootless UID mapping and 'Permission denied' on mounts
- [ ] `podman unshare` to see files as the container sees them
- [ ] `podman volume create/ls/inspect/rm`

### 05-containerfiles — Building images with Containerfiles
- [ ] Containerfile instructions: FROM, RUN, COPY, WORKDIR, ENV, EXPOSE, USER, CMD, ENTRYPOINT
- [ ] CMD vs ENTRYPOINT and how arguments combine
- [ ] Layer caching — order instructions to rebuild fast
- [ ] `.containerignore` to keep junk and secrets out
- [ ] Multi-stage builds for small images
- [ ] Run as non-root and make files group-0 writable (OpenShift-friendly images)
- [ ] `podman build -t`, then run and push your own image

### 06-rootless — Rootless containers
- [ ] User namespaces: root in the container ≠ root on the host
- [ ] How subuid/subgid ranges are used
- [ ] Where rootless storage lives (`~/.local/share/containers`)
- [ ] Limits of rootless: low ports, some networking, some mounts
- [ ] `podman info` to inspect rootless setup

### 07-podman-pods — Pods in Podman
- [ ] A pod = containers sharing one network namespace (and optionally more)
- [ ] The infra container that holds the pod's namespaces
- [ ] Containers in a pod talk over `localhost`
- [ ] `podman pod create/ps/stop/rm`
- [ ] `podman kube generate` and `podman kube play` — your bridge to Kubernetes YAML

---

## 02 — OpenShift core

### 01-architecture — Architecture
- [ ] Control plane: kube-apiserver, etcd, scheduler, controller-manager
- [ ] Worker nodes: kubelet, CRI-O, kube-proxy/OVN
- [ ] Desired state vs actual state — the reconciliation loop
- [ ] What OpenShift adds on top of Kubernetes
- [ ] RHCOS and cluster operators (`oc get clusteroperators`)
- [ ] Kubernetes version vs OpenShift version (e.g. OCP 4.x ↔ K8s 1.y)

### 02-console-and-oc — Web console and the oc CLI
- [ ] Install `oc` and log in (`oc login` with a token)
- [ ] `oc whoami`, `oc whoami --show-console`
- [ ] `oc get`, `oc describe`, `oc explain`, `-o yaml`, `-o wide`
- [ ] `oc api-resources` — what object kinds exist
- [ ] `oc` vs `kubectl` — same core, OpenShift extras
- [ ] Navigating the web console (views/perspectives are version-dependent)

### 03-projects — Projects and namespaces
- [ ] Namespaces isolate names, quotas, permissions and network policy
- [ ] A Project = namespace + OpenShift metadata + request workflow
- [ ] `oc new-project`, `oc project`, `oc projects`
- [ ] Why the Sandbox gives you fixed projects you can't create

### 04-pods-and-labels — Pods, labels and selectors
- [ ] Write a Pod manifest from scratch, piece by piece
- [ ] `oc apply -f`, `oc get pods`, `oc describe pod`, `oc logs`, `oc exec`, `oc delete`
- [ ] Pod phases (Pending, Running, Succeeded, Failed) and container states/reasons
- [ ] Reading Events in `oc describe` — the first troubleshooting step
- [ ] Labels, selectors (`-l app=orders`) and annotations
- [ ] Why you almost never create bare pods

### 05-deployments-replicasets — Deployments and ReplicaSets
- [ ] Deployment → ReplicaSet → Pods ownership chain
- [ ] Write a Deployment manifest (replicas, selector, template)
- [ ] Self-healing: delete a pod and watch it come back
- [ ] `ownerReferences` — who owns what
- [ ] DeploymentConfig is deprecated — use Deployment

### 06-services — Services
- [ ] Why pods need a stable address (pod IPs change)
- [ ] ClusterIP Service: selector, `port` vs `targetPort`
- [ ] Endpoints / EndpointSlices — the pods actually behind a Service
- [ ] Cluster DNS: `orders.zomato-dev.svc.cluster.local`
- [ ] Test from inside the cluster with a debug pod and `curl`

### 07-routes — Routes
- [ ] Route = external hostname → Service, served by the OpenShift router (HAProxy)
- [ ] `oc expose service`, and the equivalent Route YAML
- [ ] Route vs Kubernetes Ingress (OpenShift supports both)
- [ ] TLS termination types at a glance: edge, passthrough, re-encrypt
- [ ] Reading router 503s: no endpoints vs wrong port vs not ready

### 08-scaling-and-rollouts — Scaling and rolling updates
- [ ] `oc scale deployment --replicas`
- [ ] RollingUpdate strategy: `maxSurge`, `maxUnavailable`
- [ ] Recreate strategy and when to use it
- [ ] `oc rollout status`, `history`, `undo`, `pause/resume`
- [ ] `oc set image` and why the change should end up in Git

---

## 03 — Config and health

### 01-configmaps — ConfigMaps
- [ ] Create ConfigMaps from literals, files and YAML
- [ ] Consume as env vars (`env`, `envFrom`) and as mounted files
- [ ] What updates live (mounted files) vs needs a restart (env vars)
- [ ] `oc set env`, `oc rollout restart`

### 02-secrets — Secrets
- [ ] Secret types: Opaque, dockerconfigjson, tls, service-account token
- [ ] base64 is encoding, not encryption
- [ ] Consume as env vars and as files
- [ ] Image pull secrets
- [ ] etcd encryption and external secret stores (concepts)

### 03-probes — Health probes
- [ ] Liveness (restart if dead), readiness (remove from Service if not ready), startup (protect slow starters)
- [ ] Probe types: httpGet, tcpSocket, exec, grpc
- [ ] Tuning: initialDelaySeconds, periodSeconds, timeoutSeconds, failureThreshold
- [ ] Reading probe failures in Events

### 04-requests-limits — Requests, limits and quotas
- [ ] Requests (scheduling guarantee) vs limits (hard cap)
- [ ] CPU over limit = throttled; memory over limit = OOMKilled
- [ ] QoS classes: Guaranteed, Burstable, BestEffort
- [ ] LimitRange and ResourceQuota on a project
- [ ] `oc adm top pods` / metrics

### 05-hpa — Horizontal Pod Autoscaler
- [ ] HPA scales replicas on CPU/memory (or custom metrics)
- [ ] Why HPA needs requests set
- [ ] `oc autoscale` and HPA YAML (autoscaling/v2)
- [ ] Generate load and watch scaling; scale-down stabilisation

### 06-graceful-shutdown — Graceful shutdown
- [ ] Pod termination sequence: SIGTERM → grace period → SIGKILL
- [ ] `terminationGracePeriodSeconds` and `preStop` hooks
- [ ] The race between endpoint removal and process exit
- [ ] Why exec-form CMD and a proper PID 1 matter

### 07-sidecars — Multi-container pods and sidecars
- [ ] Init containers: run to completion before the app starts
- [ ] Sidecar pattern: helper container alongside the app (logs, proxy)
- [ ] Native sidecars (`restartPolicy: Always` in initContainers) — version-dependent
- [ ] Sharing data with an `emptyDir` volume

---

## 04 — Storage

### 01-pv-pvc — PersistentVolumes and Claims
- [ ] PV (the disk) vs PVC (the request for a disk)
- [ ] Access modes: RWO, ROX, RWX, RWOP
- [ ] Binding, and reclaim policies: Delete vs Retain
- [ ] Mount a PVC into a pod and prove data survives pod deletion

### 02-storageclasses — StorageClasses and dynamic provisioning
- [ ] Dynamic provisioning via a StorageClass
- [ ] Default StorageClass
- [ ] `volumeBindingMode: WaitForFirstConsumer` vs Immediate
- [ ] Volume expansion (`allowVolumeExpansion`)

### 03-statefulsets — StatefulSets
- [ ] Stable pod names (db-0, db-1) and ordered start/stop
- [ ] Headless Services for stable per-pod DNS
- [ ] `volumeClaimTemplates` — one PVC per replica
- [ ] When to use StatefulSet vs Deployment (and when to use an operator instead)

### 04-vsphere-csi — vSphere CSI
- [ ] CSI — the plug-in standard for storage drivers
- [ ] vSphere CSI driver: Cloud Native Storage (CNS), datastores, storage policies
- [ ] How a PVC becomes a VMDK attached to a node VM
- [ ] Day-2: expansion, snapshots, topology/zones (version-dependent)

---

## 05 — Builds and images

### 01-s2i — Source-to-Image (S2I)
- [ ] What S2I does: source + builder image → runnable image
- [ ] `oc new-app <git-url>` and what it creates
- [ ] Builder images (Python, Node.js, Java)
- [ ] Reading build logs (`oc logs -f bc/...`)

### 02-buildconfigs — BuildConfigs
- [ ] BuildConfig strategies: Source (S2I), Docker (Containerfile)
- [ ] Triggers: ConfigChange, ImageChange, webhooks
- [ ] `oc start-build`, `oc cancel-build`, build history
- [ ] Builds for OpenShift (Shipwright) as the newer path — version-dependent

### 03-imagestreams — ImageStreams
- [ ] ImageStream and ImageStreamTag — a pointer layer over real images
- [ ] `oc import-image`, `oc tag`, scheduled imports
- [ ] Image change triggers on Deployments (annotation)
- [ ] Promoting dev → prod by retagging

### 04-internal-registry — Internal registry
- [ ] The integrated image registry and its operator
- [ ] Exposing the registry route and pushing with Podman
- [ ] Pull access across projects (`system:image-puller`)
- [ ] Registry storage

---

## 06 — Security

### 01-authentication — Authentication
- [ ] The OpenShift OAuth server and identity providers
- [ ] kubeadmin and why to remove it
- [ ] Configure an htpasswd identity provider
- [ ] Users, Identities and Groups objects

### 02-rbac — RBAC
- [ ] Role vs ClusterRole, RoleBinding vs ClusterRoleBinding
- [ ] Default roles: view, edit, admin, cluster-admin
- [ ] `oc adm policy add-role-to-user`, `oc auth can-i`, `oc auth can-i --as`
- [ ] Least privilege in practice

### 03-serviceaccounts — ServiceAccounts
- [ ] ServiceAccounts are identities for pods
- [ ] Default SA per project; `serviceAccountName`
- [ ] Projected, short-lived tokens
- [ ] Giving an SA RBAC permissions (e.g. to read ConfigMaps)

### 04-sccs — Security Context Constraints (SCCs)
- [ ] What SCCs control: UID, capabilities, privileged, host access, volumes, SELinux
- [ ] `restricted-v2` (default), `nonroot-v2`, `anyuid`, `privileged`
- [ ] Arbitrary UIDs and why images expecting root fail
- [ ] How a pod gets an SCC (SA permissions, priority) and the `openshift.io/scc` annotation
- [ ] Pod Security Admission and how it relates to SCCs

---

## 07 — Networking

### 01-services-deep-dive — Services in depth
- [ ] ClusterIP, NodePort, LoadBalancer, ExternalName, headless
- [ ] sessionAffinity, named ports, multi-port Services
- [ ] Services without selectors (pointing outside the cluster)
- [ ] DNS search paths inside pods

### 02-routes-and-tls — Routes and TLS
- [ ] Edge, passthrough and re-encrypt termination
- [ ] Custom certificates and keys on Routes (keys never in Git!)
- [ ] insecureEdgeTerminationPolicy (Redirect)
- [ ] IngressController basics, wildcard cert, router sharding (concept)

### 03-networkpolicies — NetworkPolicies
- [ ] Default: all pods can talk to all pods
- [ ] Default-deny ingress, then allow what's needed
- [ ] podSelector, namespaceSelector, ports
- [ ] Allowing the OpenShift router and monitoring namespaces
- [ ] AdminNetworkPolicy (cluster-scoped) — version-dependent

### 04-ovn-kubernetes — OVN-Kubernetes
- [ ] CNI — what a network plug-in does
- [ ] OVN-K basics: Open vSwitch, cluster/service CIDRs, overlay (Geneve)
- [ ] EgressIP and egress firewall (concept)
- [ ] Node-level troubleshooting with `oc debug node`
- [ ] OpenShift SDN is removed in newer releases — OVN-K is the default

---

## 08 — Operators

### 01-what-is-an-operator — What is an operator
- [ ] Custom Resource Definitions (CRDs) and Custom Resources
- [ ] Operator = CRD + controller encoding ops knowledge
- [ ] Cluster operators that run OpenShift itself (`oc get co`)
- [ ] Reading an operator's CR status

### 02-olm-and-operatorhub — OLM and OperatorHub
- [ ] OperatorHub and CatalogSources
- [ ] Subscription, InstallPlan, ClusterServiceVersion (CSV), OperatorGroup
- [ ] Channels and automatic vs manual approval
- [ ] Install, upgrade and remove an operator
- [ ] OLM v1 (ClusterExtension) — newer, version-dependent

---

## 09 — GitOps

### 01-helm — Helm
- [ ] Charts, values, templates, releases
- [ ] `helm install/upgrade/rollback/uninstall`, `helm template`
- [ ] Writing a small chart for the order service
- [ ] Helm charts in the OpenShift console

### 02-kustomize — Kustomize
- [ ] Base + overlays, no templating
- [ ] Patches (strategic merge, JSON 6902), images, namePrefix, configMapGenerator
- [ ] `oc apply -k`, `oc kustomize`

### 03-openshift-gitops-argocd — OpenShift GitOps (ArgoCD)
- [ ] Install the OpenShift GitOps operator
- [ ] Application: repo, path, destination, sync policy
- [ ] Sync, self-heal, prune; drift detection
- [ ] This repo as the source of truth
- [ ] App-of-apps / ApplicationSet (concept)

---

## 10 — Observability

### 01-monitoring — Monitoring
- [ ] Built-in Prometheus, Alertmanager and console dashboards
- [ ] PromQL basics
- [ ] User workload monitoring and ServiceMonitors
- [ ] Writing an alert rule

### 02-logging — Logging
- [ ] `oc logs` (and `--previous`) vs aggregated logging
- [ ] OpenShift Logging: collector (Vector) and LokiStack (version-dependent)
- [ ] Querying logs across pods

### 03-troubleshooting-workflows — Troubleshooting workflows
- [ ] A repeatable method: get → describe → events → logs → exec/debug
- [ ] `oc debug` (pods and nodes)
- [ ] `oc adm must-gather` and `inspect`
- [ ] Common states decoded: Pending, ImagePullBackOff, CrashLoopBackOff, OOMKilled, CreateContainerConfigError

---

## 11 — Cluster admin

### 01-installation-methods — Installation methods
- [ ] IPI vs UPI vs Assisted Installer vs Agent-based
- [ ] `install-config.yaml` anatomy (and keeping secrets out of Git)
- [ ] Bootstrap process at a high level
- [ ] Pull secret from console.redhat.com

### 02-sno-on-aws — Single Node OpenShift on AWS
- [ ] SNO requirements and limits
- [ ] Cost estimate and Budget alerts before you start
- [ ] Install into the project's selected Region only
- [ ] Create → practice → `openshift-install destroy cluster`
- [ ] Verify nothing is left billing (EC2, EBS, ELB, NAT, EIPs, Route 53)

### 03-nodes-and-machineconfigs — Nodes and MachineConfigs
- [ ] `oc get nodes`, cordon, drain, uncordon
- [ ] MachineConfig, MachineConfigPool, Machine Config Operator
- [ ] Machine API: Machines and MachineSets (IPI)
- [ ] Why you don't SSH and edit RHCOS by hand

### 04-upgrades — Upgrades
- [ ] Update channels (stable, fast, candidate, eus)
- [ ] Cluster Version Operator and the update graph
- [ ] Pre-upgrade checks and watching an upgrade
- [ ] EUS-to-EUS upgrades

### 05-etcd-backup — etcd backup and restore
- [ ] Why etcd backup is your last line of defence
- [ ] `cluster-backup.sh` on a control plane node
- [ ] Restore at a high level (and when not to)

### 06-openshift-on-vsphere — OpenShift on vSphere / VCF
- [ ] vSphere IPI vs UPI vs Agent-based on vSphere
- [ ] Required vCenter permissions and networking (VIPs for API and ingress)
- [ ] vSphere CSI and storage policies (link Phase 4)
- [ ] Day-2: adding nodes, failure domains/zones (version-dependent)

---

## 🪜 Difficulty Ladder

> Checkboxes = **L1**. L2 = edge case / "what if"; L3 = incident ticket, no hints;
> Boss = combined with earlier phases. Fill in the date when reached hands-on. Never lower a level.

| Topic | L1 | L2 | L3 | Boss | Notes |
|-------|----|----|----|------|-------|
| 00/01-yaml-basics | — | — | — | — | |
| 00/02-rhel-linux-for-containers | — | — | — | — | |
| 00/03-git-refresh | — | — | — | — | |
| 01/01-what-is-a-container | — | — | — | — | |
| 01/02-images-and-registries | — | — | — | — | |
| 01/03-ports | — | — | — | — | |
| 01/04-volumes | — | — | — | — | |
| 01/05-containerfiles | — | — | — | — | |
| 01/06-rootless | — | — | — | — | |
| 01/07-podman-pods | — | — | — | — | |
| 02/01-architecture | — | — | — | — | |
| 02/02-console-and-oc | — | — | — | — | |
| 02/03-projects | — | — | — | — | |
| 02/04-pods-and-labels | — | — | — | — | |
| 02/05-deployments-replicasets | — | — | — | — | |
| 02/06-services | — | — | — | — | |
| 02/07-routes | — | — | — | — | |
| 02/08-scaling-and-rollouts | — | — | — | — | |
| 03/01-configmaps | — | — | — | — | |
| 03/02-secrets | — | — | — | — | |
| 03/03-probes | — | — | — | — | |
| 03/04-requests-limits | — | — | — | — | |
| 03/05-hpa | — | — | — | — | |
| 03/06-graceful-shutdown | — | — | — | — | |
| 03/07-sidecars | — | — | — | — | |
| 04/01-pv-pvc | — | — | — | — | |
| 04/02-storageclasses | — | — | — | — | |
| 04/03-statefulsets | — | — | — | — | |
| 04/04-vsphere-csi | — | — | — | — | |
| 05/01-s2i | — | — | — | — | |
| 05/02-buildconfigs | — | — | — | — | |
| 05/03-imagestreams | — | — | — | — | |
| 05/04-internal-registry | — | — | — | — | |
| 06/01-authentication | — | — | — | — | |
| 06/02-rbac | — | — | — | — | |
| 06/03-serviceaccounts | — | — | — | — | |
| 06/04-sccs | — | — | — | — | |
| 07/01-services-deep-dive | — | — | — | — | |
| 07/02-routes-and-tls | — | — | — | — | |
| 07/03-networkpolicies | — | — | — | — | |
| 07/04-ovn-kubernetes | — | — | — | — | |
| 08/01-what-is-an-operator | — | — | — | — | |
| 08/02-olm-and-operatorhub | — | — | — | — | |
| 09/01-helm | — | — | — | — | |
| 09/02-kustomize | — | — | — | — | |
| 09/03-openshift-gitops-argocd | — | — | — | — | |
| 10/01-monitoring | — | — | — | — | |
| 10/02-logging | — | — | — | — | |
| 10/03-troubleshooting-workflows | — | — | — | — | |
| 11/01-installation-methods | — | — | — | — | |
| 11/02-sno-on-aws | — | — | — | — | |
| 11/03-nodes-and-machineconfigs | — | — | — | — | |
| 11/04-upgrades | — | — | — | — | |
| 11/05-etcd-backup | — | — | — | — | |
| 11/06-openshift-on-vsphere | — | — | — | — | |

---

## 📅 Last Session

```
Date        : 2026-10-03
Completed   : Course scaffolded; `git init -b main` run hands-on (no commit yet)
Current     : 00-foundations/03-git-refresh — Ram ran `git add .` (126 files staged, verified
              nothing sensitive). Commit-message convention taught; draft message given.
              Resume: Ram predicts `git log --oneline`, runs `git commit` (vi) → then test
              ignores with a fake kubeconfig + `git check-ignore -v` → create GitHub repo → push.
              Still-open questions: untracked-files=all count; would `git add .` stage an
              ignored kubeconfig?
Next up     : 00-foundations/01-yaml-basics
Guidance    : HIGH (default unless Ram explicitly says otherwise)
Lab         : WSL (+ GitHub)
Blockers    : none
Notes       : Ram is a beginner to containers, K8s, OpenShift and YAML — remembers only
              'what is a pod'. Wants as much detail as possible in course material.
```

---

## 📓 Session Log (newest first)

### 2026-10-08 — repo pushed to GitHub
- Added remote (typo `orign` → fixed with `git remote rename`), then the first push was
  rejected because the GitHub repo had its own README commit (unrelated histories).
  Combined them with `git rebase origin/main` and pushed with `-u`. `main` now tracks
  `origin/main`. Details and the rebase gap are logged in ~/git-learning/PROGRESS.md.
- Still open from 03-git-refresh: test ignores with a fake kubeconfig + `git check-ignore -v`.

### 2026-10-03 — course scaffold + git init (paused)
- Ran `git init -b main` in ~/openshift-learning himself. Predicted `git status` would list all
  126 files; actual: 16 entries (untracked folders collapsed). Explained default
  `--untracked-files=normal` and why `.gitignore` itself is untracked/should be committed.
- Gap found: hadn't considered that Git summarises untracked dirs — good probing material.
- Fixed a bug of my own in .gitignore before Ram used it: inline `# comments` after a pattern
  aren't comments in gitignore (they become part of the pattern).
- Ram ran `git add .` before the ignore check — safe this time (all files Claude-written, verified
  staged list), but habit noted: verify before `git add .` in this repo.
- Taught commit-message format (imperative subject ≤50, blank line, why-body at 72). Commit pending.
- Paused for other work. No commit/push yet.
- First session. Read git-learning CLAUDE.md/PROGRESS.md for learning style and Git status
  (Git side track: next is revert/reset L1, then .gitignore, forking, PRs).
- Ram set guidance default to HIGH unless stated otherwise; asked for maximum detail in material.
- Self-assessment: very basic Kubernetes memory (what a pod is), little Docker, YAML forgotten →
  start fully from scratch at Phase 00.
- Created the full scaffold: 12 phases, module READMEs + CHALLENGEs, INDEX, PROGRESS, CLAUDE.md, .gitignore.
- No hands-on learning yet.
