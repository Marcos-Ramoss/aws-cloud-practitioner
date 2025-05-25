## Botão Voltar ao Início
[⬆️ Voltar ao Início](https://github.com/Marcos-Ramoss/aws-cloud-practitioner)

---

# Amazon Database Services

## Conceito

Os serviços de banco de dados da AWS oferecem soluções gerenciadas para armazenar, consultar e gerenciar dados estruturados e não estruturados. Eles suportam diferentes modelos de dados, como relacional, NoSQL, em memória, gráfico, entre outros, proporcionando alta disponibilidade, escalabilidade e segurança.

### Características Principais

1. **Tipos de Bancos de Dados**
   - Relacional (RDS, Aurora)
   - NoSQL (DynamoDB)
   - Em memória (ElastiCache)
   - Gráfico (Neptune)
   - Data Warehouse (Redshift)
   - Documentos (DocumentDB)
   - Time Series (Timestream)

2. **Funcionalidades**
   - Backup automatizado
   - Replicação Multi-AZ
   - Escalabilidade automática
   - Monitoramento integrado
   - Segurança avançada

3. **Configurações**
   - Controle de acesso (IAM, Security Groups)
   - Criptografia em repouso e em trânsito
   - Parâmetros de performance
   - Políticas de backup e retenção

## Para que é usado

### Casos de Uso Comuns

1. **Aplicações Web e Mobile**
   - ✅ Armazenamento de dados transacionais
   - ✅ Sessões de usuário
   - ✅ Catálogos de produtos

2. **Analytics e BI**
   - ✅ Data Warehousing
   - ✅ Dashboards
   - ✅ Relatórios

3. **IoT e Big Data**
   - ✅ Processamento de grandes volumes
   - ✅ Armazenamento de eventos
   - ✅ Time Series

4. **Enterprise**
   - ✅ ERP/CRM
   - ✅ Sistemas legados
   - ✅ Compliance e auditoria

## Vantagens

### Técnicas
- ✅ **Alta disponibilidade** e redundância
- ✅ **Escalabilidade** automática
- ✅ **Backup** e restauração simplificados
- ✅ **Performance** otimizada
- ✅ **Segurança** integrada

### Operacionais
- ✅ **Gerenciamento** automatizado
- ✅ **Monitoramento** nativo
- ✅ **Atualizações** automáticas
- ✅ **Recuperação** de desastres

### Econômicas
- ✅ **Pay-as-you-go**
- ✅ **Redução** de custos operacionais
- ✅ **Sem** investimento inicial
- ✅ **Otimização** de recursos

## Desvantagens

### Técnicas
- ❌ **Limitações** de customização
- ❌ **Dependência** do provedor
- ❌ **Latência** de rede
- ❌ **Migração** pode ser complexa

### Operacionais
- ❌ **Treinamento** necessário
- ❌ **Monitoramento** contínuo
- ❌ **Gerenciamento** de permissões

### Econômicas
- ❌ **Custos** de transferência
- ❌ **Custos** de licenciamento (alguns engines)
- ❌ **Cobrança** por recursos ociosos

## Boas práticas

### Nomenclatura
- ✅ **Nomes** padronizados
- ✅ **Identificação** por ambiente (dev, prod)
- ✅ **Documentação** clara

### Segurança
- ✅ **IAM** policies
- ✅ **Criptografia** ativada
- ✅ **Backup** regular
- ✅ **Auditoria** habilitada

### Custo
- ✅ **Monitoramento** de uso
- ✅ **Dimensionamento** correto
- ✅ **Revisão** de instâncias

## Exemplo prático

```bash
# Criar instância RDS MySQL
aws rds create-db-instance \
    --db-instance-identifier meu-db-exemplo \
    --db-instance-class db.t3.micro \
    --engine mysql \
    --allocated-storage 20 \
    --master-username admin \
    --master-user-password senhaSegura123 \
    --backup-retention-period 7 \
    --vpc-security-group-ids sg-12345678

# Criar tabela DynamoDB
aws dynamodb create-table \
    --table-name Usuarios \
    --attribute-definitions AttributeName=UserId,AttributeType=S \
    --key-schema AttributeName=UserId,KeyType=HASH \
    --provisioned-throughput ReadCapacityUnits=5,WriteCapacityUnits=5
```

## Configurações Importantes

### Backup e Restauração
- Backups automáticos
- Snapshots manuais
- Retenção configurável

### Replicação
- Multi-AZ
- Read Replicas
- Cross-region

### Segurança
- Criptografia
- Controle de acesso
- Auditoria

### Performance
- Auto Scaling
- Monitoramento de métricas
- Ajuste de parâmetros

## Considerações Importantes

1. **Escolha do Engine**
   - Compatibilidade
   - Performance
   - Custo

2. **Segurança**
   - Acesso restrito
   - Criptografia
   - Auditoria

3. **Backup**
   - Políticas de retenção
   - Testes de restauração

4. **Escalabilidade**
   - Dimensionamento automático
   - Read Replicas

---

## Arquitetura de Banco de Dados AWS
![Arquitetura de Banco de Dados](/images/Arquitetura%20Banco%20de%20Dados.png)

---

## Gerenciamento de Backup
![Gerenciamento de Backup](/images/Gerenciamento%20Backup.png)

---

## Integração com Serviços AWS
![Integração com Serviços AWS](/images/Integracao%20Servicos%20AWS.png)

---

## Configuração típica
![Configuração típica](/images/Configuracao%20tipica%20DB.png)

---