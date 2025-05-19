## Botão Voltar ao Início
[⬆️ Voltar ao Início](https://github.com/Marcos-Ramoss/aws-cloud-practitioner)

---

# AWS Shared Responsibility Model (Modelo de Responsabilidade Compartilhada)

## Conceito

O **AWS Shared Responsibility Model** é um framework que define claramente as responsabilidades de segurança e conformidade entre a AWS e seus clientes. Este modelo estabelece que a AWS é responsável pela segurança **da** nuvem, enquanto o cliente é responsável pela segurança **na** nuvem.

### Entendendo o Modelo em Detalhes

O modelo de responsabilidade compartilhada pode ser visualizado em diferentes níveis de serviço:

1. **Infraestrutura como Serviço (IaaS)**
   - AWS: Responsável pela segurança física, hardware, software de virtualização e infraestrutura de rede
   - Cliente: Responsável pelo sistema operacional, aplicações, dados e configurações de segurança

2. **Plataforma como Serviço (PaaS)**
   - AWS: Gerencia a infraestrutura subjacente e o sistema operacional
   - Cliente: Foca na segurança das aplicações e dados

3. **Software como Serviço (SaaS)**
   - AWS: Responsável pela maior parte da segurança
   - Cliente: Gerencia principalmente o acesso e os dados

### Exemplos Práticos por Serviço

#### Amazon EC2 (IaaS)
- AWS: Segurança física, hardware, virtualização
- Cliente: Sistema operacional, patches, firewall, dados

#### Amazon RDS (PaaS)
- AWS: Infraestrutura, sistema operacional, banco de dados
- Cliente: Configurações de segurança, dados, backups

#### Amazon S3 (SaaS)
- AWS: Infraestrutura, software, rede
- Cliente: Configurações de bucket, políticas de acesso, dados

## Componentes do Modelo

### Responsabilidades da AWS
- ✅ **Segurança física** dos data centers
- ✅ **Hardware e software** da infraestrutura global
- ✅ **Virtualização** da infraestrutura
- ✅ **Software de computação**, armazenamento e banco de dados
- ✅ **Configuração** e operação do ambiente de rede
- ✅ **Monitoramento** da infraestrutura global
- ✅ **Atualizações** de segurança da plataforma
- ✅ **Conformidade** da infraestrutura

### Responsabilidades do Cliente
- ✅ **Dados** do cliente
- ✅ **Plataforma**, aplicações e gerenciamento de identidade
- ✅ **Sistema operacional**, rede e configuração de firewall
- ✅ **Criptografia** do lado do cliente
- ✅ **Configuração** de segurança e gerenciamento de patches
- ✅ **Controle de acesso** e autenticação
- ✅ **Monitoramento** de aplicações
- ✅ **Backup** e recuperação de dados

## Para que é usado

### Casos de Uso Comuns

1. **Conformidade e Auditoria**
   - ✅ **Certificações** (ISO 27001, SOC 2, PCI DSS)
   - ✅ **Auditorias** internas e externas
   - ✅ **Relatórios** de compliance
   - ✅ **Documentação** de segurança
   - ✅ **Evidências** de controles

2. **Governança de Segurança**
   - ✅ **Políticas** de segurança
   - ✅ **Controles** de acesso
   - ✅ **Monitoramento** de atividades
   - ✅ **Gestão** de riscos
   - ✅ **Resposta** a incidentes

3. **Desenvolvimento e Operações**
   - ✅ **DevSecOps**
   - ✅ **CI/CD** seguro
   - ✅ **Gestão** de configurações
   - ✅ **Monitoramento** de aplicações
   - ✅ **Backup** e recuperação

4. **Proteção de Dados**
   - ✅ **Criptografia** de dados
   - ✅ **Classificação** de dados
   - ✅ **Retenção** de dados
   - ✅ **Backup** de dados
   - ✅ **Recuperação** de desastres

### Exemplos Práticos por Indústria

#### Setor Financeiro
- ✅ **Conformidade** com regulamentações
- ✅ **Proteção** de dados sensíveis
- ✅ **Auditoria** de transações
- ✅ **Monitoramento** de fraudes
- ✅ **Backup** de dados críticos

#### Saúde
- ✅ **Conformidade** com HIPAA
- ✅ **Proteção** de PHI
- ✅ **Auditoria** de acessos
- ✅ **Backup** de registros
- ✅ **Recuperação** de desastres

#### E-commerce
- ✅ **Proteção** de dados de cartão
- ✅ **Conformidade** com PCI DSS
- ✅ **Monitoramento** de fraudes
- ✅ **Backup** de pedidos
- ✅ **Segurança** de aplicações

### Benefícios por Tipo de Organização

#### Startups
- ✅ **Escalabilidade** de segurança
- ✅ **Custo-benefício**
- ✅ **Flexibilidade** de implementação
- ✅ **Foco** no core business
- ✅ **Rápida** implementação

#### Empresas Estabelecidas
- ✅ **Integração** com sistemas existentes
- ✅ **Conformidade** com regulamentações
- ✅ **Governança** robusta
- ✅ **Auditoria** detalhada
- ✅ **Controles** avançados

#### Governo
- ✅ **Conformidade** com regulamentações
- ✅ **Proteção** de dados sensíveis
- ✅ **Auditoria** detalhada
- ✅ **Controles** rigorosos
- ✅ **Documentação** extensa

## Vantagens

### Para a AWS
- ✅ **Clareza** nas responsabilidades
- ✅ **Foco** em infraestrutura global
- ✅ **Escalabilidade** dos serviços
- ✅ **Inovação** contínua
- ✅ **Eficiência** operacional

### Para o Cliente
- ✅ **Controle** sobre seus dados
- ✅ **Flexibilidade** de configuração
- ✅ **Personalização** de segurança
- ✅ **Transparência** nas responsabilidades
- ✅ **Conformidade** adaptável

## Desvantagens

### Para a AWS
- ❌ **Complexidade** de comunicação
- ❌ **Expectativas** variadas dos clientes
- ❌ **Diferentes níveis** de maturidade dos clientes
- ❌ **Necessidade** de documentação extensa
- ❌ **Desafios** de suporte

### Para o Cliente
- ❌ **Responsabilidade** adicional
- ❌ **Curva de aprendizado**
- ❌ **Custo** de implementação
- ❌ **Complexidade** de gerenciamento
- ❌ **Necessidade** de expertise

## Boas práticas

### Para a AWS
- ✅ **Manter documentação** atualizada
- ✅ **Fornecer ferramentas** de segurança
- ✅ **Oferecer treinamento** e suporte
- ✅ **Implementar controles** de segurança
- ✅ **Monitorar** ameaças globais

### Para o Cliente
- ✅ **Entender completamente** o modelo
- ✅ **Implementar controles** de segurança
- ✅ **Manter sistemas** atualizados
- ✅ **Monitorar** atividades suspeitas
- ✅ **Realizar auditorias** regulares

## Exemplo prático

```bash
# Exemplo de configuração de segurança do cliente
# Configuração de grupo de segurança EC2
aws ec2 create-security-group \
    --group-name MySecurityGroup \
    --description "Security group for my instances"

# Configuração de regras de firewall
aws ec2 authorize-security-group-ingress \
    --group-name MySecurityGroup \
    --protocol tcp \
    --port 80 \
    --cidr 0.0.0.0/0

# Exemplo de configuração de criptografia para S3 (responsabilidade do cliente)
aws s3api put-bucket-encryption \
    --bucket my-bucket \
    --server-side-encryption-configuration '{
        "Rules": [
            {
                "ApplyServerSideEncryptionByDefault": {
                    "SSEAlgorithm": "AES256"
                }
            }
        ]
    }'

# Exemplo de configuração de backup (responsabilidade do cliente)
aws backup create-backup-plan \
    --backup-plan '{
        "BackupPlanName": "MyBackupPlan",
        "Rules": [
            {
                "RuleName": "DailyBackups",
                "TargetBackupVault": "Default",
                "ScheduleExpression": "cron(0 5 ? * * *)",
                "StartWindowMinutes": 60,
                "CompletionWindowMinutes": 120,
                "Lifecycle": {
                    "DeleteAfterDays": 30
                }
            }
        ]
    }'
```

---

## Divisão de Responsabilidades
![Divisão de Responsabilidades](/images/Divisão%20de%20Responsabilidades.png)

---

##  Modelo por Tipo de Serviço
![ Modelo por Tipo de Serviço](/images/Modelo%20por%20Tipo%20de%20Serviço.png)

---

## Evolução com Serviços Gerenciados
![Evolução com Serviços Gerenciados](/images/Evolução%20com%20Serviços%20Gerenciados.png)

---

## Desafios Comuns
![Desafios Comuns](/images/Desafios%20Comuns.png) 