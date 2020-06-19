# Kubernetes monitoring

## Setup

Before deploying the kubernetes resources in this repository the prometheus operator should be installed.

```
helm -n <namespace> install prometheus stable/prometheus-operator \
                           --set nodeExporter.enabled=false       \
                           --set kubeStateMetrics.enabled=false
```

## Deploy

To deploy the kubernetes resources run the following command:

```
cd deployment/helm/kubernetes-monitoring
    
helm secrets install kubernetes-monitoring . \
      --namespace <namespace>                \
      --values environments/test/values.yaml \
      --values environments/test/secrets.yaml
                     
```
