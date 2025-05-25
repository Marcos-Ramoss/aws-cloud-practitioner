## Botão Voltar ao Início
[⬆️ Voltar ao Início](https://github.com/Marcos-Ramoss/aws-cloud-practitioner)

---

# VPC Flow Logs na AWS

## Conceito

O VPC Flow Logs é um recurso da AWS que permite capturar informações sobre o tráfego IP que entra e sai de interfaces de rede em sua VPC. Os logs podem ser enviados para Amazon CloudWatch Logs ou Amazon S3, facilitando o monitoramento, análise e auditoria de tráfego de rede.

### Características Principais

1. **Captura de Tráfego**
   - Registra tráfego de entrada e saída em VPCs, sub-redes ou ENIs
   - Permite filtrar logs por tipo de tráfego (aceito, rejeitado, todos)

2. **Destino dos Logs**
   - Envio para Amazon CloudWatch Logs ou Amazon S3
   - Integração com ferramentas de análise e SIEM

3. **Detalhamento**
   - Campos detalhados: endereços IP, portas, protocolo, ação, bytes, etc.
   - Suporte a logs customizados (campos selecionáveis)

4. **Escopo**
   - Pode ser ativado em nível de VPC, sub-rede ou interface de rede

## Para que é usado

### Casos de Uso Comuns

1. **Monitoramento de Segurança**
   - ✅ Detecção de tráfego suspeito ou não autorizado
   - ✅ Análise de tentativas de acesso negado

2. **Auditoria e Compliance**
   - ✅ Registro de acessos para fins de auditoria
   - ✅ Atender requisitos regulatórios

3. **Análise de Performance**
   - ✅ Identificação de gargalos de rede
   - ✅ Diagnóstico de problemas de conectividade

## Vantagens

### Técnicas
- ✅ **Visibilidade** detalhada do tráfego de rede
- ✅ **Integração** com CloudWatch e S3
- ✅ **Customização** dos campos de log

### Operacionais
- ✅ **Facilidade** de ativação e gerenciamento
- ✅ **Automação** de análise com ferramentas AWS

### Econômicas
- ✅ **Custo sob demanda** (pay-as-you-go)
- ✅ **Redução** de custos de auditoria manual

## Desvantagens

### Técnicas
- ❌ **Volume** de logs pode ser alto em ambientes grandes
- ❌ **Não captura** pacotes, apenas metadados de fluxo

### Operacionais
- ❌ **Necessidade** de gerenciamento de armazenamento de logs
- ❌ **Curva de aprendizado** para análise detalhada

### Econômicas
- ❌ **Custos** podem aumentar com grande volume de logs

## Boas práticas

### Nomenclatura
- ✅ **Identificação** clara dos logs por ambiente e recurso
- ✅ **Documentação** dos filtros e destinos

### Segurança
- ✅ **Restrição** de acesso aos logs
- ✅ **Monitoramento** de alterações nas configurações

### Custo
- ✅ **Revisão** periódica de retenção e volume de logs
- ✅ **Automação** de arquivamento e limpeza

## Exemplo prático

```powershell
# Criar Flow Log para uma VPC
aws ec2 create-flow-logs `
    --resource-type VPC `
    --resource-ids vpc-12345678 `
    --traffic-type ALL `
    --log-group-name MeuVPCFlowLog `
    --deliver-logs-permission-arn arn:aws:iam::123456789012:role/FlowLogsRole

# Criar Flow Log para uma sub-rede
aws ec2 create-flow-logs `
    --resource-type Subnet `
    --resource-ids subnet-12345678 `
    --traffic-type REJECT `
    --log-group-name MeuSubnetFlowLog `
    --deliver-logs-permission-arn arn:aws:iam::123456789012:role/FlowLogsRole
```

## Configurações Importantes

### Filtros de Tráfego
- ALL, ACCEPT ou REJECT
- Escolher conforme necessidade de monitoramento

### Destino dos Logs
- CloudWatch Logs para análise em tempo real
- S3 para arquivamento e análise posterior

### Retenção
- Definir política de retenção adequada
- Automatizar limpeza de logs antigos

## Considerações Importantes

1. **Planejamento de Volume**
   - Estimar volume de logs para evitar custos inesperados

2. **Segurança**
   - Restringir acesso aos logs
   - Monitorar alterações nas configurações

3. **Análise**
   - Integrar com ferramentas de SIEM e automação

4. **Custo**
   - Monitorar custos de armazenamento e processamento

---

## Arquitetura VPC Flow Logs AWS
![Arquitetura VPC Flow Logs AWS](/images/Arquitetura%20VPC%20Flow%20Logs.png)

---

## Exemplo de Log Flow
![Exemplo de Log Flow](/images/Exemplo%20VPC%20Flow%20Log.png)

---

## Integração com Serviços AWS
![Integração VPC Flow Logs AWS](/images/Integracao%20VPC%20Flow%20Logs%20AWS.png)

---

## Configuração típica
![Configuração típica VPC Flow Logs](/images/Configuracao%20tipica%20VPC%20Flow%20Logs.png)

---
