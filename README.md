# Lab - Red Hat Enterprise Linux Automation with Ansible
## Versão do Aluno

Esta versão contém apenas os enunciados, arquivos-base e arquivos propositalmente incorretos necessários para os exercícios.

Os arquivos que fazem parte da solução devem ser criados pelo aluno durante os labs.

## Topologia sugerida

| Host | Função | Sistema |
|---|---|---|
| ansible-controller | Nó de controle | RHEL 10 |
| server01 | Nó gerenciado | RHEL 9/10 |
| server02 | Nó gerenciado | RHEL 9/10 |

Endereços usados nos exemplos:

- `server01`: `192.168.56.11`
- `server02`: `192.168.56.12`

Ajuste os endereços conforme o ambiente.

## Regra desta versão

Se um arquivo faz parte da solução pedida no enunciado, ele não está incluído no pacote.

Exemplos:

- Lab 01: o aluno cria `ansible.cfg`.
- Lab 02: o aluno cria o inventário.
- Lab 04: o aluno cria `webserver.yml`.
- Lab 05: é fornecido somente o playbook propositalmente incorreto.
- Lab 13: é fornecido somente `playbook-ruim.yml`.
- Lab 14: todo o projeto deve ser criado pelo aluno.

## Execução

Quando solicitado:

```bash
ansible-navigator run arquivo.yml --mode stdout
```

Para exercícios interativos, como `--step`:

```bash
ansible-playbook arquivo.yml --step
```

## Lab 15 - Execution Environment

O aluno constrói uma EE customizada contendo uma Collection externa.
