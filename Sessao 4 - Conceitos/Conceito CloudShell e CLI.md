# AWS CloudShell e AWS CLI com IAM – Conceito Completo

## Conceito

### AWS CLI (Command Line Interface)

A **AWS CLI** é uma ferramenta de linha de comando que permite interagir com os serviços da AWS por meio de comandos digitados no terminal. Ela facilita a automação e administração de recursos da AWS de forma rápida, sem precisar acessar o Console Web.

### AWS CloudShell

O **AWS CloudShell** é um **ambiente de terminal baseado em navegador**, integrado ao Console da AWS, que vem **pré-configurado com a AWS CLI**, SDKs e outras ferramentas úteis. Ele oferece um ambiente de shell seguro e conveniente **sem necessidade de instalação local**.

---

## Para que são usados

Tanto a AWS CLI quanto o CloudShell são utilizados para:

- ✅ **Executar comandos relacionados a IAM**, como criar usuários, grupos, políticas, funções e permissões.
- ✅ **Automatizar tarefas administrativas**, como rotação de credenciais, aplicação de políticas ou consulta de permissões.
- ✅ **Gerenciar recursos da AWS por meio de scripts e infraestrutura como código**.
- ✅ **Fazer troubleshooting e inspeção de permissões diretamente via terminal**.
- ✅ **Ambientes sem acesso local a ferramentas de CLI (no caso do CloudShell)**.

---

## Vantagens

### AWS CLI
- ✅ Automação total de tarefas administrativas.
- ✅ Integração com scripts e pipelines DevOps.
- ✅ Controle granular e completo sobre todos os serviços da AWS.
- ✅ Disponível em múltiplas plataformas (Linux, macOS, Windows).

### AWS CloudShell
- ✅ Sem necessidade de instalação – já vem configurado com CLI, SDKs e ferramentas.
- ✅ Ambiente seguro e baseado em navegador.
- ✅ Persistência de arquivos temporários por sessão.
- ✅ Acesso imediato aos recursos da conta com permissões do usuário logado no Console.
- ✅ Ideal para administradores e auditores que não podem configurar ferramentas localmente.

---

## Desvantagens

### AWS CLI
- ❌ Requer configuração inicial (instalação e setup de credenciais).
- ❌ Dependência do ambiente local (compatibilidade, atualizações).
- ❌ Possíveis erros críticos se comandos forem mal utilizados (ex: revogar permissões indevidamente).

### AWS CloudShell
- ❌ Armazenamento de arquivos é temporário (limite de 1 GB por região).
- ❌ Limitações de tempo de inatividade e sessão.
- ❌ Desempenho limitado comparado a shells locais.
- ❌ Não disponível em todas as regiões da AWS.

---

## Exemplo de uso com IAM

```bash
# Criar um novo usuário IAM com AWS CLI
aws iam create-user --user-name novo_usuario

# Anexar uma política gerenciada ao usuário
aws iam attach-user-policy \
  --user-name novo_usuario \
  --policy-arn arn:aws:iam::aws:policy/AmazonS3ReadOnlyAccess
```
---

## Arquitetura Basica CLI e CloudShell 

![Arquitetura Basica CLI CloudShell](/images/ArquiteturaBasicaCLI.png)

---

## Fluxo de Autenticação
![Fluxo de Autenticação](/images/Fluxo%20de%20Autenticação%20CLI.png)

---

## Comandos
![Comandos](/images/comandosCLI.png)
