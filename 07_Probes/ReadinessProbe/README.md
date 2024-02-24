# Readiness Probe

 - A readinessProbe é uma forma de o Kubernetes verificar se o seu container está pronto para receber tráfego, se ele está pronto para receber requisições vindas de fora.
 
 - Nesse arquivo readinessprobe.yaml estamos fazendo o teste a cada 10 segundos com o recurso protocolo http na porta 80, após duas verificações o container vai ser apto para receber requisições

       - kubectl apply -f readinessprobe.yaml
       - kubectl get deployments
    