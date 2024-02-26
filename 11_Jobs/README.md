

# JOBS

- É usado para garantir que a tarefa seja concluída, garantindo que os pods associados a ela sejam executados até a finalização, independentemente do número de réplicas
     - Alguns códigos mais comuns:
     - Code 1: Application Error
     - Code 126: Command invoke Error
     - Code 127: File or directory not found
     - Code 134: Adnormal termination
     - Code 137: Immediate termination
     - Code 139: Segmentation fault
     - Code 255: Exit status out of range
     - Code 0: Purposely stopped

# 
    - kubectl apply -f job.yaml
    - kubectl get job
    - kubectl describe job my-job
    - kubectl get pods
    - peterson@Minikube:~/K8S/10_JOBS$ for i in 1 2 3 4 5 6; do echo Seu número da sorte é: $i = $((1 + RANDOM % 70)); done