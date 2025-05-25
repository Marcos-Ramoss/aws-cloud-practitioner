# AWS Fargate

## Conceito
AWS Fargate é um mecanismo de computação serverless para containers que permite executar containers sem a necessidade de provisionar, configurar ou gerenciar servidores. Ele funciona com Amazon ECS e Amazon EKS, facilitando a execução de workloads conteinerizadas de forma escalável e segura.

## Características
- **Serverless para containers**: Não é necessário gerenciar instâncias EC2.
- **Escalabilidade automática**: Aloca recursos conforme a demanda dos containers.
- **Integração com ECS e EKS**: Suporte nativo para clusters ECS e EKS.
- **Isolamento de workloads**: Cada tarefa/container executa em ambiente isolado.
- **Cobrança por uso**: Paga apenas pelos recursos consumidos (CPU, memória e tempo de execução).
- **Segurança**: Integração com IAM, VPC, Security Groups e Secrets Manager.
- **Monitoramento**: Suporte a logs e métricas via CloudWatch.

## Casos de Uso
- Execução de microserviços conteinerizados
- Workloads event-driven e jobs em lote
- APIs serverless
- Processamento de dados e pipelines CI/CD
- Ambientes de desenvolvimento e teste

## Vantagens
- Elimina a necessidade de gerenciar servidores
- Escalabilidade granular e automática
- Redução de custos para workloads variáveis
- Integração nativa com serviços AWS
- Segurança aprimorada por isolamento de tarefas

## Desvantagens
- Custo pode ser maior para workloads constantes de longa duração
- Limitações de recursos por tarefa/container
- Algumas funcionalidades avançadas do EC2 não estão disponíveis

## Boas Práticas
- Definir corretamente limites de CPU e memória para cada tarefa
- Utilizar IAM Roles para tarefas com o menor privilégio possível
- Monitorar uso de recursos e ajustar configurações conforme necessário
- Utilizar logs e métricas do CloudWatch para troubleshooting
- Manter imagens de container otimizadas e seguras

## Exemplo Prático (AWS CLI)
### Executar tarefa Fargate com ECS
```sh
aws ecs run-task \
  --cluster meu-cluster \
  --launch-type FARGATE \
  --task-definition minha-task-def \
  --network-configuration "awsvpcConfiguration={subnets=[subnet-xxxxxx],securityGroups=[sg-xxxxxx],assignPublicIp=ENABLED}"
```

### Criar definição de tarefa Fargate (exemplo JSON)
```json
{
  "family": "minha-task-def",
  "networkMode": "awsvpc",
  "requiresCompatibilities": ["FARGATE"],
  "cpu": "256",
  "memory": "512",
  "containerDefinitions": [
    {
      "name": "meu-container",
      "image": "nginx",
      "essential": true,
      "portMappings": [
        { "containerPort": 80, "hostPort": 80, "protocol": "tcp" }
      ]
    }
  ]
}
```

## Configurações Importantes
- **Task Definition**: Especifica recursos, imagem, variáveis de ambiente, etc.
- **Network Mode awsvpc**: Necessário para Fargate, cada tarefa recebe um ENI próprio.
- **Subnets e Security Groups**: Definem conectividade e segurança da tarefa.
- **IAM Role**: Permissões para execução e acesso a outros serviços AWS.

## Considerações
- Fargate é ideal para workloads imprevisíveis ou intermitentes.
- Não há acesso direto ao sistema operacional subjacente.
- Suporte a logs, métricas e tracing integrados.

## Imagem Ilustrativa
![Arquitetura AWS Fargate](../images/Arquitetura-AWS-Fargate.png)

> **Referência oficial:** [Documentação AWS Fargate](https://docs.aws.amazon.com/pt_br/AmazonECS/latest/userguide/what-is-fargate.html)
