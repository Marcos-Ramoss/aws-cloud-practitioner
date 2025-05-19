# Elastic Load Balancing (ELB) AWS

## Conceito

O Elastic Load Balancing (ELB) é um serviço da AWS que distribui automaticamente o tráfego de entrada entre múltiplos alvos, como instâncias EC2, contêineres e endereços IP, em uma ou mais zonas de disponibilidade. Ele monitora a saúde dos alvos registrados e roteia o tráfego apenas para os alvos saudáveis.

### Características Principais

1. **Tipos de Load Balancers**
   - Application Load Balancer (ALB)
   - Network Load Balancer (NLB)
   - Gateway Load Balancer (GWLB)
   - Classic Load Balancer (CLB)

2. **Funcionalidades**
   - Distribuição de carga
   - Health checks
   - SSL/TLS termination
   - Sticky sessions

3. **Monitoramento**
   - CloudWatch metrics
   - Health dashboard
   - Logs
   - Alertas

## Para que é usado

### Casos de Uso Comuns

1. **Aplicações Web**
   - ✅ Alta disponibilidade
   - ✅ Escalabilidade
   - ✅ SSL/TLS
   - ✅ Content-based routing

2. **Microserviços**
   - ✅ Path-based routing
   - ✅ Container-based routing
   - ✅ Service discovery
   - ✅ Load balancing

3. **APIs**
   - ✅ API Gateway integration
   - ✅ Rate limiting
   - ✅ SSL termination
   - ✅ Request routing

4. **Enterprise**
   - ✅ Hybrid deployments
   - ✅ Multi-region
   - ✅ Disaster recovery
   - ✅ Compliance

## Vantagens

### Técnicas
- ✅ **Alta disponibilidade**
- ✅ **Escalabilidade automática**
- ✅ **SSL/TLS termination**
- ✅ **Health checks**
- ✅ **Monitoramento integrado**

### Operacionais
- ✅ **Gerenciamento** simplificado
- ✅ **Automação** de processos
- ✅ **Monitoramento** nativo
- ✅ **Alertas** configuráveis
- ✅ **Manutenção** reduzida

### Econômicas
- ✅ **Pay-as-you-go**
- ✅ **Otimização** de custos
- ✅ **Sem** investimento inicial
- ✅ **Escalabilidade** econômica
- ✅ **Custo-benefício**

## Desvantagens

### Técnicas
- ❌ **Latência** adicional
- ❌ **Complexidade** de configuração
- ❌ **Limitações** de região
- ❌ **Dependência** de serviços
- ❌ **Custo** de processamento

### Operacionais
- ❌ **Monitoramento** necessário
- ❌ **Configuração** manual
- ❌ **Testes** de performance
- ❌ **Documentação** importante
- ❌ **Treinamento** necessário

### Econômicas
- ❌ **Custos** de processamento
- ❌ **Custos** de monitoramento
- ❌ **Custos** de rede
- ❌ **Custos** de SSL
- ❌ **Custos** de backup

## Boas práticas

### Performance
- ✅ **Monitoramento** de métricas
- ✅ **Otimização** de configuração
- ✅ **Testes** de carga
- ✅ **Documentação** de benchmarks
- ✅ **Análise** de performance

### Segurança
- ✅ **SSL/TLS** configuration
- ✅ **Security Groups**
- ✅ **WAF** integration
- ✅ **Encryption**
- ✅ **Compliance**

### Custo
- ✅ **Análise** de uso
- ✅ **Otimização** de recursos
- ✅ **Monitoramento** de custos
- ✅ **Revisão** de preços
- ✅ **Planejamento** financeiro

## Exemplo prático

```bash
# Criar Application Load Balancer
aws elbv2 create-load-balancer \
    --name my-alb \
    --subnets subnet-12345678 subnet-87654321 \
    --security-groups sg-12345678 \
    --scheme internet-facing

# Criar Target Group
aws elbv2 create-target-group \
    --name my-targets \
    --protocol HTTP \
    --port 80 \
    --vpc-id vpc-12345678 \
    --health-check-path /health \
    --health-check-interval-seconds 30

# Registrar targets
aws elbv2 register-targets \
    --target-group-arn arn:aws:elasticloadbalancing:region:123456789012:targetgroup/my-targets/1234567890123456 \
    --targets Id=i-1234567890abcdef0

# Verificar status
aws elbv2 describe-load-balancers \
    --load-balancer-arns arn:aws:elasticloadbalancing:region:123456789012:loadbalancer/app/my-alb/1234567890abcdef
```

## Tipos de Load Balancers

### Application Load Balancer (ALB)
- Layer 7
- Content-based routing
- Container support
- Lambda integration

### Network Load Balancer (NLB)
- Layer 4
- TCP/UDP/TLS
- Static IP
- High performance

### Gateway Load Balancer (GWLB)
- Layer 3
- Transparent routing
- Network appliances
- Centralized deployment

### Classic Load Balancer (CLB)
- Legacy
- EC2-Classic
- Basic features
- Migration path

## Considerações Importantes

1. **Configuração**
   - VPC
   - Security Groups
   - SSL/TLS
   - Health checks

2. **Monitoramento**
   - CloudWatch
   - Health dashboard
   - Logs
   - Alertas

3. **Segurança**
   - SSL/TLS
   - WAF
   - Security Groups
   - Encryption

4. **Integração**
   - Auto Scaling
   - Route 53
   - CloudWatch
   - WAF

---

## Elastic Load Balancing (ELB)
![Elastic Load Balancing](/images/Elastic%20Load%20Balancer%20ELB.png)

---

## Arquitetura com ALB + ASG
![Arquitetura com ALB_ASG](/images/Diagrama%20Arquitetura%20com%20ALB_ASG.png)

---