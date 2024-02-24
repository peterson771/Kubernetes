# Resources

 - O Kubernetes oferece várias maneiras de gerenciar recursos para garantir que os aplicativos implantados no cluster usem os recursos de maneira eficiente e justa. 

 Nesse arquivo resources-pod.yaml podemos ver que existem dois containers dentro de um POD mais cada um tem seu recurso definido

       - kubectl apply -f resources-pod.yaml
       - kubectl get pods 
       - kubectl describe pods resources-pod