
# POD

 - "Pod" é a menor unidade de implantação e escalonamento. Ele representa um ambiente de execução para contêineres em um cluster Kubernetes. 
 
 - Um Pod pode conter um ou mais contêineres que compartilham o mesmo contexto e recursos, como endereço IP, namespace de rede e armazenamento local.


# Verificação dos PODs
    - kubectl get pods
    - kubectl get pods --all-namespace


# Criação PODs
    - kubectl run meu-primeiro-pod --image httpd
    - kubectl get pods -o wide

# Deletando PODs
     - kubectl delete pods meu-primeiro-pod

# Criando POD através de um arquivo Yaml (pod.yaml)
     - kubectl apply -f pod.yaml
     - kubectl describe pod primeiro-pod