## Botão Voltar ao Início
[⬆️ Voltar ao Início](https://github.com/Marcos-Ramoss/aws-cloud-practitioner)

---

# Docker na AWS

## Conceito

Docker é uma plataforma de containers que permite empacotar, distribuir e executar aplicações de forma isolada e portátil. Na AWS, Docker é amplamente utilizado para criar ambientes consistentes, facilitar o deploy e escalar aplicações em serviços como Amazon ECS, EKS, Fargate e EC2.

### Características Principais

1. **Portabilidade**
   - Containers Docker rodam em qualquer ambiente compatível
   - Imagens podem ser armazenadas no Amazon ECR (Elastic Container Registry)

2. **Isolamento e Consistência**
   - Cada container executa de forma isolada
   - Facilita CI/CD e testes automatizados

3. **Integração com AWS**
   - Suporte nativo em ECS, EKS, Fargate e EC2
   - Deploy automatizado e escalável

4. **Gerenciamento de Imagens**
   - Armazenamento seguro no Amazon ECR
   - Versionamento e controle de acesso

## Para que é usado

### Casos de Uso Comuns

1. **Microserviços**
   - ✅ Deploy de aplicações desacopladas
   - ✅ Escalabilidade independente de componentes

2. **CI/CD e Testes**
   - ✅ Ambientes de build e teste consistentes
   - ✅ Automação de pipelines

3. **Migração e Modernização**
   - ✅ Lift-and-shift de aplicações legadas
   - ✅ Modernização para arquitetura de containers

4. **Data Science e Machine Learning**
   - ✅ Ambientes reprodutíveis para notebooks e jobs

## Vantagens

### Técnicas
- ✅ **Portabilidade** entre ambientes
- ✅ **Isolamento** de aplicações
- ✅ **Escalabilidade** automática com ECS/EKS/Fargate
- ✅ **Gerenciamento** centralizado de imagens (ECR)

### Operacionais
- ✅ **Automação** de deploys e rollbacks
- ✅ **Redução** de conflitos de dependências
- ✅ **Facilidade** de atualização e rollback

### Econômicas
- ✅ **Otimização** de recursos
- ✅ **Pay-as-you-go** nos serviços AWS

## Desvantagens

### Técnicas
- ❌ **Curva de aprendizado** para orquestração
- ❌ **Gerenciamento** de redes e storage pode ser complexo

### Operacionais
- ❌ **Monitoramento** e logging exigem configuração
- ❌ **Gerenciamento** de múltiplos containers pode ser desafiador

### Econômicas
- ❌ **Custos** podem aumentar com má configuração de escalabilidade

## Boas práticas

### Nomenclatura
- ✅ **Padronização** de nomes de imagens e containers
- ✅ **Documentação** de versões e pipelines

### Segurança
- ✅ **Uso de imagens oficiais e atualizadas**
- ✅ **Controle de acesso** no ECR
- ✅ **Scan de vulnerabilidades** em imagens

### Custo
- ✅ **Monitoramento** de uso e escalabilidade
- ✅ **Revisão** periódica de imagens e containers

## Exemplo prático

```powershell
# Build de uma imagem Docker
docker build -t minha-app:latest .

# Login no Amazon ECR
aws ecr get-login-password --region us-east-1 | docker login --username AWS --password-stdin 123456789012.dkr.ecr.us-east-1.amazonaws.com

# Push da imagem para o ECR
docker tag minha-app:latest 123456789012.dkr.ecr.us-east-1.amazonaws.com/minha-app:latest
docker push 123456789012.dkr.ecr.us-east-1.amazonaws.com/minha-app:latest

# Deploy no ECS usando a imagem do ECR
# (Exemplo simplificado, normalmente feito via console, CLI ou CloudFormation)
```

## Configurações Importantes

### Amazon ECR
- Armazenamento seguro e versionado de imagens
- Controle de acesso via IAM

### Amazon ECS/EKS/Fargate
- Orquestração e escalabilidade automática
- Deploy simplificado de containers

### Segurança
- Scan automático de vulnerabilidades (ECR)
- Políticas de acesso restritivas

## Considerações Importantes

1. **Gerenciamento de Imagens**
   - Manter imagens enxutas e atualizadas
   - Automatizar build e scan

2. **Orquestração**
   - Usar ECS, EKS ou Fargate para produção
   - Planejar escalabilidade e alta disponibilidade

3. **Custo**
   - Monitorar uso de recursos e escalabilidade
   - Revisar imagens e containers não utilizados

---

## Arquitetura Docker na AWS
![Arquitetura Docker AWS](/images/Arquitetura%20Docker%20AWS.png)

---

## Exemplo de Pipeline CI/CD com Docker
![Exemplo Pipeline Docker AWS](/images/Exemplo%20Pipeline%20Docker%20AWS.png)

---

## Integração com Serviços AWS
![Integração Docker AWS](/images/Integracao%20Docker%20AWS.png)

---

## Configuração típica
![Configuração típica Docker AWS](/images/Configuracao%20tipica%20Docker%20AWS.png)

---
