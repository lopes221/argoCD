<h1 align="center">
  <br>
<img src="docs/images/dev_logo_rvb.png"  alt="accessibility text">
  <br>
  ArgoCD demo
  
  <br>
</h1>


Simple demo of Nginx where we will be covering a nginx deployment.

```
argoCD/
├── README.md
├── argoDeployment
│   ├── app.yaml
│   └── install.yaml
└── nginx
    ├── deployment
    │   └── nginx-deployment.yaml
    ├── namespace
    │   └── namespace.yaml
    └── service
        └── nginx-service.yaml
```

# Get Started

```
# Clone repo
git clone https://github.com/lopes221/argoCD.git
```

```
# Make sure you're in the correct cluster
kubectl config current-context
```

```
# Create namespace
kubectl create namespace argocd
```

```
# Deploy ArgoCD on argocd namespace
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


# References
-   https://argo-cd.readthedocs.io/en/stable/getting_started/


## Author

Anderson Soares Lopes

[![GitHub](https://skillicons.dev/icons?i=github)](https://github.com/lopes221)
[![Linkedin](https://skillicons.dev/icons?i=linkedin)](https://www.linkedin.com/in/andersonsoaresl/)