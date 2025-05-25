## Botão Voltar ao Início
[⬆️ Voltar ao Início](https://github.com/Marcos-Ramoss/aws-cloud-practitioner)

---

# Amazon Neptune

## Conceito

O Amazon Neptune é um serviço de banco de dados de grafos totalmente gerenciado, otimizado para armazenar e consultar relacionamentos altamente conectados. Ele suporta os principais modelos de grafos, como Property Graph (TinkerPop/Gremlin) e RDF (SPARQL), permitindo criar aplicações como redes sociais, detecção de fraudes, gerenciamento de conhecimento e recomendações.

### Características Principais

1. **Modelos de Grafos**
   - Suporte a Property Graph (TinkerPop/Gremlin)
   - Suporte a RDF (SPARQL)

2. **Desempenho e Escalabilidade**
   - Consultas de grafos de baixa latência
   - Suporte a milhões de relacionamentos e nós
   - Escalabilidade vertical e horizontal de leitura

3. **Alta Disponibilidade e Durabilidade**
   - Replicação Multi-AZ
   - Failover automático em segundos
   - Backups automáticos e snapshots manuais

4. **Segurança**
   - Integração com VPC, IAM e KMS
   - Criptografia em trânsito e em repouso

5. **Gerenciamento Automatizado**
   - Monitoramento via Amazon CloudWatch
   - Atualizações automáticas de software

## Para que é usado

### Casos de Uso Comuns

1. **Redes Sociais**
   - ✅ Modelagem de conexões e interações entre usuários

2. **Detecção de Fraudes**
   - ✅ Análise de padrões e relacionamentos suspeitos

3. **Recomendações**
   - ✅ Sistemas de recomendação baseados em grafos

4. **Gerenciamento de Conhecimento**
   - ✅ Ontologias, taxonomias e redes semânticas

5. **Supply Chain e IoT**
   - ✅ Rastreamento de ativos e dependências complexas

## Vantagens

### Técnicas
- ✅ **Consultas de grafos** otimizadas e de baixa latência
- ✅ **Alta disponibilidade** Multi-AZ
- ✅ **Backups** automáticos e restauração point-in-time
- ✅ **Escalabilidade** de leitura com réplicas

### Operacionais
- ✅ **Gerenciamento** simplificado
- ✅ **Monitoramento** nativo (CloudWatch)
- ✅ **Automação** de tarefas administrativas

### Econômicas
- ✅ **Pay-as-you-go**
- ✅ **Redução** de custos operacionais
- ✅ **Sem** investimento inicial

## Desvantagens

### Técnicas
- ❌ **Não relacional** (apenas grafos)
- ❌ **Limitações** de customização do SO
- ❌ **Acesso restrito** ao sistema operacional

### Operacionais
- ❌ **Dependência** do provedor AWS
- ❌ **Migração** de bancos legados pode exigir reestruturação

### Econômicas
- ❌ **Custos** adicionais para alta disponibilidade
- ❌ **Cobrança** por recursos provisionados

## Boas práticas

### Nomenclatura
- ✅ **Identificação** por ambiente (dev, prod)
- ✅ **Padrão** de nomes para clusters e instâncias

### Segurança
- ✅ **Acesso restrito** via VPC e Security Groups
- ✅ **Criptografia** ativada (em trânsito e em repouso)
- ✅ **Backups** regulares

### Custo
- ✅ **Monitoramento** de uso e dimensionamento
- ✅ **Revisão** periódica de clusters e storage

## Exemplo prático

```bash
# Criar cluster Neptune
aws neptune create-db-cluster \
    --db-cluster-identifier meu-neptune-cluster \
    --engine neptune \
    --vpc-security-group-ids sg-12345678

# Criar instância no cluster Neptune
aws neptune create-db-instance \
    --db-instance-identifier meu-neptune-instancia \
    --db-cluster-identifier meu-neptune-cluster \
    --db-instance-class db.r5.large
```

## Configurações Importantes

### Backup e Restauração
- Backups automáticos contínuos
- Snapshots manuais
- Restauração point-in-time

### Alta Disponibilidade
- Multi-AZ com failover automático
- Réplicas de leitura para escalabilidade

### Segurança
- Criptografia (KMS)
- Controle de acesso (IAM, VPC, Security Groups)

### Performance
- Auto Scaling de réplicas de leitura
- Monitoramento de métricas (CloudWatch)
- Ajuste de parâmetros via Parameter Groups

## Considerações Importantes

1. **Modelagem de Grafos**
   - Escolha entre Property Graph (Gremlin) ou RDF (SPARQL)
   - Planeje índices e consultas para performance

2. **Segurança**
   - Acesso restrito à VPC
   - Criptografia e auditoria

3. **Backup**
   - Políticas de retenção
   - Testes de restauração

4. **Escalabilidade**
   - Dimensionamento automático de réplicas
   - Monitoramento de performance

---

## Arquitetura Amazon Neptune
![Arquitetura Amazon Neptune](/images/Arquitetura%20Neptune.png)

---

## Gerenciamento de Backup Neptune
![Gerenciamento de Backup Neptune](/images/Backup%20Neptune.png)

---

## Integração com Serviços AWS
![Integração Neptune AWS](/images/Integracao%20Neptune%20AWS.png)

---

## Configuração típica
![Configuração típica Neptune](/images/Configuracao%20tipica%20Neptune.png)

---