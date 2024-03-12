# Service Monitor   

  - é um serviço usado em conjunto com o Prometheus Operator para monitorar serviços em um cluster de Kubernetes. O Prometheus Operator é uma maneira de simplificar a implantação e a configuração do Prometheus, um sistema de monitoramento e alerta de código aberto, em um ambiente Kubernetes. 
  - Aqui estão as principais funções do ServiceMonitor: Descoberta Automática de Serviços, Configuração de Scraping, Consolidação da Configuração, Integração com Prometheus Operator


### Criação de uma aplicação do Nginx para efetuarmos o monitoramento.

  - O primeiro passo é a criação de um configmaps para armazenar os logs do Nginx.

        kubectl get configmaps
        kubectl apply -f nginx_configmaps.yaml
        kubectl get configmaps

### Vamos criar um manifesto Deployment, com isso vamos criar um POD com dois containers dentro dele. Eles vão estar usando o configmaps que acabamos de configurar.

       kubectl get pods
       kubectl get deployments
       kubectl apply -f nginx_deployments.yaml
       kubectl get pods
       kubectl get deployments

### Criação de um serviço ClusterIP para acessar os containers de dentro do cluster.
  
      kubectl get services
      kubectl apply -f nginx_service.yaml
      kubectl get services

### Criando nosso Service Monitor

  - Para fazer a monitoração de um POD basta alterar a linha de: *endpoints* para: *podMetricsEndpoints* .
    
      kubectl get servicemonitors
      kubectl -f apply -f nginx_servicemonitor.yaml
      kubectl get servicemonitors
    