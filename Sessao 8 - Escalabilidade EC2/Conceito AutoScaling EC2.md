## Botão Voltar ao Início
[⬆️ Voltar ao Início](https://github.com/Marcos-Ramoss/aws-cloud-practitioner)

---

# Auto Scaling EC2 AWS

## Conceito

O Amazon EC2 Auto Scaling é um serviço que ajuda a manter a disponibilidade das aplicações e permite adicionar ou remover automaticamente instâncias EC2 de acordo com as condições definidas. Ele ajuda a garantir que você tenha o número correto de instâncias EC2 disponíveis para processar a carga da sua aplicação.

### Características Principais

1. **Gerenciamento de Capacidade**
   - Mínimo de instâncias
   - Máximo de instâncias
   - Capacidade desejada
   - Políticas de escalabilidade

2. **Tipos de Escalabilidade**
   - Dinâmica (baseada em métricas)
   - Preditiva (baseada em ML)
   - Programada (baseada em horários)
   - Manual (ajuste manual)

3. **Monitoramento**
   - Health checks
   - CloudWatch metrics
   - Logs
   - Alertas

## Para que é usado

### Casos de Uso Comuns

1. **Aplicações Web**
   - ✅ Picos de tráfego
   - ✅ Sazonalidade
   - ✅ Eventos especiais
   - ✅ Manutenção

2. **Microserviços**
   - ✅ Escalabilidade independente
   - ✅ Alta disponibilidade
   - ✅ Recuperação automática
   - ✅ Balanceamento de carga

3. **Big Data**
   - ✅ Processamento em lote
   - ✅ Análise de dados
   - ✅ Machine Learning
   - ✅ ETL

4. **Desenvolvimento**
   - ✅ Ambientes de teste
   - ✅ CI/CD
   - ✅ Desenvolvimento
   - ✅ Staging

## Vantagens

### Técnicas
- ✅ **Alta disponibilidade**
- ✅ **Escalabilidade automática**
- ✅ **Recuperação automática**
- ✅ **Balanceamento de carga**
- ✅ **Monitoramento integrado**

### Operacionais
- ✅ **Automação** de processos
- ✅ **Gerenciamento** simplificado
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

# Configurar política de escalabilidade
aws autoscaling put-scaling-policy \
    --auto-scaling-group-name my-asg \
    --policy-name cpu-policy \
    --policy-type TargetTrackingScaling \
    --target-tracking-configuration file://config.json

# Verificar status
aws autoscaling describe-auto-scaling-groups \
    --auto-scaling-group-names my-asg
```

## Tipos de Escalabilidade

### Dinâmica
- Baseada em métricas
- CloudWatch
- Thresholds
- Ações automáticas

### Preditiva
- Machine Learning
- Padrões históricos
- Previsão de carga
- Escalabilidade proativa

### Programada
- Horários específicos
- Eventos conhecidos
- Manutenção
- Picos previsíveis

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

## Auto Scaling
![Auto Scaling](/images/Auto%20Scaling.png)

---

##  Integração Completa
![ Integração Completa](/images/Integração%20Completa.png)

---

## Alternative Version (Flowchart)
![Alternative Version (Flowchart)](/images/Alternative%20Version%20(Flowchart).png)

--- 