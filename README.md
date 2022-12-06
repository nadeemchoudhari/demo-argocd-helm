
# ARGOCD to deploy helm charts on kubernetes.

## Installing Argocd on k8s as containers.

  To install ArgoCD on k8s: 

  1. Create namespace argocd 
  2. deploy argocd using kubeclt . 

```
   kubectl -n argocd apply -f https://raw.githubusercontent.com/argoproj/argo-cd/stable/manifests/install.yaml

```
### Get Admin Password :

once installed get initial admin password from argocd secrets. and decode with base64.

``` 
kubect -n argocd get secrets 

kubectl get secret argocd-initial-admin-secret -n argocd -o yaml 

echo <encryptedpassword> | base64 --decode
kubectl -n argocd port-forward svc/argocd-server 8000:443



```

Connect Login page at 