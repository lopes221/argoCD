# argoCD deployment

## Deployment steps
https://argo-cd.readthedocs.io/en/stable/getting_started/

## Create namespace
kubectl create namespace argocd

## Apply manifests
kubectl apply -f argoDeployment/install.yaml -n argocd

## Get Login credential
 kubectl get secret -n argocd argocd-initial-admin-secret -o jsonpath='{.data.*}' | base64 -d

## Apply argoCD application
kubectl apply -f argoDeployment/app.yaml

<!-- 
Install nginx-ingress ( In case of ingress to be used )

helm repo add ingress-nginx https://kubernetes.github.io/ingress-nginx

helm repo update 

helm install -n nginx-controller nginx-controller ingress-nginx/ingress-nginx --set controller.service.annotations."service\.beta\.kubernetes\.io azure-load-balancer-health-probe-request-path"=/healthz  -->

