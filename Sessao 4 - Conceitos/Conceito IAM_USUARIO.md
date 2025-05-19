## Botão Voltar ao Início
[⬆️ Voltar ao Início](https://github.com/Marcos-Ramoss/aws-cloud-practitioner)

---

# Usuários no IAM da AWS

## Conceito

Na AWS, um **usuário IAM (Identity and Access Management)** representa **uma entidade individual** — geralmente uma pessoa ou um aplicativo — que precisa de acesso aos recursos da AWS. Cada usuário possui **credenciais únicas**, como:
- Nome de usuário e senha (para acesso ao Console da AWS),
- Chaves de acesso (para chamadas de API, SDK ou CLI),
- Possivelmente autenticação multifator (MFA).

Ao criar um usuário IAM, você pode **definir permissões específicas** diretamente nele ou por meio de grupos e políticas.

## Para que é usado

Usuários IAM são utilizados para:
- **Permitir o acesso seguro de pessoas reais à AWS**, sem compartilhar a conta root.
- **Controlar acessos com base em permissões granulares** (ex: permitir que um usuário só visualize instâncias EC2).
- **Atribuir credenciais seguras e auditáveis** para administradores, desenvolvedores, analistas, entre outros.
- **Fornecer autenticação para aplicações** (em casos onde roles IAM não são aplicáveis ou desejados).

## Exemplo prático

Você pode criar um usuário chamado `ana.engenheira` e atribuir a ele:
- Acesso ao Console da AWS com senha e MFA,
- Permissão de leitura e gravação no Amazon S3,
- Acesso de visualização no CloudWatch Logs.

Esse usuário pode ser adicionado a um grupo `Engenharia` ou receber políticas diretamente.

## Vantagens

- ✅ **Isolamento e controle de acesso individualizado**: Cada usuário tem permissões e credenciais separadas.
- ✅ **Auditoria e rastreabilidade**: Você pode monitorar quem fez o quê através do AWS CloudTrail.
- ✅ **Segurança**: Não é necessário compartilhar a conta root ou senhas entre pessoas.
- ✅ **Permite autenticação multifator (MFA)** para maior proteção.
- ✅ **Gerenciamento flexível**: Permissões podem ser atribuídas diretamente ou via grupos.

## Desvantagens

- ❌ **Gerenciamento complexo em grande escala**: Manter permissões individuais para muitos usuários pode se tornar difícil sem grupos ou automações.
- ❌ **Maior risco com credenciais permanentes**: Chaves de acesso não rotacionadas podem se tornar vetores de ataque se comprometidas.
- ❌ **Não deve ser usado para aplicações em produção**: O uso de **roles IAM** é mais indicado para serviços e aplicações.

## Boas práticas

- ✅ **Nunca use a conta root para tarefas diárias** — crie usuários IAM com permissões específicas.
- ✅ **Habilite MFA** para todos os usuários com acesso ao Console.
- ✅ **Use grupos IAM** para facilitar o gerenciamento de permissões em vez de atribuições diretas.
- ✅ **Rotacione regularmente as credenciais** (senhas e chaves de acesso).
- ✅ **Monitore ações dos usuários** com ferramentas como AWS CloudTrail.
- ✅ **Revise permissões periodicamente** para manter o princípio do privilégio mínimo.

---


##  Anatomia de um Usuário IAM
![ Anatomia de um Usuário IAM](/images/Anatomia%20de%20um%20Usuário%20IAM.png)

---

##  Ciclo de Vida do Usuário
![Ciclo de Vida do Usuário](/images/Ciclo%20de%20Vida%20do%20Usuário.png)

---

## 🏗️ Arquitetura Recomendada
![Arquitetura Recomendada](/images/Arquitetura%20Recomendada%20usuario.png)


---

## 📌 Boas Práticas Essenciais
![boas Práticas Essenciais](/images/oas%20Práticas%20Essenciais.png)

---

## ⚠️ Padrões Perigosos
![Padrões Perigosos](/images/Padrões%20Perigosos.png)

