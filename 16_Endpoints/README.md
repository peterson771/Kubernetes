# Endpoint

- Ele pode ser usado para acessar os Pods que fazem parte desse serviço. Esses endpoints são gerenciados pelo kube-proxy e permitem a comunicação com os Pods por meio de um único ponto de acesso, independentemente de quantos Pods estão em execução.

      - kubectl apply -f my-endpoints-pods.yaml
      - kubectl get pods -o wide
      - kubectl apply -f my-endpoints-test.yaml
      - kubectl get endpoints
      - kubectl get service

- Criando um POD para testar o Endpoint

      - kubectl run it -image debian teste-endpoint  
      - apt update && apt install dnsutils -y
      - nslookup my-endpoints-service
      - apt intall curl -y 
      - curl my-endpoints-service.default.svc.cluster.local

