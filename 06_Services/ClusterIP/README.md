# ClusterIP 
  - Permite a comunicação interna dentro do cluster. 
  
        - kubectl get services
        - kubectl apply -f clusterip-service-apache.yaml
        - kubectl apply -f clusterip-service-tomcat.yaml
        - kubectl apply -f pods.yaml
        - kubectl get services
        - kubectl get pods
# Criando um POD debian e testando a conectividade entre os pods
    - kubectl run -it debian-pod --image=debian bash
    - apt update -y
    - apt install curl -y
    - root@debian-pod:/# curl 10.100.9.40:80 (retorno apahe)
    - root@debian-pod:/# curl 10.100.9.40:8080 (retorno tomcat)

# Analisando o serviço ClusterIP
    - kubectl get services
    - kubectl get services --all-namespaces -o wide
    - kubectl describe services frontend-services

# Deletando os serviços e pods.
    - kubectl get all
    - kubectl delete services frontend-service --namespace=default
    - kubectl delete pods debian-pod web-pod
    