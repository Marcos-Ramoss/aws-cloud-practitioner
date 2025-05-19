## Botão Voltar ao Início
[⬆️ Voltar ao Início](/README.md)

--- 

# Amazon S3 Pricing

## Conceito

O Amazon S3 utiliza um modelo de preços baseado em pay-as-you-go, onde você paga apenas pelo que usa. Os custos são calculados com base em vários componentes, incluindo armazenamento, transferência de dados, requisições e recursos adicionais.

### Componentes de Preço

1. **Armazenamento**
   - Preço por GB/mês
   - Varia por classe de armazenamento
   - Varia por região
   - Duração mínima de armazenamento

2. **Transferência de Dados**
   - Transferência de dados para fora da AWS
   - Transferência entre regiões
   - Transferência para a internet
   - Transferência para outros serviços AWS

3. **Requisições**
   - GET, PUT, COPY, POST, LIST
   - Requisições de recuperação
   - Requisições de transição
   - Requisições de API

4. **Recursos Adicionais**
   - S3 Storage Lens
   - S3 Object Lambda
   - S3 Batch Operations
   - S3 Replication

## Preços Atuais (US East - N. Virginia)

### Armazenamento (por GB/mês)

1. **S3 Standard**
   - ✅ $0.023 por GB/mês
   - ✅ Primeiros 50 TB/mês
   - ✅ Alta disponibilidade
   - ✅ Baixa latência

2. **S3 Standard-IA**
   - ✅ $0.0125 por GB/mês
   - ✅ Duração mínima: 30 dias
   - ✅ Taxa de recuperação
   - ✅ Alta durabilidade

3. **S3 One Zone-IA**
   - ✅ $0.01 por GB/mês
   - ✅ Duração mínima: 30 dias
   - ✅ Single AZ
   - ✅ Alta durabilidade

4. **S3 Glacier**
   - ✅ $0.004 por GB/mês
   - ✅ Duração mínima: 90 dias
   - ✅ Recuperação flexível
   - ✅ Alta durabilidade

5. **S3 Glacier Deep Archive**
   - ✅ $0.00099 por GB/mês
   - ✅ Duração mínima: 180 dias
   - ✅ Recuperação mais lenta
   - ✅ Alta durabilidade

### Requisições

1. **Requisições GET**
   - ✅ $0.0004 por 1.000 requisições
   - ✅ S3 Standard
   - ✅ S3 Intelligent-Tiering

2. **Requisições PUT, COPY, POST, LIST**
   - ✅ $0.005 por 1.000 requisições
   - ✅ Todas as classes
   - ✅ Inclui requisições de API

3. **Requisições de Recuperação**
   - ✅ S3 Standard-IA: $0.01 por GB
   - ✅ S3 One Zone-IA: $0.01 por GB
   - ✅ S3 Glacier: $0.02 por GB
   - ✅ S3 Glacier Deep Archive: $0.02 por GB

### Transferência de Dados

1. **Para a Internet**
   - ✅ Primeiros 1 GB/mês: Grátis
   - ✅ 1 GB - 10 TB/mês: $0.09 por GB
   - ✅ 10 TB - 50 TB/mês: $0.085 por GB
   - ✅ 50 TB - 150 TB/mês: $0.07 por GB

2. **Entre Regiões AWS**
   - ✅ $0.02 por GB
   - ✅ Varia por região
   - ✅ Desconto para volumes maiores
   - ✅ Preços específicos por região

## AWS Free Tier

### Incluso Gratuitamente
- ✅ 5 GB de armazenamento S3 Standard
- ✅ 20.000 requisições GET
- ✅ 2.000 requisições PUT, COPY, POST, LIST
- ✅ 100 GB de transferência de dados para fora

### Limitações
- ❌ Aplicável apenas a novos clientes
- ❌ Válido por 12 meses
- ❌ Não acumulativo
- ❌ Não inclui todas as regiões

## Exemplo de Cálculo de Custo

### Cenário: Website com 100 GB de Dados
```bash
# Cálculo Mensal

1. Armazenamento S3 Standard
   - 100 GB * $0.023 = $2.30

2. Requisições (estimativa)
   - 100.000 GET * $0.0004/1000 = $0.04
   - 10.000 PUT * $0.005/1000 = $0.05

3. Transferência de Dados
   - 50 GB de saída * $0.09 = $4.50

Total Mensal Estimado: $6.89
```

## Otimização de Custos

### Estratégias
- ✅ Uso de classes de armazenamento apropriadas
- ✅ Configuração de lifecycle policies
- ✅ Compressão de dados
- ✅ Cache com CloudFront
- ✅ Análise de padrões de acesso

### Ferramentas
- ✅ AWS Cost Explorer
- ✅ S3 Storage Lens
- ✅ AWS Budgets
- ✅ AWS Cost and Usage Report
- ✅ AWS Pricing Calculator

## Considerações Importantes

1. **Fatores que Afetam o Custo**
   - Volume de dados
   - Padrões de acesso
   - Requisições
   - Transferência de dados
   - Região

2. **Custos Adicionais**
   - Requisições de API
   - Recursos de gerenciamento
   - Serviços integrados
   - Suporte AWS

3. **Otimização**
   - Análise de uso
   - Lifecycle policies
   - Compressão
   - Cache
   - Monitoramento

4. **Planejamento**
   - Estimativa de custos
   - Orçamento
   - Alertas
   - Revisão periódica
   - Ajustes

---

## Classes de Armazenamento (Valores)
![Classes de Armazenamento](/images/Classes%20de%20Armazenamento%20S3%20precos.png)

---

## Quando Usar Cada Classe?
![Quando Usar Cada Classe](/images/Quando%20Usar%20Cada%20Classe.png)

---

## Diagrama de Arquitetura Básica
![Diagrama de Arquitetura Básica](/images/Diagrama%20de%20Arquitetura%20Básica.png)

---

