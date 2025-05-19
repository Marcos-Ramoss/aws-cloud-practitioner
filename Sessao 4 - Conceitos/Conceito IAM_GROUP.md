## Botão Voltar ao Início
[⬆️ Voltar ao Início](/README.md)

---

# Grupos no IAM da AWS

## Conceito

Na AWS, um **grupo do IAM (Identity and Access Management)** é uma **coleção de usuários IAM**. Grupos facilitam o gerenciamento de permissões de acesso: ao invés de atribuir políticas individualmente a cada usuário, você pode associá-los a um grupo e então atribuir uma ou mais políticas ao grupo. Assim, **todos os usuários herdam automaticamente as permissões daquele grupo**.

Importante: grupos do IAM **não podem ser aninhados**, ou seja, não é possível colocar um grupo dentro de outro.

## Para que são usados

Os grupos no IAM são usados para:
- **Gerenciar permissões em escala** (ex: dar permissões de leitura no S3 para todos os desenvolvedores).
- **Organizar usuários com base em funções ou departamentos** (ex: equipe de DevOps, Financeiro, Segurança).
- **Aplicar políticas de segurança consistentes** entre usuários que compartilham responsabilidades semelhantes.
- **Facilitar o controle de acesso e auditoria** ao centralizar o gerenciamento de permissões.

## Exemplo prático

Suponha que você tenha 10 desenvolvedores que precisam acessar buckets S3 com permissão de leitura e escrever logs no CloudWatch. Em vez de adicionar políticas manualmente para cada usuário, você cria um grupo chamado `Desenvolvedores`, anexa a ele uma política que concede esses acessos, e adiciona os usuários ao grupo. Todos passam a ter as permissões imediatamente.

## Vantagens

- ✅ **Eficiência no gerenciamento**: Permissões são atribuídas uma única vez ao grupo, não individualmente.
- ✅ **Escalabilidade**: Fácil de aplicar as mesmas permissões para muitos usuários ao mesmo tempo.
- ✅ **Organização lógica**: Reflete estruturas organizacionais reais como departamentos ou equipes.
- ✅ **Consistência de permissões**: Reduz o risco de erro humano ao evitar configurações individuais inconsistentes.
- ✅ **Auditoria mais simples**: Permissões são mais fáceis de revisar quando aplicadas por grupo.

## Desvantagens

- ❌ **Sem suporte a grupos aninhados**: Não é possível ter hierarquias de grupos (ex: subgrupos dentro de um grupo).
- ❌ **Permissões não personalizadas por usuário**: Todos os usuários de um grupo compartilham exatamente as mesmas permissões.
- ❌ **Risco de permissões excessivas**: Se um grupo tem permissões amplas e o usuário não precisa de todas, isso pode violar o princípio do privilégio mínimo.
- ❌ **Gerenciamento indireto**: Alterações nas permissões de um grupo afetam todos os seus membros, o que exige cautela.

## Boas práticas

- ✅ Crie grupos baseados em **funções ou responsabilidades** (ex: `Administradores`, `Analistas de Dados`, `Desenvolvedores`).
- ✅ Use o princípio do **menor privilégio** ao definir as permissões do grupo.
- ✅ Revise regularmente os grupos e os usuários atribuídos a eles.
- ✅ Combine o uso de grupos com **políticas gerenciadas pela AWS ou personalizadas**.

---


## Estrutura Básica de Grupos IAM
![Estrutura Básica de Grupos IAM](/images/Estrutura%20Básica%20de%20Grupos%20IAM.png)

---

##  Fluxo de Herança de Permissões
![Fluxo de Herança de Permissões](/images/Fluxo%20de%20Herança%20de%20Permissões.png)

---

## 🏗️ Arquitetura Recomendada
![Arquitetura Recomendada](/images/Arquitetura%20Recomendada.png)




