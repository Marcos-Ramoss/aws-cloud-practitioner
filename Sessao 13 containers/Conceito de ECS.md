## Botão Voltar ao Início
[⬆️ Voltar ao Início](https://github.com/Marcos-Ramoss/aws-cloud-practitioner)

---

# Amazon Elastic Container Service (Amazon ECS)

## Conceito

O Amazon ECS (Elastic Container Service) é um serviço de orquestração de containers totalmente gerenciado que facilita o deploy, gerenciamento e escalabilidade de aplicações em containers Docker na AWS. Ele suporta execução em instâncias EC2 ou de forma serverless com AWS Fargate.

### Características Principais

1. **Orquestração de Containers**
   - Gerenciamento de clusters, tarefas e serviços
   - Suporte a deploys blue/green, rolling updates e auto scaling

2. **Execução Flexível**
   - Suporte a EC2 (gerenciamento de infraestrutura) ou Fargate (serverless)
   - Integração com Amazon ECR para imagens Docker

3. **Segurança e Controle**
   - Integração com IAM, VPC, Security Groups e Secrets Manager
   - Isolamento de tarefas e controle de acesso granular

4. **Monitoramento e Logging**
   - Integração com CloudWatch Logs, métricas e eventos
   - Suporte a tracing e monitoramento de aplicações

## Para que é usado

### Casos de Uso Comuns

1. **Microserviços**
   - ✅ Deploy e gerenciamento de múltiplos serviços independentes
   - ✅ Escalabilidade automática por serviço

2. **Batch e Workloads Temporários**
   - ✅ Execução de jobs em lote e pipelines de dados

3. **Aplicações Web e APIs**
   - ✅ Deploy de aplicações web escaláveis e APIs REST

4. **Ambientes Híbridos**
   - ✅ Integração com workloads on-premises via ECS Anywhere

## Vantagens

### Técnicas
- ✅ **Gerenciamento** centralizado de containers
- ✅ **Escalabilidade** automática e flexível
- ✅ **Integração** nativa com serviços AWS

### Operacionais
- ✅ **Automação** de deploys e atualizações
- ✅ **Monitoramento** e logging integrados

### Econômicas
- ✅ **Pay-as-you-go**
- ✅ **Redução** de custos operacionais com Fargate

## Desvantagens

### Técnicas
- ❌ **Curva de aprendizado** para configuração de clusters e tarefas
- ❌ **Limitações** em integrações com orquestradores externos

### Operacionais
- ❌ **Gerenciamento** de múltiplos clusters pode ser complexo

### Econômicas
- ❌ **Custos** podem aumentar com má configuração de escalabilidade

## Boas práticas

### Nomenclatura
- ✅ **Padronização** de nomes de clusters, serviços e tarefas
- ✅ **Documentação** de pipelines e configurações

### Segurança
- ✅ **Uso de roles IAM** específicas para tarefas
- ✅ **Isolamento** de redes e containers
- ✅ **Scan de imagens no ECR**

### Custo
- ✅ **Monitoramento** de uso e escalabilidade
- ✅ **Revisão** periódica de clusters e serviços

## Exemplo prático

```powershell
# Criar cluster ECS
aws ecs create-cluster --cluster-name meu-cluster

# Registrar uma task definition
aws ecs register-task-definition --cli-input-json file://task-definition.json

# Criar serviço usando Fargate
aws ecs create-service `
    --cluster meu-cluster `
    --service-name meu-servico `
    --task-definition minha-task `
    --desired-count 2 `
    --launch-type FARGATE `
    --network-configuration awsvpcConfiguration={subnets=[subnet-12345678],securityGroups=[sg-12345678],assignPublicIp=ENABLED}
```

## Configurações Importantes

### Task Definitions
- Definição de containers, recursos, variáveis e volumes
- Versionamento e reutilização

### Serviços e Deploys
- Rolling updates, blue/green deploys
- Auto Scaling de tarefas

### Segurança
- IAM Roles para tarefas
- Integração com Secrets Manager e Parameter Store

## Considerações Importantes

1. **Gerenciamento de Clusters**
   - Planejar escalabilidade e alta disponibilidade
   - Automatizar deploys e atualizações

2. **Custo**
   - Monitorar uso de recursos e escalabilidade
   - Revisar clusters e serviços não utilizados

3. **Segurança**
   - Isolar redes e roles IAM
   - Scan de imagens e controle de acesso

---

## Arquitetura Amazon ECS
![Arquitetura Amazon ECS](/images/Arquitetura%20ECS%20AWS.png)

---

## Exemplo de Pipeline CI/CD com ECS
![Exemplo Pipeline ECS AWS](/images/Exemplo%20Pipeline%20ECS%20AWS.png)

---

## Integração com Serviços AWS
![Integração ECS AWS](/images/Integracao%20ECS%20AWS.png)

---

## Configuração típica
![Configuração típica ECS AWS](/images/Configuracao%20tipica%20ECS%20AWS.png)

---
