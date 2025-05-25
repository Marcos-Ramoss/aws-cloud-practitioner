## Botão Voltar ao Início
[⬆️ Voltar ao Início](https://github.com/Marcos-Ramoss/aws-cloud-practitioner)

---

# VPC Peering na AWS

## Conceito

O VPC Peering é um serviço da AWS que permite conectar duas VPCs (Virtual Private Clouds) de forma privada, usando a rede da AWS. O tráfego entre VPCs emparelhadas é roteado de forma privada, sem passar pela internet pública, permitindo comunicação segura entre recursos em diferentes VPCs, mesmo em diferentes contas ou regiões (inter-region peering).

### Características Principais

1. **Conectividade Privada**
   - Comunicação direta entre VPCs
   - Sem uso de gateways, VPNs ou internet

2. **Escopo**
   - Suporte a peering intra-região e inter-região
   - Pode ser feito entre VPCs da mesma conta ou de contas diferentes

3. **Segurança**
   - Tráfego permanece na rede privada da AWS
   - Controle de acesso via rotas e Security Groups

4. **Transparência**
   - Instâncias se comunicam como se estivessem na mesma rede
   - Não há translação de endereços (NAT)

## Para que é usado

### Casos de Uso Comuns

1. **Integração de Ambientes**
   - ✅ Comunicação entre ambientes dev, test e prod
   - ✅ Integração entre workloads multi-conta

2. **Expansão de Rede**
   - ✅ Compartilhamento de serviços centralizados (ex: logging, AD)
   - ✅ Comunicação entre VPCs em diferentes regiões

3. **Migração e Híbrido**
   - ✅ Migração de workloads entre VPCs
   - ✅ Integração com ambientes legados

## Vantagens

### Técnicas
- ✅ **Baixa latência** e alta performance
- ✅ **Tráfego privado** e seguro
- ✅ **Sem necessidade** de hardware adicional

### Operacionais
- ✅ **Gerenciamento** simplificado
- ✅ **Escalabilidade** para múltiplos pares

### Econômicas
- ✅ **Custo menor** que VPNs ou Direct Connect para comunicação entre VPCs

## Desvantagens

### Técnicas
- ❌ **Não suporta** transitive peering (VPC A <-> B <-> C não conecta A e C)
- ❌ **Limite** de conexões por VPC
- ❌ **Gerenciamento** de rotas pode ser complexo em ambientes grandes

### Operacionais
- ❌ **Necessidade** de atualização manual das tabelas de rotas
- ❌ **Monitoramento** de múltiplos peerings

### Econômicas
- ❌ **Custos** de transferência de dados entre VPCs

## Boas práticas

### Nomenclatura
- ✅ **Identificação** clara dos pares de VPC
- ✅ **Documentação** das conexões

### Segurança
- ✅ **Regras de rotas** restritivas
- ✅ **Uso de Security Groups** para limitar acesso

### Custo
- ✅ **Monitoramento** de tráfego entre VPCs
- ✅ **Revisão** periódica de peerings ativos

## Exemplo prático

```powershell
# Criar peering entre duas VPCs
aws ec2 create-vpc-peering-connection `
    --vpc-id vpc-11111111 `
    --peer-vpc-id vpc-22222222

# Aceitar peering (na conta de destino)
aws ec2 accept-vpc-peering-connection `
    --vpc-peering-connection-id pcx-12345678

# Adicionar rota para tráfego entre VPCs
aws ec2 create-route `
    --route-table-id rtb-11111111 `
    --destination-cidr-block 10.2.0.0/16 `
    --vpc-peering-connection-id pcx-12345678
```

## Configurações Importantes

### Rotas
- Atualizar tabelas de rotas em ambas as VPCs
- Permitir tráfego apenas para CIDRs necessários

### Segurança
- Ajustar Security Groups para permitir comunicação
- Monitorar logs de tráfego

### Limitações
- Não há roteamento transitivo
- Limite de peerings por VPC

## Considerações Importantes

1. **Planejamento de CIDR**
   - CIDRs das VPCs não podem se sobrepor

2. **Segurança**
   - Revisar rotas e regras de acesso

3. **Gerenciamento**
   - Documentar e monitorar conexões

4. **Custo**
   - Avaliar custos de transferência de dados

---

## Arquitetura VPC Peering AWS
![Arquitetura VPC Peering AWS](/images/Arquitetura%20VPC%20Peering.png)

---

## Exemplo de Rotas Peering
![Exemplo de Rotas Peering](/images/Rotas%20VPC%20Peering.png)

---

## Integração com Serviços AWS
![Integração VPC Peering AWS](/images/Integracao%20VPC%20Peering%20AWS.png)

---

## Configuração típica
![Configuração típica VPC Peering](/images/Configuracao%20tipica%20VPC%20Peering.png)

---
