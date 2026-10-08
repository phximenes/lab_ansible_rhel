# Lab 11 - Ansible Vault

## Tarefa 1

Crie:

```text
vars/secrets.yml
```

Com:

- `database_user`
- `database_password`

Criptografe:

```bash
ansible-vault encrypt vars/secrets.yml
```

## Tarefa 2

Crie:

```text
vault-demo.yml
```

O playbook deve:

1. executar localmente
2. carregar `vars/secrets.yml` com `vars_files`
3. exibir o usuário
4. provar que a senha foi carregada sem exibi-la
5. usar `no_log` quando necessário

Execute com:

```bash
ansible-navigator run vault-demo.yml --mode stdout --ask-vault-pass
```
