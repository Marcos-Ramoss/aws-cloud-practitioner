## Botão Voltar ao Início
[⬆️ Voltar ao Início](https://github.com/Marcos-Ramoss/aws-cloud-practitioner)

---

# Amazon Simple Notification Service (SNS)

## Conceito
Amazon Simple Notification Service (SNS) é um serviço de mensagens totalmente gerenciado e altamente escalável que permite desacoplar e distribuir mensagens entre sistemas, aplicações e dispositivos. O SNS suporta padrões de publicação/assinatura (pub/sub), permitindo que produtores de mensagens (publicadores) enviem mensagens para tópicos, que por sua vez entregam essas mensagens a um ou mais assinantes (consumidores).

## Características
- **Pub/Sub**: Permite comunicação assíncrona entre sistemas via tópicos.
- **Entrega em múltiplos protocolos**: HTTP/S, Email, SMS, Lambda, SQS, aplicativos móveis (push notifications).
- **Alta disponibilidade e escalabilidade**: Gerenciado pela AWS, com entrega confiável e rápida.
- **Filtragem de mensagens**: Assinantes podem receber apenas mensagens de interesse.
- **Integração com outros serviços AWS**: Como Lambda, SQS, CloudWatch, etc.
- **Criptografia**: Suporte a criptografia em trânsito (TLS) e em repouso (KMS).
- **Monitoramento**: Métricas via Amazon CloudWatch.

## Casos de Uso
- Notificações em tempo real (alertas, status de sistemas, etc.)
- Integração entre microserviços
- Fan-out de mensagens para múltiplos destinos
- Disparo de workflows automáticos
- Notificações móveis (push)

## Vantagens
- Gerenciado, sem necessidade de infraestrutura
- Suporte a múltiplos protocolos de entrega
- Escalabilidade automática
- Baixa latência
- Fácil integração com outros serviços AWS

## Desvantagens
- Limites de throughput para alguns protocolos (ex: SMS)
- Custo por volume de mensagens
- Não garante ordenação de mensagens

## Boas Práticas
- Utilizar filtragem de mensagens para reduzir processamento desnecessário
- Monitorar taxas de entrega e falhas via CloudWatch
- Usar tópicos separados para diferentes tipos de mensagens
- Configurar políticas de acesso restritivas (IAM)
- Habilitar criptografia para dados sensíveis

## Exemplo Prático (AWS CLI)
### Criar um tópico SNS
```sh
aws sns create-topic --name MeuTopico
```

### Listar tópicos
```sh
aws sns list-topics
```

### Assinar um email ao tópico
```sh
aws sns subscribe --topic-arn arn:aws:sns:REGIAO:ID_CONTA:MeuTopico --protocol email --notification-endpoint seu@email.com
```

### Publicar mensagem
```sh
aws sns publish --topic-arn arn:aws:sns:REGIAO:ID_CONTA:MeuTopico --message "Mensagem de teste"
```

## Configurações Importantes
- **Políticas de acesso**: Controle quem pode publicar ou assinar tópicos.
- **Retry Policy**: Configurar tentativas de reentrega para endpoints HTTP/S.
- **Dead Letter Queue (DLQ)**: Integrar com SQS para mensagens não entregues.
- **Filtro de mensagens**: Definir regras para entrega seletiva.

## Considerações
- Mensagens podem ser entregues múltiplas vezes (at-least-once delivery)
- Para processamento garantido, combine SNS com SQS
- Limites de tamanho de mensagem: até 256 KB

## Imagem Ilustrativa
![Arquitetura SNS](../images/Arquitetura-SNS.png)

> **Referência oficial:** [Documentação Amazon SNS](https://docs.aws.amazon.com/pt_br/sns/latest/dg/welcome.html)
