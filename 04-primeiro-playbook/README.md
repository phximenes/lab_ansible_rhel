# Lab 04 - Primeiro Playbook e Idempotência

## Tarefa

Crie:

```text
webserver.yml
```

O playbook deve:

1. executar no grupo `webservers`
2. usar privilege escalation
3. instalar `httpd`
4. iniciar `httpd`
5. habilitar `httpd` no boot
6. criar `/var/www/html/index.html`
7. mostrar `inventory_hostname`
8. usar permissão `0644`
9. usar FQCN

## Validação

```bash
ansible-navigator run webserver.yml --syntax-check --mode stdout
ansible-navigator run webserver.yml --mode stdout
```

Execute uma segunda vez e compare o `PLAY RECAP`.
