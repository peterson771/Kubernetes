# RBAC

- Na arquitetura do Kubernetes, o controle de acesso é gerenciado por meio do RBAC (Role-Based Access Control), que define permissões com base em funções atribuídas aos usuários ou serviços. No contexto de endpoints, o RBAC pode ser aplicado de várias maneiras, dependendo do tipo de recurso específico ao qual você está se referindo.

- Criando o certificado digital.

      - cd /home/peterson/Documents/     
      - mkdir certificate
      - cd certificate
      - openssl genrsa -out auditor.key 2048
      - openssl req -new -key auditor.key -out autitor.csr -subj "/CN=auditor/O=MyCompany"
      - ls ~/.minikube/
      - openssl x509 -req -in auditor.csr -CA ~/.minikube/ca.crt -CAkey ~/.minikube/ca.key -CAcreateserial -out auditor.crt -days 365

- Criando as credenciais de acesso no K8S

      - kubectl config set-credentials auditor --cliente-certificate=auditor.crt --client-key=auditor.key
      - kubectl config set-context auditor-context --cluster=minikube --user=auditor
      - kubectl config view

- Verificando o contexto

      - kubectl config current-context
      - kubectl config use-context auditor-context
      - kubectl config current-context

- Nesse contexto não temos a permissão para aplciar comandos simples:

      - kubectl get pods
      - kubectl get services
      - kubectl create namespaces namespace-teste


- Comandos para verificar as permissões do usuário auditor

       - kubectl auth can-i '*' '*' --all-namespaces
       - kubectl auth can-i list pods
       - kubectl auth can-i get pods
       - kubectl auth can-i watch pods
       - kubectl auth can-i list service
       - kubectl auth can-i get service
       - kubectl auth can-i watch service

- Alterando o contexto e configurando a Roles e rolebinding

       - kubectl config use-context minikube 
       - kubectl apply -f my-rbac.yaml
       - kubectl get roles
       - kubectl get rolebinding
       - kubectl describe role auditor-role 

- Alterando o contexto e efetuando a verificação das permissões

      - kubectl config use-context minikube 
      - kubectl auth can-i '*' '*' --all-namespaces
       - kubectl auth can-i list pods
       - kubectl auth can-i get pods
       - kubectl auth can-i watch pods
       - kubectl auth can-i list service
       - kubectl auth can-i get service
       - kubectl auth can-i watch service







