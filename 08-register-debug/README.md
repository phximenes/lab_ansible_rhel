# Lab 08 - Register, Debug e Condições

Crie:

```text
register.yml
```

O playbook deve:

1. executar `uptime`
2. registrar o resultado em `resultado_uptime`
3. usar `changed_when: false`
4. exibir somente `resultado_uptime.stdout`
5. verificar `/etc/lab-ansible.txt` com `ansible.builtin.stat`
6. registrar em `arquivo_lab`
7. informar se o arquivo existe
8. criar o arquivo somente quando ele não existir

A última condição deve usar:

```text
arquivo_lab.stat.exists
```

Execute duas vezes e observe `changed` e `skipping`.
