# Exclude

- Ao aplicar esta política, todos os Pods novos ou atualizados precisam ter limites de recursos claramente definidos, exceto aqueles no namespace ProdTest. Isso assegura uma melhor gestão de recursos e evita situações onde alguns Pods possam monopolizar recursos em detrimento de outros.

### Política de Limites de Recursos

    kubectl apply -f policy_exclude.yaml
    kubectl get clusterpolicies
    kubectl describe clusterpolicies.kyverno.io policy_exclude
    
