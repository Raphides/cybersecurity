# Estratégias contra Denial of Service em Kubernetes

## Nó de Balanceamento

## Limites de recursos nos clusters e nós

Antigamente, achava-se que não devia colocar limite de recursos nos nós por causa de um mecanismos chamado .... que 

## Quality of Service (QoS)
Classificação dos pods sobre priorização em situações de estresse. Em uma situação de estresse, é possível que o Kubernetes mate algum nó ou processo dele e normalmente isso acontecerá em nós de menor proridade.

Classificações:
- Guaranteed
- Burstable
- BestEffort

## Quotas
Máximo de nós e outros recursos.

## Capacidade de Limpeza de Nó


## Horizontal Pod Autoscaler (HPA)
Solução para escalar o número de instâncias de pods. Define parâmetros, condições e limitea de escala.

Tem uma fama ruim de normalmente não dar certo.

## Keda
Um HPA que funciona.

## Vertical Pod Adutoscaler (VPA)
Mais recente.

## KNative (serverless)
Quando um pod não está trabalhando, o KNative o deixa inativo, economizando recursos. Da mesma forma, quando um trabalho é associado ao pod inativo, o KNative reativa o pod. Na prática, demora um pouco para ligar o pod, o que pode gerar um gargalo de tempo de resposta quando o KNative precisa lidar com muitos pods ao mesmo tempo.