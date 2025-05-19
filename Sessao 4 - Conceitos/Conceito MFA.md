# MFA (Multifactor Authentication) na AWS

## Conceito

**MFA (Multi-Factor Authentication)**, ou **Autenticação Multifator**, é um recurso de segurança da AWS que adiciona uma **camada extra de proteção ao processo de login**. Com o MFA ativado, os usuários devem fornecer **duas formas de autenticação**:

1. **Algo que eles sabem** – normalmente, a senha.
2. **Algo que eles têm** – como um código temporário gerado por um dispositivo físico ou aplicativo autenticador.

Isso significa que mesmo que uma senha seja comprometida, **o acesso não será concedido sem o segundo fator**.

## Para que é usado

- ✅ Proteger contas de usuário e da raiz contra acessos não autorizados.
- ✅ Aumentar a segurança de ambientes de produção, administrativos e financeiros.
- ✅ Reforçar políticas de segurança organizacional.
- ✅ Cumprir requisitos de conformidade (como ISO 27001, SOC 2, HIPAA).

## Tipos de MFA compatíveis

- 🔐 **Aplicativos autenticadores**: como Google Authenticator, Authy, Microsoft Authenticator.
- 🔐 **Dispositivos FIDO2/U2F**: como YubiKey.
- 🔐 **Dispositivos MFA baseados em hardware**: fornecidos por fornecedores como Gemalto ou Yubico.
- 🔐 **MFA virtual**: usando o aplicativo AWS MFA para dispositivos móveis.
- 🔐 **MFA por SMS**: não é mais recomendado pela AWS devido a vulnerabilidades.

## Exemplo prático

Um usuário chamado `joao.admin` acessa o Console da AWS para gerenciar infraestrutura crítica. Ao ativar o MFA, sempre que ele tentar fazer login, será necessário:
1. Digitar a senha;
2. Informar um código gerado por um aplicativo autenticador em seu smartphone.

Mesmo que alguém roube a senha de João, o acesso só será possível com o segundo fator.

## Vantagens

- ✅ **Alta segurança**: Protege contra acesso indevido mesmo se a senha for comprometida.
- ✅ **Simples de implementar**: Pode ser ativado em minutos com aplicativos gratuitos.
- ✅ **Recomendado para a conta root da AWS** (obrigatório em muitos casos).
- ✅ **Atende exigências de conformidade e governança**.
- ✅ **Compatível com usuários IAM, IAM Identity Center e AWS CLI**.

## Desvantagens

- ❌ **Dependência de dispositivo físico ou aplicativo**: Se o dispositivo for perdido ou quebrado, o acesso pode ser temporariamente bloqueado.
- ❌ **Gerenciamento adicional**: É necessário configurar processos de recuperação de MFA para evitar perda de acesso.
- ❌ **Possível frustração para usuários menos experientes**: Requer aprendizado adicional.
- ❌ **Não substitui políticas de acesso**: Deve ser usado em conjunto com boas práticas de IAM, e não como solução única de segurança.

## Boas práticas

- ✅ **Ativar o MFA na conta root da AWS imediatamente** após criá-la.
- ✅ **Exigir MFA para todos os usuários com permissões privilegiadas**.
- ✅ **Utilizar políticas IAM que verifiquem o uso de MFA** para permitir ações críticas (como deletar recursos ou modificar configurações).
- ✅ **Documentar um processo de recuperação de dispositivos MFA** para evitar bloqueios em caso de perda.
- ✅ **Auditar regularmente o uso de MFA** com ferramentas como AWS IAM Access Analyzer e CloudTrail.
- ✅ **Utilizar MFA com login federado**, especialmente quando integrado ao IAM Identity Center.

---


##  Fluxo de Autenticação com MFA
![ Fluxo de Autenticação com MFA](/images/Fluxo%20de%20Autenticação%20com%20MFA.png)

---

## Arquitetura de Segurança com MFA
![Arquitetura de Segurança com MFA](/images/Arquitetura%20de%20Segurança%20com%20MFA.png)

---

## 🏗️ Modelo de Política IAM com MFA
![Modelo de Política IAM com MFA](/images/Modelo%20de%20Política%20IAM%20com%20MFA.png)
