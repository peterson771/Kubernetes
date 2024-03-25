# Affinity and Antiaffinity

- São conceitos que permitem que você defina regras para o agendamento de Pods em determinados Nodes. Com eles você pode definir regras para que Pods sejam agendados em Nodes específicos, ou até mesmo para que Pods não sejam agendados em Nodes específicos.


### Aplicando Labels nos Nodes.

- Levando que temos em produção 5 Workers

      kubectl label nodes prod-worker1 region=sa-east-1
      kubectl label nodes prod-worker1 az=sa-east-1a

      kubectl label nodes prod-worker2 region=sa-east-1
      kubectl label nodes prod-worker2 az=sa-east-1b

      kubectl label nodes prod-worker3 region=sa-east-1
      kubectl label nodes prod-worker3 az=sa-east-1c
      
      kubectl label nodes prod-worker4 region=us-east-1
      kubectl label nodes prod-worker4 az=us-east-1a

      kubectl label nodes prod-worker5 region=us-east-1
      kubectl label nodes prod-worker5 az=us-east-1b

      kubectl get nodes prod-worker1 --show-Labels


### Aplicando o Affinity em um Deployment

    kubectl apply -f  nginx_affinity.yaml

### Aplicando o AntiAffinity em um Deployment

    kubectl apply -f  nginx_affinity.yaml