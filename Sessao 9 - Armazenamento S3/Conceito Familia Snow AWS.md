## Botão Voltar ao Início
[⬆️ Voltar ao Início](https://github.com/Marcos-Ramoss/aws-cloud-practitioner)

---

# AWS Snow Family

## Conceito

A AWS Snow Family é um conjunto de dispositivos físicos que permitem transferir grandes volumes de dados para dentro e fora da AWS, executar computação local e processamento de dados em ambientes com conectividade limitada ou sem conectividade. A família inclui AWS Snowcone, AWS Snowball e AWS Snowmobile.

### Características Principais

1. **Tipos de Dispositivos**
   - Snowcone (8 TB)
   - Snowball (50 TB)
   - Snowball Edge (80 TB)
   - Snowmobile (100 PB)

2. **Funcionalidades**
   - Transferência de dados
   - Computação local
   - Armazenamento local
   - Processamento de dados

3. **Comportamento**
   - Criptografia automática
   - Rastreamento em tempo real
   - Segurança física
   - Logs de auditoria

## Para que é usado

### Casos de Uso Comuns

1. **Transferência de Dados**
   - ✅ Migração para nuvem
   - ✅ Backup em nuvem
   - ✅ DR em nuvem
   - ✅ Arquivo em nuvem

2. **Computação Local**
   - ✅ Processamento de dados
   - ✅ Machine Learning
   - ✅ IoT
   - ✅ Edge Computing

3. **Ambientes Remotos**
   - ✅ Locais sem conectividade
   - ✅ Locais com conectividade limitada
   - ✅ Locais temporários
   - ✅ Locais móveis

4. **Compliance**
   - ✅ Retenção de dados
   - ✅ Auditoria
   - ✅ Conformidade
   - ✅ Segurança

## Vantagens

### Técnicas
- ✅ **Transferência** rápida
- ✅ **Computação** local
- ✅ **Segurança** robusta
- ✅ **Rastreabilidade**
- ✅ **Escalabilidade**

### Operacionais
- ✅ **Simplicidade** de uso
- ✅ **Monitoramento** nativo
- ✅ **Gerenciamento** centralizado
- ✅ **Documentação** completa
- ✅ **Suporte** AWS

### Econômicas
- ✅ **Custo-benefício**
- ✅ **Otimização** de recursos
- ✅ **Redução** de infraestrutura
- ✅ **Economia** em transferência
- ✅ **Escalabilidade** econômica

## Desvantagens

### Técnicas
- ❌ **Tempo** de entrega
- ❌ **Limitações** de capacidade
- ❌ **Dependência** de logística
- ❌ **Restrições** de uso
- ❌ **Complexidade** de configuração

### Operacionais
- ❌ **Monitoramento** necessário
- ❌ **Configuração** manual
- ❌ **Testes** de performance
- ❌ **Documentação** importante
- ❌ **Treinamento** necessário

### Econômicas
- ❌ **Custos** de dispositivo
- ❌ **Custos** de transporte
- ❌ **Custos** de armazenamento
- ❌ **Custos** de API
- ❌ **Custos** de gerenciamento

## Boas práticas

### Configuração
- ✅ **Planejar** capacidade
- ✅ **Configurar** segurança
- ✅ **Definir** políticas
- ✅ **Monitorar** uso
- ✅ **Revisar** periodicamente

### Gerenciamento
- ✅ **Monitorar** status
- ✅ **Auditar** acessos
- ✅ **Documentar** processos
- ✅ **Treinar** equipe
- ✅ **Testar** recuperação

### Segurança
- ✅ **Encryption** em trânsito
- ✅ **Encryption** em repouso
- ✅ **IAM roles**
- ✅ **Bucket policies**
- ✅ **Access logging**

## Exemplo prático

```bash
# Criar um job do Snowball
aws snowball create-job \
    --job-type "IMPORT" \
    --resources '{
        "S3Resources": [
            {
                "BucketArn": "arn:aws:s3:::meu-bucket",
                "KeyRange": {
                    "BeginMarker": "",
                    "EndMarker": ""
                }
            }
        ]
    }' \
    --description "Importação de dados para S3" \
    --address-id "ADID1234" \
    --kms-arn "arn:aws:kms:region:account:key/key-id" \
    --role-arn "arn:aws:iam::account:role/snowball-role" \
    --shipping-option "EXPRESS" \
    --notification '{
        "SnsTopicARN": "arn:aws:sns:region:account:topic-name"
    }'

# Listar jobs do Snowball
aws snowball list-jobs

# Atualizar status do job
aws snowball update-job \
    --job-id "JOBID1234" \
    --shipping-option "EXPRESS" \
    --notification '{
        "SnsTopicARN": "arn:aws:sns:region:account:topic-name"
    }'
```

## Tipos de Dispositivos

### Snowcone
- 8 TB de capacidade
- Computação local
- IoT e Edge
- Portátil

### Snowball
- 50 TB de capacidade
- Transferência de dados
- Backup
- Arquivo

### Snowball Edge
- 80 TB de capacidade
- Computação local
- Armazenamento local
- Processamento de dados

### Snowmobile
- 100 PB de capacidade
- Transferência massiva
- Migração de data centers
- Backup em larga escala

## Considerações Importantes

1. **Logística**
   - Tempo de entrega
   - Custos de transporte
   - Segurança física
   - Rastreabilidade

2. **Segurança**
   - Autenticação
   - Autorização
   - Encryption
   - Logging

3. **Custos**
   - Dispositivo
   - Transporte
   - Armazenamento
   - Gerenciamento

4. **Compliance**
   - Regulamentações
   - Requisitos
   - Auditoria
   - Documentação

---

## Tipos de Dispositivos Snow
![Tipos de Dispositivos Snow](/images/Tipos%20de%20Dispositivos%20Snow.png)

---

## Como Funciona a Integração com S3?
![Como Funciona a Integração com S3](/images/Como%20Funciona%20a%20Integração%20com%20S3.png)

---

## Casos de Uso: Migração para S3
![Casos de Uso](/images/Casos%20de%20Uso.png)

--- 

## Quando Usar Snow vs. S3 Transfer Acceleration?
![Quando Usar Snow vs. S3 Transfer Acceleration](/images/Quando%20Usar%20Snow%20vs.%20S3%20Transfer%20Acceleration.png)

---



