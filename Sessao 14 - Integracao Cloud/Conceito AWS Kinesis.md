## Botão Voltar ao Início
[⬆️ Voltar ao Início](https://github.com/Marcos-Ramoss/aws-cloud-practitioner)

---

# Amazon Kinesis

## Conceito

O Amazon Kinesis é um serviço gerenciado da AWS para coleta, processamento e análise de grandes volumes de dados em tempo real. Ele permite ingerir, processar e analisar streams de dados como logs, eventos, cliques, métricas e IoT, facilitando a criação de aplicações de análise em tempo real.

### Características Principais

1. **Processamento em Tempo Real**
   - Ingestão e análise de dados em segundos
   - Suporte a múltiplos consumidores simultâneos

2. **Escalabilidade e Performance**
   - Escalabilidade automática para milhares de streams e shards
   - Baixa latência para ingestão e processamento

3. **Serviços Kinesis**
   - **Kinesis Data Streams**: ingestão e processamento de streams de dados
   - **Kinesis Data Firehose**: entrega automática de dados para S3, Redshift, Elasticsearch, Splunk
   - **Kinesis Data Analytics**: análise SQL em tempo real sobre streams
   - **Kinesis Video Streams**: ingestão e processamento de vídeo em tempo real

4. **Integração e Segurança**
   - Integração com Lambda, S3, Redshift, DynamoDB, EMR, etc.
   - Controle de acesso via IAM e criptografia de dados

## Para que é usado

### Casos de Uso Comuns

1. **Monitoramento e Analytics em Tempo Real**
   - ✅ Processamento de logs, métricas e eventos
   - ✅ Detecção de fraudes e anomalias

2. **IoT e Telemetria**
   - ✅ Ingestão de dados de sensores e dispositivos

3. **Streaming de Dados**
   - ✅ Processamento de cliques, eventos e interações de usuários

4. **Processamento de Vídeo**
   - ✅ Ingestão e análise de streams de vídeo

## Vantagens

### Técnicas
- ✅ **Processamento** em tempo real
- ✅ **Escalabilidade** automática
- ✅ **Baixa latência**
- ✅ **Integração** nativa com serviços AWS

### Operacionais
- ✅ **Gerenciamento** simplificado
- ✅ **Monitoramento** e métricas integradas

### Econômicas
- ✅ **Pay-as-you-go**
- ✅ **Redução** de custos com infraestrutura própria

## Desvantagens

### Técnicas
- ❌ **Curva de aprendizado** para modelagem de streams
- ❌ **Limitações** de retenção de dados (padrão 24h, até 7 dias)

### Operacionais
- ❌ **Gerenciamento** de shards pode ser complexo em grandes volumes

### Econômicas
- ❌ **Custos** podem aumentar com alto volume de dados e shards

## Boas práticas

### Nomenclatura
- ✅ **Padronização** de nomes de streams e firehoses
- ✅ **Documentação** de pipelines e integrações

### Segurança
- ✅ **Uso de IAM** para controle de acesso
- ✅ **Criptografia** de dados em trânsito e repouso

### Custo
- ✅ **Monitoramento** de uso e shards
- ✅ **Revisão** periódica de streams e firehoses

## Exemplo prático

```powershell
# Criar um stream Kinesis Data Streams
aws kinesis create-stream --stream-name meu-stream --shard-count 2

# Enviar dados para o stream
aws kinesis put-record --stream-name meu-stream --partition-key chave1 --data "mensagem de teste"

# Criar um delivery stream Kinesis Data Firehose
aws firehose create-delivery-stream --delivery-stream-name meu-firehose --s3-destination-configuration ...
```

## Configurações Importantes

### Shards e Throughput
- Definir número de shards conforme volume de dados
- Auto scaling de shards disponível

### Integração
- Lambda, S3, Redshift, Elasticsearch, Firehose, Analytics

### Segurança
- IAM, criptografia, monitoramento de acesso

## Considerações Importantes

1. **Gerenciamento de Shards**
   - Monitorar throughput e ajustar shards

2. **Retenção de Dados**
   - Planejar retenção conforme necessidade (padrão 24h, até 7 dias)

3. **Custo**
   - Monitorar uso e custos de shards e firehoses

4. **Monitoramento**
   - Usar CloudWatch para métricas e alertas

---

## Arquitetura Amazon Kinesis
![Arquitetura Amazon Kinesis](/images/Arquitetura%20Kinesis%20AWS.png)

---

## Exemplo de Pipeline Kinesis
![Exemplo Pipeline Kinesis AWS](/images/Exemplo%20Pipeline%20Kinesis%20AWS.png)

---

## Integração com Serviços AWS
![Integração Kinesis AWS](/images/Integracao%20Kinesis%20AWS.png)

---

## Configuração típica
![Configuração típica Kinesis AWS](/images/Configuracao%20tipica%20Kinesis%20AWS.png)

---
