# Ingress Controller Default Backend

- Nesse exemplo vamos ter 3 acessos diferentes um para cada path /blue e /green e outro para a pagina do nginx na porta 80 

### Instalando o Ingress Controller no Baremetal

   https://kubernetes.github.io/ingress-nginx/deploy/
     
    kind create cluster --name kind-multinodes --config kind-3nodes.yaml
    kubectl apply -f deploy.yaml
    kubectl get pods -n ingress-nginx
    kubectl get all -n ingress-nginx

### Configurando um Ingress Controller baseado em Path

    kubectl apply -f webcolors.yaml
    kubectl get ingressclass 
    kubectl apply -f ingress.yaml