# Lab 15 - Execution Environment Customizada

## Objetivo

Descobrir por que uma Collection instalada no host não fica automaticamente disponível dentro da Execution Environment usada pelo `ansible-navigator`.

Os arquivos `ansible.cfg`, `inventory` e `timezone.yml` são fornecidos porque o foco deste exercício é construir a EE.

## 1. Compare host e EE padrão

```bash
ansible --version
ansible-galaxy collection list
```

```bash
ansible-navigator exec   --execution-environment-image registry.redhat.io/ansible-automation-platform-27/ee-supported-rhel9:latest   -- ansible --version
```

```bash
ansible-navigator exec   --execution-environment-image registry.redhat.io/ansible-automation-platform-27/ee-supported-rhel9:latest   -- ansible-galaxy collection list
```

## 2. Reproduza o erro

```bash
ansible-navigator run timezone.yml   --execution-environment-image registry.redhat.io/ansible-automation-platform-27/ee-supported-rhel9:latest   --mode stdout
```

Analise o erro de `community.general.timezone`.

## 3. Crie requirements.yml

Requisitos:

- `community.general`
- linha 11.x
- não permitir 12.x ou superior
- compatível com ansible-core 2.16

## 4. Crie execution-environment.yml

Requisitos:

- schema `version: 3`
- base `registry.redhat.io/ansible-automation-platform-27/ee-supported-rhel9:latest`
- dependências Galaxy vindas de `requirements.yml`

## 5. Construa

Nome da imagem:

```text
localhost/ee-200dev-rhel9:1.0
```

Use `ansible-builder build` e valide com `podman images`.

## 6. Valide dentro da nova EE

Execute dentro dela `ansible --version` e `ansible-galaxy collection list`. Comprove que `community.general` está presente.

## 7. Crie ansible-navigator.yml

Configure:

- EE habilitada
- Podman
- `localhost/ee-200dev-rhel9:1.0`
- `pull-policy: never`
- `mode: stdout`

Explique por que usamos `never` para a imagem criada somente localmente.

## 8. Execute novamente

```bash
ansible-navigator run timezone.yml --mode stdout
```

## 9. Valide

Confirme nos nós gerenciados que o timezone é `America/Sao_Paulo`.

## Questão final

Explique a diferença entre instalar a Collection no host com `ansible-galaxy` e incorporá-la a uma EE construída com `ansible-builder`.
