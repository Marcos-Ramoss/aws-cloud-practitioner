## Botão Voltar ao Início
[⬆️ Voltar ao Início](https://github.com/Marcos-Ramoss/aws-cloud-practitioner)

---

# Amazon VPC (Virtual Private Cloud)

## Conceito

O Amazon VPC (Virtual Private Cloud) é um serviço que permite provisionar uma seção isolada logicamente da nuvem AWS, onde você pode lançar recursos da AWS em uma rede virtual definida por você. Com o VPC, é possível controlar o ambiente de rede, incluindo seleção de intervalos de IP, criação de sub-redes, configuração de tabelas de rotas e gateways de rede.

### Características Principais

1. **Isolamento e Controle**
   - Rede virtual privada e isolada
   - Controle total sobre endereçamento IP, sub-redes e rotas

2. **Segurança**
   - Security Groups e Network ACLs para controle de tráfego
   - Integração com AWS Identity and Access Management (IAM)
   - Suporte a VPN, Direct Connect e endpoints privados

3. **Escalabilidade e Flexibilidade**
   - Suporte a múltiplas sub-redes (públicas e privadas)
   - Integração com serviços como EC2, RDS, Lambda, etc.
   - Possibilidade de peering entre VPCs

4. **Alta Disponibilidade**
   - Distribuição de recursos em múltiplas zonas de disponibilidade (AZs)
   - Suporte a failover e redundância

## Para que é usado

### Casos de Uso Comuns

1. **Hospedagem de Aplicações Web**
   - ✅ Isolamento de camadas de aplicação (web, app, banco)
   - ✅ Controle de acesso externo e interno

2. **Ambientes Seguros**
   - ✅ Execução de workloads sensíveis
   - ✅ Integração com redes corporativas via VPN

3. **Data Lakes e Analytics**
   - ✅ Tráfego privado entre serviços AWS
   - ✅ Segmentação de ambientes de dados

4. **Ambientes Multi-tenant**
   - ✅ Isolamento de clientes em diferentes VPCs

## Vantagens

### Técnicas
- ✅ **Isolamento** de rede
- ✅ **Controle granular** de tráfego
- ✅ **Integração** com múltiplos serviços AWS
- ✅ **Alta disponibilidade** e redundância

### Operacionais
- ✅ **Gerenciamento** centralizado de rede
- ✅ **Monitoramento** via VPC Flow Logs
- ✅ **Automação** de provisionamento

### Econômicas
- ✅ **Pay-as-you-go**
- ✅ **Redução** de custos de infraestrutura física

## Desvantagens

### Técnicas
- ❌ **Complexidade** de configuração inicial
- ❌ **Gerenciamento** de rotas e ACLs pode ser desafiador

### Operacionais
- ❌ **Necessidade** de conhecimento em redes
- ❌ **Monitoramento** contínuo de segurança

### Econômicas
- ❌ **Custos** adicionais para VPN, NAT Gateway, etc.

## Boas práticas

### Nomenclatura
- ✅ **Identificação** por ambiente (dev, prod)
- ✅ **Padrão** de nomes para sub-redes e VPCs

### Segurança
- ✅ **Uso de Security Groups e NACLs**
- ✅ **Segmentação** de sub-redes públicas e privadas
- ✅ **Monitoramento** com VPC Flow Logs

### Custo
- ✅ **Uso eficiente** de NAT Gateways e endpoints
- ✅ **Revisão** periódica de recursos de rede

## Exemplo prático

```powershell
# Criar uma VPC
aws ec2 create-vpc `
    --cidr-block 10.0.0.0/16

# Criar uma sub-rede pública
aws ec2 create-subnet `
    --vpc-id vpc-12345678 `
    --cidr-block 10.0.1.0/24 `
    --availability-zone us-east-1a

# Criar um Internet Gateway e associar à VPC
aws ec2 create-internet-gateway
aws ec2 attach-internet-gateway `
    --vpc-id vpc-12345678 `
    --internet-gateway-id igw-12345678
```

## Configurações Importantes

### Sub-redes
- Públicas e privadas
- Distribuição em múltiplas AZs

### Segurança
- Security Groups (nível de instância)
- Network ACLs (nível de sub-rede)
- VPC Flow Logs

### Conectividade
- Internet Gateway, NAT Gateway, VPN, Direct Connect
- VPC Peering e endpoints privados

### Roteamento
- Tabelas de rotas customizáveis
- Controle de tráfego entre sub-redes e internet

## Considerações Importantes

1. **Planejamento de Endereçamento**
   - Definir intervalos de IP adequados
   - Prever crescimento futuro

2. **Segurança**
   - Segmentar recursos críticos em sub-redes privadas
   - Monitorar logs de tráfego

3. **Custo**
   - Otimizar uso de NAT e endpoints
   - Revisar recursos não utilizados

4. **Escalabilidade**
   - Distribuir recursos em múltiplas AZs
   - Planejar para alta disponibilidade

---

## Arquitetura Amazon VPC
![Arquitetura Amazon VPC](/images/Arquitetura%20VPC.png)

---

## Gerenciamento de Sub-redes e Rotas
![Gerenciamento de Sub-redes VPC](/images/Subredes%20VPC.png)

---

## Integração com Serviços AWS
![Integração VPC AWS](/images/Integracao%20VPC%20AWS.png)

---

## Configuração típica
![Configuração típica VPC](/images/Configuracao%20tipica%20VPC.png)

---
