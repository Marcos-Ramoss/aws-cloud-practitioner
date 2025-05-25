## Botão Voltar ao Início
[⬆️ Voltar ao Início](https://github.com/Marcos-Ramoss/aws-cloud-practitioner)

---

# AWS Transit Gateway

## Conceito

O AWS Transit Gateway é um serviço que permite conectar múltiplas VPCs, redes locais (on-premises) e conexões VPN/Direct Connect por meio de um único hub centralizado. Ele simplifica a topologia de rede, reduzindo a complexidade e facilitando o gerenciamento de grandes ambientes multi-VPC e híbridos.

### Características Principais

1. **Hub Centralizado**
   - Conecta VPCs, VPNs, Direct Connect e redes locais
   - Reduz a necessidade de múltiplos peerings VPC-to-VPC

2. **Escalabilidade e Flexibilidade**
   - Suporte a milhares de conexões simultâneas
   - Segmentação de tráfego com Route Tables

3. **Segurança**
   - Controle de tráfego entre VPCs e redes
   - Integração com Security Groups e políticas de roteamento

4. **Alta Disponibilidade**
   - Implantação automática em múltiplas zonas de disponibilidade (AZs)
   - Failover automático

## Para que é usado

### Casos de Uso Comuns

1. **Ambientes Multi-VPC**
   - ✅ Conexão centralizada de dezenas ou centenas de VPCs
   - ✅ Redução da complexidade de rotas

2. **Ambientes Híbridos**
   - ✅ Integração de redes locais com AWS via VPN ou Direct Connect
   - ✅ Disaster recovery e failover

3. **Segmentação de Rede**
   - ✅ Isolamento de ambientes (dev, prod, test)
   - ✅ Controle granular de tráfego entre segmentos

## Vantagens

### Técnicas
- ✅ **Escalabilidade** para grandes ambientes
- ✅ **Gerenciamento** centralizado de rotas
- ✅ **Alta disponibilidade** e redundância

### Operacionais
- ✅ **Facilidade** de integração de novas VPCs
- ✅ **Redução** de erros de configuração

### Econômicas
- ✅ **Otimização** de custos de conectividade
- ✅ **Redução** de links redundantes

## Desvantagens

### Técnicas
- ❌ **Limite** de attachments por região
- ❌ **Curva de aprendizado** para segmentação avançada

### Operacionais
- ❌ **Gerenciamento** de políticas pode ser complexo em ambientes muito grandes

### Econômicas
- ❌ **Custos** adicionais por attachment e tráfego

## Boas práticas

### Nomenclatura
- ✅ **Identificação** clara dos attachments e route tables
- ✅ **Documentação** da topologia

### Segurança
- ✅ **Segmentação** de ambientes sensíveis
- ✅ **Monitoramento** de tráfego e logs

### Custo
- ✅ **Revisão** periódica de attachments e rotas
- ✅ **Monitoramento** de uso e tráfego

## Exemplo prático

```powershell
# Criar um Transit Gateway
aws ec2 create-transit-gateway `
    --description "Meu Transit Gateway" `
    --options AmazonSideAsn=64512

# Associar uma VPC ao Transit Gateway
aws ec2 create-transit-gateway-vpc-attachment `
    --transit-gateway-id tgw-12345678 `
    --vpc-id vpc-12345678 `
    --subnet-ids subnet-12345678 subnet-87654321

# Associar uma VPN ao Transit Gateway
aws ec2 create-transit-gateway-vpn-attachment `
    --transit-gateway-id tgw-12345678 `
    --vpn-connection-id vpn-12345678
```

## Configurações Importantes

### Route Tables
- Definir rotas para controlar o tráfego entre attachments
- Suporte a múltiplas route tables para segmentação

### Attachments
- VPC, VPN, Direct Connect, Peering
- Gerenciar permissões e segmentação

### Alta Disponibilidade
- Implantação automática em múltiplas AZs
- Failover automático

## Considerações Importantes

1. **Planejamento de Topologia**
   - Definir segmentos e rotas antes da implantação

2. **Segurança**
   - Isolar ambientes sensíveis
   - Monitorar logs e tráfego

3. **Custo**
   - Avaliar custos de attachments e tráfego

4. **Gerenciamento**
   - Documentar topologia e políticas
   - Automatizar provisionamento quando possível

---

## Arquitetura AWS Transit Gateway
![Arquitetura AWS Transit Gateway](/images/Arquitetura%20Transit%20Gateway.png)

---

## Exemplo de Attachments
![Exemplo de Attachments Transit Gateway](/images/Exemplo%20Transit%20Gateway%20Attachments.png)

---

## Integração com Serviços AWS
![Integração Transit Gateway AWS](/images/Integracao%20Transit%20Gateway%20AWS.png)

---

## Configuração típica
![Configuração típica Transit Gateway](/images/Configuracao%20tipica%20Transit%20Gateway.png)

---
