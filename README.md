# TechStore Lab — Terraform + Docker + Ansible

Laboratório prático de Gerência de Configurações e Automação, provisionando e configurando um ambiente web com **Terraform**, **Docker** e **Ansible**.

## Objetivo

Demonstrar na prática os conceitos de:

- Provisionamento de infraestrutura
- Gerência de Configurações
- Desired State (Estado Desejado)
- Idempotência
- Configuration Drift e correção automatizada

## Arquitetura

## Estrutura do repositório
## Papel de cada ferramenta

| Ferramenta | Responsabilidade |
|---|---|
| **Terraform** | Provisionamento — cria a imagem Docker e o container |
| **Docker** | Ambiente isolado de execução (`techstore-dev`) |
| **Ansible** | Gerência de Configurações — instala dependências e mantém o estado desejado |

## Como executar

```bash
# 1. Provisionar com Terraform
cd terraform
terraform init
terraform apply

# 2. Configurar com Ansible
cd ../ansible
ansible-playbook -i inventory.ini playbook.yml
```

Acesse: [http://localhost:8080](http://localhost:8080)

## Conceitos demonstrados

**Idempotência**: executar o playbook múltiplas vezes sem alterar o ambiente quando ele já está no estado desejado (`changed=0` na segunda execução).

**Configuration Drift**: divergência entre o estado atual e o estado desejado, provocada por alteração manual fora do Ansible. Corrigida reexecutando o playbook, que restaura o estado definido no código.

## Conclusão

O objetivo não era criar uma página HTML — ela foi apenas uma forma visual de tornar o conceito observável. O que este laboratório demonstra é **Infraestrutura como Código**: ambientes reproduzíveis, consistentes e autocorrigíveis, sem depender de intervenção manual.


