

# Deamonset.

- O funcionamento dele é semelhante ao replicaset ou deployments, mais ele garante que 1 POD seja criado em cada um dos NODES do K8S. Com isso vamos precisar adicionar mais um  node em nosso servidor do Minikube

      - kubectl get nodes 
      - kubectl node add
      - kubectl get nodes
      - kubectl apply -f my-daemonset
      - kubectl get daemonset
      - kubectl get pods
      - kubectl get pods 
      - kubectl get pods -o wide --fiel-selector spec.nodeName=minikube 
      - kubectl delete daemonset
      - minikube delete
      - minikube start --node 3



### Deamonset Orphan Pods ( - Podemos excluir um daemonset e manter os PODs que estão rodando dentro dele)     

        - kubectl apply -f my-daemonset 
        - kubectl get pods
        - kuebctl delete daemonset my-daemonset --cascade=orphan
        - kubectl get daemonset
        - kubectl get pods -o wide

    
### Criando Deamonset dentro de NODES específicos por labels

         - kubectl apply -f my-daemonset-specificnodes.yaml
         - kubectl get nodes --show-labels | grep disktype
         - kubectl labels nodes minikube-04 disktype=ssd 

### Criando Deamonset dentro de NODES específicos por nome dos NODES

        - kubectl apply -f my-daemonset-specificnodes-nodename.yaml


