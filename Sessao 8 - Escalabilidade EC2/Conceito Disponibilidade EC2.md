## Botão Voltar ao Início
[⬆️ Voltar ao Início](https://github.com/Marcos-Ramoss/aws-cloud-practitioner)

---

# Disponibilidade EC2 AWS

## Conceito

A Disponibilidade no Amazon EC2 (Elastic Compute Cloud) é a capacidade de manter aplicações e serviços em execução continuamente, mesmo em caso de falhas ou interrupções. A AWS oferece múltiplas camadas de disponibilidade através de diferentes zonas de disponibilidade, regiões e serviços complementares.

### Características Principais

1. **Alta Disponibilidade**
   - Múltiplas AZs
   - Redundância
   - Failover automático
   - Recuperação rápida

2. **Componentes de Disponibilidade**
   - Load Balancers
   - Auto Scaling
   - Health Checks
   - Backup e DR

3. **Monitoramento**
   - CloudWatch
   - Health Dashboard
   - Logs
   - Alertas

## Para que é usado

### Casos de Uso Comuns

1. **Aplicações Críticas**
   - ✅ Sistemas de missão crítica
   - ✅ Aplicações 24/7
   - ✅ Serviços essenciais
   - ✅ Operações contínuas

2. **E-commerce**
   - ✅ Lojas online
   - ✅ Processamento de pagamentos
   - ✅ Catálogos de produtos
   - ✅ Carrinhos de compra

3. **Enterprise**
   - ✅ Sistemas corporativos
   - ✅ Aplicações internas
   - ✅ Serviços de TI
   - ✅ Operações de negócio

4. **Serviços Web**
   - ✅ APIs
   - ✅ Websites
   - ✅ Aplicações web
   - ✅ Microserviços

## Vantagens

### Técnicas
- ✅ **Alta disponibilidade** (99.99%)
- ✅ **Redundância** automática
- ✅ **Failover** automático
- ✅ **Recuperação** rápida
- ✅ **Monitoramento** integrado

### Operacionais
- ✅ **Gerenciamento** simplificado
- ✅ **Automação** de processos
- ✅ **Monitoramento** nativo
- ✅ **Alertas** configuráveis
- ✅ **Manutenção** reduzida

### Econômicas
- ✅ **Pay-as-you-go**
- ✅ **Otimização** de custos
- ✅ **Sem** investimento inicial
- ✅ **Escalabilidade** econômica
- ✅ **Custo-benefício**

## Desvantagens

### Técnicas
- ❌ **Complexidade** de configuração
- ❌ **Custo** de redundância
- ❌ **Latência** entre regiões
- ❌ **Dependência** de serviços
- ❌ **Limitações** de região

### Operacionais
- ❌ **Monitoramento** necessário
- ❌ **Configuração** manual
- ❌ **Testes** de failover
- ❌ **Documentação** importante
- ❌ **Treinamento** necessário

### Econômicas
- ❌ **Custos** de redundância
- ❌ **Custos** de monitoramento
- ❌ **Custos** de rede
- ❌ **Custos** de backup
- ❌ **Custos** de DR

## Boas práticas

### Arquitetura
- ✅ **Multi-AZ** deployment
- ✅ **Load balancing**
- ✅ **Auto scaling**
- ✅ **Health checks**
- ✅ **Backup** regular

### Segurança
- ✅ **IAM** roles
- ✅ **Security Groups**
- ✅ **VPC** configuration
- ✅ **Encryption**
- ✅ **Compliance**

### Monitoramento
- ✅ **CloudWatch** alarms
- ✅ **Health** dashboard
- ✅ **Logs** centralizados
- ✅ **Alertas** configurados
- ✅ **Métricas** personalizadas

## Exemplo prático

```bash
# Criar Load Balancer
aws elbv2 create-load-balancer \
    --name my-load-balancer \
    --subnets subnet-12345678 subnet-87654321 \
    --security-groups sg-12345678

# Configurar Auto Scaling
aws autoscaling create-auto-scaling-group \
    --auto-scaling-group-name my-asg \
    --launch-template LaunchTemplateId=lt-1234567890abcdef0,Version=1 \
    --min-size 2 \
    --max-size 10 \
    --desired-capacity 4 \
    --vpc-zone-identifier "subnet-12345678,subnet-87654321"

# Configurar Health Check
aws elbv2 create-target-group \
    --name my-targets \
    --protocol HTTP \
    --port 80 \
    --vpc-id vpc-12345678 \
    --health-check-path /health \
    --health-check-interval-seconds 30

# Verificar status
aws elbv2 describe-load-balancers \
    --load-balancer-arns arn:aws:elasticloadbalancing:region:123456789012:loadbalancer/app/my-load-balancer/1234567890abcdef
```

## Componentes de Disponibilidade

### Load Balancers
- Distribuição de carga
- Health checks
- SSL termination
- Sticky sessions

### Auto Scaling
- Escalabilidade automática
- Recuperação de falhas
- Balanceamento de carga
- Otimização de custos

### Health Checks
- Monitoramento de instâncias
- Verificação de aplicação
- Failover automático
- Recuperação rápida

### Backup e DR
- Snapshots
- Replicação
- Failover
- Recuperação

## Considerações Importantes

1. **Arquitetura**
   - Multi-AZ
   - Load balancing
   - Auto scaling
   - Health checks

2. **Monitoramento**
   - CloudWatch
   - Health dashboard
   - Logs
   - Alertas

3. **Segurança**
   - IAM
   - Security Groups
   - VPC
   - Encryption

4. **Custo**
   - Redundância
   - Monitoramento
   - Backup
   - DR

---

## Diagrama de Disponibilidade EC2 AWS
![Diagrama de Disponibilidade EC2 AWS](/images/Diagrama%20de%20Disponibilidade%20EC2%20AWS.png)

---

## Versão Alternativa Simplificada
![Versão Alternativa Simplificada](/images/Versão%20Alternativa%20Simplificada%20Disponibilidade.png)

---

## Multi-AZ Deployment
![Multi-AZ Deployment](/images/Multi-AZ%20Deployment.png)

---

## Arquitetura - Exemplo Prático: Banco Online

![Arquitetura](/images/Arquitetura.png)

 