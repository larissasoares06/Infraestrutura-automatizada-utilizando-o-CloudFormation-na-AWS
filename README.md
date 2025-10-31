# Infraestrutura-automatizada-utilizando-o-CloudFormation-na-AWS
Esse repositório é uma breve descrição sobre os principais ensinamentos no curso da AWS Cloud Foundations sobre a implementação da infraestrutura automatizada na AWS utilizando o CloudFormation

## 📘 O que é o AWS CloudFormation?
O **AWS CloudFormation** é um serviço que permite **provisionar e configurar automaticamente** os recursos da nuvem AWS, a partir de arquivos de definição em YAML ou JSON.

Isso elimina a necessidade de criar recursos manualmente no console, permitindo:

- Automação e versionamento da infraestrutura  
- Padronização de ambientes (desenvolvimento, teste e produção)  
- Redução de erros manuais  
- Facilidade de rollback em falhas

---

## 🧩 Estrutura do Projeto

| Pasta / Arquivo | Descrição |
|------------------|------------|
| `templates/` | Contém os arquivos YAML que definem os recursos da infraestrutura |
| `docs/` | Documentação e explicações teóricas |
| `images/` | Diagramas e ilustrações de apoio |
| `README.md` | Guia principal do repositório |

---

## 🏗️ Templates Incluídos

### 🔹 `network-vpc.yaml`
Cria uma **VPC básica** com sub-redes públicas e privadas.

```yaml
AWSTemplateFormatVersion: "2010-09-09"
Description: Criação de VPC básica com sub-redes públicas e privadas

Resources:
  MinhaVPC:
    Type: AWS::EC2::VPC
    Properties:
      CidrBlock: 10.0.0.0/16
      EnableDnsSupport: true
      EnableDnsHostnames: true
      Tags:
        - Key: Name
          Value: VPC-Exemplo

Outputs:
  VpcId:
    Description: ID da VPC criada
    Value: !Ref MinhaVPC
