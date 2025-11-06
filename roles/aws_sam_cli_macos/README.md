AWS SAM CLI macOS
================

Esta role instala o AWS SAM CLI (Serverless Application Model Command Line Interface) no macOS utilizando o instalador binário oficial.

Requirements
------------

- macOS
- Privilégios de administrador (sudo) para instalação do pacote
- Conexão com a internet para download do instalador

Role Variables
--------------

As seguintes variáveis estão disponíveis em `defaults/main.yml`:

```yaml
# URL de download do AWS SAM CLI para macOS
sam_cli_download_url: "https://github.com/aws/aws-sam-cli/releases/latest/download/aws-sam-cli-macos-x86_64.pkg"

# Forçar reinstalação mesmo se o SAM CLI já estiver instalado
sam_cli_force_install: false
```

Dependencies
------------

Nenhuma dependência externa.

Example Playbook
----------------

```yaml
- hosts: localhost
  roles:
    - aws_sam_cli_macos

# Ou com variáveis customizadas:
- hosts: localhost
  roles:
    - role: aws_sam_cli_macos
      sam_cli_force_install: true
```

License
-------

MIT-0

Author Information
------------------

Role criada para automação de instalação do AWS SAM CLI no macOS.
