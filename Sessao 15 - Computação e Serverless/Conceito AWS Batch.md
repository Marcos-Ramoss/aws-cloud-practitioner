# AWS Batch

## Conceito
AWS Batch é um serviço totalmente gerenciado que permite aos desenvolvedores, cientistas e engenheiros executar facilmente cargas de trabalho de computação em lote na AWS. Ele provisiona dinamicamente a quantidade ideal e o tipo de recursos computacionais (como instâncias EC2 ou Spot Instances) com base no volume e nos requisitos específicos dos jobs enviados.

## Características
- **Gerenciamento automático de recursos**: Provisiona, gerencia e escala recursos conforme a demanda dos jobs.
- **Suporte a múltiplos ambientes**: Pode ser usado com EC2 On-Demand, Spot e Fargate.
- **Integração com IAM**: Controle de acesso detalhado para jobs e ambientes.
- **Suporte a dependências de jobs**: Permite definir ordem de execução entre jobs.
- **Monitoramento e logs**: Integração com CloudWatch para monitoramento e logs.
- **Sem necessidade de gerenciar infraestrutura**: AWS gerencia filas, ambientes de computação e execução dos jobs.

## Casos de Uso
- Processamento de dados em larga escala (ETL, análise de logs, simulações científicas)
- Renderização de imagens e vídeos
- Treinamento de modelos de machine learning
- Processamento de genoma e bioinformática
- Workloads financeiros e de engenharia

## Vantagens
- Escalabilidade automática
- Redução de custos com uso de Spot Instances
- Facilidade de integração com outros serviços AWS
- Gerenciamento simplificado de dependências e filas
- Suporte a containers (Docker)

## Desvantagens
- Latência de inicialização dos jobs pode ser alta em ambientes frios
- Curva de aprendizado para configuração inicial
- Limitações de recursos em regiões específicas

## Boas Práticas
- Utilizar Spot Instances para workloads tolerantes a interrupções
- Definir limites de recursos para evitar sobrecarga
- Monitorar jobs e filas via CloudWatch
- Utilizar múltiplos ambientes de computação para diferentes tipos de jobs
- Automatizar submissão de jobs via scripts ou SDK

## Exemplo Prático (AWS CLI)
### Criar um ambiente de computação
```sh
aws batch create-compute-environment \
  --compute-environment-name meu-ambiente-batch \
  --type MANAGED \
  --state ENABLED \
  --compute-resources type=EC2,allocationStrategy=BEST_FIT_PROGRESSIVE,minvCpus=0,maxvCpus=16,instanceTypes=m4.large,subnets=subnet-xxxxxx,securityGroupIds=sg-xxxxxx,instanceRole=ecsInstanceRole
```

### Criar uma fila de jobs
```sh
aws batch create-job-queue \
  --job-queue-name minha-fila-batch \
  --state ENABLED \
  --priority 1 \
  --compute-environment-order order=1,computeEnvironment=meu-ambiente-batch
```

### Submeter um job
```sh
aws batch submit-job \
  --job-name meu-job \
  --job-queue minha-fila-batch \
  --job-definition minha-definicao-job
```

## Configurações Importantes
- **Compute Environment**: Define os recursos computacionais disponíveis.
- **Job Queue**: Fila onde os jobs aguardam execução.
- **Job Definition**: Especifica como o job será executado (imagem Docker, vCPUs, memória, etc).
- **Políticas IAM**: Controle de acesso para submissão e gerenciamento de jobs.

## Considerações
- Jobs podem ser executados em paralelo ou em sequência, conforme dependências.
- É possível usar AWS Fargate para jobs sem necessidade de gerenciar instâncias EC2.
- Custo depende dos recursos consumidos durante a execução dos jobs.

## Imagem Ilustrativa
![Arquitetura AWS Batch](../images/Arquitetura-AWS-Batch.png)

> **Referência oficial:** [Documentação AWS Batch](https://docs.aws.amazon.com/pt_br/batch/latest/userguide/what-is-batch.html)
