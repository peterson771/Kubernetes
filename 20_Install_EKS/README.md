
# EKS

- O Amazon Elastic Kubernetes Service (EKS) é um serviço gerenciado oferecido pela Amazon Web Services (AWS) que facilita a execução de aplicativos baseados em contêineres usando o Kubernetes. O Kubernetes é uma plataforma de código aberto para automatizar a implantação, escalabilidade e operação de aplicativos contêinerizados.

### Instalando o EKSCTL

    curl --silent --location "https://github.com/weaveworks/eksctl/releases/latest/download/eksctl_$(uname -s)_amd64.tar.gz" | tar xz -C /tmp
    sudo mv /tmp/eksctl /usr/local/bin
    eksctl

### Instalando o AWS CLI

    curl "https://awscli.amazonaws.com/awscli-exe-linux-x86_64.zip" -o "awscliv2.zip"
    unzip awscliv2.zip
    sudo ./aws/install
    aws configure

### Instalando nosso 

    eksctl create cluster --name=eks-cluster --version=1.24 --region=us-east-1 --nodegroup-name=eks-cluster-nodegroup --node-type=t3.medium --nodes=2 --nodes-min=1 --nodes-max=3 --managed
    
   Resumo desse comando, vamos criar um cluster EKS na versão 1.24 na região US-EAST-1, o nome do cluster vai ser eks-cluster, ele vai ter 2 nodes no máximo 3 e no mínimo 1.
   O --managed informa que quero que o cluster seja gerenciado pela AWS

### Instalação do Kubectl

    curl -LO "https://dl.k8s.io/release/$(curl -L -s https://dl.k8s.io/release/stable.txt)/bin/linux/amd64/kubectl"
    chmod +x ./kubectl
    sudo mv ./kubectl /usr/local/bin/kubectl

- Configurando o Kubectl para acessar nosso cluster na AWS. 
  Atentando para as mudanças do nome da região e nome do cluster.

      aws eks --region us-east-1 update-kubeconfig --name eks-cluster
      kubectl get nodes

- Comandos úteis:

      eksctl get cluster -A
      eksctl get cluster -r us-east-1
      eksctl scale nodegroup --cluster=eks-cluster --nodes=3 --nodes-min=1 --nodes-max=3 --name=eks-cluster-nodegroup -r us-east-1
      eksctl scale nodegroup --cluster=eks-cluster --nodes=1 --nodes-min=1 --nodes-max=3 --name=eks-cluster-nodegroup -r us-east-1
      eksctl delete cluster --name=eks-cluster -r us-east-1
