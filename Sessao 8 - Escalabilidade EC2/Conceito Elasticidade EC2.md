## Botão Voltar ao Início
[⬆️ Voltar ao Início](/README.md)

---

# Elasticidade EC2 AWS

## Conceito

A Elasticidade no Amazon EC2 (Elastic Compute Cloud) é a capacidade de expandir e contrair a infraestrutura de processamento conforme a demanda. É um conceito fundamental da computação em nuvem que permite que os recursos de computação sejam dimensionados automaticamente e dinamicamente.

### Características Principais

1. **Escalabilidade Dinâmica**
   - Aumento automático de recursos
   - Redução automática de recursos
   - Adaptação à demanda
   - Otimização de custos

2. **Tipos de Elasticidade**
   - Vertical (Scale Up/Down)
   - Horizontal (Scale Out/In)
   - Automática
   - Manual

3. **Recursos Elásticos**
   - CPU
   - Memória
   - Armazenamento
   - Rede

## Para que é usado

### Casos de Uso Comuns

1. **Aplicações Web**
   - ✅ Picos de tráfego
   - ✅ Sazonalidade
   - ✅ Eventos especiais
   - ✅ Manutenção

2. **Processamento de Dados**
   - ✅ Jobs em lote
   - ✅ Análise de dados
   - ✅ Machine Learning
   - ✅ Big Data

3. **Desenvolvimento**
   - ✅ Ambientes de teste
   - ✅ CI/CD
   - ✅ Desenvolvimento
   - ✅ Staging

4. **Enterprise**
   - ✅ Workloads variáveis
   - ✅ DR/BC
   - ✅ Migração
   - ✅ Consolidação

## Vantagens

### Técnicas
- ✅ **Flexibilidade** de recursos
- ✅ **Performance** otimizada
- ✅ **Disponibilidade** alta
- ✅ **Recuperação** rápida
- ✅ **Adaptabilidade** à carga

### Operacionais
- ✅ **Automação** de processos
- ✅ **Gerenciamento** simplificado
- ✅ **Monitoramento** integrado
- ✅ **Controle** granular
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
# Modificar tipo de instância (Scale Up/Down)
aws ec2 modify-instance-attribute \
    --instance-id i-1234567890abcdef0 \
    --instance-type "{\"Value\": \"t3.large\"}"

# Adicionar instâncias (Scale Out)
aws autoscaling set-desired-capacity \
    --auto-scaling-group-name my-asg \
    --desired-capacity 5

# Remover instâncias (Scale In)
aws autoscaling set-desired-capacity \
    --auto-scaling-group-name my-asg \
    --desired-capacity 2

# Verificar status
aws ec2 describe-instances \
    --instance-ids i-1234567890abcdef0
```

## Tipos de Elasticidade

### Vertical (Scale Up/Down)
- Aumento de recursos
- Redução de recursos
- Mudança de tipo
- Otimização de custos

### Horizontal (Scale Out/In)
- Adição de instâncias
- Remoção de instâncias
- Balanceamento de carga
- Alta disponibilidade

### Automática
- Auto Scaling
- CloudWatch
- Métricas
- Políticas

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

## Diagrama de Elasticidade EC2
![Diagrama de Elasticidade EC2](/images/Diagrama%20de%20Elasticidade%20EC2.png)

---

## Auto Scaling Groups (ASG)
![Auto Scaling Groups (ASG)](/images/Auto%20Scaling%20Groups%20(ASG)%20Elasticidade.png)

---

## Arquitetura Elástica - Exemplo Prático: Plataforma de VOD
![Arquitetura Elástica](/images/Arquitetura%20Elástica.png)

