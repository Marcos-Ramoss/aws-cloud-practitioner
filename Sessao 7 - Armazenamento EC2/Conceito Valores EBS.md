## Botão Voltar ao Início
[⬆️ Voltar ao Início](/README.md)

---

# Valores do EBS AWS

## Conceito

Os **Valores do EBS** são baseados em diferentes componentes e modelos de cobrança, variando de acordo com o tipo de volume, região, tamanho e características específicas de performance. A AWS oferece uma estrutura de preços flexível que permite otimizar custos de acordo com as necessidades específicas de cada aplicação.

### Componentes de Custo

1. **Armazenamento Base**
   - Cobrança por GB-mês
   - Varia por tipo de volume
   - Preços diferentes por região
   - Faturamento por hora

2. **IOPS Provisionados**
   - Aplicável para volumes io1/io2
   - Cobrança por IOPS-mês
   - Escalonamento de preços
   - Diferentes faixas de preço

3. **Throughput**
   - Aplicável para volumes gp3
   - Cobrança por MB/s-mês
   - Preços por faixa
   - Otimização de custos

4. **Snapshots**
   - Cobrança por GB-mês
   - Diferentes preços por região
   - Compressão aplicada
   - Incrementais

## Para que são usados

### Modelos de Cobrança

1. **Pay-as-you-go**
   - ✅ **Flexibilidade** de custos
   - ✅ **Sem compromisso** de longo prazo
   - ✅ **Escalabilidade** dinâmica
   - ✅ **Otimização** contínua
   - ✅ **Controle** de gastos

2. **Reserved Capacity**
   - ✅ **Descontos** significativos
   - ✅ **Previsibilidade** de custos
   - ✅ **Compromisso** de uso
   - ✅ **Planejamento** financeiro
   - ✅ **Otimização** de recursos

3. **Volume Savings**
   - ✅ **Descontos** por volume
   - ✅ **Economia** em larga escala
   - ✅ **Flexibilidade** de uso
   - ✅ **Sem compromisso**
   - ✅ **Aplicação** automática

## Vantagens

### Técnicas
- ✅ **Transparência** de custos
- ✅ **Previsibilidade** de gastos
- ✅ **Otimização** de recursos
- ✅ **Flexibilidade** de pagamento
- ✅ **Controle** granular

### Operacionais
- ✅ **Fácil gestão** de custos
- ✅ **Monitoramento** integrado
- ✅ **Alertas** de gastos
- ✅ **Relatórios** detalhados
- ✅ **Análise** de uso

### Econômicas
- ✅ **Custo-benefício**
- ✅ **Economia** de escala
- ✅ **Otimização** de recursos
- ✅ **Previsibilidade** de gastos
- ✅ **Controle** de orçamento

## Desvantagens

### Técnicas
- ❌ **Complexidade** de preços
- ❌ **Variação** por região
- ❌ **Dependência** de uso
- ❌ **Custos** ocultos
- ❌ **Limitações** de performance

### Operacionais
- ❌ **Gestão** de múltiplos componentes
- ❌ **Monitoramento** complexo
- ❌ **Previsão** de custos
- ❌ **Otimização** contínua
- ❌ **Documentação** necessária

### Econômicas
- ❌ **Custos** variáveis
- ❌ **Previsão** complexa
- ❌ **Otimização** necessária
- ❌ **Custos** de migração
- ❌ **Custos** de backup

## Boas práticas

### Otimização
- ✅ **Análise** de uso
- ✅ **Monitoramento** de custos
- ✅ **Ajuste** de recursos
- ✅ **Revisão** periódica
- ✅ **Documentação** clara

### Custo
- ✅ **Análise** de preços
- ✅ **Otimização** de recursos
- ✅ **Monitoramento** de gastos
- ✅ **Revisão** de preços
- ✅ **Planejamento** financeiro

### Performance
- ✅ **Balanceamento** custo/performance
- ✅ **Monitoramento** de uso
- ✅ **Ajuste** de parâmetros
- ✅ **Testes** regulares
- ✅ **Documentação** de métricas

## Exemplo prático

```bash
# Calcular custo de volume gp3
aws ec2 describe-volumes \
    --filters "Name=volume-type,Values=gp3" \
    --query 'Volumes[*].[VolumeId,Size,State]' \
    --output table

# Calcular custo de IOPS provisionados
aws ec2 describe-volumes \
    --filters "Name=volume-type,Values=io2" \
    --query 'Volumes[*].[VolumeId,Iops,State]' \
    --output table

# Calcular custo de throughput
aws ec2 describe-volumes \
    --filters "Name=volume-type,Values=gp3" \
    --query 'Volumes[*].[VolumeId,Throughput,State]' \
    --output table

# Calcular custo de snapshots
aws ec2 describe-snapshots \
    --owner-ids self \
    --query 'Snapshots[*].[SnapshotId,VolumeSize,State]' \
    --output table
```

## Preços Atuais (2025)

### Volumes SSD

1. **General Purpose SSD (gp3)**
   - Armazenamento: $0.08/GB-mês
   - IOPS Base: 3,000 IOPS gratuitos
   - IOPS Adicional: $0.005/IOPS-mês
   - Throughput Base: 125 MB/s gratuito
   - Throughput Adicional: $0.06/MB/s-mês

2. **Provisioned IOPS SSD (io2)**
   - Armazenamento: $0.125/GB-mês
   - IOPS (até 32,000): $0.065/IOPS-mês
   - IOPS (32,001-64,000): $0.046/IOPS-mês
   - IOPS (>64,000): $0.032/IOPS-mês

### Volumes HDD

1. **Throughput Optimized HDD (st1)**
   - Armazenamento: $0.045/GB-mês
   - Throughput Base: 40 MB/s por TB
   - Throughput Máximo: 500 MB/s por volume

2. **Cold HDD (sc1)**
   - Armazenamento: $0.015/GB-mês
   - Throughput Base: 12 MB/s por TB
   - Throughput Máximo: 250 MB/s por volume

### Snapshots

1. **Snapshots Standard**
   - Armazenamento: $0.05/GB-mês
   - Compressão aplicada
   - Incrementais

2. **Snapshots Archive**
   - Armazenamento: $0.0125/GB-mês
   - Taxa de recuperação: $0.03/GB
   - Período mínimo: 90 dias

### Exemplos de Cálculo

1. **Volume gp3 de 2,000 GB por 12 horas**
   ```
   Custo do Volume: $0.08/GB-mês * 2,000 GB * (12/720) = $2.667
   ```

2. **Volume io2 de 2,000 GB com 60,000 IOPS**
   ```
   Custo do Volume: $0.125/GB-mês * 2,000 GB = $250
   Custo dos IOPS: ($0.065 * 32,000 + $0.046 * 28,000) = $3,328
   Total: $3,578/mês
   ```

3. **Snapshot de 200 GB no Archive**
   ```
   Custo Mensal: $0.0125/GB-mês * 200 GB = $2.50
   Custo de Recuperação: $0.03/GB * 200 GB = $6.00 (taxa única)
   ```

### Observações Importantes

1. **Faturamento**
   - Cobrança por segundo
   - Mínimo de 60 segundos
   - Faturamento por hora

2. **Regiões**
   - Preços variam por região
   - Consulte a calculadora de preços AWS
   - Considerar custos de transferência

3. **Free Tier**
   - 30 GB de armazenamento
   - 2 milhões de I/Os
   - 1 GB de snapshot 


---

## Componente de Custos EBS
![Componente de Custos EBS](/images/Componente%20de%20Custos%20EBS.png)

---

## Otimização de Custos
![Otimização de Custos](/images/Otimização%20de%20Custos.png)

---
