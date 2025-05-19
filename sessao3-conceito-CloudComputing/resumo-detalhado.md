## Botão Voltar ao Início
[⬆️ Voltar ao Início](/README.md)

---

# Tipos de Cloud Computing com Exemplos

## Diagrama Interativo (Mermaid)

```mermaid
graph TD
    A[Cloud Computing] --> B[Modelo de Implantação]
    A --> C[Modelo de Serviço]
    
    %% Modelos de Implantação
    B --> B1[Nuvem Pública<br>👉 AWS<br>👉 Azure<br>👉 Google Cloud]
    B --> B2[Nuvem Privada<br>👉 Data Center Local<br>👉 VMware]
    B --> B3[Nuvem Híbrida<br>👉 AWS + On-Premises]
    
    %% Modelos de Serviço
    C --> C1[IaaS<br>👉 EC2 (AWS)<br>👉 Máquinas Virtuais (Azure)]
    C --> C2[PaaS<br>👉 Elastic Beanstalk (AWS)<br>👉 App Service (Azure)]
    C --> C3[SaaS<br>👉 Gmail<br>👉 Netflix]
```

> **Observação:** O diagrama acima funciona em plataformas como GitHub, GitLab e VS Code (com extensão Mermaid).

---

## Versão Textual (ASCII)

```text
+-------------------------------------------------------------------------+
|                   TIPOS DE CLOUD COMPUTING                              |
+-----------------------------+-------------------------------------------+
|  MODELO DE IMPLANTAÇÃO      |  MODELO DE SERVIÇO                        |
+-----------------------------+-------------------------------------------+
|  ⛅ NUVEM PÚBLICA           |  🖥️ IaaS (Infraestrutura como Serviço)   |
|  ▪ AWS                      |  ▪ EC2 (AWS)                              |
|  ▪ Azure                    |  ▪ Máquinas Virtuais (Azure)              |
|  ▪ Google Cloud             |                                           |
|                             |                                           |
|  🔒 NUVEM PRIVADA           |  🛠️ PaaS (Plataforma como Serviço)       |
|  ▪ Data Center Local        |  ▪ Elastic Beanstalk (AWS)                |
|  ▪ VMware                   |  ▪ App Service (Azure)                    |
|                             |                                           |
|  🌐 NUVEM HÍBRIDA           |  📱 SaaS (Software como Serviço)         |
|  ▪ AWS + On-Premises        |  ▪ Gmail                                  |
|                             |  ▪ Netflix                                |
+-----------------------------+-------------------------------------------+
```

---

## Como Usar Este Arquivo
1. **Para Mermaid**:
   - Copie o código entre ```mermaid``` e cole em qualquer editor Markdown compatível.
   - Plataformas suportadas: GitHub, GitLab, VS Code (com extensão Mermaid).

2. **Para Versão ASCII**:
   - Copie o bloco de texto e use em e-mails, fóruns ou documentos simples.

3. **Gerar Imagem PNG**:
   - Acesse [Mermaid Live Editor](https://mermaid.live), cole o código Mermaid e exporte como imagem.

---

## Recursos Úteis
- [Documentação AWS sobre Cloud Computing](https://aws.amazon.com/pt/what-is-cloud-computing/)
- [Mermaid.js Official Docs](https://mermaid.js.org/)