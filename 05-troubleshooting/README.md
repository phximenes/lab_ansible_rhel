# Lab 05 - Troubleshooting

Neste diretório existe somente:

```text
playbook-com-erros.yml
```

Ele contém um problema proposital.

## Tarefa

Diagnostique usando:

```bash
ansible-navigator run playbook-com-erros.yml --syntax-check --mode stdout
ansible-navigator run playbook-com-erros.yml --check --mode stdout
ansible-navigator run playbook-com-erros.yml --mode stdout -vvv
```

Depois crie:

```text
playbook-corrigido.yml
```

A versão corrigida deve:

- instalar um pacote válido
- possuir uma segunda task com `ansible.builtin.debug`
- executar sem falha

Teste o modo interativo:

```bash
ansible-playbook playbook-corrigido.yml --step
```

Depois teste `--start-at-task`.
