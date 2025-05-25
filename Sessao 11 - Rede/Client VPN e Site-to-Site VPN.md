## Botão Voltar ao Início
[⬆️ Voltar ao Início](https://github.com/Marcos-Ramoss/aws-cloud-practitioner)

---

# VPN na AWS: Client VPN e Site-to-Site VPN

## Conceito

A AWS oferece dois principais tipos de VPN para conectar redes locais ou dispositivos remotos à nuvem AWS: **Client VPN** e **Site-to-Site VPN**. Ambas fornecem conexões seguras e criptografadas, mas atendem a cenários diferentes.

### Client VPN

O AWS Client VPN é um serviço gerenciado que permite que usuários remotos se conectem com segurança à sua VPC usando clientes OpenVPN. Ideal para acesso remoto de funcionários, home office e dispositivos móveis.

#### Características Principais
- Serviço totalmente gerenciado e escalável
- Suporte a autenticação baseada em Active Directory, certificados ou SAML
- Integração com Security Groups e políticas de acesso
- Conexão via cliente OpenVPN
- Alta disponibilidade automática

#### Casos de Uso
- ✅ Acesso remoto seguro para funcionários
- ✅ Home office e trabalho híbrido
- ✅ Conexão de dispositivos móveis à VPC

#### Exemplo prático
```powershell
# Criar endpoint Client VPN
aws ec2 create-client-vpn-endpoint `
    --client-cidr-block 10.0.0.0/22 `
    --server-certificate-arn arn:aws:acm:REGION:ACCOUNT:certificate/CERTIFICATE_ID `
    --authentication-options Type=certificate,MutualAuthentication={ClientRootCertificateChainArn=arn:aws:acm:REGION:ACCOUNT:certificate/CLIENT_CERT_ID} `
    --connection-log-options Enabled=true,CloudwatchLogGroup=LOG_GROUP,CloudwatchLogStream=LOG_STREAM
```

### Site-to-Site VPN

O AWS Site-to-Site VPN conecta sua rede local (on-premises) à AWS por meio de túneis VPN IPsec, usando gateways virtuais. Ideal para integração de data centers, filiais e ambientes híbridos.

#### Características Principais
- Conexão segura e criptografada entre redes
- Suporte a múltiplos túneis para alta disponibilidade
- Integração com AWS Transit Gateway e Virtual Private Gateway
- Suporte a BGP para roteamento dinâmico
- Monitoramento e failover automático

#### Casos de Uso
- ✅ Integração de data centers com AWS
- ✅ Conexão de filiais e escritórios remotos
- ✅ Ambientes híbridos e disaster recovery

#### Exemplo prático
```powershell
# Criar Site-to-Site VPN
aws ec2 create-vpn-connection `
    --type ipsec.1 `
    --customer-gateway-id cgw-12345678 `
    --vpn-gateway-id vgw-12345678
```

## Vantagens
- ✅ **Segurança**: criptografia ponta a ponta
- ✅ **Escalabilidade**: múltiplas conexões simultâneas
- ✅ **Alta disponibilidade**: failover automático (Site-to-Site)
- ✅ **Gerenciamento**: integração com IAM, CloudWatch e Security Groups

## Desvantagens
- ❌ **Latência**: depende da internet pública
- ❌ **Limitações** de banda comparado ao Direct Connect
- ❌ **Gerenciamento** de certificados e configurações pode ser complexo

## Boas práticas
- ✅ **Revisar** políticas de acesso e autenticação
- ✅ **Monitorar** conexões e logs
- ✅ **Automatizar** failover e testes de conectividade
- ✅ **Documentar** configurações e topologias

## Considerações Importantes
1. **Segurança**: use autenticação forte e criptografia
2. **Escalabilidade**: planeje para múltiplos usuários ou sites
3. **Custo**: monitore uso e conexões ativas
4. **Monitoramento**: integre com CloudWatch para alertas

---

## Arquitetura Client VPN AWS
![Arquitetura Client VPN AWS](/images/Arquitetura%20Client%20VPN.png)

---

## Arquitetura Site-to-Site VPN AWS
![Arquitetura Site-to-Site VPN AWS](/images/Arquitetura%20Site-to-Site%20VPN.png)

---

## Integração com Serviços AWS
![Integração VPN AWS](/images/Integracao%20VPN%20AWS.png)

---

## Configuração típica
![Configuração típica VPN](/images/Configuracao%20tipica%20VPN.png)

---
