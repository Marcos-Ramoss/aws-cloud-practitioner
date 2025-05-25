## Botão Voltar ao Início
[⬆️ Voltar ao Início](https://github.com/Marcos-Ramoss/aws-cloud-practitioner)

---

# Amazon Elastic Kubernetes Service (Amazon EKS)

## Conceito

O Amazon EKS (Elastic Kubernetes Service) é um serviço gerenciado que facilita a execução do Kubernetes na AWS, eliminando a necessidade de instalar, operar e manter o plano de controle do Kubernetes. O EKS oferece alta disponibilidade, escalabilidade e integração nativa com outros serviços AWS.

### Características Principais

1. **Gerenciamento de Kubernetes**
   - Plano de controle gerenciado pela AWS
   - Atualizações automáticas e patches de segurança

2. **Execução Flexível**
   - Suporte a EC2, AWS Fargate e ambientes on-premises (EKS Anywhere)
   - Escalabilidade automática de nós e pods

3. **Segurança e Integração**
   - Integração com IAM, VPC, Security Groups e Secrets Manager
   - Suporte a RBAC, autenticação e criptografia de dados

4. **Monitoramento e Logging**
   - Integração com CloudWatch, Container Insights e CloudTrail
   - Suporte a métricas, logs e tracing

## Para que é usado

### Casos de Uso Comuns

1. **Microserviços e Aplicações Cloud Native**
   - ✅ Deploy e gerenciamento de aplicações baseadas em containers
   - ✅ Escalabilidade automática de workloads

2. **Machine Learning e Data Science**
   - ✅ Execução de pipelines de ML e jobs distribuídos

3. **Ambientes Híbridos e Multi-Cloud**
   - ✅ Execução de clusters Kubernetes on-premises e em múltiplas nuvens

4. **Batch e Workloads Temporários**
   - ✅ Execução de jobs em lote e pipelines de dados

## Vantagens

### Técnicas
- ✅ **Alta disponibilidade** e resiliência
- ✅ **Escalabilidade** automática de clusters e workloads
- ✅ **Integração** nativa com serviços AWS

### Operacionais
- ✅ **Gerenciamento** simplificado do plano de controle
- ✅ **Automação** de deploys, atualizações e monitoramento

### Econômicas
- ✅ **Pay-as-you-go**
- ✅ **Redução** de custos operacionais

## Desvantagens

### Técnicas
- ❌ **Curva de aprendizado** do Kubernetes
- ❌ **Gerenciamento** de redes e storage pode ser complexo

### Operacionais
- ❌ **Monitoramento** e logging exigem configuração
- ❌ **Gerenciamento** de múltiplos clusters pode ser desafiador

### Econômicas
- ❌ **Custos** podem aumentar com má configuração de escalabilidade

## Boas práticas

### Nomenclatura
- ✅ **Padronização** de nomes de clusters, namespaces e recursos
- ✅ **Documentação** de pipelines e configurações

### Segurança
- ✅ **Uso de roles IAM** específicas para workloads
- ✅ **Isolamento** de redes e RBAC
- ✅ **Scan de imagens e secrets**

### Custo
- ✅ **Monitoramento** de uso e escalabilidade
- ✅ **Revisão** periódica de clusters e workloads

## Exemplo prático

```powershell
# Criar cluster EKS
aws eks create-cluster `
    --name meu-cluster `
    --role-arn arn:aws:iam::123456789012:role/EKSClusterRole `
    --resources-vpc-config subnetIds=subnet-12345678,subnet-87654321,securityGroupIds=sg-12345678

# Atualizar cluster EKS
aws eks update-cluster-version `
    --name meu-cluster `
    --kubernetes-version 1.29
```

## Configurações Importantes

### Node Groups
- EC2 Managed Node Groups e Fargate Profiles
- Auto Scaling de nós e pods

### Segurança
- IAM Roles para Service Accounts (IRSA)
- RBAC e políticas de acesso
- Integração com Secrets Manager

### Monitoramento
- CloudWatch Container Insights
- Logs e métricas customizadas

## Considerações Importantes

1. **Gerenciamento de Clusters**
   - Planejar escalabilidade e alta disponibilidade
   - Automatizar deploys e atualizações

2. **Custo**
   - Monitorar uso de recursos e escalabilidade
   - Revisar clusters e workloads não utilizados

3. **Segurança**
   - Isolar redes, RBAC e roles IAM
   - Scan de imagens e controle de acesso

---

## Arquitetura Amazon EKS
![Arquitetura Amazon EKS](/images/Arquitetura%20EKS%20AWS.png)

---

## Exemplo de Pipeline CI/CD com EKS
![Exemplo Pipeline EKS AWS](/images/Exemplo%20Pipeline%20EKS%20AWS.png)

---

## Integração com Serviços AWS
![Integração EKS AWS](/images/Integracao%20EKS%20AWS.png)

---

## Configuração típica
![Configuração típica EKS AWS](/images/Configuracao%20tipica%20EKS%20AWS.png)

---
