# Extra 16 - Collections

Liste as Collections instaladas:

```bash
ansible-galaxy collection list
```

Instale `community.general`.

Depois crie:

```text
requirements.yml
```

Declare a Collection no arquivo e instale usando:

```bash
ansible-galaxy collection install -r requirements.yml
```

Por fim, utilize um módulo da Collection pelo FQCN em um playbook.
