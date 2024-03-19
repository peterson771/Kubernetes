# Helm

- É um gerenciador de pacotes para Kubernetes que facilita a definição, instalação e atualização de aplicações complexas no Kubernetes. Com ele você pode definir no detalhe como a sua aplicação será instalada, quais configurações serão utilizadas e como será feita a atualização da aplicação.

### Instalação do Helm

    curl -fsSL -o get_helm.sh https://raw.githubusercontent.com/helm/helm/main/scripts/get-helm-3
    chmod 700 get_helm.sh
    ./get_helm.sh
    helm version
    helm help

### Helm Chart 

- É um pacote contendo todas as informações necessárias para criar uma instância de uma aplicação no sistema de gerenciamento de orquestração Kubernetes

### Instalando o Ingress Controler Nginx via Helm

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
   
