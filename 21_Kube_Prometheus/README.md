# Kube-Prometheus

- É um projeto que fornece configurações e regras predefinidas para monitorar ambientes Kubernetes usando o Prometheus. Ele é uma implementação pronta para uso que inclui uma variedade de componentes do ecossistema Prometheus adaptados para ambientes Kubernetes.
- Ele tem um conjunto de ferramentas que monitoram nosso cluster K8S: Prometheus Operator, Node Exporter, Kube-state-metrics, Alertmanager e o Grafana.

### Instalação do Kube-Prometheus.

    git clone https://github.com/prometheus-operator/kube-prometheus
    cd kube-prometheus
    kubectl create -f manifests/setup
    kubectl get namespace
    kubectl get servicemonitors -A
    kubectl apply -f manifests/
    kubectl get pods -n monitoring

