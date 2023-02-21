<h1 align="center">
  <br>
<img src="docs/images/dev_logo_rvb.png"  alt="accessibility text">
  <br>
  ArgoCD demo
  <br>
</h1>

Simple demonstration of ArgoCD on AKS.

# Get Started


```
#Create namespace
kubectl create namespace argocd
```

```
# Deploy ArgoCD
kubectl apply -f argoDeployment/install.yaml -n argocd
```

```
# Get ArgoCD secret for user admin login
 kubectl get secret -n argocd argocd-initial-admin-secret -o jsonpath='{.data.*}' | base64 -d
```

```
# Deploy an ArgoCD app
kubectl apply -f argoDeployment/app.yaml -n argocd
```

```
#Create namespace
kubectl create namespace argocd
```