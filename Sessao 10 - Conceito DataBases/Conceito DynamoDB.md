## Botão Voltar ao Início
[⬆️ Voltar ao Início](https://github.com/Marcos-Ramoss/aws-cloud-practitioner)

---

# Amazon DynamoDB

## Conceito

O Amazon DynamoDB é um serviço de banco de dados NoSQL totalmente gerenciado, projetado para fornecer desempenho rápido e previsível com escalabilidade automática. Ele armazena dados em formato de chave-valor e documentos, sendo ideal para aplicações que exigem baixa latência e alta disponibilidade.

### Características Principais

1. **Modelo de Dados**
   - Estrutura baseada em tabelas, itens e atributos
   - Suporte a tipos de dados flexíveis (strings, números, listas, mapas)

2. **Desempenho e Escalabilidade**
   - Latência de milissegundos em qualquer escala
   - Escalabilidade automática de throughput e armazenamento
   - Suporte a milhões de solicitações por segundo

3. **Alta Disponibilidade e Durabilidade**
   - Replicação automática entre múltiplas zonas de disponibilidade (Multi-AZ)
   - Backup contínuo e restauração point-in-time

4. **Segurança**
   - Integração com IAM, VPC e KMS
   - Criptografia em trânsito e em repouso

5. **Gerenciamento Automatizado**
   - Monitoramento via Amazon CloudWatch
   - Atualizações automáticas de software
   - Suporte a triggers com AWS Lambda

## Para que é usado

### Casos de Uso Comuns

1. **Aplicações Web e Mobile**
   - ✅ Armazenamento de sessões de usuário
   - ✅ Catálogos de produtos
   - ✅ Perfis e preferências

2. **IoT e Gaming**
   - ✅ Telemetria de dispositivos
   - ✅ Leaderboards em tempo real

3. **Analytics e Big Data**
   - ✅ Armazenamento de eventos e logs
   - ✅ Processamento de grandes volumes de dados

4. **Enterprise**
   - ✅ Workloads serverless
   - ✅ Integração com outros serviços AWS

## Vantagens

### Técnicas
- ✅ **Alta performance** e baixa latência
- ✅ **Escalabilidade** automática
- ✅ **Alta disponibilidade** Multi-AZ
- ✅ **Backups** contínuos e automáticos
- ✅ **Triggers** com Lambda

### Operacionais
- ✅ **Gerenciamento** simplificado
- ✅ **Monitoramento** nativo (CloudWatch)
- ✅ **Automação** de tarefas administrativas

### Econômicas
- ✅ **Pay-as-you-go**
- ✅ **Redução** de custos operacionais
- ✅ **Sem** investimento inicial

## Desvantagens

### Técnicas
- ❌ **Limitações** de consultas complexas (joins, transações limitadas)
- ❌ **Modelagem** de dados diferente do relacional
- ❌ **Limitações** de tamanho de item (até 400 KB)

### Operacionais
- ❌ **Dependência** do provedor AWS
- ❌ **Migração** de bancos relacionais pode exigir reestruturação

### Econômicas
- ❌ **Custos** podem aumentar com alto volume de leitura/escrita
- ❌ **Cobrança** por throughput provisionado ou sob demanda

## Boas práticas

### Nomenclatura
- ✅ **Identificação** por ambiente (dev, prod)
- ✅ **Padrão** de nomes para tabelas

### Segurança
- ✅ **Acesso restrito** via IAM e VPC
- ✅ **Criptografia** ativada (em trânsito e em repouso)
- ✅ **Backups** regulares

### Custo
- ✅ **Monitoramento** de uso e dimensionamento
- ✅ **Revisão** periódica de throughput e storage

## Exemplo prático

```bash
# Criar tabela DynamoDB
aws dynamodb create-table \
    --table-name Usuarios \
    --attribute-definitions AttributeName=UserId,AttributeType=S \
    --key-schema AttributeName=UserId,KeyType=HASH \
    --provisioned-throughput ReadCapacityUnits=5,WriteCapacityUnits=5

# Inserir item na tabela
aws dynamodb put-item \
    --table-name Usuarios \
    --item '{"UserId": {"S": "123"}, "Nome": {"S": "João"}}'
```

## Configurações Importantes

### Backup e Restauração
- Backups automáticos contínuos
- Snapshots manuais
- Restauração point-in-time

### Alta Disponibilidade
- Replicação Multi-AZ automática

### Segurança
- Criptografia (KMS)
- Controle de acesso (IAM, VPC, Security Groups)

### Performance
- Auto Scaling de throughput
- Monitoramento de métricas (CloudWatch)
- Ajuste de índices secundários

## Considerações Importantes

1. **Modelagem de Dados**
   - Pensar em acesso por chave primária
   - Uso de índices secundários para consultas adicionais

2. **Segurança**
   - Acesso restrito à VPC
   - Criptografia e auditoria

3. **Backup**
   - Políticas de retenção
   - Testes de restauração

4. **Escalabilidade**
   - Dimensionamento automático de throughput
   - Monitoramento de performance

---

## Arquitetura Amazon DynamoDB
![Arquitetura Amazon DynamoDB](/images/Arquitetura%20DynamoDB.png)

---

## Gerenciamento de Backup DynamoDB
![Gerenciamento de Backup DynamoDB](/images/Backup%20DynamoDB.png)

---

## Integração com Serviços AWS
![Integração DynamoDB AWS](/images/Integracao%20DynamoDB%20AWS.png)

---

## Configuração típica
![Configuração típica DynamoDB](/images/Configuracao%20tipica%20DynamoDB.png)

---