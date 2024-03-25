# Tolerations

- Agora que entendemos como os Taints funcionam e como eles influenciam o agendamento de Pods nos Nodes, vamos mergulhar no mundo das Tolerations. As Tolerations são como o "antídoto" para os Taints. Elas permitem que um Pod seja agendado em um Node que possui um Taint específico. Em outras palavras, elas "toleram" as Taints.

### Criando um Tolerations

- Vamos usar um caso de um worker que está usando máquinas com suporte a GPU. Mesmo com a Tants setada os Pods vão ser criados em todos os Workers incluse no Worker1

      kubectl taint nodes prod-worker1 gpu=true:NoSchedule
      kubectl apply -f nginx-gpu.yaml
