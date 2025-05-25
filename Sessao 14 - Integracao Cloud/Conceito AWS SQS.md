## Botão Voltar ao Início
[⬆️ Voltar ao Início](https://github.com/Marcos-Ramoss/aws-cloud-practitioner)

---

# Amazon Simple Queue Service (SQS)

## Conceito

O Amazon SQS (Simple Queue Service) é um serviço gerenciado de filas de mensagens que permite desacoplar e escalar sistemas distribuídos, microsserviços e aplicações serverless. Ele oferece filas altamente disponíveis, seguras e escaláveis para troca de mensagens entre componentes de software.

### Características Principais

1. **Filas Gerenciadas**
   - Suporte a filas padrão (alta taxa, entrega eventual) e FIFO (ordem garantida, sem duplicidade)
   - Escalabilidade automática para milhões de mensagens por segundo

2. **Entrega Confiável**
   - Mensagens armazenadas redundante e duravelmente
   - Suporte a Dead Letter Queues (DLQ) para tratamento de falhas

3. **Segurança e Controle**
   - Criptografia em trânsito e em repouso
   - Controle de acesso via IAM e políticas de fila

4. **Integração**
   - Integração nativa com Lambda, SNS, EC2, ECS, S3, Step Functions, etc.
   - Suporte a triggers e eventos automáticos

## Para que é usado

### Casos de Uso Comuns

1. **Desacoplamento de Sistemas**
   - ✅ Comunicação assíncrona entre microsserviços
   - ✅ Bufferização de workloads e processamento em lote

2. **Escalabilidade e Resiliência**
   - ✅ Balanceamento de carga entre produtores e consumidores
   - ✅ Retry automático e tratamento de falhas

3. **Integração de Sistemas**
   - ✅ Orquestração de pipelines serverless
   - ✅ Integração com aplicações legadas

## Vantagens

### Técnicas
- ✅ **Alta disponibilidade** e durabilidade
- ✅ **Escalabilidade** automática
- ✅ **Entrega confiável** de mensagens
- ✅ **Integração** nativa com serviços AWS

### Operacionais
- ✅ **Gerenciamento** simplificado
- ✅ **Monitoramento** e métricas integradas

### Econômicas
- ✅ **Pay-as-you-go**
- ✅ **Redução** de custos com infraestrutura própria

## Desvantagens

### Técnicas
- ❌ **Limite** de tamanho de mensagem (256 KB)
- ❌ **Latência** eventual em filas padrão
- ❌ **Sem ordenação garantida** em filas padrão

### Operacionais
- ❌ **Gerenciamento** de DLQs pode ser complexo

### Econômicas
- ❌ **Custos** podem aumentar com alto volume de mensagens

## Boas práticas

### Nomenclatura
- ✅ **Padronização** de nomes de filas
- ✅ **Documentação** de fluxos e integrações

### Segurança
- ✅ **Uso de IAM** para controle de acesso
- ✅ **Criptografia** de mensagens

### Custo
- ✅ **Monitoramento** de uso e DLQs
- ✅ **Revisão** periódica de filas e políticas

## Exemplo prático

```powershell
# Criar uma fila padrão
aws sqs create-queue --queue-name minha-fila-padrao

# Criar uma fila FIFO
aws sqs create-queue --queue-name minha-fila.fifo --attributes FifoQueue=true

# Enviar mensagem para a fila
aws sqs send-message --queue-url https://sqs.us-east-1.amazonaws.com/123456789012/minha-fila-padrao --message-body "mensagem de teste"

# Receber mensagem da fila
aws sqs receive-message --queue-url https://sqs.us-east-1.amazonaws.com/123456789012/minha-fila-padrao
```

## Configurações Importantes

### Tipos de Fila
- Padrão: alta taxa, entrega eventual, sem ordenação
- FIFO: ordem garantida, sem duplicidade

### Dead Letter Queues (DLQ)
- Tratamento de mensagens não processadas
- Monitoramento e análise de falhas

### Segurança
- IAM, criptografia, políticas de acesso

## Considerações Importantes

1. **Gerenciamento de Mensagens**
   - Monitorar DLQs e falhas
   - Definir políticas de retenção e visibilidade

2. **Custo**
   - Monitorar uso e volume de mensagens
   - Revisar filas não utilizadas

3. **Integração**
   - Automatizar triggers e processamento com Lambda

---

## Arquitetura Amazon SQS
![Arquitetura Amazon SQS](/images/Arquitetura%20SQS%20AWS.png)

---

## Exemplo de Pipeline SQS
![Exemplo Pipeline SQS AWS](/images/Exemplo%20Pipeline%20SQS%20AWS.png)

---

## Integração com Serviços AWS
![Integração SQS AWS](/images/Integracao%20SQS%20AWS.png)

---

## Configuração típica
![Configuração típica SQS AWS](/images/Configuracao%20tipica%20SQS%20AWS.png)

---
