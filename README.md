# Pi-hole

Este guia descreve a instalação e remoção do **Pi-hole** em um cluster Kubernetes, utilizando o manifesto `pihole.yaml`.

## Pré-requisitos

- `Kubernetes` instalado
- `kubectl` instalado
- `Ingress Controller NGINX` instalado
- `cert-manager` instalado
- `ClusterIssuer` instalado

---

## Instalar o Pi-hole

```bash
git clone https://github.com/diegofnunesbr/pihole.git
kubectl apply -f pihole/applications/argocd-pihole.yaml
```

## Configurar o acesso local do Pi-hole no Windows

**Este comando deve ser executado em um PowerShell aberto como Administrador.**

> Execute o comando abaixo em um **PowerShell aberto como Administrador**.

```powershell (mode ADM)
Add-Content C:\Windows\System32\drivers\etc\hosts "192.168.1.3 pihole.local"
```

## Acessar o Pi-hole

https://pihole.local/

## Remover o Pi-hole

```bash
kubectl delete -f pihole/applications/argocd-pihole.yaml
kubectl delete namespace pihole
```
