## Botão Voltar ao Início
[⬆️ Voltar ao Início](https://github.com/Marcos-Ramoss/aws-cloud-practitioner)

---

# AWS Glue

## Conceito

O AWS Glue é um serviço de integração de dados totalmente gerenciado que facilita a preparação, extração, transformação e carregamento (ETL) de dados para análise. Ele permite descobrir, catalogar, limpar, enriquecer e mover dados entre diferentes fontes de dados, tornando-os prontos para análise e machine learning.

### Características Principais

1. **Catálogo de Dados**
   - Descoberta automática de dados (crawler)
   - Catálogo centralizado e pesquisável

2. **ETL Serverless**
   - Criação de jobs ETL em Python ou Scala
   - Execução serverless, sem necessidade de gerenciar infraestrutura

3. **Transformação e Limpeza**
   - Suporte a transformações complexas de dados
   - Limpeza, enriquecimento e formatação de dados

4. **Integração**
   - Conexão com S3, Redshift, RDS, DynamoDB, JDBC, entre outros
   - Integração com serviços de analytics e machine learning da AWS

5. **Orquestração**
   - Workflows para pipelines de dados
   - Triggers e dependências entre jobs

## Para que é usado

### Casos de Uso Comuns

1. **Data Lakes**
   - ✅ Descoberta e catalogação de dados em S3
   - ✅ Preparação de dados para análise

2. **ETL e Integração**
   - ✅ Extração, transformação e carregamento de dados entre sistemas
   - ✅ Limpeza e padronização de dados

3. **Analytics e BI**
   - ✅ Preparação de dados para Redshift, Athena, EMR
   - ✅ Enriquecimento de dados para dashboards

4. **Machine Learning**
   - ✅ Preparação de datasets para modelos de ML

## Vantagens

### Técnicas
- ✅ **Serverless**: sem necessidade de gerenciar servidores
- ✅ **Escalabilidade** automática
- ✅ **Catálogo de dados** centralizado
- ✅ **Transformações** poderosas e flexíveis

### Operacionais
- ✅ **Automação** de pipelines de dados
- ✅ **Monitoramento** e logging integrados
- ✅ **Orquestração** de workflows

### Econômicas
- ✅ **Pay-as-you-go**
- ✅ **Redução** de custos operacionais
- ✅ **Sem** investimento inicial

## Desvantagens

### Técnicas
- ❌ **Limitações** em transformações muito customizadas
- ❌ **Latência** em jobs grandes ou complexos

### Operacionais
- ❌ **Curva de aprendizado** para scripts ETL
- ❌ **Dependência** do provedor AWS

### Econômicas
- ❌ **Custos** podem aumentar com grandes volumes de dados e execuções frequentes

## Boas práticas

### Nomenclatura
- ✅ **Identificação** por ambiente (dev, prod)
- ✅ **Padrão** de nomes para jobs, crawlers e tabelas

### Segurança
- ✅ **Acesso restrito** via IAM
- ✅ **Criptografia** de dados em trânsito e em repouso

### Custo
- ✅ **Monitoramento** de uso e execução
- ✅ **Revisão** periódica de jobs e crawlers

## Exemplo prático

```bash
# Criar um crawler para catalogar dados no S3
aws glue create-crawler \
    --name meu-crawler \
    --role GlueServiceRole \
    --database-name meu-database \
    --targets S3Targets=[{Path="s3://meu-bucket/dados/"}]

# Criar um job ETL
aws glue create-job \
    --name meu-job-etl \
    --role GlueServiceRole \
    --command '{"Name":"glueetl","ScriptLocation":"s3://meu-bucket/scripts/meu-script.py"}'
```

## Configurações Importantes

### Catálogo de Dados
- Crawlers automáticos
- Metadados pesquisáveis

### ETL
- Scripts em Python ou Scala
- Transformações customizadas

### Segurança
- Controle de acesso (IAM)
- Criptografia (KMS)

### Orquestração
- Workflows e triggers
- Monitoramento de execução

## Considerações Importantes

1. **Modelagem de Dados**
   - Definir esquemas e particionamento
   - Padronizar nomenclatura

2. **Segurança**
   - Acesso restrito via IAM
   - Criptografia de dados

3. **Custo**
   - Monitorar execuções e crawlers
   - Otimizar jobs para eficiência

4. **Escalabilidade**
   - Aproveitar execução serverless
   - Planejar para grandes volumes de dados

---

## Arquitetura AWS Glue
![Arquitetura AWS Glue](/images/Arquitetura%20AWS%20Glue.png)

---

## Gerenciamento de Catálogo Glue
![Gerenciamento de Catálogo Glue](/images/Catalogo%20AWS%20Glue.png)

---

## Integração com Serviços AWS
![Integração Glue AWS](/images/Integracao%20Glue%20AWS.png)

---

## Configuração típica
![Configuração típica Glue](/images/Configuracao%20tipica%20Glue.png)

---