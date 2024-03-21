# Helm

- É um gerenciador de pacotes para Kubernetes que facilita a definição, instalação e atualização de aplicações complexas no Kubernetes. Com ele você pode definir no detalhe como a sua aplicação será instalada, quais configurações serão utilizadas e como será feita a atualização da aplicação.

### Instalação do Helm

    curl -fsSL -o get_helm.sh https://raw.githubusercontent.com/helm/helm/main/scripts/get-helm-3
    chmod 700 get_helm.sh
    ./get_helm.sh
    helm version
    helm help

### Manipulando repositórios 

- No Helm conseguimos adicionar repositórios para fazermos as instalações dos recursos assim como fazemos nas distribuições Linux.

      helm repo add stable https://charts.helm.sh/stable
      helm repo add jenkins https://charts.jenkins.io
      helm repo update
      helm repo list

      helm repo remove jenkins

     

