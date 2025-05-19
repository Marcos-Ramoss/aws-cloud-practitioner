# Amazon EC2 Auto Scaling

## Conceito

O Amazon EC2 Auto Scaling é um serviço que ajuda a manter a disponibilidade das aplicações e permite adicionar ou remover automaticamente instâncias EC2 de acordo com as condições definidas. Ele ajuda a garantir que você tenha o número correto de instâncias EC2 disponíveis para lidar com a carga da sua aplicação.

### Características Principais

1. **Gerenciamento de Capacidade**
   - Escalabilidade automática
   - Balanceamento de carga
   - Alta disponibilidade
   - Recuperação automática

2. **Tipos de Escalonamento**
   - Dinâmico
   - Preditivo
   - Programado
   - Manual

3. **Monitoramento**
   - Health checks
   - Métricas CloudWatch
   - Logs de atividade
   - Alertas configuráveis

## Para que é usado

### Casos de Uso Comuns

1. **Aplicações Web**
   - ✅ Balanceamento de carga
   - ✅ Alta disponibilidade
   - ✅ Escalabilidade automática
   - ✅ Recuperação de falhas

2. **Microserviços**
   - ✅ Escalabilidade independente
   - ✅ Isolamento de recursos
   - ✅ Gerenciamento de versões
   - ✅ Deployments canário

3. **Big Data**
   - ✅ Processamento em lote
   - ✅ Análise de dados
   - ✅ Machine Learning
   - ✅ Computação distribuída

4. **Desenvolvimento**
   - ✅ Ambientes de teste
   - ✅ CI/CD
   - ✅ Desenvolvimento
   - ✅ Staging

## Vantagens

### Técnicas
- ✅ **Alta disponibilidade**
- ✅ **Escalabilidade** automática
- ✅ **Balanceamento** de carga
- ✅ **Recuperação** automática
- ✅ **Monitoramento** integrado

### Operacionais
- ✅ **Gerenciamento** simplificado
- ✅ **Automação** de tarefas
- ✅ **Flexibilidade** de configuração
- ✅ **Integração** com AWS
- ✅ **Manutenção** reduzida

### Econômicas
- ✅ **Otimização** de custos
- ✅ **Pay-as-you-go**
- ✅ **Escalabilidade** econômica
- ✅ **Sem** investimento inicial
- ✅ **Custo-benefício**

## Desvantagens

### Técnicas
- ❌ **Latência** de inicialização
- ❌ **Complexidade** de configuração
- ❌ **Limitações** de região
- ❌ **Dependência** de AMI
- ❌ **Custo** de instâncias

### Operacionais
- ❌ **Monitoramento** necessário
- ❌ **Configuração** manual
- ❌ **Manutenção** de AMIs
- ❌ **Testes** necessários
- ❌ **Documentação** importante

### Econômicas
- ❌ **Custos** de instâncias
- ❌ **Custos** de monitoramento
- ❌ **Custos** de rede
- ❌ **Otimização** necessária
- ❌ **Custos** de backup

## Boas práticas

### Performance
- ✅ **Monitoramento** de métricas
- ✅ **Otimização** de AMIs
- ✅ **Testes** de carga
- ✅ **Documentação** de benchmarks
- ✅ **Análise** de performance

### Segurança
- ✅ **IAM** roles
- ✅ **Security Groups**
- ✅ **VPC** configuration
- ✅ **Encryption**
- ✅ **Compliance**

### Custo
- ✅ **Análise** de uso
- ✅ **Otimização** de recursos
- ✅ **Monitoramento** de custos
- ✅ **Revisão** de preços
- ✅ **Planejamento** financeiro

## Exemplo prático

```bash
# Criar Auto Scaling Group
aws autoscaling create-auto-scaling-group \
    --auto-scaling-group-name my-asg \
    --launch-template LaunchTemplateId=lt-1234567890abcdef0,Version=1 \
    --min-size 2 \
    --max-size 10 \
    --desired-capacity 4 \
    --vpc-zone-identifier "subnet-12345678,subnet-87654321"

# Configurar política de escalonamento
aws autoscaling put-scaling-policy \
    --auto-scaling-group-name my-asg \
    --policy-name cpu-policy \
    --policy-type TargetTrackingScaling \
    --target-tracking-configuration '{
        "PredefinedMetricSpecification": {
            "PredefinedMetricType": "ASGAverageCPUUtilization"
        },
        "TargetValue": 70.0
    }'

# Verificar status
aws autoscaling describe-auto-scaling-groups \
    --auto-scaling-group-name my-asg
```

## Tipos de Escalonamento

### Dinâmico
- Baseado em métricas
- CloudWatch Alarms
- Target Tracking
- Step Scaling

### Preditivo
- Machine Learning
- Previsão de carga
- Escalonamento antecipado
- Otimização de custos

### Programado
- Horários específicos
- Datas específicas
- Eventos recorrentes
- Manutenção planejada

### Manual
- Ajuste manual
- Testes
- Manutenção
- Debugging

## Considerações Importantes

1. **Configuração**
   - Launch Template
   - Security Groups
   - VPC
   - IAM Roles

2. **Monitoramento**
   - CloudWatch
   - Health Checks
   - Logs
   - Alertas

3. **Custo**
   - Instâncias
   - Monitoramento
   - Rede
   - Backup

4. **Integração**
   - ELB
   - CloudWatch
   - SNS
   - CloudTrail

---

## Diagrama de Escalabilidade EC2 AWS
![Diagrama de Escalabilidade EC2 AWS](/images/Diagrama%20de%20Escalabilidade%20EC2%20AWS.png)

---

## Versão Alternativa Simplificada
![Versão Alternativa Simplificada](/images/Versão%20Alternativa%20Simplificada.png)

---

## Auto Scaling Groups (ASG)
![Auto Scaling Groups (ASG)](/images/Auto%20Scaling%20Groups%20(ASG).png)

---

## Configuração ASG Exemplo Prático: E-commerce
![Configuração ASG](/images/Configuração%20ASG.png)

---
