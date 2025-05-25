## Botão Voltar ao Início
[⬆️ Voltar ao Início](https://github.com/Marcos-Ramoss/aws-cloud-practitioner)

---

# Amazon ElastiCache

## Conceito

O Amazon ElastiCache é um serviço gerenciado de cache em memória, compatível com Redis e Memcached, que permite implantar, operar e escalar facilmente caches de dados de alta performance na nuvem. Ele é projetado para acelerar aplicações web, reduzindo a latência e melhorando o throughput ao armazenar dados frequentemente acessados na memória.

### Características Principais

1. **Compatibilidade**
   - Suporte a Redis e Memcached
   - APIs padrão open source

2. **Desempenho e Escalabilidade**
   - Latência de microssegundos
   - Suporte a clusters com sharding
   - Auto Scaling e failover automático (Redis)

3. **Alta Disponibilidade e Durabilidade**
   - Replicação Multi-AZ (Redis)
   - Snapshots e backups automáticos (Redis)
   - Failover automático

4. **Segurança**
   - Integração com VPC, IAM e KMS
   - Criptografia em trânsito e em repouso (Redis)
   - Autenticação e controle de acesso

5. **Gerenciamento Automatizado**
   - Monitoramento via Amazon CloudWatch
   - Atualizações automáticas de software
   - Manutenção simplificada

## Para que é usado

### Casos de Uso Comuns

1. **Aceleração de Aplicações Web**
   - ✅ Cache de sessões de usuário
   - ✅ Cache de páginas e objetos
   - ✅ Redução de latência em consultas a banco de dados

2. **Filas e Mensageria**
   - ✅ Fila de tarefas em tempo real
   - ✅ Pub/Sub (Redis)

3. **Analytics e Machine Learning**
   - ✅ Armazenamento temporário de resultados
   - ✅ Feature store para ML

4. **Gaming e IoT**
   - ✅ Leaderboards em tempo real
   - ✅ Estado de jogos e dispositivos

## Vantagens

### Técnicas
- ✅ **Baixa latência** e alta performance
- ✅ **Escalabilidade** horizontal e vertical
- ✅ **Alta disponibilidade** com failover automático (Redis)
- ✅ **Backups** automáticos (Redis)
- ✅ **Compatibilidade** com Redis e Memcached

### Operacionais
- ✅ **Gerenciamento** simplificado
- ✅ **Monitoramento** nativo (CloudWatch)
- ✅ **Automação** de manutenção

### Econômicas
- ✅ **Pay-as-you-go**
- ✅ **Redução** de custos de infraestrutura
- ✅ **Otimização** de recursos

## Desvantagens

### Técnicas
- ❌ **Persistência** limitada (Memcached)
- ❌ **Não relacional** (apenas chave-valor)
- ❌ **Limitações** de tamanho de cluster

### Operacionais
- ❌ **Dependência** do provedor AWS
- ❌ **Gerenciamento** de sharding pode ser complexo

### Econômicas
- ❌ **Custos** adicionais para alta disponibilidade
- ❌ **Cobrança** por recursos provisionados

## Boas práticas

### Nomenclatura
- ✅ **Identificação** por ambiente (dev, prod)
- ✅ **Padrão** de nomes para clusters e nós

### Segurança
- ✅ **Acesso restrito** via VPC e Security Groups
- ✅ **Criptografia** ativada (em trânsito e em repouso)
- ✅ **Autenticação** habilitada (Redis)

### Custo
- ✅ **Monitoramento** de uso e dimensionamento
- ✅ **Revisão** periódica de clusters e nós

## Exemplo prático

```bash
# Criar cluster ElastiCache Redis
aws elasticache create-cache-cluster \
    --cache-cluster-id meu-redis-cluster \
    --engine redis \
    --cache-node-type cache.t3.micro \
    --num-cache-nodes 1 \
    --vpc-security-group-ids sg-12345678

# Criar cluster ElastiCache Memcached
aws elasticache create-cache-cluster \
    --cache-cluster-id meu-memcached-cluster \
    --engine memcached \
    --cache-node-type cache.t3.micro \
    --num-cache-nodes 2 \
    --vpc-security-group-ids sg-12345678
```

## Configurações Importantes

### Backup e Restauração (Redis)
- Snapshots automáticos e manuais
- Restauração de dados

### Alta Disponibilidade
- Replicação Multi-AZ (Redis)
- Failover automático

### Segurança
- Criptografia (KMS)
- Controle de acesso (IAM, VPC, Security Groups)
- Autenticação (Redis)

### Performance
- Auto Scaling de nós (Redis)
- Monitoramento de métricas (CloudWatch)
- Ajuste de parâmetros via Parameter Groups

## Considerações Importantes

1. **Escolha do Engine**
   - Redis para persistência e alta disponibilidade
   - Memcached para simplicidade e cache puro

2. **Segurança**
   - Acesso restrito à VPC
   - Criptografia e autenticação

3. **Backup**
   - Snapshots regulares (Redis)
   - Testes de restauração

4. **Escalabilidade**
   - Dimensionamento automático de nós
   - Monitoramento de performance

---

## Arquitetura Amazon ElastiCache
![Arquitetura Amazon ElastiCache](/images/Arquitetura%20ElastiCache.png)

---

## Gerenciamento de Backup ElastiCache
![Gerenciamento de Backup ElastiCache](/images/Backup%20ElastiCache.png)

---

## Integração com Serviços AWS
![Integração ElastiCache AWS](/images/Integracao%20ElastiCache%20AWS.png)

---

## Configuração típica
![Configuração típica ElastiCache](/images/Configuracao%20tipica%20ElastiCache.png)

---