# Instalando o Ingress Controler Nginx via Helm

    helm repo add ingress-nginx https://kubernetes.github.io/ingress-nginx
    helm repo update
    helm search repo ingress-nginx
    helm inspect all ingress-nginx/ingress-nginx
    helm inspect values ingress-nginx/ingress-nginx
    helm install meu-ingress-controller ingress-nginx/ingress-nginx
    kubectl get all
    helm uninstall meu-ingress-controller
    helm list 
    kubectl get all

### Instalando o Ingress Controler Nginx em outro namespace

    kubectl create namespace nginx-ingress
    helm install meu-ingress-controller ingress-nginx/ingress-nginx --namespace nginx-ingress
    helm list -n nginx-ingress

### Alterando a linha do arquivo values.yaml para ( controller: replicaCount: 2)

    helm upgrade meu-ingress-controller ingress-nginx/ingress-nginx --namespace nginx-ingress --values values.yaml
    kubectl get pods -n nginx-ingress
    helm list -n nginx-ingress
    helm history meu-ingress-controller -n nginx-ingress
    helm rollback meu-ingress-controller -n nginx-ingress
   
