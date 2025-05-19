## Botão Voltar ao Início
[⬆️ Voltar ao Início](/README.md)

---

# Modelos de Preços EC2 AWS

## Conceito

Os **Modelos de Preços EC2** são diferentes opções de cobrança que a AWS oferece para suas instâncias, permitindo otimizar custos de acordo com as necessidades específicas de cada aplicação. Cada modelo é projetado para diferentes padrões de uso e requisitos de flexibilidade.

### Entendendo os Modelos de Preço

1. **On-Demand Instances**
   - **Definição**: Pagamento por hora ou segundo de uso
   - **Flexibilidade**: Sem compromisso de longo prazo
   - **Custo**: Preço padrão da AWS
   - **Ideal para**: Cargas de trabalho imprevisíveis

2. **Reserved Instances (RI)**
   - **Definição**: Desconto em troca de compromisso de uso
   - **Períodos**: 1 ou 3 anos
   - **Pagamento**: Total, parcial ou nenhum adiantamento
   - **Ideal para**: Cargas de trabalho previsíveis

3. **Savings Plans**
   - **Definição**: Compromisso de uso com flexibilidade
   - **Tipos**: Compute e EC2 Instance
   - **Economia**: Até 72% em relação ao On-Demand
   - **Ideal para**: Uso consistente de recursos

4. **Spot Instances**
   - **Definição**: Uso de capacidade não utilizada
   - **Preço**: Até 90% de desconto
   - **Interrupção**: Pode ser interrompido com aviso
   - **Ideal para**: Cargas de trabalho tolerantes a falhas

5. **Dedicated Hosts**
   - **Definição**: Servidor físico dedicado
   - **Controle**: Total sobre o hardware
   - **Licenciamento**: BYOL (Bring Your Own License)
   - **Ideal para**: Requisitos de compliance

## Para que são usados

### Casos de Uso por Modelo

1. **On-Demand**
   - ✅ **Aplicações em desenvolvimento**
   - ✅ **Cargas de trabalho imprevisíveis**
   - ✅ **Testes e experimentos**
   - ✅ **Aplicações de curta duração**
   - ✅ **Primeira execução de aplicações**

2. **Reserved Instances**
   - ✅ **Servidores de produção**
   - ✅ **Bancos de dados**
   - ✅ **Aplicações empresariais**
   - ✅ **Serviços críticos**
   - ✅ **Cargas de trabalho estáveis**

3. **Savings Plans**
   - ✅ **Ambientes de produção**
   - ✅ **Cargas de trabalho consistentes**
   - ✅ **Auto-scaling groups**
   - ✅ **Serviços gerenciados**
   - ✅ **Aplicações de longo prazo**

4. **Spot Instances**
   - ✅ **Processamento em lote**
   - ✅ **Análise de dados**
   - ✅ **Testes de carga**
   - ✅ **Renderização**
   - ✅ **Machine Learning**

5. **Dedicated Hosts**
   - ✅ **Licenciamento específico**
   - ✅ **Compliance regulatório**
   - ✅ **Isolamento de hardware**
   - ✅ **Aplicações legadas**
   - ✅ **Requisitos de segurança**

## Vantagens

### Técnicas
- ✅ **Flexibilidade** de escolha
- ✅ **Otimização** de recursos
- ✅ **Escalabilidade** de custos
- ✅ **Controle** granular
- ✅ **Integração** com outros serviços

### Operacionais
- ✅ **Previsibilidade** de custos
- ✅ **Facilidade** de gerenciamento
- ✅ **Automação** de otimização
- ✅ **Monitoramento** de uso
- ✅ **Relatórios** detalhados

### Econômicas
- ✅ **Redução** de custos
- ✅ **Otimização** de investimento
- ✅ **Flexibilidade** de pagamento
- ✅ **Economia** em escala
- ✅ **ROI** previsível

## Desvantagens

### Técnicas
- ❌ **Complexidade** de escolha
- ❌ **Risco** de interrupção (Spot)
- ❌ **Compromisso** de longo prazo (RI)
- ❌ **Limitações** de flexibilidade
- ❌ **Dependência** de disponibilidade

### Operacionais
- ❌ **Gestão** de múltiplos modelos
- ❌ **Monitoramento** complexo
- ❌ **Otimização** contínua
- ❌ **Migração** entre modelos
- ❌ **Documentação** extensa

### Econômicas
- ❌ **Custos** iniciais (RI)
- ❌ **Penalidades** por não uso
- ❌ **Complexidade** de preços
- ❌ **Otimização** necessária
- ❌ **Previsão** de custos

## Boas práticas

### Seleção
- ✅ **Analise padrões** de uso
- ✅ **Considere compromissos**
- ✅ **Avalie flexibilidade**
- ✅ **Planeje crescimento**
- ✅ **Teste diferentes modelos**

### Otimização
- ✅ **Use ferramentas** de análise
- ✅ **Monitore utilização**
- ✅ **Ajuste conforme necessidade**
- ✅ **Implemente auto-scaling**
- ✅ **Otimize configurações**

### Custo
- ✅ **Use reserved instances**
- ✅ **Implemente spot instances**
- ✅ **Monitore uso**
- ✅ **Limpe recursos**
- ✅ **Use savings plans**

## Exemplo prático

```bash
# Listar preços On-Demand
aws ec2 describe-spot-price-history \
    --instance-types t3.micro \
    --product-description "Linux/UNIX" \
    --start-time=$(Get-Date).AddDays(-1).ToString("yyyy-MM-ddTHH:mm:ss")

# Comprar Reserved Instance
aws ec2 purchase-reserved-instances-offering \
    --reserved-instances-offering-id "12345678-1234-1234-1234-123456789012" \
    --instance-count 1

# Configurar Spot Instance
aws ec2 request-spot-instances \
    --spot-price "0.05" \
    --instance-count 1 \
    --type "one-time" \
    --launch-specification '{
        "ImageId": "ami-0c55b159cbfafe1f0",
        "InstanceType": "t3.micro",
        "KeyName": "MyKeyPair",
        "SecurityGroupIds": ["sg-xxxxxxxx"]
    }'
```

---

## Distribuição de Modelos de Preços
![Distribuição de Modelos de Preços](/images/Distribuição%20de%20Modelos%20de%20Preços.png)

---

## Modelos Disponíveis
![Modelos Disponíveis](/images/Modelos%20Disponíveis.png)

---

## Mecânica de Funcionamento
![Mecânica de Funcionamento](/images/Mecânica%20de%20Funcionamento.png)

---

## Estratégia Híbrida de Custos
![Estratégia Híbrida de Custos](/images/Estratégia%20Híbrida%20de%20Custos.png) 