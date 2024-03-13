# HPA

- É uma funcionalidade que ajusta automaticamente a quantidade de pods em um Deployment, StatefulSet, ReplicaSet ou ReplicationController com base na utilização atual de CPU ou memória, em comparação com a meta definida pelo usuário. Isso é especialmente útil para aplicações com carga de trabalho variável, permitindo que o sistema escale para cima ou para baixo automaticamente, conforme necessário, para atender à demanda e otimizar o uso dos recursos.


### Instalando o Metrics Server.

    kubectl apply -f https://github.com/kubernetes-sigs/metrics-server/releases/latest/download/components.yaml
    kubectl get pods -n kube-system
    kubectl top node
    kubectl top pods
    kubectl top pods -namespace kube-system

### Criando um Deployment para efetuar os testes do HPA

    kubectl apply -f deployment_hpa.yaml
    kubectl get pods
    kubectl get deployments

### Criando nosso HPA para monitorar o Deployment.

    kubectl apply -f hpa_nginx.yaml
    kubectl get hpa