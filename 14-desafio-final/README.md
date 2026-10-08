# Lab 14 - Desafio Final Integrador

## Cenário

A empresa recebeu dois servidores RHEL:

- `server01` - Web
- `server02` - Banco de Dados

Você deverá criar do zero um projeto Ansible completo. Nenhum arquivo de solução é fornecido.

## Entregáveis

Crie, no mínimo:

```text
ansible.cfg
ansible-navigator.yml
inventory
group_vars/
host_vars/
playbooks/
templates/
site.yml
.gitignore
```

## ansible.cfg

Configure inventário padrão, usuário remoto, privilege escalation e timeout.

## ansible-navigator.yml

Configure:

- EE habilitada
- Podman
- `registry.redhat.io/ansible-automation-platform-27/ee-supported-rhel9:latest`
- `pull-policy: missing`
- `mode: stdout`

Explique por que `missing` evita pulls desnecessários quando a imagem já existe localmente.

## Inventário

Crie `webservers`, `dbservers` e `production` com `:children`.

IPs:

- `server01`: `192.168.56.11`
- `server02`: `192.168.56.12`

## Variáveis

Separe variáveis globais, do grupo Web e específicas de host.

## Baseline

Automatize pacotes básicos e um arquivo de identificação do servidor. Não utilize Collection externa neste desafio.

## Webserver

Automatize instalação do Apache, start, enable e publicação de HTML.

## Template Jinja2

Mostre empresa, inventory hostname, hostname real, distribuição, versão, IP e perfil do servidor.

## Facts

Use `ansible_facts`.

## Validação

```bash
ansible-inventory --graph
ansible-lint .
ansible-navigator run site.yml --syntax-check --mode stdout
ansible-navigator run site.yml --check --mode stdout
ansible-navigator run site.yml --mode stdout
```

Execute duas vezes e explique qualquer `changed` na segunda execução.

## Git

Versione o projeto e crie `.gitignore` adequado.
