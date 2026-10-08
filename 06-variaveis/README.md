# Lab 06 - Variáveis e Precedência

O inventário e o `ansible.cfg` já são fornecidos.

## Tarefas

Crie:

```text
group_vars/all.yml
group_vars/webservers.yml
host_vars/server01.yml
host_vars/server02.yml
variaveis.yml
web.yml
```

### `group_vars/all.yml`

Defina:

- empresa
- timezone padrão

### `group_vars/webservers.yml`

Defina:

- pacote web
- serviço web
- porta web

### `host_vars`

Cada host deve possuir uma descrição diferente.

### `variaveis.yml`

Exiba:

- empresa
- `inventory_hostname`
- descrição do host

### `web.yml`

Instale e inicie o servidor web usando as variáveis criadas.

Teste precedência:

```bash
ansible-navigator run web.yml --mode stdout -e porta_web=8080
```
