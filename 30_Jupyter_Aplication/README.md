# Jupiter Aplication

- https://jupyter.org/

- O Projeto Jupyter é um projeto de código aberto sem fins lucrativos, nascido do Projeto IPython em 2014, à medida que evoluiu para apoiar a ciência de dados interativa e a computação científica em todas as linguagens de programação.  O Jupyter sempre será um software 100% de código aberto, gratuito para uso de todos e lançado sob os termos liberais da licença BSD modificada. O Jupyter é desenvolvido abertamente no GitHub, por meio do consenso da comunidade Jupyter.  Para obter mais informações sobre nossa governança, consulte nossa documentação de governança.            Todas as interações e comunicações online e presenciais diretamente relacionadas ao projeto são cobertas pelo Código de Conduta Jupyter.  Este Código de Conduta estabelece expectativas para permitir que uma comunidade diversificada de usuários e colaboradores participe do projeto com respeito e segurança.

- Aplicando o namespace e o deployment da aplicação.
 
      - kubectl apply -f jupyter-ns.yaml
      - kubectl apply -f jupyter-dp.yaml
      - kubectl get pods -n jupyter -w

- Verificando a aplicação
    
      - kubectl describe namespace jupyter
      - kubectl get deployments -n jupyter
      - kubectl config view | grep namespace
      - kubectl config set-context --current --namespace=jupyter
      - kubectl get pods -o wide

- Migrando a aplicação para Service
   
      - kubectl get service
      - kubectl expose deployment jupyter-dp -n jupyter --type=NodePort --name=jupyter-svc --dry-run=client
      - kubectl expose deployment jupyter-dp -n jupyter --type=NodePort --name=jupyter-svc
      - kubectl get service
      - kubectl get service jupyter-svc -o yaml
      - minikube service jupyter-svc -n jupyter --url

- Migrando a porta da aplicação

      - kubectl get svc jupyter-svc -o yaml | grep nodePort 
      - kubectl edit service jupyter-svc
      - Alterar a linha NodePort: 30000
      - kubectl get svc jupyter-svc -o yaml | grep nodePort


- Escalando a aplicação
 
      - Alterando a linha replicas do arquivo jupyter-dp.yaml para 6
      - kubectl apply -f jupyter-dp.yaml
      - kubectl get deployments
      - kubectl get pod -o wide

- Atulizando a aplicação

      - kubectl set image deployment/jupyter-dp jupyter-container=jupyter/minimal-notebook:python-3.10
      - Alteração também pode ser feita no arquivo jupyter-dp.yaml alterando a linha image:
      - kubectl get describe pod jupyter-dp-59f5558555-85f5n
