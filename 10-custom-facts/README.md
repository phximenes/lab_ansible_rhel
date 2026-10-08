# Lab 10 - Custom Facts

Crie:

```text
custom-facts.yml
```

O playbook deve:

1. criar `/etc/ansible/facts.d`
2. criar `/etc/ansible/facts.d/application.fact`
3. usar formato INI
4. armazenar nome, ambiente, responsável e versão
5. executar novamente `setup`
6. exibir o conteúdo em `ansible_facts['ansible_local']`

Valide:

```bash
ansible all -m ansible.builtin.setup -a "filter=ansible_local"
```

Depois crie uma task que execute somente quando o ambiente for `production`.
