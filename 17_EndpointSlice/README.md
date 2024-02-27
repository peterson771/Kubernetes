# EndpointSlice

- EndpointSlice é um recurso no Kubernetes que foi introduzido para melhorar a escalabilidade e eficiência na gestão de endpoints de serviço. Ele é parte do projeto "Service Topology", que visa aprimorar a funcionalidade de serviços e a comunicação entre Pods. 

      - kubectl apply -f my-pods.yaml
      - kubectl get pods -o wide
      - kubectl apply -f my-eps.yaml
      - kubectl get service
      - kubectl get endpointslice

- Criando um POD para testar o Endpointslice

      - kubectl run it -image debian teste-endpointslice
      - apt update && apt install curl dnsutils -y
      - nslookup my-eps-service
      - curl my-endpoints-service.default.svc.cluster.local

- Deletando todos os serviços e PODs criados.

      - kubectl delete pods -all
      - kubectl delete svc -all
      - kubectl delete endpointslice my-eps my-eps-2
