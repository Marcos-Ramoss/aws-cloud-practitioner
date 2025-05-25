## Botão Voltar ao Início
[⬆️ Voltar ao Início](https://github.com/Marcos-Ramoss/aws-cloud-practitioner)

---

# Amazon Route 53

## Conceito

O Amazon Route 53 é um serviço de DNS (Domain Name System) altamente disponível e escalável, totalmente gerenciado pela AWS. Ele permite registrar domínios, gerenciar zonas hospedadas, rotear tráfego de usuários para aplicações na AWS ou fora dela, e monitorar a integridade de endpoints.

### Características Principais

1. **Gerenciamento de DNS**
   - Criação e gerenciamento de zonas hospedadas públicas e privadas
   - Suporte a múltiplos tipos de registros (A, AAAA, CNAME, MX, TXT, etc.)

2. **Registro de Domínios**
   - Registro, transferência e gerenciamento de domínios diretamente pela AWS

3. **Roteamento de Tráfego**
   - Políticas de roteamento simples, ponderado, baseado em latência, failover, geolocalização e geoproximidade
   - Suporte a health checks para failover automático

4. **Alta Disponibilidade e Escalabilidade**
   - Infraestrutura global e redundante
   - Baixa latência e alta performance

5. **Integração com AWS**
   - Integração nativa com ELB, S3, CloudFront, API Gateway, etc.

## Para que é usado

### Casos de Uso Comuns

1. **Gerenciamento de Domínios**
   - ✅ Registro e gerenciamento de domínios
   - ✅ Gerenciamento centralizado de DNS

2. **Roteamento Inteligente de Tráfego**
   - ✅ Balanceamento de carga global
   - ✅ Failover automático entre endpoints
   - ✅ Direcionamento por latência ou geolocalização

3. **Ambientes Híbridos e Multi-Cloud**
   - ✅ Integração de aplicações on-premises e AWS
   - ✅ DNS privado para VPCs

## Vantagens

### Técnicas
- ✅ **Alta disponibilidade** e resiliência global
- ✅ **Roteamento avançado** e flexível
- ✅ **Monitoramento** de integridade de endpoints

### Operacionais
- ✅ **Gerenciamento** centralizado de DNS
- ✅ **Automação** via AWS CLI, SDK e CloudFormation

### Econômicas
- ✅ **Pay-as-you-go**
- ✅ **Redução** de custos com infraestrutura própria de DNS

## Desvantagens

### Técnicas
- ❌ **Curva de aprendizado** para políticas avançadas
- ❌ **Limitações** em integrações com domínios externos

### Operacionais
- ❌ **Gerenciamento** de múltiplas zonas pode ser complexo

### Econômicas
- ❌ **Custos** por consultas e registros adicionais

## Boas práticas

### Nomenclatura
- ✅ **Padronização** de nomes de domínios e subdomínios
- ✅ **Documentação** das zonas e registros

### Segurança
- ✅ **Uso de DNSSEC** para proteção contra ataques
- ✅ **Controle de acesso** via IAM

### Custo
- ✅ **Monitoramento** de consultas e registros
- ✅ **Revisão** periódica de zonas e domínios

## Exemplo prático

```powershell
# Criar uma zona hospedada pública
aws route53 create-hosted-zone `
    --name exemplo.com `
    --caller-reference "meu-referencia-unica"

# Criar um registro A
aws route53 change-resource-record-sets `
    --hosted-zone-id ZONEID `
    --change-batch '{"Changes":[{"Action":"CREATE","ResourceRecordSet":{"Name":"www.exemplo.com","Type":"A","TTL":300,"ResourceRecords":[{"Value":"192.0.2.1"}]}}]}'
```

## Configurações Importantes

### Zonas Hospedadas
- Públicas: para domínios acessíveis na internet
- Privadas: para resolução interna em VPCs

### Políticas de Roteamento
- Simples, ponderado, failover, latência, geolocalização, geoproximidade
- Health checks para failover automático

### Segurança
- DNSSEC para proteção de integridade
- Controle de acesso via IAM

## Considerações Importantes

1. **Planejamento de Domínios**
   - Definir hierarquia e subdomínios
   - Prever crescimento futuro

2. **Segurança**
   - Habilitar DNSSEC quando possível
   - Restringir alterações via IAM

3. **Custo**
   - Monitorar consultas e registros
   - Revisar domínios e zonas não utilizados

4. **Gerenciamento**
   - Documentar zonas, registros e políticas
   - Automatizar via CloudFormation ou Terraform

---

## Arquitetura Amazon Route 53
![Arquitetura Amazon Route 53](/images/Arquitetura%20Route53.png)

---

## Exemplo de Políticas de Roteamento
![Exemplo de Políticas Route53](/images/Politicas%20Route53.png)

---

## Integração com Serviços AWS
![Integração Route53 AWS](/images/Integracao%20Route53%20AWS.png)

---

## Configuração típica
![Configuração típica Route53](/images/Configuracao%20tipica%20Route53.png)

---
