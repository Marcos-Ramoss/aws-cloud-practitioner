## Botão Voltar ao Início
[⬆️ Voltar ao Início](https://github.com/Marcos-Ramoss/aws-cloud-practitioner)

---

# Tipos de Volumes EBS AWS

## Conceito

Os **Tipos de Volumes EBS** são diferentes categorias de armazenamento em bloco oferecidas pela AWS, cada uma otimizada para diferentes casos de uso e padrões de acesso. Eles são divididos em duas categorias principais: volumes baseados em SSD (Solid State Drive) e volumes baseados em HDD (Hard Disk Drive).

### Entendendo os Tipos de Volumes

1. **Volumes SSD**
   - **SSD de Uso Geral (gp2/gp3)**
     - Balanceamento entre IOPS e throughput
     - Ideal para cargas de trabalho transacionais
     - Suporte a boot volumes
     - Durabilidade de 99.8% - 99.9%

   - **SSD Provisionado (io1/io2)**
     - Alta performance para I/O intensivo
     - IOPS provisionados garantidos
     - Ideal para bancos de dados
     - Durabilidade de 99.999% (io2)

2. **Volumes HDD**
   - **Throughput Optimized (st1)**
     - Otimizado para throughput
     - Ideal para big data
     - Custo-benefício
     - Não suporta boot volumes

   - **Cold HDD (sc1)**
     - Menor custo por GB
     - Dados acessados raramente
     - Throughput limitado
     - Não suporta boot volumes

## Para que são usados

### Casos de Uso por Tipo

1. **SSD de Uso Geral (gp2/gp3)**
   - ✅ **Sistemas de desenvolvimento e teste**
   - ✅ **Desktops virtuais**
   - ✅ **Aplicações de baixa latência**
   - ✅ **Boot volumes**
   - ✅ **Sistemas de arquivos**

2. **SSD Provisionado (io1/io2)**
   - ✅ **Bancos de dados críticos**
   - ✅ **Aplicações I/O intensivas**
   - ✅ **SAP HANA**
   - ✅ **Microsoft SQL Server**
   - ✅ **Oracle Database**

3. **Throughput Optimized (st1)**
   - ✅ **Big Data**
   - ✅ **Data warehouses**
   - ✅ **Processamento de logs**
   - ✅ **ETL**
   - ✅ **Streaming**

4. **Cold HDD (sc1)**
   - ✅ **Backup**
   - ✅ **Arquivos raramente acessados**
   - ✅ **Dados históricos**
   - ✅ **Armazenamento de baixo custo**
   - ✅ **Dados de compliance**

## Vantagens

### Técnicas
- ✅ **Performance otimizada** por caso de uso
- ✅ **Escalabilidade** dinâmica
- ✅ **Durabilidade** garantida
- ✅ **Latência** consistente
- ✅ **Throughput** ajustável

### Operacionais
- ✅ **Flexibilidade** de escolha
- ✅ **Fácil migração** entre tipos
- ✅ **Monitoramento** integrado
- ✅ **Backup** simplificado
- ✅ **Recuperação** rápida

### Econômicas
- ✅ **Otimização** de custos
- ✅ **Pay-as-you-go**
- ✅ **Escalabilidade** econômica
- ✅ **Sem investimento** inicial
- ✅ **Custo-benefício**

## Desvantagens

### Técnicas
- ❌ **Limitações** de performance
- ❌ **Restrições** por tipo
- ❌ **Complexidade** de escolha
- ❌ **Dependência** de instância
- ❌ **Latência** variável

### Operacionais
- ❌ **Gestão** de diferentes tipos
- ❌ **Monitoramento** específico
- ❌ **Backup** por tipo
- ❌ **Manutenção** diferenciada
- ❌ **Documentação** necessária

### Econômicas
- ❌ **Custos** variáveis
- ❌ **Otimização** complexa
- ❌ **Previsão** de custos
- ❌ **Custos** de migração
- ❌ **Custos** de backup

## Boas práticas

### Seleção
- ✅ **Análise** de requisitos
- ✅ **Testes** de performance
- ✅ **Monitoramento** de uso
- ✅ **Revisão** periódica
- ✅ **Documentação** clara

### Performance
- ✅ **Otimização** de IOPS
- ✅ **Balanceamento** de carga
- ✅ **Monitoramento** contínuo
- ✅ **Ajuste** de parâmetros
- ✅ **Testes** regulares

### Custo
- ✅ **Análise** de custos
- ✅ **Otimização** de recursos
- ✅ **Monitoramento** de gastos
- ✅ **Revisão** de preços
- ✅ **Planejamento** financeiro

## Exemplo prático

```bash
# Criar volume gp3
aws ec2 create-volume \
    --availability-zone us-east-1a \
    --size 100 \
    --volume-type gp3 \
    --iops 3000 \
    --throughput 125

# Criar volume io2
aws ec2 create-volume \
    --availability-zone us-east-1a \
    --size 100 \
    --volume-type io2 \
    --iops 10000

# Criar volume st1
aws ec2 create-volume \
    --availability-zone us-east-1a \
    --size 500 \
    --volume-type st1

# Criar volume sc1
aws ec2 create-volume \
    --availability-zone us-east-1a \
    --size 1000 \
    --volume-type sc1
```

---

## Distribuição de Tipos EBS
![Distribuição de Tipos EBS](/images/Distribuição%20de%20Tipos%20EBS.png)

---

## Seleção de Tipos EBS
![Seleção de Tipos EBS](/images/Seleção%20de%20Tipos%20EBS.png)

---

## Diagrama de Seleçãos
![Diagrama de Seleção](/images/Diagrama%20de%20Seleção.png)

---

## Custo por Tipo
![Custo por Tipo](/images/Custo%20por%20Tipo.png) 