# Docker Compose macOS Role

Esta role do Ansible instala o Docker Compose CLI no macOS via download direto do binário, especificamente otimizada para chips Apple Silicon (M4 Max).

## Requisitos

- macOS 10.15 ou superior
- Chip Apple Silicon (M1, M2, M3, M4)
- Ansible 2.9 ou superior
- Privilégios de sudo para instalação
- Role `andrewrothstein.docker-compose` do Ansible Galaxy

## Variáveis da Role

### Variáveis Padrão (defaults/main.yml)

| Variável | Valor Padrão | Descrição |
|----------|--------------|-----------|
| `docker_compose_galaxy_role` | `andrewrothstein.docker-compose` | Role do Ansible Galaxy |
| `docker_compose_version` | `2.29.7` | Versão do Docker Compose a ser instalada |
| `docker_compose_arch` | `darwin-aarch64` | Arquitetura para Apple Silicon |
| `docker_compose_force_reinstall` | `false` | Forçar reinstalação da role |

## Exemplo de Uso

### Playbook Básico

```yaml
---
- hosts: localhost
  connection: local
  roles:
    - role: docker_compose_macos
      become: true
```

### Playbook com Versão Específica

```yaml
---
- hosts: localhost
  connection: local
  vars:
    docker_compose_version: "2.30.0"
  roles:
    - role: docker_compose_macos
      become: true
```

## Funcionalidades

- ✅ Instalação automática da role do Ansible Galaxy
- ✅ Uso da role `andrewrothstein.docker-compose` para instalação
- ✅ Instalação otimizada para Apple Silicon
- ✅ Suporte a diferentes versões do Docker Compose
- ✅ Verificação e instalação de dependências
- ✅ Suporte a idempotência

## Como Funciona

1. **Instalação da Role**: Baixa e instala a role `andrewrothstein.docker-compose` do Ansible Galaxy
2. **Execução**: Executa a role instalada com as configurações específicas para macOS Apple Silicon
3. **Configuração**: Aplica as variáveis específicas para a versão e arquitetura desejadas

## Estrutura de Arquivos

```
roles/docker_compose_macos/
├── defaults/main.yml      # Variáveis padrão
├── handlers/main.yml      # Handlers para verificação
├── meta/main.yml         # Metadados da role
├── tasks/main.yml        # Tarefas principais (usa Galaxy)
├── vars/main.yml         # Variáveis específicas
└── README.md            # Esta documentação
```

## Dependências

Esta role depende da role `andrewrothstein.docker-compose` do Ansible Galaxy, que é instalada automaticamente.

## Compatibilidade

- **macOS**: 10.15+ (Catalina, Big Sur, Monterey, Ventura, Sonoma, Sequoia)
- **Arquitetura**: Apple Silicon (arm64/aarch64)
- **Docker Compose**: v2.x
- **Ansible Galaxy**: Role `andrewrothstein.docker-compose` v1.4.16+

## Licença

MIT

## Autor

DevOps Team