# Lab 09 - Ansible Facts

Explore primeiro:

```bash
ansible all -m ansible.builtin.setup
ansible all -m ansible.builtin.setup -a "filter=ansible_distribution*"
```

## Tarefa 1

Crie:

```text
facts.yml
```

Exiba usando `ansible_facts`:

- inventory hostname
- hostname real
- distribuição
- versão
- arquitetura
- vCPUs
- memória
- IPv4 padrão

## Tarefa 2

Crie:

```text
facts-hardware.yml
```

Colete apenas o subset de hardware e mostre a memória total.
