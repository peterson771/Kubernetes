# Namespace 
 - Namespace eéum recurso que é usado para organizar e dividir recursos de um cluster em espaços isolados. Os namespaces fornecem uma forma de criar múltiplos ambientes virtuais em um único cluster Kubernetes. Exemplo: (Frontend, Backend, Middleware etc).

# Comandos úteis
      - kubectl get namespaces
      - kubectl get pods -n kube-system
    
# Criando Namespace
    - kubectl create namespace teste
    - kubectl apply -f tomcat-pod.yaml --namespace=teste
    - kubectl get pods -n teste

# Alterando o namespace default
    - kubectl config set-context --current --namespace=teste
    - kubectl config set-context --current --namespace=default
    - kubectl delete namespace teste

# Criando um namespace através de um arquivo yaml

    -kubectl apply -f backend-namespace.yaml
    - kubectl get namespace
    - kubectl apply -f redis-pod.yaml --namespace=backend-ns
    - kubectl apply -f tomcat-pod.yaml --namespace=backend
    - kubectl delete pod tomcat-pod -n backend-ns