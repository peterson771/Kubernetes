# StatefulSet

- É um recurso no Kubernetes projetado para lidar com aplicações que exigem identidade única e persistência de estado. Ele fornece garantias específicas de ordem e nomes persistentes para os Pods que são implantados. Enquanto os Deployments são frequentemente usados para aplicativos sem estado e replicáveis, o StatefulSet é mais adequado para aplicativos com estado.

      - kubectl apply -f svc-sts.yaml
      - kubectl get statefulset 
      - kubectl get pods 

- Atualizando a linha do arquivo svc-sts.yaml replicas: 1, vamos ver que o StatefulSet vai eleminando os PODS em sequencia deixando apenas o POD: my-sts-0 o mesmo acontece quando fazemos o scale UP

      - kubectl apply -f svc-sts.yaml
      - kubectl get statefulset 
      - kubectl get pods 

- O mesmo acontece para alterações nos pods podemos efetuar os mesmos testes alterando a linha da imagem do POD de *image: nginx:1.23.1* para *image: nginx:1.18.1*

- Todos os dados dos PODs estão armazenados dentor do Cluster no caminho: *root@Minikube:/var/lib/docker/volumes/minikube/_data/hostpath-provisioner/default*