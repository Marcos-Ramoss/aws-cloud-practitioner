# AWS Lambda

## Conceito
AWS Lambda é um serviço de computação serverless que permite executar código em resposta a eventos sem a necessidade de provisionar ou gerenciar servidores. O Lambda executa seu código apenas quando necessário e escala automaticamente, desde algumas requisições por dia até milhares por segundo.

## Características
- **Execução baseada em eventos**: Responde a eventos de outros serviços AWS (S3, DynamoDB, API Gateway, etc.) ou chamadas diretas.
- **Totalmente gerenciado**: Sem necessidade de gerenciar infraestrutura.
- **Escalabilidade automática**: Escala conforme a demanda de eventos.
- **Suporte a múltiplas linguagens**: Python, Node.js, Java, Go, .NET, Ruby, entre outras.
- **Cobrança por uso**: Paga apenas pelo tempo de execução e quantidade de requisições.
- **Integração com outros serviços AWS**: Pode ser acionado por mais de 200 serviços e integrações.
- **Gerenciamento de versões e aliases**: Permite versionamento e deploy controlado.
- **Ambiente seguro**: Execução isolada, com permissões controladas via IAM.

## Casos de Uso
- Processamento de arquivos em tempo real (ex: imagens enviadas ao S3)
- Backend de APIs serverless
- Automação de tarefas e workflows
- Processamento de streams de dados (Kinesis, DynamoDB Streams)
- Integração entre sistemas e microserviços
- Monitoramento e notificações automáticas

## Vantagens
- Sem necessidade de gerenciar servidores
- Escalabilidade automática e alta disponibilidade
- Redução de custos para workloads intermitentes
- Fácil integração com o ecossistema AWS
- Deploy rápido e versionamento

## Desvantagens
- Limite de tempo de execução (até 15 minutos por invocação)
- Limites de memória e armazenamento temporário
- Cold start (latência inicial em funções pouco utilizadas)
- Não indicado para workloads de longa duração ou com estado persistente

## Boas Práticas
- Manter funções pequenas e com responsabilidade única
- Utilizar variáveis de ambiente para configuração
- Monitorar logs e métricas via CloudWatch
- Controlar permissões com políticas IAM restritivas
- Utilizar camadas (Layers) para dependências compartilhadas
- Otimizar o tempo de inicialização e uso de memória

## Exemplo Prático (AWS CLI)
### Criar uma função Lambda (Python)
```sh
aws lambda create-function \
  --function-name minha-funcao \
  --runtime python3.12 \
  --role arn:aws:iam::ID_CONTA:role/minha-role-lambda \
  --handler lambda_function.lambda_handler \
  --zip-file fileb://meu_codigo.zip
```

### Invocar uma função Lambda
```sh
aws lambda invoke \
  --function-name minha-funcao \
  --payload '{"chave": "valor"}' \
  resposta.json
```

### Listar funções Lambda
```sh
aws lambda list-functions
```

## Configurações Importantes
- **Handler**: Ponto de entrada da função.
- **Timeout**: Tempo máximo de execução (até 15 minutos).
- **Memória**: 128 MB a 10 GB.
- **Variáveis de ambiente**: Configurações dinâmicas.
- **Triggers**: Eventos que disparam a função.
- **Layers**: Compartilhamento de dependências.
- **Permissões IAM**: Controle de acesso à função e recursos AWS.

## Considerações
- Funções são stateless (sem estado persistente entre execuções).
- Armazenamento temporário /tmp até 10 GB.
- Suporte a deployment package (zip) ou container image.
- Integração nativa com VPC, X-Ray, CloudWatch, Secrets Manager, etc.

## Imagem Ilustrativa
![Arquitetura AWS Lambda](../images/Arquitetura-AWS-Lambda.png)

> **Referência oficial:** [Documentação AWS Lambda](https://docs.aws.amazon.com/pt_br/lambda/latest/dg/welcome.html)
