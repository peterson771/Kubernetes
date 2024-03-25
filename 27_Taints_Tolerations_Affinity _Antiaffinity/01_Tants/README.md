# Taints

- Taints são marcações aplicadas aos Nodes que os marcam para evitar que certos Pods sejam agendados neles. Essa é uma forma bastante comum de isolar workloads em um cluster Kubernetes, por exemplo em momentos de manutenção ou quando você tem Nodes com recursos especiais, como GPUs.

### Taints NoSchedule

- Impede que novos pods sejam agendados no nó, a menos que o pod tenha uma tolerância correspondente ao taint. O control-plane vem com essa marcação por padrão.

      kubectl taint nodes prod-worker1 key=value:NoSchedule

- Retirando a Taints

      kubectl taint nodes prod-worker1 key=value:NoSchedule-
      kubectl rollout restart deployment nginx

### Taints NoExecute

- Quando um nó tem um taint com efeito NoExecute, os pods que não toleram esse taint serão removidos do nó. Isso é útil para garantir que certos tipos de workloads sejam interrompidos em um nó se as condições de taint não forem atendidas, por exemplo, em caso de falhas de hardware ou atualizações de software.

      kubectl taint nodes prod-worker1 key=value:NoExecute

### Taints PreferNoSchedule

- É semelhante ao NoSchedule, mas o Kubernetes tentará evitar agendar pods neste nó, a menos que não haja outra opção disponível. É útil para indicar preferências de agendamento sem impor restrições rígidas.

      kubectl taint nodes strigus-worker1 key=value:PreferNoSchedule