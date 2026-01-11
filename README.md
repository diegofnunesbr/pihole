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

## Configurar o acesso local para o Pi-hole

```bash
echo "192.168.1.3 pihole.local" | sudo tee -a /mnt/c/Windows/System32/drivers/etc/hosts
```

## Acessar o Pi-hole

https://pihole.local/

## Remover o Pi-hole

```bash
kubectl delete -f pihole/applications/argocd-pihole.yaml
kubectl delete namespace pihole
```
