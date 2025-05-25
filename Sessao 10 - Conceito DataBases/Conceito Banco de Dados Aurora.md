## Botão Voltar ao Início
[⬆️ Voltar ao Início](https://github.com/Marcos-Ramoss/aws-cloud-practitioner)

---

# Amazon Aurora

## Conceito

O Amazon Aurora é um banco de dados relacional totalmente gerenciado, compatível com MySQL e PostgreSQL, desenvolvido para oferecer desempenho e disponibilidade superiores a um custo muito menor do que bancos de dados comerciais tradicionais. Aurora combina a performance e disponibilidade de bancos de dados de alto nível com a simplicidade e economia de bancos de dados open source.

### Características Principais

1. **Compatibilidade**
   - Compatível com MySQL e PostgreSQL
   - Migração facilitada de bancos existentes

2. **Desempenho e Escalabilidade**
   - Até 5x mais rápido que MySQL padrão e 3x mais rápido que PostgreSQL padrão
   - Suporte a até 128 TB por cluster de banco de dados
   - Auto Scaling de leitura com até 15 réplicas de leitura de baixa latência

3. **Alta Disponibilidade e Durabilidade**
   - Armazenamento distribuído em múltiplas zonas de disponibilidade (Multi-AZ)
   - Failover automático em segundos
   - Backups contínuos para o Amazon S3

4. **Segurança**
   - Criptografia em repouso e em trânsito
   - Integração com AWS IAM, VPC e KMS

5. **Gerenciamento Automatizado**
   - Backups automáticos, snapshots e restauração point-in-time
   - Atualizações automáticas de software

## Para que é usado

### Casos de Uso Comuns

1. **Aplicações Web e Mobile**
   - ✅ Bancos de dados transacionais de alta performance
   - ✅ Backend de aplicações SaaS

2. **Analytics e BI**
   - ✅ Processamento de grandes volumes de dados
   - ✅ Relatórios em tempo real

3. **Enterprise**
   - ✅ ERP, CRM e sistemas críticos
   - ✅ Migração de bancos comerciais para open source

4. **Desenvolvimento e Teste**
   - ✅ Ambientes temporários e escaláveis

## Vantagens

### Técnicas
- ✅ **Alta performance** e baixa latência
- ✅ **Alta disponibilidade** Multi-AZ
- ✅ **Escalabilidade** automática de leitura
- ✅ **Backups** contínuos e automáticos
- ✅ **Recuperação** rápida de falhas

### Operacionais
- ✅ **Gerenciamento** simplificado
- ✅ **Monitoramento** nativo (CloudWatch)
- ✅ **Automação** de tarefas administrativas

### Econômicas
- ✅ **Custo-benefício** comparado a bancos comerciais
- ✅ **Pay-as-you-go**
- ✅ **Redução** de custos operacionais

## Desvantagens

### Técnicas
- ❌ **Compatibilidade** limitada a MySQL e PostgreSQL
- ❌ **Limitações** de customização do SO
- ❌ **Acesso restrito** ao sistema operacional

### Operacionais
- ❌ **Dependência** do provedor AWS
- ❌ **Migração** de bancos legados pode exigir ajustes

### Econômicas
- ❌ **Custos** adicionais para alta disponibilidade e storage
- ❌ **Cobrança** por recursos provisionados, mesmo ociosos

## Boas práticas

### Nomenclatura
- ✅ **Identificação** por ambiente (dev, prod)
- ✅ **Padrão** de nomes para clusters e instâncias

### Segurança
- ✅ **Acesso restrito** via VPC e Security Groups
- ✅ **Criptografia** ativada (em trânsito e em repouso)
- ✅ **Backups** regulares
- ✅ **Auditoria** habilitada

### Custo
- ✅ **Monitoramento** de uso e dimensionamento
- ✅ **Revisão** periódica de clusters e storage

## Exemplo prático

```bash
# Criar cluster Aurora MySQL
aws rds create-db-cluster \
    --db-cluster-identifier meu-aurora-cluster \
    --engine aurora-mysql \
    --master-username admin \
    --master-user-password senhaSegura123 \
    --vpc-security-group-ids sg-12345678

# Criar instância no cluster Aurora
aws rds create-db-instance \
    --db-instance-identifier meu-aurora-instancia \
    --db-cluster-identifier meu-aurora-cluster \
    --engine aurora-mysql \
    --db-instance-class db.r6g.large
```

## Configurações Importantes

### Backup e Restauração
- Backups automáticos contínuos
- Snapshots manuais
- Restauração point-in-time

### Alta Disponibilidade
- Multi-AZ com failover automático
- Réplicas de leitura para escalabilidade

### Segurança
- Criptografia (KMS)
- Controle de acesso (IAM, VPC, Security Groups)
- Auditoria de logs

### Performance
- Auto Scaling de réplicas de leitura
- Monitoramento de métricas (CloudWatch)
- Ajuste de parâmetros via Parameter Groups

## Considerações Importantes

1. **Compatibilidade**
   - Verificar suporte a MySQL/PostgreSQL
   - Testar aplicações após migração

2. **Segurança**
   - Acesso restrito à VPC
   - Criptografia e auditoria

3. **Backup**
   - Políticas de retenção
   - Testes de restauração

4. **Escalabilidade**
   - Dimensionamento automático de réplicas
   - Monitoramento de performance

---

## Arquitetura Amazon Aurora
![Arquitetura Amazon Aurora](/images/Arquitetura%20Aurora.png)

---

## Gerenciamento de Backup Aurora
![Gerenciamento de Backup Aurora](/images/Backup%20Aurora.png)

---

## Integração com Serviços AWS
![Integração Aurora AWS](/images/Integracao%20Aurora%20AWS.png)

---

## Configuração típica
![Configuração típica Aurora](/images/Configuracao%20tipica%20Aurora.png)

---