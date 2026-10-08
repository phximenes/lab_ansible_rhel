# Lab 01 - ansible.cfg

## Objetivo

Criar a configuração padrão do projeto Ansible e entender a precedência dos arquivos de configuração.

O inventário inicial já foi fornecido.

## Tarefa

Crie:

```text
ansible.cfg
```

Ele deve configurar:

- inventário padrão `./inventory`
- usuário remoto `ansible`
- timeout de 30 segundos
- `host_key_checking` desativado para o laboratório
- log em `./ansible.log`
- privilege escalation com sudo
- `become_user = root`
- sem solicitação de senha de sudo

## Validação

```bash
ansible-config view
ansible-config dump --only-changed
ansible all --list-hosts
ansible all -m ansible.builtin.ping
```
