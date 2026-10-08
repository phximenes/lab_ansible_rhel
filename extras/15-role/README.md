# Extra 15 - Introdução a Roles

## Criar role

```bash
ansible-galaxy role init roles/webserver
```

Estrutura esperada:

```text
roles/webserver/
├── defaults/
├── files/
├── handlers/
├── meta/
├── tasks/
├── templates/
├── tests/
└── vars/
```

## Desafio

Converta o conteúdo do playbook de Apache para uma role chamada:

```text
webserver
```

Depois invoque-a com:

```yaml
roles:
  - webserver
```
