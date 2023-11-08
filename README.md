# mvp eks terraform
## Prerequisites
* aws
* terraform configured
* kubectl installed
  
## Configure kubectl
```
aws eks --region $(terraform output -raw region) update-kubeconfig \
    --name $(terraform output -raw cluster_name)
```
## Verify connection to your cluster
```
kubectl get nodes
```
## Helpful Additions
### metrics-server
```
kubectl apply -f https://github.com/kubernetes-sigs/metrics-server/releases/latest/download/components.yaml
```
### cert-manager
```
kubectl apply -f https://github.com/cert-manager/cert-manager/releases/download/v1.13.2/cert-manager.yaml
```
### argocd
[Argo CD](https://argo-cd.readthedocs.io/en/stable/getting_started/)