# Event Ease IAC
This repository contains the configuration files for the [Event Ease](https://github.com/omarade/EventEase) project.

## Commands

```bash
# ArgoCD
# install ArgoCD in k8s
kubectl create namespace argocd
kubectl apply -n argocd -f https://raw.githubusercontent.com/argoproj/argo-cd/stable/manifests/install.yaml

# access ArgoCD UI
kubectl get svc -n argocd
kubectl port-forward svc/argocd-server 8080:443 -n argocd

# login with admin user and below token (as in documentation):
kubectl -n argocd get secret argocd-initial-admin-secret -o jsonpath="{.data.password}" | base64 --decode && echo

# you can change and delete init password



# Monitoring with Prometheus & Grafana
# the app should be running on Kubernetes
kubectl create namespace monitoring
kubectl apply -f kubernetes-prometheus
kubectl apply -f kubernetes-grafana
```
</br>

## Links

* Install ArgoCD: https://argo-cd.readthedocs.io/en/stable/getting_started/#1-install-argo-cd

* Login to ArgoCD: https://argo-cd.readthedocs.io/en/stable/getting_started/#4-login-using-the-cli

* ArgoCD Configuration: https://argo-cd.readthedocs.io/en/stable/operator-manual/declarative-setup/

* Prometheus Setup: https://devopscube.com/setup-prometheus-monitoring-on-kubernetes/

* Grafana Setup: https://devopscube.com/setup-grafana-kubernetes/