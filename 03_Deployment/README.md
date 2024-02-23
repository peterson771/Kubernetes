
# Deployment

- Deployments:  referem-se a um recurso que permite gerenciar a implantação de aplicativos em clusters Kubernetes. Um "Deployment" fornece uma maneira declarativa de definir o estado desejado para os aplicativos e gerenciar as atualizações para esses aplicativos ao longo do tempo.

# Verificação dos Deployments
    - kubectl get deployments
    - kubectl get deployments --all-namespaces

# Criando um Deployment através de uma arquivo Yaml (deployments.yaml)
     - kubectl apply -f deployments.yaml
     - kubectl get deployments  
     - kubectl describe deployments frontend-deployment
     - kubectl get deployments -o wide

# Quando criamos um deployment automaticamente o K8S também cria um Replicaset
     - kubectl get replicaset

# Rollout
 - Após efetuar a troca da imagem para nginx:1.18.0 e aplicar o comando kubectl apply -f deployments.yaml a imagem do Deployment foi alterada e conseguimos verificar através dos comandos:

         - kubectl rollout status deployment/frontend-deployment
         - kubectl rollout history deployment/frontend-deployment

# Rollback
 - Com o Rollback conseguimos voltar a uma atualização aplicada no Deployment

   - Listando as altrações com o comando:
            - kubectl rollout history deployment/frontend-deployment

  - Pegando as informações que foram feitas em umas das atualizações
         - kubectl rollout history deployment/frontend-deployment --revision=2

  - Com o comando undo voltamos o estado do nosso deployment após a atualizção:
            - kubectl rollout undo deployment/frontend-deployment

  - Ou podemos especificar a uma atualização específica.
            - kubectl rollout undo deployment/frontend-deployment --to-revision=5
      


