# GCP

-  GKE oferece uma experiência de gestão de clusters Kubernetes simplificada, automatizando tarefas como atualizações de patches, monitoramento e gerenciamento de segurança. Isso reduz significativamente a carga operacional sobre os times de DevOps.

### Instalando o Kubectl e Gcloud.

    sudo apt-get update && sudo apt-get install -y apt-transport-https gnupg2 curl
    curl -s https://packages.cloud.google.com/apt/doc/apt-key.gpg | sudo apt-key add -
    echo "deb https://apt.kubernetes.io/ kubernetes-xenial main" | sudo tee -a /etc/apt/sources.list.d/kubernetes.list
    sudo apt-get update
    sudo apt-get install -y kubectl

### Configurando o acesso da conta da GCP.

    gcloud init
    gcloud auth list
    gcloud config set account `YOUR_ACCOUNT`

### Subindo um cluster K8S na GCP.

    CLUSTER_NAME=gcp-gke-prod
    gcloud container clusters create $CLUSTER_NAME --num-nodes=1 \
    --disk-type=pd-standard --disk-size=30GB \
    --enable-autoupgrade --no-enable-basic-auth --no-issue-client-certificate \
    --enable-ip-alias --metadata disable-legacy-endpoint=true \
    --zone us-central1-a

### Redimensionando o numero de Nodes no cluster

    CLUSTER_NAME=gcp-gke-prod
    gcloud container node-pools list --cluster $CLUSTER_NAME --zone us-central1-a

    CLUSTER_NAME=gcp-gke-prod
    NAME_OF_NODE_POOL=default-pool
    gcloud container clusters resize $CLUSTER_NAME --node-pool $NAME_OF_NODE_POOL --num-nodes 2 --zone us-central1-a
     

### Conectando no Cluster do desktop

    CLUSTER_NAME=gcp-gke-prod
    gcloud container clusters get-credentials $CLUSTER_NAME --zone us-central1-a


### Deletando o Cluster

    gcloud container clusters delete $CLUSTER_NAME --zone us-central1-a







