# CI Hawk Ops 

Este repositório é responsável pela execução da integração contínua (CI) para o projeto [Hawk Ops](https://gitlab.com/lappis-unb/decidimbr/decidim-whatsapp-integration/airflow/hawk-ops).

## Descrição

O objetivo deste repositório é automatizar a execução de testes sempre que houver mudanças significativas no repositório do Hawk Ops. As ações de CI são disparadas em eventos de push e merge request nas branches `main` e `development` do repositório do Hawk Ops.

## Funcionalidades

- **Verificação de Mudanças**: Monitora as branches `main` e `development` para novos commits.
- **Linting de Código**: Executa ferramentas de linting para garantir a qualidade do código.
- **Execução de Testes**: Realiza testes automatizados utilizando o `pytest` sempre que houver uma nova alteração.

## Estrutura do CI/CD

O CI/CD é configurado no arquivo `.gitlab-ci.yml`. As etapas do pipeline incluem:

1. **check_changes**: Verifica se houve novos commits ou merge requests nas branches monitoradas.
2. **lint_code**: Executa o linting do código para garantir que siga as melhores práticas.
3. **run_tests**: Executa os testes automatizados usando `pytest`.

## Requisitos

- GitLab CI/CD habilitado para o repositório.
- Acesso ao repositório do Hawk Ops.
- Dependências listadas em `dags/tests/requirements.txt` devem estar disponíveis.

## Configuração

### Variáveis de Ambiente

Antes de usar, certifique-se de configurar as seguintes variáveis de ambiente no GitLab:

- `ACCESS_TOKEN`: Seu Personal Access Token para acesso à API do GitLab.
- `CI_TOKEN`: Token do GitLab CI/CD, se necessário.