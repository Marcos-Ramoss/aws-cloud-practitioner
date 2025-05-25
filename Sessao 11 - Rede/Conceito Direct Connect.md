## Botão Voltar ao Início
[⬆️ Voltar ao Início](https://github.com/Marcos-Ramoss/aws-cloud-practitioner)

---

# AWS Direct Connect

## Conceito

O AWS Direct Connect é um serviço que permite estabelecer uma conexão de rede dedicada e privada entre seu ambiente local (on-premises ou data center) e a AWS. Essa conexão física proporciona maior largura de banda, menor latência e maior segurança em comparação com conexões pela internet pública.

### Características Principais

1. **Conexão Dedicada**
   - Link físico privado entre o data center/local e a AWS
   - Largura de banda de 50 Mbps até 100 Gbps

2. **Baixa Latência e Alta Performance**
   - Menor latência e jitter em relação à internet
   - Ideal para aplicações sensíveis a tempo de resposta

3. **Segurança**
   - Tráfego não passa pela internet pública
   - Suporte a criptografia via VPN sobre Direct Connect

4. **Integração com VPC**
   - Integração direta com VPCs usando Virtual Interfaces (VIFs)
   - Suporte a múltiplas VPCs e contas

5. **Redundância e Alta Disponibilidade**
   - Suporte a múltiplos links e failover
   - Recomendado usar conexões redundantes

## Para que é usado

### Casos de Uso Comuns

1. **Migração de Dados em Larga Escala**
   - ✅ Transferência de grandes volumes de dados para a AWS
   - ✅ Backup e replicação de dados

2. **Aplicações de Baixa Latência**
   - ✅ Workloads financeiros, jogos, streaming
   - ✅ Integração de sistemas críticos

3. **Ambientes Híbridos**
   - ✅ Integração contínua entre data center e AWS
   - ✅ Disaster recovery e failover

## Vantagens

### Técnicas
- ✅ **Alta performance** e baixa latência
- ✅ **Largura de banda** dedicada
- ✅ **Segurança** aprimorada

### Operacionais
- ✅ **Confiabilidade** e previsibilidade de rede
- ✅ **Gerenciamento** centralizado

### Econômicas
- ✅ **Redução** de custos de transferência de dados em larga escala
- ✅ **Previsibilidade** de custos

## Desvantagens

### Técnicas
- ❌ **Tempo de provisionamento** (instalação física pode levar semanas)
- ❌ **Dependência** de provedores parceiros

### Operacionais
- ❌ **Gerenciamento** de múltiplos links pode ser complexo
- ❌ **Necessidade** de planejamento de capacidade

### Econômicas
- ❌ **Custos** fixos mensais e por porta
- ❌ **Investimento** inicial para instalação

## Boas práticas

### Nomenclatura
- ✅ **Identificação** clara das conexões e interfaces
- ✅ **Documentação** das topologias

### Segurança
- ✅ **Criptografia** de dados sensíveis (VPN sobre Direct Connect)
- ✅ **Monitoramento** de tráfego e falhas

### Custo
- ✅ **Avaliação** de custos vs. volume de dados
- ✅ **Uso eficiente** de múltiplas conexões

## Exemplo prático

```powershell
# Criar uma conexão Direct Connect
aws directconnect create-connection `
    --connection-name MinhaConexaoDC `
    --location EqDC2 `
    --bandwidth 1Gbps

# Criar uma Virtual Interface Pública
aws directconnect create-public-virtual-interface `
    --connection-id dxcon-abc123 `
    --new-public-virtual-interface Allocation={...}

# Criar uma Virtual Interface Privada
aws directconnect create-private-virtual-interface `
    --connection-id dxcon-abc123 `
    --new-private-virtual-interface Allocation={...}
```

## Configurações Importantes

### Virtual Interfaces (VIFs)
- Pública: acesso a serviços AWS públicos (S3, DynamoDB)
- Privada: acesso direto a VPCs
- Transit: integração com AWS Transit Gateway

### Redundância
- Recomenda-se múltiplas conexões para alta disponibilidade
- Planejar failover e rotas alternativas

### Integração
- Suporte a múltiplas contas e VPCs
- Integração com VPN para criptografia adicional

## Considerações Importantes

1. **Planejamento de Capacidade**
   - Avaliar largura de banda necessária
   - Prever crescimento futuro

2. **Segurança**
   - Usar VPN para dados sensíveis
   - Monitorar acessos e tráfego

3. **Custo**
   - Analisar custos fixos e variáveis
   - Revisar uso e necessidade de múltiplos links

4. **Gerenciamento**
   - Documentar topologia e conexões
   - Monitorar disponibilidade e performance

---

## Arquitetura AWS Direct Connect
![Arquitetura AWS Direct Connect](/images/Arquitetura%20Direct%20Connect.png)

---

## Exemplo de Virtual Interfaces
![Exemplo de Virtual Interfaces](/images/Exemplo%20Direct%20Connect%20VIF.png)

---

## Integração com Serviços AWS
![Integração Direct Connect AWS](/images/Integracao%20Direct%20Connect%20AWS.png)

---

## Configuração típica
![Configuração típica Direct Connect](/images/Configuracao%20tipica%20Direct%20Connect.png)

---
