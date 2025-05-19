# Amazon EC2 (Elastic Compute Cloud)

## Conceito

O **Amazon EC2** é um serviço web que fornece capacidade computacional redimensionável na nuvem. É uma parte fundamental da infraestrutura da AWS, permitindo que você execute aplicações em servidores virtuais (instâncias) com total controle sobre a configuração.

## Principais características do EC2

   - **Elasticidade**: Escala conforme a demanda (aumenta ou diminui capacidade)
   - **Variedade de instâncias**: Otimizadas para computação, memória, GPU, armazenamento, etc.
   - **Modelos de cobrança**: Sob demanda, Reserved Instances, Spot Instances, Savings Plans
   - **Integração com outros serviços AWS**:  VPC, EBS, S3, RDS, Lambda, etc.
   - **Personalização**:  Escolha de SO (Linux, Windows, macOS), configurações de rede e segurança

### Entendendo o EC2 em Detalhes

1. **Tipos de Instâncias**
   - **Uso Geral (t3, m5)**: Balanceamento entre computação, memória e rede
   - **Computação Otimizada (c5)**: Alto desempenho de CPU
   - **Memória Otimizada (r5)**: Alto desempenho de memória
   - **Armazenamento Otimizado (i3)**: Alto desempenho de I/O
   - **GPU (g4)**: Processamento gráfico acelerado
   - **Inferência (inf1)**: Machine Learning

2. **Componentes Principais**
   - **AMI (Amazon Machine Image)**: Template para instâncias
   - **EBS (Elastic Block Store)**: Armazenamento persistente
   - **Security Groups**: Firewall virtual
   - **Key Pairs**: Autenticação SSH
   - **Elastic IP**: Endereço IP estático

3. **Modelos de Preço**
   - **On-Demand**: Pagamento por hora
   - **Reserved**: Desconto por compromisso
   - **Spot**: Preços variáveis
   - **Dedicated Hosts**: Hardware dedicado

## Para que é usado

### Casos de Uso Comuns

1. **Aplicações Web**
   - ✅ **Sites** e aplicações web
   - ✅ **APIs** e microserviços
   - ✅ **Load balancing**
   - ✅ **Auto-scaling**
   - ✅ **High availability**

2. **Desenvolvimento e Testes**
   - ✅ **Ambientes** de desenvolvimento
   - ✅ **Testes** de carga
   - ✅ **CI/CD** pipelines
   - ✅ **Staging** environments
   - ✅ **Prototipagem** rápida

3. **Processamento de Dados**
   - ✅ **Batch processing**
   - ✅ **Data analysis**
   - ✅ **Machine Learning**
   - ✅ **Big Data**
   - ✅ **ETL** processes

4. **Serviços Corporativos**
   - ✅ **Active Directory**
   - ✅ **File servers**
   - ✅ **Database servers**
   - ✅ **Application servers**
   - ✅ **Monitoring systems**

### Exemplos por Indústria

#### E-commerce
- ✅ **Web servers**
- ✅ **Application servers**
- ✅ **Database servers**
- ✅ **Cache servers**
- ✅ **Load balancers**

#### Fintech
- ✅ **Trading platforms**
- ✅ **Risk analysis**
- ✅ **Fraud detection**
- ✅ **Payment processing**
- ✅ **Compliance systems**

#### Saúde
- ✅ **Medical imaging**
- ✅ **Patient records**
- ✅ **Research computing**
- ✅ **Analytics**
- ✅ **Compliance systems**

## Vantagens

### Técnicas
- ✅ **Elasticidade** e escalabilidade
- ✅ **Alta disponibilidade**
- ✅ **Diversidade** de tipos de instância
- ✅ **Integração** com outros serviços AWS
- ✅ **Flexibilidade** de configuração

### Operacionais
- ✅ **Controle** total sobre instâncias
- ✅ **Monitoramento** detalhado
- ✅ **Backup** e recuperação
- ✅ **Segurança** avançada
- ✅ **Automação** de tarefas

### Econômicas
- ✅ **Pay-as-you-go**
- ✅ **Otimização** de custos
- ✅ **Reserved instances**
- ✅ **Spot instances**
- ✅ **Elasticidade** de recursos

## Desvantagens

### Técnicas
- ❌ **Complexidade** de gerenciamento
- ❌ **Curva de aprendizado**
- ❌ **Responsabilidade** de patches
- ❌ **Configuração** manual
- ❌ **Monitoramento** necessário

### Operacionais
- ❌ **Gestão** de segurança
- ❌ **Manutenção** de instâncias
- ❌ **Backup** e DR
- ❌ **Compliance**
- ❌ **Documentação**

### Econômicas
- ❌ **Custos** imprevisíveis
- ❌ **Otimização** necessária
- ❌ **Reserved instances** commitment
- ❌ **Data transfer** costs
- ❌ **Storage** costs

## Boas práticas

### Segurança
- ✅ **Use security groups** adequadamente
- ✅ **Implemente IAM roles**
- ✅ **Enable encryption**
- ✅ **Regular patches**
- ✅ **Monitor access**

### Performance
- ✅ **Choose right** instance type
- ✅ **Use EBS optimized**
- ✅ **Implement caching**
- ✅ **Monitor metrics**
- ✅ **Auto-scaling**

### Custo
- ✅ **Use reserved instances**
- ✅ **Implement auto-scaling**
- ✅ **Monitor usage**
- ✅ **Clean up** unused resources
- ✅ **Use spot instances**

## Exemplo prático

```bash
# Criar uma instância EC2
aws ec2 run-instances \
    --image-id ami-0c55b159cbfafe1f0 \
    --count 1 \
    --instance-type t2.micro \
    --key-name MyKeyPair \
    --security-group-ids sg-xxxxxxxx \
    --subnet-id subnet-xxxxxxxx

# Configurar auto-scaling
aws autoscaling create-auto-scaling-group \
    --auto-scaling-group-name my-asg \
    --launch-configuration-name my-launch-config \
    --min-size 1 \
    --max-size 3 \
    --desired-capacity 2 \
    --vpc-zone-identifier "subnet-xxxxxxxx,subnet-yyyyyyyy"

# Configurar load balancer
aws elbv2 create-load-balancer \
    --name my-load-balancer \
    --subnets subnet-xxxxxxxx subnet-yyyyyyyy \
    --security-groups sg-xxxxxxxx
```

---

## Arquitetura Básica do EC2
![Arquitetura Básica do EC2](/images/Arquitetura%20Básica%20do%20EC2.png)

---

## Comparativo EC2 vs Serviços Gerenciados
![Comparativo EC2 vs Serviços Gerenciados](/images/Comparativo%20EC2%20vs%20Serviços%20Gerenciados.png)

