# Lab 13 - Ansible Lint

Neste diretório existe somente:

```text
playbook-ruim.yml
```

Ele está propositalmente fora das boas práticas.

Execute:

```bash
ansible-lint playbook-ruim.yml
```

Depois crie:

```text
playbook-corrigido.yml
```

A versão correta deve:

- possuir nome para a play
- possuir nome para a task
- usar FQCN
- evitar `shell` para instalar pacotes
- usar módulo declarativo apropriado
- passar no `ansible-lint`

Valide:

```bash
ansible-lint playbook-corrigido.yml
```
