# Ingress Controller

- Desempenha um papel crucial na gestão do acesso externo aos serviços dentro de um cluster. Ele age como um gateway de entrada, permitindo que o tráfego externo chegue aos serviços internos do cluster de acordo com as regras definidas em um recurso Ingress.


### Instalando o Ingress Controller no Baremetal

   https://kubernetes.github.io/ingress-nginx/deploy/
     
    kind create cluster --name kind-multinodes --config kind-3nodes.yaml
    kubectl apply -f deploy.yaml
    kubectl get pods -n ingress-nginx
    kubectl get all -n ingress-nginx

### Configurando um Ingress Simples

    kubectl apply -f webcolors.yaml
    kubectl get ingressclass 
    kubectl apply -f ingress.yaml