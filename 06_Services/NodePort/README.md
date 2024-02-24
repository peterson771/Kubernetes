# NodePort

 - O NodePort é um tipo de serviço no Kubernetes que expõe um aplicativo fora do cluster, tornando-o acessível em um determinado porto em todos os nós do cluster.

       - kubectl get services
       - kubectl apply -f nodeport-service.yaml
       - kubectl apply -f web-pod.yaml
       - kubectl get all
       - kubectl describe service frontend-service-nodeport
       - minikube service --url frontend-service-nodeport --namespace=default
       - peterson@Minikube:~/K8S/07_Services$ minikube service --url frontend-service-nodeport --namespace=default

# Removendo as configurações
    - kubectl get all
    - kubectl delete service frontend-service-nodeport
    - kubectl delete pod web-pod

