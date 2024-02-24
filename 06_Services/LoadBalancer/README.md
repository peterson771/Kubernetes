# LoadBalancer

 - LoadBalancer é usado para expor um serviço para a Internet ou para uma rede externa, e normalmente é usado em ambientes de nuvem pública. Este tipo de serviço provisiona automaticamente um balanceador de carga externo que roteia o tráfego para os pods do serviço.

       - kubectl get services
       - kubectl apply -f loadbalancer-service.yaml
       - kubectl apply -f web-pod.yaml
       - kubectl get all
       - kubectl describe service frontend-service-loadbalancer
       - minikube service --url frontend-service-loadbalancer --namespace=default
       - peterson@Minikube:~/K8S/07_Services$ minikube service --url frontend-service-loadbalancer --namespace=default

# Removendo as configurações
    - kubectl get all
    - kubectl delete service frontend-service-balancer
    - kubectl delete pod web-pod

