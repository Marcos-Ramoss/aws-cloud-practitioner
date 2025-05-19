## Botão Voltar ao Início
[⬆️ Voltar ao Início](https://github.com/Marcos-Ramoss/aws-cloud-practitioner)

---

# Discos EBS (Elastic Block Store)

## Conceito

O Amazon EBS (Elastic Block Store) é um serviço de armazenamento em bloco persistente projetado para uso com instâncias Amazon EC2. Os discos EBS são dispositivos de armazenamento em bloco que podem ser anexados a instâncias EC2, funcionando como discos rígidos virtuais.

### Características Principais

1. **Persistência**
   - Dados mantidos independentemente da instância
   - Replicação automática dentro da AZ
   - Alta disponibilidade e durabilidade

2. **Flexibilidade**
   - Múltiplos tipos de volumes
   - Redimensionamento dinâmico
   - Modificação de tipo em tempo real
   - Anexação a múltiplas instâncias (Multi-Attach)

3. **Performance**
   - IOPS provisionados
   - Throughput otimizado
   - Baixa latência
   - Consistência de dados

## Para que são usados

### Casos de Uso Comuns

1. **Sistema Operacional**
   - ✅ Volume de boot
   - ✅ Sistema de arquivos
   - ✅ Aplicações do sistema
   - ✅ Configurações

2. **Bancos de Dados**
   - ✅ Dados transacionais
   - ✅ Logs de transações
   - ✅ Backups
   - ✅ Cache

3. **Aplicações Enterprise**
   - ✅ SAP
   - ✅ Oracle
   - ✅ Microsoft SQL Server
   - ✅ Aplicações críticas

4. **Big Data**
   - ✅ Hadoop
   - ✅ Spark
   - ✅ Análise de dados
   - ✅ Processamento em lote

## Vantagens

### Técnicas
- ✅ **Alta disponibilidade** (99.999%)
- ✅ **Durabilidade** dos dados
- ✅ **Performance** consistente
- ✅ **Escalabilidade** dinâmica
- ✅ **Backup** automatizado

### Operacionais
- ✅ **Fácil gerenciamento**
- ✅ **Monitoramento** integrado
- ✅ **Snapshots** incrementais
- ✅ **Recuperação** rápida
- ✅ **Migração** simplificada

### Econômicas
- ✅ **Pay-as-you-go**
- ✅ **Otimização** de custos
- ✅ **Sem investimento** inicial
- ✅ **Escalabilidade** econômica
- ✅ **Economia** de escala

## Desvantagens

### Técnicas
- ❌ **Limitação** por AZ
- ❌ **Latência** de rede
- ❌ **IOPS** limitados
- ❌ **Throughput** máximo
- ❌ **Tamanho** máximo

### Operacionais
- ❌ **Gestão** de snapshots
- ❌ **Backup** manual
- ❌ **Monitoramento** necessário
- ❌ **Manutenção** regular
- ❌ **Documentação** necessária

### Econômicas
- ❌ **Custos** de armazenamento
- ❌ **Custos** de IOPS
- ❌ **Custos** de snapshot
- ❌ **Custos** de transferência
- ❌ **Otimização** necessária

## Boas práticas

### Performance
- ✅ **Monitoramento** de métricas
- ✅ **Balanceamento** de carga
- ✅ **Otimização** de IOPS
- ✅ **Testes** de performance
- ✅ **Documentação** de benchmarks

### Segurança
- ✅ **Criptografia** ativa
- ✅ **Controle** de acesso
- ✅ **Backup** regular
- ✅ **Snapshots** automatizados
- ✅ **Auditoria** de acesso

### Custo
- ✅ **Análise** de uso
- ✅ **Otimização** de recursos
- ✅ **Monitoramento** de custos
- ✅ **Revisão** de preços
- ✅ **Planejamento** financeiro

## Exemplo prático

```bash
# Criar volume EBS
aws ec2 create-volume \
    --volume-type gp3 \
    --size 100 \
    --availability-zone us-east-1a

# Anexar volume à instância
aws ec2 attach-volume \
    --volume-id vol-1234567890abcdef0 \
    --instance-id i-1234567890abcdef0 \
    --device /dev/sdf

# Criar snapshot
aws ec2 create-snapshot \
    --volume-id vol-1234567890abcdef0 \
    --description "Backup diário"

# Modificar volume
aws ec2 modify-volume \
    --volume-id vol-1234567890abcdef0 \
    --size 200 \
    --volume-type gp3
```

## Tipos de Volumes

### SSD (Solid State Drive)

1. **General Purpose SSD (gp3)**
   - Performance balanceada
   - IOPS base: 3,000
   - Throughput base: 125 MB/s
   - Ideal para workloads variados

2. **Provisioned IOPS SSD (io2)**
   - Performance consistente
   - IOPS: até 256,000
   - Latência mais baixa
   - Ideal para aplicações críticas

### HDD (Hard Disk Drive)

1. **Throughput Optimized HDD (st1)**
   - Throughput otimizado
   - Ideal para big data
   - Custo-benefício
   - Workloads sequenciais

2. **Cold HDD (sc1)**
   - Custo mais baixo
   - Throughput menor
   - Ideal para dados frios
   - Acesso menos frequente

## Limitações e Considerações

1. **Tamanho**
   - Mínimo: 1 GB
   - Máximo: 16 TB
   - Incrementos de 1 GB

2. **Performance**
   - IOPS: até 256,000
   - Throughput: até 4,000 MB/s
   - Latência: < 1ms

3. **Disponibilidade**
   - Replicação dentro da AZ
   - Snapshots entre regiões
   - Backup automático

4. **Custo**
   - Armazenamento base
   - IOPS provisionados
   - Throughput adicional
   - Snapshots

---

## Arquitetura disco EBS
![ Arquitetura disco EBS](/images/Arquitetura%20disco%20EBS.png)

---

## Ambiente de Banco de Dados:
![Ambiente de Banco de Dados:](/images/Ambiente%20de%20Banco%20de%20Dados%20EBS.png)

--- 

## Segurança
![Segurança](/images/Segurança%20EBS.png)

