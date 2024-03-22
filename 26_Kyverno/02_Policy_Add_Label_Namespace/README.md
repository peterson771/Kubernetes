# Policy Add Label Namespace

- Essa policy é projetada para automatizar a adição de um label específico a todos os Namespaces em um cluster Kubernetes. Esta abordagem é essencial para a organização, monitoramento e controle de acesso em ambientes complexos..

### Política de Limites de Recursos

    kubectl apply -f add-label-namespace.yaml
    kubectl get clusterpolicies
    kubectl describe clusterpolicies.kyverno.io add-label-namespace
    kubectl create namespace Dev
    kubectl describe namespace Dev

- Em todos os Namespaces desse cluster vai ter uma label informando: Cluster: "Prod"