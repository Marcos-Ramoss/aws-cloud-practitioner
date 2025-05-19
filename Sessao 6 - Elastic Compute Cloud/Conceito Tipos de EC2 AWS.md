## Botão Voltar ao Início
[⬆️ Voltar ao Início](https://github.com/Marcos-Ramoss/aws-cloud-practitioner)

---

# Tipos de Instâncias EC2 AWS

## Conceito

Os **Tipos de Instâncias EC2** são diferentes configurações de CPU, memória, armazenamento e capacidade de rede que permitem escolher a combinação apropriada de recursos para suas aplicações. Cada tipo de instância é otimizado para diferentes casos de uso.

### Entendendo os Tipos de Instâncias

1. **Famílias de Instâncias**
   - **Uso Geral (t3, m5)**: Balanceamento entre computação, memória e rede
   - **Computação Otimizada (c5)**: Alto desempenho de CPU
   - **Memória Otimizada (r5)**: Alto desempenho de memória
   - **Armazenamento Otimizado (i3)**: Alto desempenho de I/O
   - **GPU (g4)**: Processamento gráfico acelerado
   - **Inferência (inf1)**: Machine Learning

2. **Gerações de Instâncias**
   - **Primeira Geração**: Instâncias mais antigas (m1, c1)
   - **Segunda Geração**: Melhorias de performance (m3, c3)
   - **Terceira Geração**: Otimizações de custo (m4, c4)
   - **Quarta Geração**: Melhorias de rede (m5, c5)
   - **Quinta Geração**: Últimas inovações (m6, c6)

3. **Tamanhos de Instâncias**
   - **Nano**: 0.5 vCPU, 0.5 GiB RAM
   - **Micro**: 1 vCPU, 1 GiB RAM
   - **Small**: 1 vCPU, 2 GiB RAM
   - **Medium**: 2 vCPU, 4 GiB RAM
   - **Large**: 2 vCPU, 8 GiB RAM
   - **XLarge**: 4 vCPU, 16 GiB RAM
   - **2XLarge**: 8 vCPU, 32 GiB RAM
   - **4XLarge**: 16 vCPU, 64 GiB RAM

## Para que são usados

### Casos de Uso por Família

1. **Uso Geral (t3, m5)**
   - ✅ **Aplicações web**
   - ✅ **Servidores de desenvolvimento**
   - ✅ **Ambientes de teste**
   - ✅ **Servidores de banco de dados pequenos**
   - ✅ **Servidores de aplicação**

2. **Computação Otimizada (c5)**
   - ✅ **Processamento em lote**
   - ✅ **Servidores web de alto tráfego**
   - ✅ **Análise de dados**
   - ✅ **Servidores de jogos**
   - ✅ **Computação científica**

3. **Memória Otimizada (r5)**
   - ✅ **Bancos de dados**
   - ✅ **Caches em memória**
   - ✅ **Análise de dados em tempo real**
   - ✅ **Aplicações empresariais**
   - ✅ **Processamento de big data**

4. **Armazenamento Otimizado (i3)**
   - ✅ **Bancos de dados NoSQL**
   - ✅ **Data warehousing**
   - ✅ **Processamento de logs**
   - ✅ **Sistemas de arquivos distribuídos**
   - ✅ **Análise de dados**

5. **GPU (g4)**
   - ✅ **Machine Learning**
   - ✅ **Processamento de vídeo**
   - ✅ **Renderização 3D**
   - ✅ **Streaming de jogos**
   - ✅ **Computação gráfica**

## Vantagens

### Técnicas
- ✅ **Otimização** para casos de uso específicos
- ✅ **Escalabilidade** vertical e horizontal
- ✅ **Flexibilidade** de configuração
- ✅ **Performance** previsível
- ✅ **Integração** com outros serviços AWS

### Operacionais
- ✅ **Fácil migração** entre tipos
- ✅ **Monitoramento** detalhado
- ✅ **Auto-scaling** por tipo
- ✅ **Backup** e recuperação
- ✅ **Manutenção** simplificada

### Econômicas
- ✅ **Otimização** de custos
- ✅ **Pay-as-you-go**
- ✅ **Reserved instances**
- ✅ **Spot instances**
- ✅ **Savings plans**

## Desvantagens

### Técnicas
- ❌ **Complexidade** de escolha
- ❌ **Limitações** de recursos
- ❌ **Custos** de migração
- ❌ **Dependência** de disponibilidade
- ❌ **Configuração** manual

### Operacionais
- ❌ **Gestão** de múltiplos tipos
- ❌ **Monitoramento** complexo
- ❌ **Manutenção** por tipo
- ❌ **Documentação** extensa
- ❌ **Treinamento** necessário

### Econômicas
- ❌ **Custos** variáveis
- ❌ **Otimização** necessária
- ❌ **Commitment** de recursos
- ❌ **Transferência** de dados
- ❌ **Armazenamento** adicional

## Boas práticas

### Seleção
- ✅ **Analise requisitos** de aplicação
- ✅ **Considere custos**
- ✅ **Avalie performance**
- ✅ **Planeje escalabilidade**
- ✅ **Teste diferentes tipos**

### Otimização
- ✅ **Use auto-scaling**
- ✅ **Monitor recursos**
- ✅ **Ajuste conforme necessidade**
- ✅ **Implemente caching**
- ✅ **Otimize configurações**

### Custo
- ✅ **Use reserved instances**
- ✅ **Implemente spot instances**
- ✅ **Monitore uso**
- ✅ **Limpe recursos**
- ✅ **Use savings plans**

## Exemplo prático

```bash
# Listar tipos de instâncias disponíveis
aws ec2 describe-instance-types \
    --filters "Name=processor-info.supported-architecture,Values=x86_64" \
    --query "InstanceTypes[*].[InstanceType,ProcessorInfo.SupportedArchitectures,MemoryInfo.SizeInMiB]"

# Criar instância com tipo específico
aws ec2 run-instances \
    --image-id ami-0c55b159cbfafe1f0 \
    --count 1 \
    --instance-type t3.micro \
    --key-name MyKeyPair \
    --security-group-ids sg-xxxxxxxx

# Modificar tipo de instância
aws ec2 modify-instance-attribute \
    --instance-id i-1234567890abcdef0 \
    --instance-type "Value=t3.small"
```

---

## Categorias de Instâncias EC2
![Categorias de Instâncias EC2](/images/Categorias%20de%20Instâncias%20EC2.png)

---

## Seleção de Instância por Workload
![Seleção de Instância por Workload](/images/Seleção%20de%20Instância%20por%20Workload.png)

---

