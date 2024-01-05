# Setting helm chart with prometheus, grafana and loki

## Common
This readme use:
- Helm version v3.13.3
- kubectl version v1.28.4
- minikube version v1.28.3 on Docker 24.0.7   

Create namespace
```
kubectl create --namespace monitor
```
## Prometheus
```
CHART NAME: prometheus-25.8.2
CHART VERSION: 25.8.2
APP VERSION: 0.5.1
```

## Grafana
```
CHART NAME: grafana-operator
CHART VERSION: 3.5.12
APP VERSION: 5.6.0
```
## Loki
```
CHART NAME: grafana-loki
CHART VERSION: 2.11.20
APP VERSION: 2.9.3
```

## Debug
Use that manifest to create a Pod dnsutils
```
kubectl apply -f https://k8s.io/examples/admin/dns/dnsutils.yaml
```

Once that Pod is running, you can exec nslookup in that environment. If you see something like the following, DNS is working correctly.
```
kubectl exec -i -t dnsutils -- nslookup loki-gateway.monitor.svc.cluster.local
```