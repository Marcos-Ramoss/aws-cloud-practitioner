## Botão Voltar ao Início
[⬆️ Voltar ao Início](https://github.com/Marcos-Ramoss/aws-cloud-practitioner)

---

# AWS Global Accelerator

## Conceito

O AWS Global Accelerator é um serviço de rede que melhora a disponibilidade e a performance de aplicações globais, direcionando o tráfego de usuários para endpoints otimizados na AWS por meio da rede global da Amazon. Ele utiliza endereços IP estáticos e roteamento inteligente para garantir baixa latência e alta disponibilidade.

### Características Principais

1. **IP Estático Global**
   - Provisão de um ou mais IPs estáticos globais para aplicações
   - Simplifica DNS e failover

2. **Roteamento Inteligente**
   - Direciona tráfego para o endpoint mais saudável e próximo
   - Failover automático em caso de falha de endpoint ou região

3. **Alta Disponibilidade e Performance**
   - Utiliza a rede backbone da AWS para otimizar rotas
   - Reduz latência e jitter para usuários globais

4. **Suporte a Diversos Endpoints**
   - Integração com ALB, NLB, EC2, Elastic IPs e IPs de endpoints de aplicações

5. **Monitoramento e Health Checks**
   - Health checks automáticos para failover rápido
   - Métricas integradas ao CloudWatch

## Para que é usado

### Casos de Uso Comuns

1. **Aplicações Globais de Alta Disponibilidade**
   - ✅ Web apps, APIs, jogos, SaaS
   - ✅ Redução de latência para usuários internacionais

2. **Failover e Disaster Recovery**
   - ✅ Failover automático entre regiões e endpoints

3. **Simplificação de IP e DNS**
   - ✅ Endereços IP estáticos globais para aplicações

## Vantagens

### Técnicas
- ✅ **Baixa latência** e alta performance global
- ✅ **Failover** automático e rápido
- ✅ **IP estático** para simplificar DNS

### Operacionais
- ✅ **Gerenciamento** centralizado de endpoints
- ✅ **Monitoramento** e métricas integradas

### Econômicas
- ✅ **Pay-as-you-go**
- ✅ **Redução** de custos com downtime e complexidade de DNS

## Desvantagens

### Técnicas
- ❌ **Custo adicional** por uso do serviço
- ❌ **Limitações** para alguns tipos de endpoints

### Operacionais
- ❌ **Curva de aprendizado** para configuração avançada

## Boas práticas

### Nomenclatura
- ✅ **Identificação** clara de aceleradores e endpoints
- ✅ **Documentação** das configurações

### Segurança
- ✅ **Controle de acesso** via IAM
- ✅ **Monitoramento** de tráfego e falhas

### Custo
- ✅ **Monitoramento** de uso e custos
- ✅ **Revisão** periódica de aceleradores ativos

## Exemplo prático

```powershell
# Criar um acelerador global
aws globalaccelerator create-accelerator `
    --name MeuAceleradorGlobal

# Adicionar um listener
aws globalaccelerator create-listener `
    --accelerator-arn arn:aws:globalaccelerator::123456789012:accelerator/abcd1234 `
    --protocol TCP `
    --port-ranges FromPort=80,ToPort=80

# Adicionar endpoint group
aws globalaccelerator create-endpoint-group `
    --listener-arn arn:aws:globalaccelerator::123456789012:listener/abcd5678 `
    --endpoint-group-region us-east-1 `
    --endpoint-configurations EndpointId=arn:aws:elasticloadbalancing:us-east-1:123456789012:loadbalancer/app/my-alb/abcd1234
```

## Configurações Importantes

### Endpoints
- ALB, NLB, EC2, Elastic IPs, endpoints de aplicações

### Health Checks
- Configuração de health checks customizados
- Failover automático

### Segurança
- Controle de acesso via IAM
- Monitoramento de logs e métricas

## Considerações Importantes

1. **Planejamento de Endpoints**
   - Definir regiões e tipos de endpoints

2. **Custo**
   - Avaliar custos de aceleradores e transferência de dados

3. **Gerenciamento**
   - Documentar aceleradores, listeners e endpoints
   - Monitorar performance e disponibilidade

---

## Arquitetura AWS Global Accelerator
![Arquitetura AWS Global Accelerator](/images/Arquitetura%20Global%20Accelerator.png)

---

## Exemplo de Configuração
![Exemplo de Configuração Global Accelerator](/images/Exemplo%20Global%20Accelerator.png)

---

## Integração com Serviços AWS
![Integração Global Accelerator AWS](/images/Integracao%20Global%20Accelerator%20AWS.png)

---

## Configuração típica
![Configuração típica Global Accelerator](/images/Configuracao%20tipica%20Global%20Accelerator.png)

---
