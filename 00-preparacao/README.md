# Lab 00 - Preparação do Ambiente

## Objetivo

Preparar o controller e os managed nodes.

## No controller

Execute:

```bash
sudo dnf install -y git podman
sudo dnf --enablerepo=ansible-automation-platform-2.7-for-rhel-10-x86_64-rpms install ansible-dev-tools
```

Valide:

```bash
ansible --version
ansible-navigator --version
ansible-lint --version
podman --version
git --version
```

## Nos managed nodes

Crie o usuário de automação:

```bash
sudo useradd -m ansible
sudo passwd ansible
```

Configure sudo para laboratório:

```bash
echo 'ansible ALL=(ALL) NOPASSWD: ALL' | sudo tee /etc/sudoers.d/ansible
sudo chmod 440 /etc/sudoers.d/ansible
```

## No controller

Crie a chave SSH:

```bash
ssh-keygen -t ed25519
```

Copie para os hosts:

```bash
ssh-copy-id ansible@192.168.56.11
ssh-copy-id ansible@192.168.56.12
```

Teste:

```bash
ssh ansible@192.168.56.11 hostname
ssh ansible@192.168.56.12 hostname
```

## Validação

A conexão deve ocorrer sem solicitar senha do usuário remoto.

## Exercício adicional

Descubra, via SSH:

- hostname
- versão do RHEL
- quantidade de CPUs
- memória total
