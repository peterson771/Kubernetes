# Intra-Node Pod Network Communication
  - É a comunicação via rede entre PODs no mesmo cluster, o K8S cuida da parte do endereçamento e roteamento IP.

# Inter-Node Pod Netwokr Communication
  - É a comunicação via rede entre PODs em cluster diferentes, O K8S faz a parte de endereçamento e roteamento. Não importa onde estejam esses clusters se é em uma nuvem pública ou privada.

# Testando comunicação entre dois PODs
    - kubectl apply -f tomcat-pod.yaml
    - kubectl apply -f redis-pod.yaml
    - kubectl get pods
    - kubectl describe pods redis-pod | grep IP

    - Acessando o POD do Tom-Cat 
    - kubectl exec -it tomcat-pod -- bash
    - apt update -y (Atualizando o Pod)
    - apt install iputils-ping -y 
    - ping (ip do pod-redis)
  