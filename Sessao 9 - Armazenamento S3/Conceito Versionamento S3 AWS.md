# Amazon S3 Versioning

## Conceito

O Amazon S3 Versioning é um recurso que permite manter múltiplas variantes de um objeto no mesmo bucket. Com o versionamento, você pode preservar, recuperar e restaurar todas as versões de cada objeto armazenado em seus buckets, facilitando a recuperação de ações acidentais e falhas de aplicação.

### Características Principais

1. **Estados do Bucket**
   - Unversioned (padrão)
   - Versioning-enabled
   - Versioning-suspended

2. **Funcionalidades**
   - Preservação de versões
   - Recuperação de objetos
   - Proteção contra exclusão
   - Proteção contra sobrescrita

3. **Comportamento**
   - Versões únicas por objeto
   - IDs de versão únicos
   - Marcadores de exclusão
   - Versões atuais e não atuais

## Para que é usado

### Casos de Uso Comuns

1. **Proteção de Dados**
   - ✅ Recuperação de exclusões acidentais
   - ✅ Proteção contra sobrescritas
   - ✅ Conformidade regulatória
   - ✅ Auditoria de alterações

2. **Desenvolvimento**
   - ✅ Versionamento de código
   - ✅ Rollback de alterações
   - ✅ Testes de versões
   - ✅ Desenvolvimento paralelo

3. **Compliance**
   - ✅ Retenção de dados
   - ✅ Auditoria
   - ✅ Conformidade
   - ✅ Histórico de alterações

4. **DR e Backup**
   - ✅ Recuperação de desastres
   - ✅ Backup incremental
   - ✅ Restauração pontual
   - ✅ Proteção de dados

## Vantagens

### Técnicas
- ✅ **Proteção** contra exclusão acidental
- ✅ **Recuperação** de versões anteriores
- ✅ **Preservação** de dados
- ✅ **Rastreabilidade** de alterações
- ✅ **Flexibilidade** de gerenciamento

### Operacionais
- ✅ **Simplicidade** de configuração
- ✅ **Automação** de versionamento
- ✅ **Monitoramento** nativo
- ✅ **Integração** com outros serviços
- ✅ **Gerenciamento** centralizado

### Econômicas
- ✅ **Custo-benefício**
- ✅ **Otimização** de armazenamento
- ✅ **Redução** de riscos
- ✅ **Economia** em DR
- ✅ **Escalabilidade** econômica

## Desvantagens

### Técnicas
- ❌ **Custo** adicional de armazenamento
- ❌ **Complexidade** de gerenciamento
- ❌ **Latência** em operações
- ❌ **Limitações** de API
- ❌ **Restrições** de uso

### Operacionais
- ❌ **Monitoramento** necessário
- ❌ **Configuração** manual
- ❌ **Testes** de performance
- ❌ **Documentação** importante
- ❌ **Treinamento** necessário

### Econômicas
- ❌ **Custos** de armazenamento
- ❌ **Custos** de requisições
- ❌ **Custos** de transferência
- ❌ **Custos** de API
- ❌ **Custos** de gerenciamento

## Boas práticas

### Configuração
- ✅ **Habilitar** versionamento no bucket
- ✅ **Configurar** MFA Delete
- ✅ **Definir** políticas de lifecycle
- ✅ **Monitorar** uso de versões
- ✅ **Revisar** periodicamente

### Gerenciamento
- ✅ **Limpar** versões antigas
- ✅ **Monitorar** custos
- ✅ **Auditar** acessos
- ✅ **Documentar** processos
- ✅ **Treinar** equipe

### Segurança
- ✅ **Encryption**
- ✅ **MFA Delete**
- ✅ **Bucket policies**
- ✅ **Access logging**
- ✅ **Versioning policies**

## Exemplo prático

```bash
# Habilitar versionamento no bucket
aws s3api put-bucket-versioning \
    --bucket meu-bucket-exemplo \
    --versioning-configuration Status=Enabled

# Habilitar MFA Delete
aws s3api put-bucket-versioning \
    --bucket meu-bucket-exemplo \
    --versioning-configuration Status=Enabled,MFADelete=Enabled \
    --mfa "SERIAL 123456"

# Configurar lifecycle para versões antigas
aws s3api put-bucket-lifecycle-configuration \
    --bucket meu-bucket-exemplo \
    --lifecycle-configuration '{
        "Rules": [
            {
                "ID": "ExpireOldVersions",
                "Status": "Enabled",
                "Prefix": "",
                "NoncurrentVersionExpiration": {
                    "NoncurrentDays": 90
                }
            }
        ]
    }'
```

## Estados do Versionamento

### Unversioned (Padrão)
- Sem versionamento
- Exclusão permanente
- Sem histórico
- Sem proteção

### Versioning-enabled
- Múltiplas versões
- Proteção contra exclusão
- Histórico completo
- Recuperação flexível

### Versioning-suspended
- Versões existentes mantidas
- Novas versões não criadas
- Proteção parcial
- Transição possível

## Considerações Importantes

1. **Custos**
   - Armazenamento por versão
   - Requisições
   - Transferência
   - Gerenciamento

2. **Performance**
   - Latência
   - Throughput
   - Disponibilidade
   - Durabilidade

3. **Segurança**
   - MFA Delete
   - Políticas de acesso
   - Logging
   - Auditoria

4. **Compliance**
   - Regulamentações
   - Requisitos
   - Auditoria
   - Documentação

---

## Como Funciona?
![Como Funciona Versionamento](/images/Como%20Funciona%20Versionamento.png)

---

## Lifecycle Rules
![Lifecycle Rules](/images/Lifecycle%20Rules.png)

---

## Fluxo de upload e delete de arquivos
![Fluxo de upload](/images/Fluxo%20de%20upload.png)

--- 