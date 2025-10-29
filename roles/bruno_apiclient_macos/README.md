Bruno API Client macOS
=====================

Instala o Bruno API Client no macOS baixando o binário oficial do GitHub.

Bruno é um cliente de API rápido e Git-friendly, uma alternativa ao Postman.

Requirements
------------

- macOS
- Conexão com a internet para download
- Permissões para instalar em /Applications

Role Variables
--------------

Variáveis disponíveis em `defaults/main.yml`:

```yaml
# Diretório de instalação do Bruno
bruno_install_dir: /Applications

# Estado do pacote (present, latest, absent)
bruno_package_state: present
```

Dependencies
------------

Nenhuma

Example Playbook
----------------

```yaml
- hosts: localhost
  roles:
    - role: bruno_apiclient_macos
      when: ansible_os_family == 'Darwin'
```

Ou com variáveis customizadas:

```yaml
- hosts: localhost
  roles:
    - role: bruno_apiclient_macos
      bruno_package_state: latest
      when: ansible_os_family == 'Darwin'
```

License
-------

MIT

Author Information
------------------

DevOps Team
