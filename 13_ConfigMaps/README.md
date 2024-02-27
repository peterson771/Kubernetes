# Configmaps

- É um recurso usado para armazenar configurações não confidenciais, como dados de configuração, strings de chave-valor, arquivos de configuração ou qualquer informação que um aplicativo possa precisar. Ele oferece uma maneira de separar a configuração do aplicativo do código-fonte, o que facilita a modificação das configurações sem alterar o código do aplicativo.

      - kubectl apply -f my-cm-test-env.yaml
      - kubectl get configmap
      - kubectl get pods
      - kubectl describe configmap my-cm

- Nesse proximo exemplo vou criar um POD com um volume dentro do POD usando o configmap para armazenar o conteúdo.

      - kubectl aplly -f pod-cm-vol.yaml
      - kubectl apply -f my-cm.yaml
      

