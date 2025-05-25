## Botão Voltar ao Início
[⬆️ Voltar ao Início](https://github.com/Marcos-Ramoss/aws-cloud-practitioner)

---

# Amazon CloudFront

## Conceito

O Amazon CloudFront é um serviço de Content Delivery Network (CDN) gerenciado pela AWS, projetado para distribuir conteúdo (sites, APIs, vídeos, dados, etc.) globalmente com baixa latência e alta performance. Ele utiliza uma rede de pontos de presença (edge locations) para entregar conteúdo de forma rápida e segura aos usuários finais.

### Características Principais

1. **Distribuição Global**
   - Rede de edge locations em todo o mundo
   - Entrega de conteúdo estático e dinâmico

2. **Baixa Latência e Alta Performance**
   - Cache em edge locations para reduzir tempo de resposta
   - Otimização automática de rotas

3. **Segurança**
   - Integração com AWS Shield, WAF e ACM (SSL/TLS)
   - Suporte a autenticação, restrição de acesso e logs detalhados

4. **Personalização e Integração**
   - Suporte a Lambda@Edge para customização de requisições/respostas
   - Integração com S3, EC2, ELB, API Gateway, Media Services, etc.

5. **Escalabilidade e Disponibilidade**
   - Escalabilidade automática para grandes volumes de tráfego
   - Alta disponibilidade global

## Para que é usado

### Casos de Uso Comuns

1. **Distribuição de Sites e Aplicações Web**
   - ✅ Sites estáticos e dinâmicos
   - ✅ APIs e aplicações serverless

2. **Streaming de Vídeo e Mídia**
   - ✅ Vídeo sob demanda (VoD) e ao vivo
   - ✅ Otimização de entrega de mídia

3. **Segurança e Proteção**
   - ✅ Proteção contra DDoS (AWS Shield)
   - ✅ Controle de acesso e autenticação

4. **Aceleração de Downloads**
   - ✅ Distribuição de arquivos grandes e atualizações de software

## Vantagens

### Técnicas
- ✅ **Baixa latência** e alta performance global
- ✅ **Escalabilidade** automática
- ✅ **Segurança** integrada (WAF, Shield, SSL/TLS)

### Operacionais
- ✅ **Gerenciamento** simplificado
- ✅ **Monitoramento** e logs detalhados
- ✅ **Automação** via AWS CLI, SDK e CloudFormation

### Econômicas
- ✅ **Pay-as-you-go**
- ✅ **Redução** de custos de infraestrutura própria de CDN

## Desvantagens

### Técnicas
- ❌ **Curva de aprendizado** para configurações avançadas
- ❌ **Limitações** em integrações com CDNs externas

### Operacionais
- ❌ **Gerenciamento** de múltiplas distribuições pode ser complexo

### Econômicas
- ❌ **Custos** por transferência de dados e requisições

## Boas práticas

### Nomenclatura
- ✅ **Padronização** de nomes de distribuições
- ✅ **Documentação** das configurações e origens

### Segurança
- ✅ **Uso de HTTPS/SSL** para todo o tráfego
- ✅ **Configuração de WAF e Shield**
- ✅ **Restrição de acesso por geolocalização ou autenticação

### Custo
- ✅ **Monitoramento** de uso e transferências
- ✅ **Revisão** periódica de distribuições e regras de cache

## Exemplo prático

```powershell
# Criar uma distribuição CloudFront para S3
aws cloudfront create-distribution `
    --origin-domain-name meu-bucket.s3.amazonaws.com

# Invalidate cache de um arquivo
aws cloudfront create-invalidation `
    --distribution-id E1234567890 `
    --paths /index.html
```

## Configurações Importantes

### Origens
- S3, EC2, ELB, API Gateway, Media Services, endpoints customizados

### Políticas de Cache
- TTL, regras de cache, invalidations
- Compressão automática de conteúdo

### Segurança
- HTTPS/SSL, WAF, Shield, autenticação
- Logs detalhados e monitoramento

## Considerações Importantes

1. **Planejamento de Origens e Caching**
   - Definir origens e regras de cache adequadas

2. **Segurança**
   - Habilitar HTTPS e proteção contra DDoS

3. **Custo**
   - Monitorar transferências e requisições

4. **Gerenciamento**
   - Documentar distribuições e configurações
   - Automatizar via CloudFormation ou Terraform

---

## Arquitetura Amazon CloudFront
![Arquitetura Amazon CloudFront](/images/Arquitetura%20CloudFront.png)

---

## Exemplo de Distribuição CloudFront
![Exemplo de Distribuição CloudFront](/images/Exemplo%20CloudFront.png)

---

## Integração com Serviços AWS
![Integração CloudFront AWS](/images/Integracao%20CloudFront%20AWS.png)

---

## Configuração típica
![Configuração típica CloudFront](/images/Configuracao%20tipica%20CloudFront.png)

---
