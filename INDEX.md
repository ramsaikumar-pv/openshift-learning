# 📚 OpenShift Learning — Index

> A self-paced Red Hat OpenShift course, from zero (YAML and containers) to cluster admin.
> Work through phases in order. Each module has a README (outline) and CHALLENGE (ladder + session write-back).
> Progress lives in `PROGRESS.md`.

---

## 🗂️ 00 — Foundations
*The tools you need before touching a container: YAML, the RHEL bits of Linux that containers rely on, and enough Git to keep your manifests safe.*

| Module | What You Learn | Est. Time | Lab | Status |
|--------|---------------|-----------|-----|--------|
| [01-yaml-basics](00-foundations/01-yaml-basics/README.md) | Key/value pairs and why indentation (spaces, never tabs) is the syntax; Maps (dictionaries) vs lists (sequences); Scalars and types | 60 min | WSL | ⏳ |
| [02-rhel-linux-for-containers](00-foundations/02-rhel-linux-for-containers/README.md) | Linux namespaces (pid, net, mnt, uts, ipc, user); cgroups v2; SELinux basics | 2–3 sessions | WSL RHEL | ⏳ |
| [03-git-refresh](00-foundations/03-git-refresh/README.md) | Initialise this course repo and push it to GitHub (ramsaikumar-pv); `.gitignore` for kubeconfigs, pull secrets, keys and install state; Verify ignores with `git status` and `git check-ignore -v` | 30 min | WSL GH | 🔄 |

---

## 🗂️ 01 — Containers with Podman
*Learn containers on your own laptop with Podman — the Red Hat container engine. Everything here carries straight into OpenShift.*

| Module | What You Learn | Est. Time | Lab | Status |
|--------|---------------|-----------|-----|--------|
| [01-what-is-a-container](01-containers-podman/01-what-is-a-container/README.md) | Container vs virtual machine (shared kernel vs own kernel); Image vs container (template vs running instance); OCI standard | 45 min | P | 🔒 |
| [02-images-and-registries](01-containers-podman/02-images-and-registries/README.md) | Image layers and how they're shared/cached; Fully-qualified image names; Tags vs digests (`@sha256 | 60 min | P | 🔒 |
| [03-ports](01-containers-podman/03-ports/README.md) | Each container gets its own network namespace; Publishing ports with `-p hostPort; Why the app must listen on 0.0.0.0, not 127.0.0.1 | 45 min | P | 🔒 |
| [04-volumes](01-containers-podman/04-volumes/README.md) | Container filesystems are ephemeral; Bind mounts vs named volumes; SELinux relabelling with ` | 60 min | P | 🔒 |
| [05-containerfiles](01-containers-podman/05-containerfiles/README.md) | Containerfile instructions; CMD vs ENTRYPOINT and how arguments combine; Layer caching | 2 sessions | P | 🔒 |
| [06-rootless](01-containers-podman/06-rootless/README.md) | User namespaces; How subuid/subgid ranges are used; Where rootless storage lives (`~/.local/share/containers`) | 45 min | P | 🔒 |
| [07-podman-pods](01-containers-podman/07-podman-pods/README.md) | A pod = containers sharing one network namespace (and optionally more); The infra container that holds the pod's namespaces; Containers in a pod talk over `localhost` | 60 min | P | 🔒 |

---

## 🗂️ 02 — OpenShift core
*Your first real cluster. Understand the architecture, drive it with `oc` and the console, and deploy the Zomato app with Deployments, Services and Routes.*

| Module | What You Learn | Est. Time | Lab | Status |
|--------|---------------|-----------|-----|--------|
| [01-architecture](02-openshift-core/01-architecture/README.md) | Control plane; Worker nodes; Desired state vs actual state | 60 min | S C | 🔒 |
| [02-console-and-oc](02-openshift-core/02-console-and-oc/README.md) | Install `oc` and log in (`oc login` with a token); `oc whoami`, `oc whoami --show-console`; `oc get`, `oc describe`, `oc explain`, `-o yaml`, `-o wide` | 60 min | S | 🔒 |
| [03-projects](02-openshift-core/03-projects/README.md) | Namespaces isolate names, quotas, permissions and network policy; A Project = namespace + OpenShift metadata + request workflow; `oc new-project`, `oc project`, `oc projects` | 30 min | S C | 🔒 |
| [04-pods-and-labels](02-openshift-core/04-pods-and-labels/README.md) | Write a Pod manifest from scratch, piece by piece; `oc apply -f`, `oc get pods`, `oc describe pod`, `oc logs`, `oc exec`, `oc delete`; Pod phases (Pending, Running, Succeeded, Failed) and container states/reasons | 2 sessions | S | 🔒 |
| [05-deployments-replicasets](02-openshift-core/05-deployments-replicasets/README.md) | Deployment → ReplicaSet → Pods ownership chain; Write a Deployment manifest (replicas, selector, template); Self-healing | 60 min | S | 🔒 |
| [06-services](02-openshift-core/06-services/README.md) | Why pods need a stable address (pod IPs change); ClusterIP Service; Endpoints / EndpointSlices | 60 min | S | 🔒 |
| [07-routes](02-openshift-core/07-routes/README.md) | Route = external hostname → Service, served by the OpenShift router (HAProxy); `oc expose service`, and the equivalent Route YAML; Route vs Kubernetes Ingress (OpenShift supports both) | 60 min | S | 🔒 |
| [08-scaling-and-rollouts](02-openshift-core/08-scaling-and-rollouts/README.md) | `oc scale deployment --replicas`; RollingUpdate strategy; Recreate strategy and when to use it | 60 min | S | 🔒 |

---

## 🗂️ 03 — Config and health
*Make the Zomato app configurable, safe with secrets, self-healing with probes, and well-behaved with resources and autoscaling.*

| Module | What You Learn | Est. Time | Lab | Status |
|--------|---------------|-----------|-----|--------|
| [01-configmaps](03-config-and-health/01-configmaps/README.md) | Create ConfigMaps from literals, files and YAML; Consume as env vars (`env`, `envFrom`) and as mounted files; What updates live (mounted files) vs needs a restart (env vars) | 45 min | S | 🔒 |
| [02-secrets](03-config-and-health/02-secrets/README.md) | Secret types; base64 is encoding, not encryption; Consume as env vars and as files | 45 min | S | 🔒 |
| [03-probes](03-config-and-health/03-probes/README.md) | Liveness (restart if dead), readiness (remove from Service if not ready), startup (protect slow starters); Probe types; Tuning | 60 min | S | 🔒 |
| [04-requests-limits](03-config-and-health/04-requests-limits/README.md) | Requests (scheduling guarantee) vs limits (hard cap); CPU over limit = throttled; memory over limit = OOMKilled; QoS classes | 60 min | S C | 🔒 |
| [05-hpa](03-config-and-health/05-hpa/README.md) | HPA scales replicas on CPU/memory (or custom metrics); Why HPA needs requests set; `oc autoscale` and HPA YAML (autoscaling/v2) | 45 min | S C | 🔒 |
| [06-graceful-shutdown](03-config-and-health/06-graceful-shutdown/README.md) | Pod termination sequence; `terminationGracePeriodSeconds` and `preStop` hooks; The race between endpoint removal and process exit | 45 min | S | 🔒 |
| [07-sidecars](03-config-and-health/07-sidecars/README.md) | Init containers; Sidecar pattern; Native sidecars (`restartPolicy | 60 min | S | 🔒 |

---

## 🗂️ 04 — Storage
*Give the Zomato database real persistent storage, and connect it to what you run at work: vSphere CSI.*

| Module | What You Learn | Est. Time | Lab | Status |
|--------|---------------|-----------|-----|--------|
| [01-pv-pvc](04-storage/01-pv-pvc/README.md) | PV (the disk) vs PVC (the request for a disk); Access modes; Binding, and reclaim policies | 60 min | S C | 🔒 |
| [02-storageclasses](04-storage/02-storageclasses/README.md) | Dynamic provisioning via a StorageClass; Default StorageClass; `volumeBindingMode | 45 min | S C | 🔒 |
| [03-statefulsets](04-storage/03-statefulsets/README.md) | Stable pod names (db-0, db-1) and ordered start/stop; Headless Services for stable per-pod DNS; `volumeClaimTemplates` | 60 min | S C | 🔒 |
| [04-vsphere-csi](04-storage/04-vsphere-csi/README.md) | CSI; vSphere CSI driver; How a PVC becomes a VMDK attached to a node VM | 45 min | V C | 🔒 |

---

## 🗂️ 05 — Builds and images
*OpenShift can build images for you from source code. Learn S2I, BuildConfigs, ImageStreams and the internal registry.*

| Module | What You Learn | Est. Time | Lab | Status |
|--------|---------------|-----------|-----|--------|
| [01-s2i](05-builds-and-images/01-s2i/README.md) | What S2I does; `oc new-app <git-url>` and what it creates; Builder images (Python, Node.js, Java) | 60 min | S | 🔒 |
| [02-buildconfigs](05-builds-and-images/02-buildconfigs/README.md) | BuildConfig strategies; Triggers; `oc start-build`, `oc cancel-build`, build history | 60 min | S C | 🔒 |
| [03-imagestreams](05-builds-and-images/03-imagestreams/README.md) | ImageStream and ImageStreamTag; `oc import-image`, `oc tag`, scheduled imports; Image change triggers on Deployments (annotation) | 45 min | S C | 🔒 |
| [04-internal-registry](05-builds-and-images/04-internal-registry/README.md) | The integrated image registry and its operator; Exposing the registry route and pushing with Podman; Pull access across projects (`system | 45 min | C | 🔒 |

---

## 🗂️ 06 — Security
*Who can log in, what they can do, what identity pods run with, and what pods are allowed to do on the node.*

| Module | What You Learn | Est. Time | Lab | Status |
|--------|---------------|-----------|-----|--------|
| [01-authentication](06-security/01-authentication/README.md) | The OpenShift OAuth server and identity providers; kubeadmin and why to remove it; Configure an htpasswd identity provider | 60 min | C | 🔒 |
| [02-rbac](06-security/02-rbac/README.md) | Role vs ClusterRole, RoleBinding vs ClusterRoleBinding; Default roles; `oc adm policy add-role-to-user`, `oc auth can-i`, `oc auth can-i --as` | 60 min | C S | 🔒 |
| [03-serviceaccounts](06-security/03-serviceaccounts/README.md) | ServiceAccounts are identities for pods; Default SA per project; `serviceAccountName`; Projected, short-lived tokens | 45 min | S C | 🔒 |
| [04-sccs](06-security/04-sccs/README.md) | What SCCs control; `restricted-v2` (default), `nonroot-v2`, `anyuid`, `privileged`; Arbitrary UIDs and why images expecting root fail | 2 sessions | C S | 🔒 |

---

## 🗂️ 07 — Networking
*Services and Routes in depth, TLS, locking traffic down with NetworkPolicies, and how OVN-Kubernetes moves packets.*

| Module | What You Learn | Est. Time | Lab | Status |
|--------|---------------|-----------|-----|--------|
| [01-services-deep-dive](07-networking/01-services-deep-dive/README.md) | ClusterIP, NodePort, LoadBalancer, ExternalName, headless; sessionAffinity, named ports, multi-port Services; Services without selectors (pointing outside the cluster) | 60 min | S C | 🔒 |
| [02-routes-and-tls](07-networking/02-routes-and-tls/README.md) | Edge, passthrough and re-encrypt termination; Custom certificates and keys on Routes (keys never in Git!); insecureEdgeTerminationPolicy (Redirect) | 60 min | S C | 🔒 |
| [03-networkpolicies](07-networking/03-networkpolicies/README.md) | Default; Default-deny ingress, then allow what's needed; podSelector, namespaceSelector, ports | 60 min | S C | 🔒 |
| [04-ovn-kubernetes](07-networking/04-ovn-kubernetes/README.md) | CNI; OVN-K basics; EgressIP and egress firewall (concept) | 60 min | C | 🔒 |

---

## 🗂️ 08 — Operators
*Operators are how OpenShift runs itself and how you install complex software. Learn the pattern and OLM.*

| Module | What You Learn | Est. Time | Lab | Status |
|--------|---------------|-----------|-----|--------|
| [01-what-is-an-operator](08-operators/01-what-is-an-operator/README.md) | Custom Resource Definitions (CRDs) and Custom Resources; Operator = CRD + controller encoding ops knowledge; Cluster operators that run OpenShift itself (`oc get co`) | 45 min | C | 🔒 |
| [02-olm-and-operatorhub](08-operators/02-olm-and-operatorhub/README.md) | OperatorHub and CatalogSources; Subscription, InstallPlan, ClusterServiceVersion (CSV), OperatorGroup; Channels and automatic vs manual approval | 60 min | C | 🔒 |

---

## 🗂️ 09 — GitOps
*Package the Zomato app with Helm and Kustomize, then let OpenShift GitOps (ArgoCD) deploy it from your GitHub repo.*

| Module | What You Learn | Est. Time | Lab | Status |
|--------|---------------|-----------|-----|--------|
| [01-helm](09-gitops/01-helm/README.md) | Charts, values, templates, releases; `helm install/upgrade/rollback/uninstall`, `helm template`; Writing a small chart for the order service | 60 min | S C | 🔒 |
| [02-kustomize](09-gitops/02-kustomize/README.md) | Base + overlays, no templating; Patches (strategic merge, JSON 6902), images, namePrefix, configMapGenerator; `oc apply -k`, `oc kustomize` | 60 min | S C | 🔒 |
| [03-openshift-gitops-argocd](09-gitops/03-openshift-gitops-argocd/README.md) | Install the OpenShift GitOps operator; Application; Sync, self-heal, prune; drift detection | 2 sessions | C | 🔒 |

---

## 🗂️ 10 — Observability
*See what the cluster and the app are doing: metrics, alerts, logs, and a repeatable troubleshooting method.*

| Module | What You Learn | Est. Time | Lab | Status |
|--------|---------------|-----------|-----|--------|
| [01-monitoring](10-observability/01-monitoring/README.md) | Built-in Prometheus, Alertmanager and console dashboards; PromQL basics; User workload monitoring and ServiceMonitors | 60 min | C S | 🔒 |
| [02-logging](10-observability/02-logging/README.md) | `oc logs` (and `--previous`) vs aggregated logging; OpenShift Logging; Querying logs across pods | 60 min | C | 🔒 |
| [03-troubleshooting-workflows](10-observability/03-troubleshooting-workflows/README.md) | A repeatable method; `oc debug` (pods and nodes); `oc adm must-gather` and `inspect` | ongoing | S C | 🔒 |

---

## 🗂️ 11 — Cluster admin
*Install, run and upgrade clusters — including SNO on AWS and OpenShift on vSphere like at work.*

| Module | What You Learn | Est. Time | Lab | Status |
|--------|---------------|-----------|-----|--------|
| [01-installation-methods](11-cluster-admin/01-installation-methods/README.md) | IPI vs UPI vs Assisted Installer vs Agent-based; `install-config.yaml` anatomy (and keeping secrets out of Git); Bootstrap process at a high level | 60 min | A V | 🔒 |
| [02-sno-on-aws](11-cluster-admin/02-sno-on-aws/README.md) | SNO requirements and limits; Cost estimate and Budget alerts before you start; Install into the project's selected Region only | 2–3 sessions | A | 🔒 |
| [03-nodes-and-machineconfigs](11-cluster-admin/03-nodes-and-machineconfigs/README.md) | `oc get nodes`, cordon, drain, uncordon; MachineConfig, MachineConfigPool, Machine Config Operator; Machine API | 60 min | C A | 🔒 |
| [04-upgrades](11-cluster-admin/04-upgrades/README.md) | Update channels (stable, fast, candidate, eus); Cluster Version Operator and the update graph; Pre-upgrade checks and watching an upgrade | 45 min | A | 🔒 |
| [05-etcd-backup](11-cluster-admin/05-etcd-backup/README.md) | Why etcd backup is your last line of defence; `cluster-backup.sh` on a control plane node; Restore at a high level (and when not to) | 45 min | A C | 🔒 |
| [06-openshift-on-vsphere](11-cluster-admin/06-openshift-on-vsphere/README.md) | vSphere IPI vs UPI vs Agent-based on vSphere; Required vCenter permissions and networking (VIPs for API and ingress); vSphere CSI and storage policies (link Phase 4) | 60 min | V | 🔒 |

---

## 🧪 Lab key

| Code | Environment |
|---|---|
| WSL | 🐧 Ubuntu on WSL (your laptop) |
| RHEL | 🎩 A RHEL 9/10 machine — free Red Hat Developer subscription VM (Ubuntu WSL has no SELinux/firewalld by default) |
| P | 📦 Podman on WSL |
| S | ☁️ Developer Sandbox (free, namespace-level, no cluster-admin) |
| C | 💻 OpenShift Local / CRC on Windows (16 GB+ RAM, cluster-admin) |
| A | 🟧 AWS Single Node OpenShift (Paid plan, billed hourly — create → practice → destroy) |
| V | 🏢 vSphere — your work environment (read-only exploration unless you have a lab) |
| GH | 🐙 GitHub + your openshift-learning repo |

## 🔑 Status legend

| Icon | Meaning |
|---|---|
| ✅ | Completed hands-on |
| 🔄 | In progress |
| ⏳ | Up next |
| 🔒 | Locked — complete earlier phases first |

## ➕ Expanding

New module → folder in the right phase + row here + checkboxes in PROGRESS.md (status ⏳/🔒).
New phase → next number `12-<topic>/`, same three places.
