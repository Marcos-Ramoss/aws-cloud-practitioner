## Botão Voltar ao Início
[⬆️ Voltar ao Início](https://github.com/Marcos-Ramoss/aws-cloud-practitioner)

---

# Amazon RDS (Relational Database Service)

## Conceito

O Amazon RDS (Relational Database Service) é um serviço gerenciado que facilita a configuração, operação e escalabilidade de bancos de dados relacionais na nuvem. Ele automatiza tarefas administrativas como provisionamento, backups, patching e recuperação, permitindo que você foque no desenvolvimento das aplicações.

### Características Principais

1. **Engines Suportados**
   - Amazon Aurora
   - PostgreSQL
   - MySQL
   - MariaDB
   - Oracle
   - Microsoft SQL Server

2. **Funcionalidades**
   - Backup automatizado e snapshots manuais
   - Replicação Multi-AZ para alta disponibilidade
   - Read Replicas para escalabilidade de leitura
   - Atualizações automáticas de software
   - Monitoramento integrado (Amazon CloudWatch)
   - Criptografia em repouso e em trânsito

3. **Configurações**
   - Controle de acesso via IAM e Security Groups
   - Parâmetros de performance customizáveis
   - Políticas de backup e retenção configuráveis
   - Opções de escalabilidade vertical e horizontal

## Para que é usado

### Casos de Uso Comuns

1. **Aplicações Web e Mobile**
   - ✅ Bancos de dados transacionais
   - ✅ Backend de aplicações SaaS

2. **Analytics e BI**
   - ✅ Data marts
   - ✅ Relatórios e dashboards

3. **Enterprise**
   - ✅ ERP, CRM e sistemas legados
   - ✅ Aplicações críticas de negócios

4. **Desenvolvimento e Teste**
   - ✅ Ambientes temporários
   - ✅ Prototipagem rápida

## Vantagens

### Técnicas
- ✅ **Alta disponibilidade** com Multi-AZ
- ✅ **Escalabilidade** fácil (vertical e horizontal)
- ✅ **Backups** automáticos e restauração point-in-time
- ✅ **Segurança** avançada (VPC, KMS, IAM)
- ✅ **Atualizações** automáticas de patches

### Operacionais
- ✅ **Gerenciamento** simplificado
- ✅ **Monitoramento** nativo
- ✅ **Automação** de tarefas administrativas

### Econômicas
- ✅ **Pay-as-you-go**
- ✅ **Redução** de custos operacionais
- ✅ **Sem** investimento inicial

## Desvantagens

### Técnicas
- ❌ **Limitações** de customização do SO
- ❌ **Acesso restrito** ao sistema operacional
- ❌ **Algumas features** específicas podem não estar disponíveis

### Operacionais
- ❌ **Dependência** do provedor
- ❌ **Migração** de bancos legados pode ser complexa

### Econômicas
- ❌ **Custos** adicionais para alta disponibilidade e storage
- ❌ **Cobrança** por recursos provisionados, mesmo ociosos

## Boas práticas

### Nomenclatura
- ✅ **Identificação** por ambiente (dev, prod)
- ✅ **Padrão** de nomes para instâncias e snapshots

### Segurança
- ✅ **Acesso restrito** via Security Groups
- ✅ **Criptografia** ativada (em trânsito e em repouso)
- ✅ **Backups** regulares
- ✅ **Auditoria** habilitada (CloudTrail, logs)

### Custo
- ✅ **Monitoramento** de uso e dimensionamento
- ✅ **Revisão** periódica de instâncias e storage

## Exemplo prático

```bash
# Criar instância RDS MySQL
aws rds create-db-instance \
    --db-instance-identifier meu-rds-exemplo \
    --db-instance-class db.t3.micro \
    --engine mysql \
    --allocated-storage 20 \
    --master-username admin \
    --master-user-password senhaSegura123 \
    --backup-retention-period 7 \
    --multi-az \
    --vpc-security-group-ids sg-12345678
```

## Configurações Importantes

### Backup e Restauração
- Backups automáticos diários
- Snapshots manuais
- Restauração point-in-time

### Alta Disponibilidade
- Multi-AZ (failover automático)
- Read Replicas para leitura escalável

### Segurança
- Criptografia (KMS)
- Controle de acesso (IAM, Security Groups)
- Auditoria de logs

### Performance
- Auto Scaling de storage
- Monitoramento de métricas (CloudWatch)
- Ajuste de parâmetros via Parameter Groups

## Considerações Importantes

1. **Escolha do Engine**
   - Compatibilidade com a aplicação
   - Performance e custo

2. **Segurança**
   - Acesso restrito à VPC
   - Criptografia e auditoria

3. **Backup**
   - Políticas de retenção
   - Testes de restauração

4. **Escalabilidade**
   - Dimensionamento automático de storage
   - Read Replicas para leitura

---

## Arquitetura Amazon RDS
![Arquitetura Amazon RDS](/images/Arquitetura%20RDS.png)

---

## Gerenciamento de Backup RDS
![Gerenciamento de Backup RDS](/images/Backup%20RDS.png)

---

## Integração com Serviços AWS
![Integração RDS AWS](/images/Integracao%20RDS%20AWS.png)

---

## Configuração típica
![Configuração típica RDS](/images/Configuracao%20tipica%20RDS.png)

---