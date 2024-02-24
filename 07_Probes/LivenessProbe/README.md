# LivenessProbes

 - A livenessProbe é a nossa probe de verificação de integridade, o que ela faz é verificar se o que está rodando dentro do Pod está saudável. O que fazemos é criar uma forma de testar se o que temos dentro do Pod está respondendo conforme esperado. Se por acaso o teste falhar, o Pod será reiniciado.

 - Nesse arquivo livenessprobe-tcpsocket.yaml estamos fazendo o teste a cada 10 segundos com o recurso tcpsocket na porta 80, se tivermos acima de 3 erros de verificação o K8S vai reiniciar automaticamente o POD

       - kubectl apply -f livenessprobe-tcpsocket.yaml
       - kubectl get deployments
     
- - Nesse arquivo livenessprobe-httpget.yaml estamos fazendo o teste a cada 10 segundos na porta 80, se tivermos acima de 3 erros de verificação o K8S vai reiniciar automaticamente o POD

        - kubectl apply -f livenessprobe-httpget.yaml
        - kubectl get deployments
        - kubectl describe pod nginx-deployment-7455766945-4sbgc 
- Nessa linha temos a informação que nossa Probe está funcionando corretamente: 

         - Liveness:     http-get http://:80/ delay=10s timeout=5s period=10s #success=1 #failure=3

- Um dos testes que podemos fazer é alterar a porta do arquivo livenessprobe-httpget.yaml de 80 para 70 dessa forma a livenessProbe vai ficar reiniciando nossos PODs por que vai haver um erro de resposta na porta.
      
      - kubectl describe pod nginx-deployment-6b8f696d86-5sm4j
      - Liveness probe failed: Get "http://10.244.0.11:70/": dial tcp 10.244.0.11:70: connect: connection refused
      - kubectl get pods
          
      - NAME                               READY    STATUS      RESTARTS     AGE
      - nginx-deployment-6b8f696d86-5sm4j   1/1     Running   4 (16s ago)   2m36s
      - nginx-deployment-6b8f696d86-7tbn5   1/1     Running   3 (34s ago)   2m35s