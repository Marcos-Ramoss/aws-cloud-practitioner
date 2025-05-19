# AWS Organizations – Conceito Completo

## Conceito

O **AWS Organizations** é um serviço da AWS que permite **gerenciar múltiplas contas da AWS de forma centralizada**. Ele possibilita a criação de **uma hierarquia de contas**, chamadas de **organização**, com uma **conta principal (mestre)** que controla outras **contas-membro**.

Por meio da AWS Organizations, é possível:
- Criar novas contas AWS programaticamente.
- Agrupar contas em **unidades organizacionais (OUs)**.
- Aplicar **políticas centralizadas** (como Service Control Policies – SCPs).
- Consolidar o faturamento (billing) entre contas.

## Para que é usado

- ✅ **Gerenciar múltiplas contas AWS** em grandes organizações ou ambientes complexos.
- ✅ **Isolar ambientes** (produção, desenvolvimento, testes, segurança, faturamento).
- ✅ **Aplicar políticas de segurança e controle de forma centralizada**, como restrições de serviços ou regiões.
- ✅ **Consolidar custos e relatórios de faturamento** entre contas.
- ✅ **Delegar a responsabilidade de contas específicas** a diferentes equipes ou departamentos, mantendo o controle geral.

## Exemplo prático

Uma empresa de tecnologia organiza suas contas AWS da seguinte forma:

- Conta principal (root): controle e faturamento.
- Conta 1: Desenvolvimento.
- Conta 2: Produção.
- Conta 3: Segurança.
- Conta 4: Análise de dados.

Cada conta é colocada em uma **Unidade Organizacional (OU)** como `Desenvolvimento` ou `Produção`, e a equipe de segurança aplica **políticas SCP** para limitar ações (por exemplo, impedir que desenvolvedores criem instâncias EC2 em regiões não aprovadas).

## Vantagens

- ✅ **Gerenciamento centralizado de contas**: Criação, organização e controle de múltiplas contas de um só lugar.
- ✅ **Segurança aprimorada**: Uso de SCPs para aplicar restrições de serviços, regiões e permissões.
- ✅ **Isolamento de ambientes**: Reduz risco de falhas ou erros afetarem toda a organização.
- ✅ **Conformidade e governança**: Facilita aplicação de normas e políticas de segurança.
- ✅ **Consolidação de faturamento**: Visualização e gestão de custos de todas as contas em uma só fatura.
- ✅ **Delegação controlada**: Equipes têm autonomia em suas contas, mas dentro dos limites definidos pela organização.

## Desvantagens

- ❌ **Curva de aprendizado inicial**: Entender SCPs, hierarquias de OUs e gerenciamento pode ser complexo no começo.
- ❌ **Gerenciamento adicional**: Requer políticas e estrutura bem definidas para evitar conflitos e má administração.
- ❌ **Risco de bloqueio acidental**: SCPs mal configuradas podem limitar recursos essenciais ou causar interrupções.
- ❌ **Dependência da conta principal**: A conta de gerenciamento tem controle central; sua segurança deve ser prioridade máxima.

## Boas práticas

- ✅ **Separar ambientes por contas** (ex: dev, prod, segurança).
- ✅ **Usar Unidades Organizacionais (OUs)** para refletir a estrutura da empresa.
- ✅ **Aplicar SCPs com o princípio do menor privilégio**, validando cuidadosamente antes da aplicação.
- ✅ **Habilitar faturamento consolidado** para monitorar gastos e gerar relatórios por conta.
- ✅ **Proteger a conta principal com MFA e acesso restrito**.
- ✅ **Automatizar a criação e configuração de novas contas** com o AWS Control Tower.

---

## Arquitetura Básica de uma Organização

![Arquitetura Básica de uma Organização](/images/Arquitetura%20Básica%20de%20uma%20Organização.png)

---

## Fluxo de Criação de Conta
![Fluxo de Criação de Conta](/images/Fluxo%20de%20Criação%20de%20Conta.png)

---

##  Estrutura Organizacional Típica
![Estrutura Organizacional Típica](/images/Estrutura%20Organizacional%20Típica.png)



