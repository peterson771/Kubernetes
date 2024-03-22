# Policy Require Resources Limits

- Nessa politica vamos garantir que todos os PODS criados dentro do cluster tenham o limites de CPU e Memória definidos.

### Política de Limites de Recursos

    kubectl apply -f require-resources-limits.yaml
    kubectl get clusterpolicies
    kubectl describe clusterpolicies.kyverno.io require-cpu-memory-limits
    kubectl apply -f pod.yaml
- Ao tentar criar o POD retorna a mensagem de erro que não podemos criar um sem os limites de recursos