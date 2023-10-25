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
