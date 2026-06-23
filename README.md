---
> 🚀 **Trial v0.30.0 is live!** The latest release is available for trial today — [get started in 5 minutes →](#try-v030-in-5-minutes)

# HyperCluster — Community

> **Bare-metal Kubernetes lifecycle over SSH — Kubespray + k3s, Cilium, KubeVirt, full Zyvor stack.**

![Version](https://img.shields.io/badge/version-v0.30.0-blue) ![Discussions](https://img.shields.io/github/discussions/hypersdk/hypercluster-community) ![Issues](https://img.shields.io/github/issues/hypersdk/hypercluster-community) ![License](https://img.shields.io/badge/license-Proprietary-red)

Public issue tracker and community feedback space for **HyperCluster** by [Zyvor AI Labs](https://zyvor.dev).
The source code is maintained in a private repository. This repo is for bug reports, feature requests, UX feedback, and community discussion.

---

## What's new in v0.30

- k3s path GPU support — installs NVIDIA device plugin and DCGM exporter automatically
- Air-gap bundle — download all images and charts for offline cluster bootstrap
- Desktop app v0.30 — Electron cluster studio with visual node health and one-click deploy
- Preflight parallelized — checks 10 nodes simultaneously, bootstrap time cut by 60%
- Zyvor platform stack guide updated — documented install order for Forge, Machina, PacketWolf on v0.30

---

## Why HyperCluster

| Problem | HyperCluster answer |
|---------|--------------------|
| Kubespray is powerful but raw Ansible | Opinionated wrapper with preflight, kubeconfig fetch, and smoke tests |
| Lab clusters need KubeVirt but setup is complex | k3s path installs Cilium + MetalLB + KubeVirt + CDI automatically |
| Day-2 platform stack is a separate undocumented project | Documented Zyvor stack install order — Forge, Machina, PacketWolf in sequence |
| macOS operators have no local cluster test environment | Desktop app + remote SSH deploy — test locally, deploy to bare metal |
| Cloud-specific tooling breaks on edge and air-gap | Pure SSH — no cloud provider, no special agents, air-gap ready |

---

## Architecture

```
┌──────────────────────────────────────────────────────────────┐
│  CLI          hypercluster — deploy · upgrade · scale · test │
├──────────────────────────────────────────────────────────────┤
│  Paths        Kubespray (Ansible) · k3s platform stack       │
├──────────────────────────────────────────────────────────────┤
│  Day-2        forge · machina · packetwolf install order     │
└──────────────────────────────────────────────────────────────┘
```

---

## Try v0.30 in 5 minutes

```bash
git clone https://github.com/hypersdk/hypercluster && cd hypercluster
git checkout v0.30.0
cp config/cluster.conf.example cluster.conf
# Edit cluster.conf — node IPs, SSH user, K8S_DISTRO (kubespray or k3s)

./hypercluster preflight   # validate SSH, ports, deps
./hypercluster deploy      # bootstrap Kubernetes
./hypercluster kubeconfig  # fetch kubeconfig → ~/.kube/config
./hypercluster test        # run smoke tests
```

**k3s lab (fastest path, includes KubeVirt):**
```bash
K8S_DISTRO=k3s ./hypercluster deploy
```

**Requirements:** SSH access from bootstrap machine, Ubuntu 22.04/24.04 or Rocky Linux 9 on nodes, 4 GB RAM minimum per node

---

## Report a bug

[Open a Bug Report →](../../issues/new?template=bug_report.yml)

Include: what you did, what happened, what you expected, your environment, screenshots or logs (redact secrets).

## Request a feature

[Open a Feature Request →](../../issues/new?template=feature_request.yml)

## UX feedback

[Open a UX Report →](../../issues/new?template=ux_feedback.yml)

## Ask a question

Use [GitHub Discussions](../../discussions) for open-ended questions, ideas, and roadmap conversations.

---

## Security

**Do not report security vulnerabilities publicly.**
Email **security@zyvor.dev** — see [SECURITY.md](SECURITY.md).

---

## Do not post

- Source code, internal configs, or architecture details
- API tokens, license keys, or credentials
- Private logs with sensitive data
- Security vulnerabilities — email security@zyvor.dev instead

---

## Join the community

⭐ [Star this repo](https://github.com/hypersdk/hypercluster-community) · 💬 [Open a Discussion](https://github.com/hypersdk/hypercluster-community/discussions) · 🐛 [Report a Bug](../../issues/new?template=bug_report.yml) · 📧 [hello@zyvor.dev](mailto:hello@zyvor.dev)

Maintained by [Zyvor AI Labs](https://zyvor.dev)
