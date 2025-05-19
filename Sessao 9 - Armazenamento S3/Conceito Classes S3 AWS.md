## Botão Voltar ao Início
[⬆️ Voltar ao Início](https://github.com/Marcos-Ramoss/aws-cloud-practitioner)

---

# Amazon S3 Storage Classes

## Conceito

As classes de armazenamento do Amazon S3 são diferentes níveis de armazenamento projetados para diferentes casos de uso, com base em requisitos de acesso, durabilidade e custo. Cada classe de armazenamento é otimizada para um padrão específico de acesso aos dados.

### Características Principais

1. **Classes de Acesso Frequente**
   - S3 Standard
   - S3 Express One Zone
   - Alta disponibilidade
   - Baixa latência

2. **Classes de Acesso Infrequente**
   - S3 Standard-IA
   - S3 One Zone-IA
   - Custo reduzido
   - Taxa de recuperação

3. **Classes de Arquivo**
   - S3 Glacier
   - S3 Glacier Deep Archive
   - Custo mínimo
   - Recuperação flexível

4. **Classes Inteligentes**
   - S3 Intelligent-Tiering
   - Otimização automática
   - Monitoramento de acesso
   - Transição automática

## Para que é usado

### Casos de Uso Comuns

1. **S3 Standard**
   - ✅ Dados frequentemente acessados
   - ✅ Websites dinâmicos
   - ✅ Aplicações em nuvem
   - ✅ Big Data analytics

2. **S3 Standard-IA**
   - ✅ Backups de longo prazo
   - ✅ Dados de DR
   - ✅ Conteúdo menos acessado
   - ✅ Dados de compliance

3. **S3 Glacier**
   - ✅ Arquivos de longo prazo
   - ✅ Dados de compliance
   - ✅ Backups de arquivo
   - ✅ Dados históricos

4. **S3 Intelligent-Tiering**
   - ✅ Padrões de acesso desconhecidos
   - ✅ Dados com acesso variável
   - ✅ Otimização automática
   - ✅ Custos reduzidos

## Vantagens

### Técnicas
- ✅ **Durabilidade** 99.999999999%
- ✅ **Disponibilidade** configurável
- ✅ **Performance** otimizada
- ✅ **Recuperação** flexível
- ✅ **Escalabilidade** ilimitada

### Operacionais
- ✅ **Gerenciamento** automático
- ✅ **Transição** automática
- ✅ **Monitoramento** nativo
- ✅ **Alertas** configuráveis
- ✅ **Manutenção** reduzida

### Econômicas
- ✅ **Custos** otimizados
- ✅ **Pay-as-you-go**
- ✅ **Sem** investimento inicial
- ✅ **Escalabilidade** econômica
- ✅ **Custo-benefício**

## Desvantagens

### Técnicas
- ❌ **Latência** variável
- ❌ **Custo** de recuperação
- ❌ **Limitações** de acesso
- ❌ **Complexidade** de configuração
- ❌ **Restrições** de uso

### Operacionais
- ❌ **Monitoramento** necessário
- ❌ **Configuração** manual
- ❌ **Testes** de performance
- ❌ **Documentação** importante
- ❌ **Treinamento** necessário

### Econômicas
- ❌ **Custos** de armazenamento
- ❌ **Custos** de recuperação
- ❌ **Custos** de requisições
- ❌ **Custos** de transferência
- ❌ **Custos** de API

## Boas práticas

### Seleção de Classe
- ✅ **Análise** de padrões de acesso
- ✅ **Avaliação** de custos
- ✅ **Requisitos** de performance
- ✅ **Necessidades** de recuperação
- ✅ **Compliance** e regulamentações

### Otimização
- ✅ **Lifecycle** policies
- ✅ **Monitoramento** de uso
- ✅ **Análise** de custos
- ✅ **Revisão** periódica
- ✅ **Ajuste** de configurações

### Segurança
- ✅ **Encryption**
- ✅ **Versionamento**
- ✅ **MFA Delete**
- ✅ **Bucket policies**
- ✅ **Access logging**

## Exemplo prático

```bash
# Configurar lifecycle para transição entre classes
aws s3api put-bucket-lifecycle-configuration \
    --bucket meu-bucket-exemplo \
    --lifecycle-configuration '{
        "Rules": [
            {
                "ID": "TransicaoParaIA",
                "Status": "Enabled",
                "Transitions": [
                    {
                        "Days": 30,
                        "StorageClass": "STANDARD_IA"
                    }
                ]
            },
            {
                "ID": "TransicaoParaGlacier",
                "Status": "Enabled",
                "Transitions": [
                    {
                        "Days": 90,
                        "StorageClass": "GLACIER"
                    }
                ]
            }
        ]
    }'

# Configurar Intelligent-Tiering
aws s3api put-bucket-intelligent-tiering-configuration \
    --bucket meu-bucket-exemplo \
    --id "config1" \
    --intelligent-tiering-configuration '{
        "Status": "Enabled",
        "Tierings": [
            {
                "Days": 90,
                "AccessTier": "DEEP_ARCHIVE_ACCESS"
            }
        ]
    }'
```

## Classes de Armazenamento

### S3 Standard
- Acesso frequente
- Baixa latência
- Alta durabilidade
- Alta disponibilidade

### S3 Standard-IA
- Acesso infrequente
- Baixo custo de armazenamento
- Taxa de recuperação
- Alta durabilidade

### S3 One Zone-IA
- Acesso infrequente
- Custo ainda menor
- Single AZ
- Alta durabilidade

### S3 Glacier
- Arquivo de longo prazo
- Custo mínimo
- Recuperação flexível
- Alta durabilidade

### S3 Glacier Deep Archive
- Arquivo mais longo prazo
- Custo mais baixo
- Recuperação mais lenta
- Alta durabilidade

### S3 Intelligent-Tiering
- Otimização automática
- Monitoramento de acesso
- Transição automática
- Sem custos de recuperação

## Considerações Importantes

1. **Custos**
   - Armazenamento
   - Transferência
   - Requisições
   - Recuperação

2. **Performance**
   - Latência
   - Throughput
   - Disponibilidade
   - Durabilidade

3. **Recuperação**
   - Tempo de acesso
   - Flexibilidade
   - Custos
   - Requisições

4. **Compliance**
   - Regulamentações
   - Requisitos
   - Auditoria
   - Documentação

---

## Classes de Armazenamento
![Classes de Armazenamento](/images/Classes%20de%20Armazenamento.png)

---

## Transição entre Classes Lifecycle 
![Transição entre Classes Lifecycle ](/images/Transição%20entre%20Classes%20Lifecycle.png)

---

## Exemplo Prático: Cenário de Mídia Digital
![Cenário de Mídia Digital](/images/Cenário%20de%20Mídia%20Digital.png)

---



