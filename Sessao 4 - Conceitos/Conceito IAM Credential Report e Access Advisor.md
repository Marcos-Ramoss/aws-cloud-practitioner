## Botão Voltar ao Início
[⬆️ Voltar ao Início](/README.md)

---

# IAM Credential Report e Access Advisor

## Conceito

### IAM Credential Report

O **IAM Credential Report** é um relatório detalhado que lista todos os usuários em sua conta AWS e o status de suas várias credenciais, incluindo senhas, chaves de acesso e dispositivos MFA. Este relatório é uma ferramenta essencial para auditoria e conformidade.

### IAM Access Advisor

O **IAM Access Advisor** é uma ferramenta que mostra quando um usuário acessou pela última vez um serviço específico da AWS. Ele ajuda a identificar permissões não utilizadas e a aplicar o princípio do menor privilégio de forma mais eficaz.

## Para que são usados

### Credential Report
- ✅ **Auditoria de credenciais** de usuários
- ✅ **Monitoramento de conformidade** com políticas de segurança
- ✅ **Identificação de credenciais** não utilizadas ou expiradas
- ✅ **Verificação do status** de MFA e senhas
- ✅ **Análise de segurança** da conta AWS

### Access Advisor
- ✅ **Otimização de permissões** baseada no uso real
- ✅ **Identificação de permissões** não utilizadas
- ✅ **Redução de riscos** de segurança
- ✅ **Simplificação de políticas** IAM
- ✅ **Aplicação do princípio** do menor privilégio

## Vantagens

### Credential Report
- ✅ **Visibilidade completa** das credenciais
- ✅ **Formato CSV** para fácil análise
- ✅ **Atualização automática** a cada 4 horas
- ✅ **Suporte a auditorias** externas
- ✅ **Detalhamento de status** de todas as credenciais

### Access Advisor
- ✅ **Recomendações baseadas** em uso real
- ✅ **Interface visual** intuitiva
- ✅ **Histórico de acesso** aos serviços
- ✅ **Otimização contínua** de permissões
- ✅ **Redução de riscos** de segurança

## Desvantagens

### Credential Report
- ❌ **Atualização limitada** (a cada 4 horas)
- ❌ **Necessidade de processamento** manual dos dados
- ❌ **Sem recomendações** automáticas
- ❌ **Formato fixo** de relatório
- ❌ **Sem integração** com ferramentas de análise

### Access Advisor
- ❌ **Histórico limitado** (90 dias)
- ❌ **Sem detalhes** de operações específicas
- ❌ **Necessidade de interpretação** manual
- ❌ **Sem automação** de remoção de permissões
- ❌ **Dependência** de dados de uso

## Boas práticas

### Credential Report
- ✅ **Gere relatórios regularmente** para auditoria
- ✅ **Implemente análise automatizada** dos relatórios
- ✅ **Mantenha histórico** dos relatórios
- ✅ **Use para validação** de políticas de segurança
- ✅ **Integre com ferramentas** de monitoramento

### Access Advisor
- ✅ **Revise permissões** periodicamente
- ✅ **Remova permissões** não utilizadas
- ✅ **Documente decisões** de remoção
- ✅ **Use em conjunto** com políticas de segurança
- ✅ **Implemente revisões** regulares

## Exemplo prático

```bash
# Gerar relatório de credenciais via AWS CLI
aws iam generate-credential-report

# Baixar o relatório gerado
aws iam get-credential-report

# Exemplo de análise do Access Advisor via AWS CLI
aws iam get-service-last-accessed-details \
    --job-id example-job-id
```

---

## Fluxo do Credential Report
![Fluxo do Credential Report](/images/Fluxo%20do%20Credential%20Report.png)

---

## Análise com Access Advisor
![Análise com Access Advisor](/images/Análise%20com%20Access%20Advisor.png)

---

## Ciclo de Melhoria Contínua
![Ciclo de Melhoria Contínua](/images/Ciclo%20de%20Melhoria%20Contínua.png)

---

## Integração com Outros Serviços
![Integração com Outros Serviços](/images/Integração%20com%20Outros%20Serviços.png) 