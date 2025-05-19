# AWS Access Keys e SDKs

## Conceito

### AWS Access Keys

As **AWS Access Keys** são credenciais de segurança que consistem em um **Access Key ID** e um **Secret Access Key**. Elas são usadas para autenticar solicitações programáticas para os serviços da AWS, permitindo acesso seguro via APIs, SDKs e CLI.

### AWS SDK (Software Development Kit)

O **AWS SDK** é um conjunto de ferramentas de desenvolvimento que permite aos desenvolvedores **interagir com os serviços da AWS diretamente em suas aplicações**. Os SDKs estão disponíveis para várias linguagens de programação, incluindo Python, Java, JavaScript, .NET, Go e mais.

## Para que são usados

### Access Keys
- ✅ **Autenticação programática** com serviços AWS
- ✅ **Acesso via AWS CLI** para automação e administração
- ✅ **Integração com aplicações** que precisam acessar recursos AWS
- ✅ **Automação de tarefas** e scripts de infraestrutura

### SDKs
- ✅ **Desenvolvimento de aplicações** que interagem com serviços AWS
- ✅ **Automação de processos** e workflows
- ✅ **Integração de serviços AWS** em aplicações existentes
- ✅ **Gerenciamento programático** de recursos AWS

## Vantagens

### Access Keys
- ✅ **Flexibilidade** de uso em diferentes ambientes
- ✅ **Suporte a múltiplos usuários** e aplicações
- ✅ **Rotação de credenciais** para segurança
- ✅ **Controle granular** de permissões via IAM

### SDKs
- ✅ **Fácil integração** com serviços AWS
- ✅ **Suporte a múltiplas linguagens** de programação
- ✅ **Documentação abrangente** e exemplos
- ✅ **Gerenciamento automático** de credenciais
- ✅ **Tratamento de erros** robusto

## Desvantagens

### Access Keys
- ❌ **Risco de segurança** se expostas indevidamente
- ❌ **Necessidade de gerenciamento** e rotação
- ❌ **Possível comprometimento** se armazenadas incorretamente
- ❌ **Limitações de permissões** baseadas em políticas IAM

### SDKs
- ❌ **Curva de aprendizado** inicial
- ❌ **Dependência de versões** específicas
- ❌ **Possível overhead** em aplicações simples
- ❌ **Necessidade de atualizações** regulares

## Boas práticas

### Access Keys
- ✅ **Nunca compartilhe** suas chaves de acesso
- ✅ **Use o princípio do menor privilégio**
- ✅ **Rote as chaves regularmente**
- ✅ **Armazene as chaves de forma segura**
- ✅ **Use variáveis de ambiente** ou serviços de gerenciamento de segredos

### SDKs
- ✅ **Mantenha os SDKs atualizados**
- ✅ **Implemente tratamento de erros adequado**
- ✅ **Use credenciais temporárias** quando possível
- ✅ **Siga as melhores práticas** de cada linguagem
- ✅ **Implemente retry logic** para operações críticas

## Exemplo prático

```python
# Exemplo de uso do AWS SDK para Python (boto3)
import boto3

# Configuração das credenciais
s3_client = boto3.client(
    's3',
    aws_access_key_id='YOUR_ACCESS_KEY',
    aws_secret_access_key='YOUR_SECRET_KEY'
)

# Uso do serviço
response = s3_client.list_buckets()
for bucket in response['Buckets']:
    print(f'Bucket: {bucket["Name"]}')
```

---

## Fluxo de Autenticação com Access Key
![Fluxo de Autenticação com Access Key](/images/Fluxo%20de%20Autenticação%20com%20Access%20Key.png)

---

## Arquitetura com SDK
![Arquitetura com SDK](/images/Arquitetura%20com%20SDK.png)

---

## Ciclo de Vida de Access Keys
![Ciclo de Vida de Access Keys](/images/Ciclo%20de%20Vida%20de%20Access%20Keys.png) 

---

## Alternativas Seguras
![Alternativas Seguras](/images/Alternativas%20Seguras.png) 



