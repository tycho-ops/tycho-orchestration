> 🇫🇷 [Version française](README.fr.md)

# Tycho Orchestration

`@tycho/orchestration` is the Tycho module behind `tycho orchestration`. Its purpose is to deploy catalogue recipes on Kubernetes: bootstrap the ingress (Traefik v3) and Cert-Manager, issue TLS certificates, deploy workload stacks, check cluster health and drive Terraform. For the overall picture, see the [Tycho core README](https://git.qtrn.io/tycho/tycho).

## Install

```bash
tycho module add orchestration
```

`status` needs `kubectl` configured for the target cluster.

## Usage

```bash
tycho orchestration bootstrap          # bootstrap Traefik v3 ingress, Cert-Manager and TLS
tycho orchestration cert <domain>      # issue a Let's Encrypt certificate
tycho orchestration deploy <stack>     # deploy a Kubernetes workload stack
tycho orchestration status             # list nodes and pods (kubectl get nodes,pods -A)
tycho orchestration tf [plan]          # Terraform orchestration
```

Without a command, or with an unknown one, the module prints its usage.

## Status

Early skeleton. Only `status` does real work: it calls `kubectl get nodes,pods -A`. `bootstrap`, `cert`, `deploy` and `tf` are placeholders that only print a message.

## Licence

AGPL-3.0-only, © Quatrain Technologies. Source: https://git.qtrn.io/tycho/tycho-orchestration
