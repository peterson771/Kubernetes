# Instalação de uma aplicação via Helm

### Instalando o Ingress Controller

    helm repo add ingress-nginx https://kubernetes.github.io/ingress-nginx
    helm repo update
    helm search repo ingress-nginx
    helm inspect all ingress-nginx/ingress-nginx
    helm inspect values ingress-nginx/ingress-nginx > values.yaml

### Alterando o numero de replicas do meu Ingress Controller
     
    kubectl create namespace nginx-ingress
    kubectl get namespaces
    helm install meu-ingress-controller ingress-nginx/ingress-nginx --namespace nginx-ingress
    helm list -n nginx-ingress
    kubectl get pods -n nginx-ingress
    helm upgrade meu-ingress-controller ingress-nginx/ingress-nginx --namespace nginx-ingress --values values.yaml
    kubectl get all -n nginx-ingress
    
