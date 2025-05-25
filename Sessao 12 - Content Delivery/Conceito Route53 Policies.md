## Botão Voltar ao Início
[⬆️ Voltar ao Início](https://github.com/Marcos-Ramoss/aws-cloud-practitioner)

---

# Políticas de Roteamento do Amazon Route 53

## Conceito

O Amazon Route 53 oferece diversas políticas de roteamento para controlar como as requisições DNS são direcionadas para diferentes recursos, proporcionando alta disponibilidade, performance e resiliência. Cada política atende a cenários específicos de balanceamento de carga, failover, geolocalização e otimização de tráfego.

### Tipos de Políticas de Roteamento

1. **Simple Routing (Simples)**
   - Retorna um único valor para cada consulta DNS.
   - Usado para aplicações simples sem requisitos de failover ou balanceamento.

2. **Weighted Routing (Ponderado)**
   - Distribui o tráfego entre múltiplos recursos com base em pesos atribuídos.
   - Útil para balanceamento de carga e testes A/B.

3. **Latency Routing (Latência)**
   - Direciona o tráfego para o recurso com menor latência para o usuário.
   - Ideal para aplicações globais que exigem baixa latência.

4. **Failover Routing (Failover)**
   - Suporta alta disponibilidade direcionando tráfego para recursos primários e, em caso de falha, para recursos de backup.
   - Requer configuração de health checks.

5. **Geolocation Routing (Geolocalização)**
   - Direciona o tráfego com base na localização geográfica do usuário (país, continente ou estado).
   - Útil para conformidade, localização de conteúdo e restrições regionais.

6. **Geoproximity Routing (Geoproximidade)**
   - Direciona o tráfego com base na proximidade do usuário a recursos definidos, podendo ajustar a influência de cada recurso.
   - Requer uso do Route 53 Traffic Flow.

7. **Multi-Value Answer Routing (Resposta Multi-Valor)**
   - Retorna múltiplos valores (até oito) para cada consulta DNS, ajudando no balanceamento e resiliência.
   - Pode ser usado com health checks para remover endpoints não saudáveis.

## Para que é usado

- ✅ Balanceamento de carga global
- ✅ Alta disponibilidade e failover automático
- ✅ Otimização de performance por latência
- ✅ Direcionamento de tráfego por região ou proximidade
- ✅ Testes A/B e deploys graduais

## Exemplo prático

```powershell
# Exemplo de registro ponderado (Weighted Routing)
aws route53 change-resource-record-sets `
    --hosted-zone-id ZONEID `
    --change-batch '{"Changes":[{"Action":"CREATE","ResourceRecordSet":{"Name":"www.exemplo.com","Type":"A","SetIdentifier":"Servidor1","Weight":70,"TTL":300,"ResourceRecords":[{"Value":"192.0.2.1"}]}}]}'
```

## Boas práticas
- Documentar a política usada para cada registro
- Usar health checks para failover e multi-value
- Monitorar consultas e performance
- Revisar periodicamente as políticas e necessidades do negócio

## Considerações Importantes
- Algumas políticas exigem configuração adicional (ex: health checks, Traffic Flow)
- Custos podem variar conforme o uso de políticas avançadas
- Planejar para crescimento e mudanças de topologia

---

## Exemplo de Políticas de Roteamento
![Exemplo de Políticas Route53](/images/Politicas%20Route53.png)

---

## Integração com Serviços AWS
![Integração Route53 AWS](/images/Integracao%20Route53%20AWS.png)

---

## Configuração típica
![Configuração típica Route53](/images/Configuracao%20tipica%20Route53.png)

---
