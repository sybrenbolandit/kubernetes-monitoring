# Kubernetes monitoring

## Setup

Before deploying the kubernetes resources in this repository the prometheus operator should be installed.

```helm install coreos/prometheus-operator --name prometheus-operator --namespace jenkins-project```

## Deploy

To deploy the kubernetes resources run the following command:

```cd deployment | kustomize build overlays/test | kubectl apply --record -f  -```
