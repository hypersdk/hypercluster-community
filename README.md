# Hypercluster — Community

> **Bare-metal Kubernetes lifecycle over SSH — Kubespray + k3s, Cilium, KubeVirt, full Zyvor stack**

Public issue tracker and community feedback space for **Hypercluster** by [Zyvor AI Labs](https://zyvor.dev).

The source code is maintained in a private repository. This repo is for:
- Bug reports
- Feature requests
- UX feedback
- Documentation gaps
- Questions and discussion

---

## Key features

- Kubespray (Ansible) and k3s deployment paths
- Automated kubeconfig fetch after deploy
- k3s path pre-installs: Cilium, cert-manager, MetalLB, KubeVirt, CDI
- Preflight checks — SSH, port, and dependency validation
- Platform smoke tests post-deploy
- Documented Zyvor platform stack install order (Forge, Machina, PacketWolf)
- Desktop Electron cluster studio
- Pure SSH — no cloud provider, no special agents, air-gap ready

---

## Installation

**Deploy a cluster:**
```bash
git clone https://github.com/hypersdk/hypercluster && cd hypercluster
cp config/cluster.conf.example cluster.conf
# Edit cluster.conf — set node IPs, SSH user, K8S_DISTRO (kubespray or k3s)

./hypercluster preflight   # check connectivity and deps
./hypercluster deploy      # bootstrap Kubernetes
./hypercluster kubeconfig  # fetch kubeconfig to ~/.kube/config
./hypercluster test        # run platform smoke tests
```

**k3s lab (fast, KubeVirt included):**
```bash
K8S_DISTRO=k3s ./hypercluster deploy
# Installs: k3s + Cilium + cert-manager + MetalLB + KubeVirt + CDI
```

**Requirements:** SSH access from bootstrap machine, Ubuntu 22.04/24.04 or Rocky Linux 9 on nodes, 4 GB RAM per node minimum

---

## Report a bug

[Open a Bug Report →](../../issues/new?template=bug_report.yml)

Include: what you did, what happened, what you expected, your environment, and screenshots/logs (redact secrets).

## Request a feature

[Open a Feature Request →](../../issues/new?template=feature_request.yml)

## UX feedback

[Open a UX Feedback →](../../issues/new?template=ux_feedback.yml)

## Ask a question

Use [GitHub Discussions](../../discussions) for open-ended questions, ideas, and roadmap conversations.

---

## Security

**Do not report security vulnerabilities publicly.**

Email **security@zyvor.dev** — see [SECURITY.md](SECURITY.md).

---

## Do not post

- Source code or internal configuration
- API tokens, license keys, or credentials  
- Private logs with sensitive data
- Security vulnerabilities (email security@zyvor.dev)

---

Maintained by [Zyvor AI Labs](https://zyvor.dev)
