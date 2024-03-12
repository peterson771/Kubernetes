# PrometheusRule

- É utilizado quando você está trabalhando com o Prometheus para monitoramento. O Prometheus é uma solução de monitoramento e alerta de código aberto amplamente adotada para coletar e processar métricas de vários sistemas, incluindo clusters Kubernetes.

### Criando um PrometheusRule para monitorar uma aplicação Nginx.

    kubectl get namespace monitoring
    kubectl apply -f nginx-prometheus-rule.yaml
    kubectl get namespace monitoring