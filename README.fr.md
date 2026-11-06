> 🇬🇧 [English version](README.md)

# Tycho Orchestration

`@tycho/orchestration` est le module Tycho derrière `tycho orchestration`. Il a pour but de déployer les recettes du catalogue sur Kubernetes : amorcer l'ingress (Traefik v3) et Cert-Manager, émettre des certificats TLS, déployer des stacks applicatives, vérifier l'état du cluster et piloter Terraform. Pour la vue d'ensemble, voir le [README du cœur Tycho](https://git.qtrn.io/tycho/tycho).

## Installation

```bash
tycho module add orchestration
```

`status` nécessite `kubectl` configuré pour le cluster cible.

## Utilisation

```bash
tycho orchestration bootstrap          # amorcer l'ingress Traefik v3, Cert-Manager et TLS
tycho orchestration cert <domain>      # émettre un certificat Let's Encrypt
tycho orchestration deploy <stack>     # déployer une stack Kubernetes
tycho orchestration status             # lister nœuds et pods (kubectl get nodes,pods -A)
tycho orchestration tf [plan]          # orchestration Terraform
```

Sans commande, ou avec une commande inconnue, le module affiche son aide.

## Statut

Squelette précoce. Seul `status` fait un vrai travail : il appelle `kubectl get nodes,pods -A`. `bootstrap`, `cert`, `deploy` et `tf` sont des emplacements réservés qui affichent seulement un message.

## Licence

AGPL-3.0-only, © Quatrain Technologies. Source : https://git.qtrn.io/tycho/tycho-orchestration
