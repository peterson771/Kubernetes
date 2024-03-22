# Policy Generate ConfigMap for Namespaces

- É uma estratégia prática no gerenciamento de Kubernetes para automatizar a criação de ConfigMaps em Namespaces. Esta política simplifica a configuração e a gestão de múltiplos ambientes dentro de um cluster.

### Política de Limites de Recursos

    kubectl apply -f generate-configmap-for-namespace.yaml
    kubectl get clusterpolicies
    kubectl describe clusterpolicies.kyverno.io generate-namespace-configmap
    

- Em todos os Namespaces desse cluster vai ter uma label informando: Cluster: "Prod"