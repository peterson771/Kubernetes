

# Volumes.

- Com os volumes persistentes conseguimos manter os dados dos PODs mesmo após o seu restart. 

### Empytidir
  - É um tipo de volume que pode ser montado em um contêiner. Ele é usado para armazenar dados temporários que são compartilhados entre os contêineres em um mesmo Pod. O arquivo é mantido em caso de restart, mais em caso de delação do POD os arquivos são perdidos.

        - kubectl apply -f volumes.yaml
        - kubectl get pods 
        - kubectl exec -it redis-pod -- /bin/bash
        - cd /my-volume 
        - echo "Ola Volume" > teste.txt


### HostPath
   - Diferente do Empytidir ele mantém os arquivos mesmo após o restart e deleção do POD. 
   O diretório fica armazenado dentro do cluster e não do POD

        - kubectl apply -f volumes-persist.yaml
        - kubectl get pods 
        - kubectl exec -it redis-pod2 -- /bin/bash
        - cd /my-volume
        - echo "Teste hostpah" > teste.txt
        - kubectl delete pod redis-pod2
        - kubectl apply -f volumes-persist.yaml


























