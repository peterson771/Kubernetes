# Disallow Root User

- é uma regra de segurança crítica no gerenciamento de clusters Kubernetes. Ela proíbe a execução de containers como usuário root dentro de Pods. Este controle ajuda a prevenir possíveis vulnerabilidades de segurança e a reforçar as melhores práticas no ambiente de contêineres.

### Política de Limites de Recursos

    kubectl apply -f disallow-root-user.yaml
    kubectl get clusterpolicies
    kubectl describe clusterpolicies.kyverno.io disallow-root-user
    