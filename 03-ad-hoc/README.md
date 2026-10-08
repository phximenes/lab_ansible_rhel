# Lab 03 - Comandos Ad-Hoc

## Objetivo

Executar operações rápidas sem escrever um playbook.

## Teste de conectividade

```bash
ansible all -m ansible.builtin.ping
```

## Informações do sistema

```bash
ansible all -m ansible.builtin.command -a "uptime"
ansible all -m ansible.builtin.command -a "df -h"
ansible all -m ansible.builtin.command -a "free -m"
```

## Instalar Apache apenas nos webservers

```bash
ansible webservers -b -m ansible.builtin.dnf -a "name=httpd state=present"
```

## Iniciar e habilitar o serviço

```bash
ansible webservers -b -m ansible.builtin.service -a "name=httpd state=started enabled=true"
```

## Criar arquivo

```bash
ansible all -b -m ansible.builtin.copy -a "content='Criado pelo Ansible\n' dest=/etc/lab-ansible.txt mode=0644"
```

## Comparar command e shell

Sem shell:

```bash
ansible all -m ansible.builtin.command -a "echo teste"
```

Com pipe:

```bash
ansible all -m ansible.builtin.shell -a "ps -ef | grep sshd | grep -v grep"
```

## Discussão

Explique por que:

```bash
dnf install httpd -y
```

dentro de `shell` é inferior ao uso de:

```text
ansible.builtin.dnf
```

para automação declarativa e idempotente.
