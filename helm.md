# Installation des charts Helm

## Installation de l'ingress controller nginx

```shell
helm repo add bitnami https://charts.bitnami.com/bitnami
helm repo add mesosphere-stable https://mesosphere.github.io/charts/stable

helm repo update

helm install nginx-ingress bitnami/nginx-ingress-controller \
  --create-namespace \
  --namespace ingress-nginx \
  --set service.type=LoadBalancer
  
helm install kubecost mesosphere-stable/kubecost \
  --create-namespace \
  --namespace kubecost \
  --set grafana.sidecar.dashboards.enabled=true
```


