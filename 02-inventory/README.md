# Lab 02 - Inventários Estáticos

## Objetivo

Criar inventários com hosts, grupos, grupos filhos, variáveis e ranges.

O `ansible.cfg` já está disponível.

## Tarefa 1

Crie:

```text
inventory
```

Requisitos:

- grupo `webservers` com `server01`
- grupo `dbservers` com `server02`
- `server01` usa `192.168.56.11`
- `server02` usa `192.168.56.12`
- grupo `production` agrega os dois grupos com `:children`
- variável de grupo `ambiente=production`

## Validação

```bash
ansible all --list-hosts
ansible webservers --list-hosts
ansible dbservers --list-hosts
ansible production --list-hosts
ansible-inventory --graph
ansible-inventory --list
ansible production -m ansible.builtin.debug -a "var=ambiente"
```

## Tarefa 2

Crie:

```text
inventory-range
```

Usando range para representar `server01.example.com` até `server10.example.com`.

Valide:

```bash
ansible-inventory -i inventory-range --graph
```
