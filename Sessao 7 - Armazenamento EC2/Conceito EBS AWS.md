# EBS AWS (Elastic Block Store)

## Conceito

O **Amazon EBS** (Elastic Block Store) é um serviço de armazenamento em bloco que fornece volumes de armazenamento persistentes para uso com instâncias EC2. É uma solução de armazenamento de alto desempenho e baixa latência que permite criar e gerenciar volumes de armazenamento independentes das instâncias EC2.

### Entendendo o EBS

1. **Características Principais**
   - **Persistência**: Dados mantidos mesmo após término da instância
   - **Alta Disponibilidade**: Replicação automática dentro da AZ
   - **Escalabilidade**: Redimensionamento dinâmico
   - **Backup**: Snapshots para backup e recuperação
   - **Criptografia**: Suporte nativo a criptografia

2. **Tipos de Volumes**
   - **SSD de Uso Geral (gp2/gp3)**: Balanceamento entre IOPS e throughput
   - **SSD Provisionado (io1/io2)**: Alta performance para cargas I/O intensivas
   - **HDD Throughput (st1)**: Otimizado para throughput
   - **HDD Cold (sc1)**: Baixo custo para dados acessados raramente

3. **Recursos Principais**
   - **Volumes**: Armazenamento em bloco persistente
   - **Snapshots**: Backup pontual dos volumes
   - **Criptografia**: Proteção de dados em repouso
   - **Monitoramento**: Métricas de performance
   - **Resizing**: Redimensionamento dinâmico

## Para que é usado

### Casos de Uso Comuns

1. **Sistemas de Arquivos**
   - ✅ **Sistemas operacionais**
   - ✅ **Aplicações empresariais**
   - ✅ **Bancos de dados**
   - ✅ **Sistemas de arquivos**
   - ✅ **Armazenamento de dados**

2. **Bancos de Dados**
   - ✅ **Oracle**
   - ✅ **SQL Server**
   - ✅ **MySQL/PostgreSQL**
   - ✅ **MongoDB**
   - ✅ **Cassandra**

3. **Aplicações Empresariais**
   - ✅ **SAP**
   - ✅ **Microsoft Exchange**
   - ✅ **SharePoint**
   - ✅ **Aplicações críticas**
   - ✅ **Sistemas legados**

4. **Big Data e Analytics**
   - ✅ **Hadoop**
   - ✅ **Spark**
   - ✅ **Data warehouses**
   - ✅ **ETL processes**
   - ✅ **Machine Learning**

## Vantagens

### Técnicas
- ✅ **Alta disponibilidade**
- ✅ **Baixa latência**
- ✅ **Escalabilidade**
- ✅ **Persistência**
- ✅ **Performance consistente**

### Operacionais
- ✅ **Fácil gerenciamento**
- ✅ **Backup simplificado**
- ✅ **Monitoramento integrado**
- ✅ **Recuperação rápida**
- ✅ **Flexibilidade**

### Econômicas
- ✅ **Custo-benefício**
- ✅ **Otimização de custos**
- ✅ **Escalabilidade econômica**
- ✅ **Sem investimento inicial**
- ✅ **Pay-as-you-go**

## Desvantagens

### Técnicas
- ❌ **Limitação por AZ**
- ❌ **Latência em algumas operações**
- ❌ **Limites de IOPS**
- ❌ **Complexidade de gerenciamento**
- ❌ **Dependência de rede**

### Operacionais
- ❌ **Gestão de snapshots**
- ❌ **Monitoramento contínuo**
- ❌ **Backup e recuperação**
- ❌ **Manutenção**
- ❌ **Documentação**

### Econômicas
- ❌ **Custos de snapshot**
- ❌ **Custos de transferência**
- ❌ **Custos de IOPS**
- ❌ **Custos de armazenamento**
- ❌ **Custos de backup**

## Boas práticas

### Configuração
- ✅ **Seleção adequada do tipo**
- ✅ **Dimensionamento correto**
- ✅ **Criptografia ativa**
- ✅ **Backup regular**
- ✅ **Monitoramento**

### Performance
- ✅ **Otimização de IOPS**
- ✅ **Balanceamento de carga**
- ✅ **Monitoramento de métricas**
- ✅ **Ajuste de performance**
- ✅ **Cache adequado**

### Segurança
- ✅ **Criptografia de dados**
- ✅ **Controle de acesso**
- ✅ **Backup seguro**
- ✅ **Auditoria**
- ✅ **Compliance**

## Exemplo prático

```bash
# Criar volume EBS
aws ec2 create-volume \
    --availability-zone us-east-1a \
    --size 100 \
    --volume-type gp3 \
    --encrypted

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
    --volume-type io2 \
    --iops 4000
```

---

## Arquitetura Básica do EBS
![Arquitetura Básica do EBS](/images/Arquitetura%20Básica%20do%20EBS.png)

---

## Fluxo de Snapshots
![Fluxo de Snapshots](/images/Fluxo%20de%20Snapshots.png)

---

## Solução de Problemas Comuns
![Solução de Problemas Comuns](/images/Solução%20de%20Problemas%20Comuns.png)

---

## Configuração para Banco de Dados
![Configuração para Banco de Dados](/images/Configuração%20para%20Banco%20de%20Dados.png)

---

## Segurança
![Segurança](/images/Segurança.png) 

---

## Cenário de Disaster Recovery
![Cenário de Disaster Recovery](/images/Cenário%20de%20Disaster%20Recovery.png) 