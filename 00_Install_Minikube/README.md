
# Instalação Mini Kube

### 1 - Instação Docker.

    curl -fsSL https://get.docker.com | bash

### 2 - Instação kubectl

    curl -LO https://dl.k8s.io/release/v1.24.2/bin/linux/amd64/kubectl
    sudo install -o root -g root -m 0755 kubectl /usr/local/bin/kubectl
    kubectl version --client --output=yaml   

### 3 Instalação Minikube

    curl -Lo minikube https://storage.googleapis.com/minikube/releases/v1.26.0/minikube-linux-amd64
    chmod +x minikube
    sudo install minikube /usr/local/bin/
    sudo usermod -aG docker $USER
    sudo reboot
    minikube delete
    minikube start


# Instalação KIND

- Repita os passos da instalação do Docker e Kubectl.

      curl -Lo ./kind https://kind.sigs.k8s.io/dl/v0.14.0/kind-linux-amd64
      chmod +x ./kind
      sudo mv ./kind /usr/local/bin/kind
      kind create cluster
      kind delete cluster

- Criando um cluster KIND com 3 nodes

      kind create cluster --name kind-multinodes --config kind-3nodes.yaml
      kubectl get nodes

    


