# Conceito de IAM na AWS

O **IAM (Identity and Access Management)** é um serviço essencial da **AWS (Amazon Web Services)** que permite **gerenciar com segurança o acesso aos recursos da AWS**. Com o IAM, você pode **criar e gerenciar usuários, grupos e permissões**, garantindo que apenas as pessoas ou sistemas autorizados possam acessar determinados serviços ou dados dentro da sua conta AWS.

## Conceitos principais do IAM

- **Usuários IAM**: Representam pessoas ou aplicações que precisam de acesso aos recursos da AWS. Cada usuário pode ter credenciais específicas, como senha para o Console da AWS e chaves de acesso para a CLI ou APIs.

- **Grupos IAM**: São conjuntos de usuários com permissões comuns. Ao adicionar um usuário a um grupo, ele herda todas as permissões atribuídas ao grupo.

- **Políticas (Policies)**: São documentos JSON que definem permissões. Elas especificam **quem** pode fazer **o quê**, **em quais recursos** e sob **quais condições**. Por exemplo, uma política pode permitir que um grupo tenha acesso de leitura ao Amazon S3, mas negue acesso de escrita.

- **Funções IAM (Roles)**: São identidades com permissões que não estão associadas diretamente a um usuário. Elas são muito usadas para **delegar permissões temporárias**, por exemplo, para serviços da AWS (como o EC2 acessar o S3) ou para usuários externos (como o login federado).

## Princípios de segurança do IAM

- **Privilégio mínimo**: conceder apenas as permissões necessárias.
- **Uso de MFA (Autenticação Multifator)** para aumentar a segurança.
- **Monitoramento de acessos** com AWS CloudTrail e IAM Access Analyzer.

## Exemplo prático

Imagine uma aplicação que roda em uma instância EC2 e precisa acessar arquivos em um bucket do S3. Em vez de armazenar chaves de acesso na instância, você atribui uma **role IAM** à instância com permissões para o S3, garantindo segurança e boas práticas.

---


