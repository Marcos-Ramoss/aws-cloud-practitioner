## Botão Voltar ao Início
[⬆️ Voltar ao Início](https://github.com/Marcos-Ramoss/aws-cloud-practitioner)

---

# Network ACL (Access Control List) na AWS

## Conceito

Uma Network ACL (NACL) é uma camada de segurança opcional para sua VPC que atua como um firewall para controlar o tráfego de entrada e saída de uma ou mais sub-redes. As NACLs permitem ou negam tráfego com base em regras numéricas e são avaliadas em ordem crescente.

### Características Principais

1. **Controle de Tráfego**
   - Permite ou nega tráfego de entrada e saída
   - Regras baseadas em número, protocolo, porta e origem/destino

2. **Ordem de Avaliação**
   - Regras avaliadas em ordem crescente (menor número primeiro)
   - Primeira regra correspondente é aplicada

3. **Stateless**
   - NACLs são stateless: respostas ao tráfego devem ser explicitamente permitidas

4. **Aplicação**
   - Associadas a sub-redes (todas as instâncias na sub-rede seguem as regras da NACL)
   - Uma sub-rede pode ter apenas uma NACL associada

## Para que é usado

### Casos de Uso Comuns

1. **Segurança Adicional**
   - ✅ Camada extra de filtragem além dos Security Groups
   - ✅ Bloqueio de faixas de IP específicas

2. **Ambientes Multi-tenant**
   - ✅ Isolamento de sub-redes

3. **Compliance**
   - ✅ Implementação de políticas de acesso restritivas

## Vantagens

### Técnicas
- ✅ **Controle granular** de tráfego
- ✅ **Bloqueio** de IPs e portas indesejadas
- ✅ **Aplicação** a múltiplas sub-redes

### Operacionais
- ✅ **Gerenciamento** centralizado de regras
- ✅ **Facilidade** de auditoria

### Econômicas
- ✅ **Sem custo adicional** para uso de NACLs

## Desvantagens

### Técnicas
- ❌ **Stateless**: regras de resposta devem ser explícitas
- ❌ **Limitações** de regras por NACL

### Operacionais
- ❌ **Gerenciamento** pode ser complexo em ambientes grandes
- ❌ **Erros** em ordem de regras podem causar bloqueios inesperados

## Boas práticas

### Nomenclatura
- ✅ **Identificação** por ambiente (dev, prod)
- ✅ **Padrão** de nomes para NACLs

### Segurança
- ✅ **Regras explícitas** para entrada e saída
- ✅ **Auditoria** regular das regras

### Custo
- ✅ **Sem custo**, mas revisar para evitar regras desnecessárias

## Exemplo prático

```bash
# Criar uma NACL
aws ec2 create-network-acl \
    --vpc-id vpc-12345678

# Adicionar regra de entrada (permitir HTTP)
aws ec2 create-network-acl-entry \
    --network-acl-id acl-12345678 \
    --ingress \
    --rule-number 100 \
    --protocol 6 \
    --port-range From=80,To=80 \
    --cidr-block 0.0.0.0/0 \
    --rule-action allow

# Adicionar regra de saída (permitir HTTPS)
aws ec2 create-network-acl-entry \
    --network-acl-id acl-12345678 \
    --egress \
    --rule-number 100 \
    --protocol 6 \
    --port-range From=443,To=443 \
    --cidr-block 0.0.0.0/0 \
    --rule-action allow
```

## Configurações Importantes

### Regras
- Ordem de avaliação importa
- Regras explícitas para entrada e saída
- Regra padrão é negar tudo

### Associação
- Uma NACL por sub-rede
- Sub-redes sem NACL explícita usam a padrão

## Considerações Importantes

1. **Stateless**
   - Permissões de ida e volta devem ser configuradas

2. **Ordem das Regras**
   - Menor número tem prioridade

3. **Auditoria**
   - Revisar periodicamente as regras

---

## Arquitetura NACL AWS
![Arquitetura NACL AWS](/images/Arquitetura%20NACL.png)

---

## Exemplo de Regras NACL
![Exemplo de Regras NACL](/images/Regras%20NACL.png)

---

## Integração com Serviços AWS
![Integração NACL AWS](/images/Integracao%20NACL%20AWS.png)

---

## Configuração típica
![Configuração típica NACL](/images/Configuracao%20tipica%20NACL.png)

---
