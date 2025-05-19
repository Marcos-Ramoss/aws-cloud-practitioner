## Botão Voltar ao Início
[⬆️ Voltar ao Início](https://github.com/Marcos-Ramoss/aws-cloud-practitioner)

---

# Política de Senha na AWS – Conceito Completo

## Conceito

A **Política de Senha da AWS** é um conjunto de **regras configuráveis que definem os requisitos mínimos** para as senhas de usuários IAM (Identity and Access Management). Essas regras ajudam a garantir que as senhas utilizadas para acessar a conta AWS sejam **fortes, seguras e consistentes com as práticas recomendadas de segurança**.

A política de senha é aplicada apenas aos usuários **IAM com acesso ao Console de Gerenciamento da AWS**.

## Para que é usada

- ✅ **Fortalecer a segurança de contas de usuário IAM**.
- ✅ **Impor regras obrigatórias para criação e alteração de senhas**.
- ✅ **Garantir conformidade com padrões de segurança internos ou externos (como ISO, PCI-DSS, HIPAA, etc.)**.
- ✅ **Reduzir a probabilidade de ataques de força bruta e roubo de credenciais**.
- ✅ **Definir padrões organizacionais consistentes para todas as senhas na nuvem AWS**.

## Parâmetros configuráveis

A AWS permite personalizar diversos critérios em sua política de senha, como:

- Tamanho mínimo da senha (entre 6 e 128 caracteres).
- Exigir letras maiúsculas.
- Exigir letras minúsculas.
- Exigir números.
- Exigir caracteres especiais (!@#$...).
- Exigir que senhas sejam trocadas após determinado período.
- Impedir reutilização de senhas anteriores.
- Permitir ou não que usuários alterem suas próprias senhas.
- Exigir troca de senha no primeiro login.

## Exemplo prático

Um administrador define a seguinte política de senha:
- Mínimo de 12 caracteres,
- Deve conter letras maiúsculas, minúsculas, números e caracteres especiais,
- Troca obrigatória a cada 90 dias,
- Impede reuso das últimas 5 senhas.

Todos os usuários IAM da organização devem obedecer a essa política ao criar ou atualizar suas senhas.

## Vantagens

- ✅ **Aumento da segurança**: Senhas mais fortes e complexas reduzem vulnerabilidades.
- ✅ **Conformidade com auditorias e regulamentos**.
- ✅ **Padronização**: Todos os usuários seguem o mesmo conjunto de regras.
- ✅ **Flexibilidade**: Permite personalização de acordo com as necessidades da organização.
- ✅ **Controle centralizado**: Política aplicada globalmente a todos os usuários IAM.

## Desvantagens

- ❌ **Afeta apenas usuários IAM locais**: Não se aplica a usuários federados via SSO ou Identity Center.
- ❌ **Pode gerar frustração entre usuários** se regras forem muito rigorosas.
- ❌ **Não resolve todos os problemas de segurança**: Deve ser combinada com MFA e boas práticas de acesso.
- ❌ **Política rígida mal planejada** pode causar dificuldades de acesso e suporte adicional.

## Boas práticas

- ✅ **Defina senhas fortes**: Mínimo de 12 caracteres com combinação de letras, números e símbolos.
- ✅ **Exija troca periódica de senha**, conforme a política da empresa (ex: a cada 90 dias).
- ✅ **Evite reuso de senhas anteriores** (ex: última 5 senhas).
- ✅ **Habilite MFA (autenticação multifator)** em conjunto com a política de senha.
- ✅ **Eduque os usuários sobre boas práticas de senha** (como não compartilhar ou anotar senhas).
- ✅ **Monitore logins suspeitos** usando AWS CloudTrail e IAM Access Analyzer.

---

## Componentes da Política de Senha
![Componentes da Política de Senha](/images/Componentes%20da%20Política%20de%20Senha.png)

---

##  Fluxo de Aplicação da Política
![Fluxo de Aplicação da Política](/images/Fluxo%20de%20Aplicação%20da%20Política.png)

---

## Configuração Recomendada
![Configuração Recomendada](/images/Configuração%20Recomendada.png)

---

## ⚠️ Limitações Importantes
![Limitações Importantes](/images/Limitações%20Importantes.png)

---

## 🛡️ Boas Práticas de Segurança
![Limitações Importantes](/images/Boas%20Práticas%20de%20Segurança.png)


