
# Replicaset

 - ReplicaSet é utilizado para garantir que um número específico de réplicas (pods) de um aplicativo esteja sempre em execução 
 
 - O Kubernetes monitora o estado real dos pods e fará ajustes conforme necessário para garantir que o número de réplicas seja mantido.


# Comandos úteis

- Verificação dos Replicaset
    - kubectl get replicaset
    - kubectl get replicaset --all-namespaces

- Criando Replicaset através de um arquivo Yaml (replicaset.yaml)
    - kubectl apply -f replicaset.yaml
    - kubectl describe replicaset primeiro-replicaset
    - kubectl get replicaset -o wide

- Aumentando ou dimiuindo o numero de replicas.
  - kubectl scale replicaset primeiro-replicaset --replicas=10
  - kubectl get pods
  - kubectl scale replicaset primeiro-replicaset --replicas=2
  - kubectl get pods

- Deletando um replicaset
  - kubectl delete replicaset primeiro-replicaset