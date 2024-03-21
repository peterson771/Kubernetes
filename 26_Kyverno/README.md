# Kyverno

- É uma ferramenta de gerenciamento de políticas para Kubernetes, focada na automação de várias tarefas relacionadas à segurança e configuração dos clusters de Kubernetes. Ele permite que você defina, gerencie e aplique políticas de forma declarativa para garantir que os clusters e suas cargas de trabalho estejam em conformidade com as regras e normas definidas.

### Instalação do Kyverno via Helm

    helm repo add kyverno https://kyverno.github.io/kyverno/
    helm repo update
    helm install kyverno kyverno/kyverno --namespace kyverno --create-namespace
    kubectl get pods -n kyverno
    kubectl get crd | grep kyverno



