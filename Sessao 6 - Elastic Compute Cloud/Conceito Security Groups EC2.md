## Botão Voltar ao Início
[⬆️ Voltar ao Início](https://github.com/Marcos-Ramoss/aws-cloud-practitioner)

---

# Security Groups EC2 AWS

## Conceito

Os **Security Groups** do EC2 funcionam como um firewall virtual para suas instâncias, controlando o tráfego de entrada (inbound) e saída (outbound). Eles são uma camada fundamental de segurança que permite definir regras de acesso granular para suas instâncias EC2.

### Entendendo os Security Groups

1. **Características Principais**
   - **Estado**: São stateful (mantêm estado das conexões)
   - **Regras**: Permissivas (só permitem o que é explicitamente autorizado)
   - **Escopo**: Por VPC (não podem ser usados fora da VPC onde foram criados)
   - **Associação**: Múltipla (uma instância pode ter vários security groups)

2. **Tipos de Regras**
   - **Inbound (Entrada)**: Controla tráfego que chega à instância
   - **Outbound (Saída)**: Controla tráfego que sai da instância
   - **Protocolos**: TCP, UDP, ICMP, ou todos (-1)
   - **Portas**: Intervalos específicos ou todas

3. **Fontes e Destinos**
   - **CIDR Blocks**: Intervalos de IP específicos
   - **Security Groups**: Outros security groups
   - **Prefix Lists**: Listas de prefixos IP
   - **Anywhere**: 0.0.0.0/0 (IPv4) ou ::/0 (IPv6)

## Para que são usados

### Casos de Uso Comuns

1. **Acesso SSH/RDP**
   - ✅ **Acesso remoto** a instâncias Linux/Windows
   - ✅ **Administração** de servidores
   - ✅ **Manutenção** de sistemas
   - ✅ **Troubleshooting**
   - ✅ **Deploy** de aplicações

2. **Aplicações Web**
   - ✅ **HTTP/HTTPS** (portas 80/443)
   - ✅ **Load Balancers**
   - ✅ **APIs** e microserviços
   - ✅ **Web servers**
   - ✅ **Application servers**

3. **Bancos de Dados**
   - ✅ **MySQL/PostgreSQL** (porta 3306/5432)
   - ✅ **MongoDB** (porta 27017)
   - ✅ **Redis** (porta 6379)
   - ✅ **Elasticsearch** (porta 9200)
   - ✅ **Cache servers**

4. **Comunicação Interna**
   - ✅ **Entre instâncias**
   - ✅ **Entre serviços**
   - ✅ **Entre camadas**
   - ✅ **Entre regiões**
   - ✅ **Entre VPCs**

## Vantagens

### Técnicas
- ✅ **Controle granular** de acesso
- ✅ **Estado mantido** das conexões
- ✅ **Regras dinâmicas**
- ✅ **Integração** com VPC
- ✅ **Monitoramento** de tráfego

### Operacionais
- ✅ **Fácil configuração**
- ✅ **Alterações em tempo real**
- ✅ **Documentação clara**
- ✅ **Auditoria** de regras
- ✅ **Manutenção** simplificada

### Segurança
- ✅ **Isolamento** de recursos
- ✅ **Defesa em profundidade**
- ✅ **Controle de acesso**
- ✅ **Prevenção** de ataques
- ✅ **Compliance**

## Desvantagens

### Técnicas
- ❌ **Limitação** por VPC
- ❌ **Complexidade** em grandes ambientes
- ❌ **Limite** de regras
- ❌ **Sem negação** explícita
- ❌ **Sem logging** nativo

### Operacionais
- ❌ **Gestão** manual
- ❌ **Documentação** necessária
- ❌ **Auditoria** constante
- ❌ **Treinamento** necessário
- ❌ **Manutenção** contínua

### Segurança
- ❌ **Risco** de configuração incorreta
- ❌ **Exposição** acidental
- ❌ **Complexidade** de regras
- ❌ **Dependência** de boas práticas
- ❌ **Limitações** de proteção

## Boas práticas

### Configuração
- ✅ **Princípio do menor privilégio**
- ✅ **Regras específicas**
- ✅ **Documentação clara**
- ✅ **Revisão periódica**
- ✅ **Testes de segurança**

### Manutenção
- ✅ **Monitoramento** contínuo
- ✅ **Atualização** de regras
- ✅ **Limpeza** de regras não usadas
- ✅ **Backup** de configurações
- ✅ **Versionamento** de regras

### Segurança
- ✅ **Restrição** de portas
- ✅ **Limitação** de IPs
- ✅ **Uso de grupos**
- ✅ **Auditoria** regular
- ✅ **Compliance** check

## Exemplo prático

```bash
# Criar security group
aws ec2 create-security-group \
    --group-name my-security-group \
    --description "My security group" \
    --vpc-id vpc-1234567890abcdef0

# Adicionar regra de entrada (SSH)
aws ec2 authorize-security-group-ingress \
    --group-id sg-1234567890abcdef0 \
    --protocol tcp \
    --port 22 \
    --cidr 203.0.113.0/24

# Adicionar regra de saída (HTTP)
aws ec2 authorize-security-group-egress \
    --group-id sg-1234567890abcdef0 \
    --protocol tcp \
    --port 80 \
    --cidr 0.0.0.0/0

# Modificar regras existentes
aws ec2 modify-security-group-rules \
    --group-id sg-1234567890abcdef0 \
    --security-group-rules '[
        {
            "SecurityGroupRuleId": "sgr-1234567890abcdef0",
            "SecurityGroupRule": {
                "IpProtocol": "tcp",
                "FromPort": 80,
                "ToPort": 80,
                "CidrIpv4": "10.0.0.0/16"
            }
        }
    ]'
```

---

## Configuração para Servidor Web
![Configuração para Servidor Web](/images/Configuração%20para%20Servidor%20Web.png)

---

## Segurança Avançada
![Segurança Avançada](/images/Segurança%20Avançada.png)

---

## Arquitetura Segura
![Arquitetura Segura](/images/Arquitetura%20Segura.png)

---